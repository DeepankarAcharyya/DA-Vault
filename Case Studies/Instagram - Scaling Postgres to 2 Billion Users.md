---
aliases:
  - Instagram Scaled Postgres to 2 Billion Users
tags:
  - case-study
  - db
  - distributed
  - solid
type: case-study
status: solid
up:
  - "[[Distributed Systems MOC]]"
---

# Instagram - Scaling Postgres to 2 Billion Users

Up: [[Distributed Systems MOC]] · [[Databases MOC]]
Concepts: [[Sharding]] · [[Distributed ID Generation]] · [[PostgreSQL]]

- Boring Technology with good engineering always beat bad engineering with latest technology.
- 1st Problem : 
	- 1.3 MB memory for each pg connection
	- Solution : pgbouncer 
- 2nd Problem :
	- Size is 2TB
		- max ec2 instance at that time
		- Normal path : switch to NoSQL
	- Shard Postgres
		- shared key ?
			- obvious option : user_id --> not ideal for instagram
				- expensive cross user queries
		- Instagram implemented logical shards - independent of physical shards
			- decoupled 2 things
				- how the data is partitioned and where the data is stored physically
				- another logical layer which maintains the mapping of the data to the shard (logical and physical)
			- postgres's built in streaming replication --> migrating data between nodes
				- just a mapping update to the logical layer
			- Unique id for the data points
				- serial id --> doesnt work for sharded setup as multiple nodes will generate the same ids
				- uuids --> its random
				- Flickr's approach -- a separate service just for the purpose of handling the unique id -- but it becomes the single source of failure.
				- twitter snowflake -- extra service that generated time ordered IDs
					- whole separate service
					- more moving parts - more points of failures
			- What instagram did 
				- generate snowflake style ids inside postgresql
				- next_id() -- postgres function 
				- 64 bit ID
					- 3 parts
						- Timestamp - 41 bits
						- Shard - 12 bits
						- Seq - 10 bits
				- 3 inputs flow in - one 64 bit ID falls out. 
					- No external service
					- No coordination
					- Just a function ticking in each shard
				- Since the high order bits are based on timestamp - IDs sort by creation time - newest photos = ORDER by id

---

## Why this note matters

Three separate vault concepts converge here, which is why it's the anchor case study:

1. **[[Sharding]]** — the logical/physical split is the reusable idea, not the Instagram-specific detail. Rebalancing becomes a mapping update instead of a data migration.
2. **[[Distributed ID Generation]]** — the full option tree (serial → UUID → Flickr ticket server → Twitter Snowflake → in-database function) is laid out above. That progression *is* the concept note.
3. **Connection pooling** — pgbouncer. 1.3 MB × N connections is why you never point an app server pool straight at [[PostgreSQL]].

## Transferable lessons

- **Add a layer of indirection before you add a service.** Instagram's answer to both problems was a mapping layer and a SQL function — not new infrastructure. Contrast with the Flickr and Snowflake approaches, both of which added a failure point.
- **"Switch to NoSQL" was the default advice and was wrong here.** Worth holding against [[MongoDB]], [[Cassandra]], [[DynamoDB]] — what would each have actually bought?
- **Time-ordered IDs are free indexing.** `ORDER BY id` = newest-first, no extra column, no extra index.

## Open questions

- [ ] 41-bit timestamp — when does it roll over, and from what epoch?
- [ ] 10-bit sequence = 1024 IDs per ms per shard. What happens on overflow?
- [ ] What *was* their shard key, since `user_id` was rejected?

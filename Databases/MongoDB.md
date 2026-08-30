---
tags:
  - db
  - concept
  - growing
type: concept
status: growing
up:
  - "[[Databases MOC]]"
---

# MongoDB

Up: [[Databases MOC]] · Compare: [[PostgreSQL]] · [[Cassandra]]

docs -> collections -> database

Compass --> UI interface for mongodb
Default Port : 27017

`show dbs` --- show all databases
`use admin` --- use admin database
`use school` --- create database if not present
`db.createCollection("students")` --- create collection
`db.dropDatabase()` --- for dropping database
`db.students.insertOne({name:"Spongebob", age:30, gpa:3.2})` -- to insert --> will get an ack response
db.students.insertMany([{...},{...},{...}])

db.students.find()
db.students.find().sort({name:1}) --> 1 for asc order / -1 for desc order
db.students.find().limit(1)

db.students.find()
-- {query}, {projection}

db.students.updateOne(filter, update)
filter : {name: "Spongebob"}
update: {$set: {fullTime:true}}

---

## Mapping to SQL

| Mongo | Relational |
| --- | --- |
| database | database |
| collection | table |
| document | row |
| field | column |
| `_id` | primary key |
| `find({q}, {proj})` | `SELECT proj FROM t WHERE q` |
| `$set` in `updateOne` | `UPDATE ... SET` |

## Connections

- **Sharding is built in** here, bolted on in Postgres — see [[Sharding]] and what that cost Instagram in [[Instagram - Scaling Postgres to 2 Billion Users]].
- **Schema-on-read** shifts validation into the application layer. That's a tradeoff, not a free win.

## Open questions

- [ ] Aggregation pipeline — `$match`, `$group`, `$lookup`
- [ ] Indexes: compound, and how they interact with sort
- [ ] Replica sets and elections
- [ ] Choosing a shard key, and why a bad one is very hard to undo
- [ ] Transactions — multi-document, and their real cost

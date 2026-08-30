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
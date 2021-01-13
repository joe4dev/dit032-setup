# MongoDB

* Docs: https://docs.mongodb.com/
* Curated list of resources: https://github.com/ramnes/awesome-mongodb
* Coursera [Introduction to MongoDB](https://www.coursera.org/learn/introduction-mongodb/lecture/fDjfl/mongodb-document-model)
* Cheat Sheet 1: https://gist.github.com/aponxi/4380516
* Cheat Sheet 2: https://blog.codecentric.de/files/2012/12/MongoDB-CheatSheet-v1_0.pdf

## GUI Apps

* Robo 3T: https://robomongo.org/

## mongo shell

Start the mongo shell with `mongo` (or `mongo my_database`)

* Docs: https://docs.mongodb.com/manual/mongo/
* List databases `show dbs`
* Use database `use app_database`
* Show current database `db`
* Format printed results  `db.myCollection.find().pretty()`
* Quit `quit()`

## Import Data

A JSON data dump file will be provided on Canvas in the respective assignment.
So you can skip this part for now.

```bash
# MacOS/Linux shell
mongoimport -d conferences -c conferences conferences.json
mongoimport -d conferences -c delegates delegates.json
# Windows shell
mongoimport /d conferences /c conferences conferences.json
mongoimport /d conferences /c delegates delegates.json
```

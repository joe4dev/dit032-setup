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

```
# macOS shell
mongoimport −d plants −c plants /path/to/plants.json
mongoimport −d plants −c gardens /path/to/gardens.json

# Windows shell
mongoimport /d plants /c plants C:\path\to\plants.json
mongoimport /d plants /c gardens C:\path\to\gardens.json
```

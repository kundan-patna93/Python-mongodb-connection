# python-and-mongodb connection

Step1:
-download the python and mongodb
-python:(link: https://www.python.org/downloads/)
-mongodb:(link: https://www.mongodb.com/try/download/community)


step2:
-download pymongo(link: cmd--> python -m pip install pymongo)
it is mediator of python and mongodb connection


step3:
-set the mongodb path of the enviroment variables setting
(C:\Program Files\MongoDB\Server\4.4\bin)


step4:
open cmd and write "mongod"
open cmd and write "mongo" to start the server


step5
1)create a collection:
import pymongo
myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydatabase"]
mycol = mydb["customers"]

2)Insert into collection:
import pymongo
myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydatabase"]
mycol = mydb["customers"]
mydict = { "name": "John", "address": "Highway 37" }
x = mycol.insert_one(mydict)

3)Update collection:
import pymongo
myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydatabase"]
mycol = mydb["customers"]
myquery = { "address": "Valley 345" }
newvalues = { "$set": { "address": "Canyon 123" } }
mycol.update_one(myquery, newvalues)
#print "customers" after the update:
for x in mycol.find():
print(x)

4)Delete Document:
import pymongo
myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydatabase"]
mycol = mydb["customers"]
myquery = { "address": "Mountain 21" }
mycol.delete_one(myquery)

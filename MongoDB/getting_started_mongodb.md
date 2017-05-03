# Getting Started With MongoDB


##### Creating folders for Database and Log

create folders in drive 
[path]/data/db, and [path]/log to set this folders as saving data and logs of mongoDB

```sh
# Set directory for database and file for log
$ mongod --directoryperdb --dbpath [path/data/db] --logpath [path/log/mongo.log] --rest --install 

$ net start MongoDB

# Start mongo shell

$ mongo
> show dbs  #will show databases
admin  0.000GB
local  0.000GB
> use mycustomers # will create database and select as well
switched to db mycustomers
```

##### how data is stored in mongoDB


```json
{
    first_name:"jon",
    last_name:"doe",
    memberships: ["m1","m2"],
    address:{
        street: "4 th street",
        city: "NY"
    }
    contacts: [
        {name:"joe", relationship:"buddy"}
    ]
}
```

##### Creating User

```sh
# create user:
db.createUser({
    user:"mongo",
    pwd:"1234",
    roles:["readWrite,"dbAdmin"],
});

Successfully added user: { "user" : "mongo", "roles" : [ "readWrite", "dbAdmin" ] }
```
##### creating collections
```sh

# collections are similar to tables in relational database, basically they hold documents

$ db.createCollection('customers');
$ show collections
$ db.customers.insert({first_name:"jon",last_name:"doe"});
WriteResult({ "nInserted" : 1 })

# output
{ "_id" : ObjectId("5909f68c159ce6e910347281"), "first_name" : "jon", "last_name" : "doe" }
# _id will be automatically created which is ObjectID this is used as unique value to identify document
```
```sh

# multiple documents at once:
$ db.customers.insert({first_name:"joey",last_name:"joe"},{first_name:"chandler",last_name:"bing",gender:"female"});
```
##### pretty
```sh
db.customers.find()
db.customers.find().pretty();
```
##### update document
```sh
$ db.customers.update({first_name:"john"},{first_name:"Doe",gender:"male"})
# here first field is the one which is to be updated and second one is what is to be updated.
# this wolud be bad idea on production application because it will update all the pepople named john it is better to update using ObjectID.
```
##### set operator
```sh
# set operator
$ db.customers.update({first_name:"john"},{$set:{gender:"male"}})
# using set it will keep what was there previously and just add gender
```
##### inc operator
```sh
$ db.customers.update({first_name:"john"},{$set:{age:45}})
$ db.customers.update({first_name:"john"},{$inc:{age:5}});
# here inc will increment age by 5
```
##### unset operator
```sh
$ db.customers.update({first_name:"john"},{$unset:{age:1}});
```
##### unavailable data
```sh
# try to update data which isn't there
$ db.customers.update({first_name:"mary"},{gender:"female"});
WriteResult({ "nMatched" : 0, "nUpserted" : 0, "nModified" : 0 })
```
##### If data is not present
###### upsert
```sh
$ db.customers.update({first_name:"mary"},{gender:"female"},{upsert:true}); # even if data is not present it will be inserted
```
##### rename operator
```sh
$ db.customers.update({first_name:"mary"},{$rename:{"gender":"sex"}});
```
##### removing document
```sh
db.customers.remove({first_name"john"});
```
##### justOne
```sh
#refine
db.customers.remove({first_name"john"},{justOne:true});
# just one will remove first record it finds
```
##### find
```sh
 db.customers.find({first_name:"sharon"});
# if want to find more records
```
##### or operator
```sh
$ db.customers.find($or:[{first_name:"sharon"},{first_name:"troy"}]);
```
#####  $lt,$gt operator
```sh
#  $lt,$gt less than ,greator than
db.customers.find({age:{$lt:40}});
```
##### find data in embedded document
```sh
# if want to find people living in same city

{
    first_name:"jon",
    last_name:"doe",
    memberships: ["m1","m2"],
    address:{
        street: "4 th street",
        city: "NY"
    }
    contacts: [
        {name:"joe", relationship:"buddy"}
    ]
}

db.customers.find({"address.city":"Boston"});
#query memberships
db.customers.find({memberships:"m1"});
```
##### sorting

```sh
#sorting
db.customers.find().sort({last_name:1});
# here 1 means ascending , -1 means decending 
```
##### count documents
```sh
#count documents
db.customers.find(gender:"male").count();
```
##### limit
```sh
db.customers.find(gender:"male").limit(4);
```
##### forEach loop
```sh

# for each
db.customers.find().forEach(function(doc){print("customer name":+doc.first_name)});
# here doc is variable it can be anything
```

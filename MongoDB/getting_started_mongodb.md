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
> use mycustomers # will create database and select as well

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
    roles:["readWrite,"dbAdmin"]
});

```
##### creating collections
```sh

# collections are similar to tables in relational database, basically they hold documents

$ db.createCollection('customers');
$ show collections
$ db.customers.insert({first_name:"jon",last_name:"doe"});

#show output:
_id will be automatically created which is ObjectID this is used as unique value to identify document
# multiple documents at once:
$ db.customers.insert({first_name:"joey",last_name:"joe"},{first_name:"chandler",last_name:"bing",gender:"female"});

#here we have added gender field on the go
#show output

# pretty()
db.customers.find()
db.customers.find().pretty();
#update document
$ db.customers.update({first_name:"john"},{first_name:"Doe",gender:"male"})
# here first field is the one which is to be updated and second one is what is to be updated.
# this wolud be bad idea on production application because it will update all the pepople named john it is better to update using ObjectID.
# set operator
$ db.customers.update({first_name:"john"},{$set:{gender:"male"}})
# using set it will keep what was there previously and just add gender
# Inc opeartor
$ db.customers.update({first_name:"john"},{$set:{age:45}})
$ db.customers.update({first_name:"john"},{$inc:{age:5}});
# here inc will increment age by 5
# unset opeartor
$ db.customers.update({first_name:"john"},{$unset:{age:1}});
# try to update data which isn't there
$ db.customers.update({first_name:"mary"});
#show result
#upsert if it isnt found then insert it
$ db.customers.update({first_name:"mary"},{upsert:true});
$ db.customers.update({first_name:"mary"},{$rename:{"gender":"sex"}});

# remove document
db.customers.remove({first_name"john"});
#refine
db.customers.remove({first_name"john"},{justOne:true});
# just one will remove first record it finds
 db.customers.find({first_name:"sharon"});
# if want to find more records
$ db.customers.find($or:[{first_name:"sharon"},{first_name:"troy"}]);
#  $lt,$gt less than ,greator than
db.customers.find({age:{$lt:40}});


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
#output

#sorting
db.customers.find().sort({last_name:1});
# here 1 means ascending , -1 means decending 
#count documents
db.customers.find(gender:"male").count();
#limit
db.customers.find(gender:"male").limit(4);
# for each
db.customers.find().forEach(function(doc){print("customer name":+doc.first_name)});
# here doc is variable it can be anything


```

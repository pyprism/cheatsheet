####Term
* Collection : Table (SQL)
* Document : Record or Row (SQL)
* Field (key : value) : Column (SQL)

####Simple Commands
* Connect mongp shell : mongo
* Show all databases : show dbs
* Connect to a database : use databaseName
* show collections in current database : show collections
* Show connected database : db
* Show list of documents : db.links.count()

####Insert
 ```
 db.collection.insert({})
 ```
 Example
 ``` 
 db.links.insert({name : "hello",age : "fuck" , tag :["s","x"]})
 ```
Javascript way
 ```
 var doc = {};
 doc.title = "net";
 doc.age = "fuck";
 db.links.save(doc)    #now save
 ```
Print/Show
```
db.links.find()
```   
Or for nice output
```
db.links.find().forEach(printjson)  
```
Show object creation time 
```
db.links.find()[1]._id.getTimestamp()
```

Query :
db.DOCUMENTNAME.find({ key : value })
db.DOCUMENTNAME.findOne({ key : value }).SUBCATEGORY
db.DOCUMENTNAME.find({ key : value } , { key : 1 , key : 0 } )  # Key : 1 means True and Key : 0 means False => For enable / disable certain value for printing
db.DOCUMENTNAME.find({ key.subobject : value })
db.DOCUMENTNAME.find({ key : value } , {key.subobject : 0})
db.DOCUMENTNAME.find({ key : {$gt : 20} })   # $gt means greater then 
db.DOCUMENTNAME.find({ key : {$lt : 20} })    # $lt means less then
db.DOCUMENTNAME.find({ key : {$gt : 20 , $lt : 25} }) 
db.DOCUMENTNAME.find({ key : {$in : [20 , 30] } })  # $in means any two values ( 20  or 30 ) are  included
db.DOCUMENTNAME.find({ key : {$nin : [20 , 30] } })  # $in means any two values ( 20  or 30 ) are not included
db.DOCUMENTNAME.find({ key : {$ne : "code" } })  # $ne means not equal to "code"
db.users.find({ $or : [{ 'name.first' : "John" }, { 'name.last" : "Wilson"}]  # $or > print name.first == john or print name.last == Wilson
db.users.find({ $nor : [{ 'name.first' : "John" }, { 'name.last" : "Wilson"}]  # $nor (not or )  > print dont have name.first == john or print dont have name.last == Wilson
db.users.find({ $and : [{ 'name.first' : 'John' }, { 'name.last' : 'Doe'} ] }) # $and means must fullfill two conditions
db.users.find({ email : { $exits : true }},) # retrun all of documents that have email field exits
db.links.find({ age : { $not : {$lt : 100 }}}   # retrun age that less than 100
Some Other Operator :
$mod
$elemMatch
$where

db.links.distinct('favourites')  # remove duplicate

db.links.group({ key : { userId : true }) 


Update : 
db.users.update({ 'name.last' : 'John'}, { job : 'Developer'});
db.users.update({name : "Hiren"} , {name : "Hiren Down" , job : "Python Developer"} )  #Find name hiren and replace with Hiren Down and Job Bla bla


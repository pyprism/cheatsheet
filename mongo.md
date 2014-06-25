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
Or
```
db.collections.find().pretty()
```
Show object creation time 
```
db.links.find()[1]._id.getTimestamp()
```

#### Query
Find by key-value / return cursor object
```
db.DOCUMENTNAME.find({ key : value })
```
Return single object
```
db.DOCUMENTNAME.findOne({ key : value }).SUBCATEGORY
```
Print specific value
```
db.DOCUMENTNAME.find({ key : value } , { key : 1 , key : 1 , _id : 0} )  # Key : 1 means True and Key : 0 means False => For 
enable / disable certain value for printing
```
Quering nested object
```
db.DOCUMENTNAME.find({ key.subobject : value })
db.DOCUMENTNAME.find({ key : value } , {key.subobject : 0})
```
Find object greater/less  than or equal to 
```
db.DOCUMENTNAME.find({ key : {$gt : 20} })   
db.DOCUMENTNAME.find({ key : {$lt : 20} })
db.DOCUMENTNAME.find({ key : {$gt : 20 , $lt : 25} })
db.DOCUMENTNAME.find({ key : {$gte : 20 , $lt : 25} })
```
Some others operators : $in = include , $nin = not include
```
db.DOCUMENTNAME.find({ key : {$in : [20 , 30] } }) 
db.DOCUMENTNAME.find({ key : {$nin : [20 , 30] } })  
db.DOCUMENTNAME.find({ key : {$ne : "code" } }) 
```
$all operator : find all values not just one
```
db.document.find({'hiren':{ $all : ['rater' , 'santo' , 'tara' }})
```
Now equal operator
```
db.hiren.find({ $ne : "nish" })
```
Boolean operators : $or , $nor =  not or , $and
```
db.users.find({ $or : [{ 'name.first' : "Naima" }, { 'name.last" : "Anjum"}]  
db.users.find({ $nor : [{ 'name.first' : "Naima" }, { 'name.last" : "Anjum"}]
db.users.find({ $and : [{ 'name.first' : "Naima" }, { 'name.last" : "Anjum"}]
```
Specialized operator : $exits , $not 
```
db.users.find({ email : { $exits : true }},) 
db.links.find({ age : { $not : {$lt : 100 }}}  
```

Some Other Operator :
$mod
$elemMatch
$where
##remove duplicate
```
db.links.distinct('favourites')  
```
db.links.group({ key : { userId : true }) 


Update : 
db.users.update({ 'name.last' : 'John'}, { job : 'Developer'});
db.users.update({name : "Hiren"} , {name : "Hiren Down" , job : "Python Developer"} )  #Find name hiren and replace with Hiren Down and Job Bla bla


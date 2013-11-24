####comment 
//   and /* */

#### Noscript element  
```javascript
<noscript>
<p>This page requires a JavaScript-enabled browser.</p></noscript>```

#### variable declaration  
```javascript
var date;
date = 56; ```
or   
```var date = 56; ```
                           
#### condition   
```javascript
if ( condition )
{        
   code;
}
else
{        
   code;
} ```
               
#### loops 
 just like C/C++ ; all r same (while ,do-while , for loop ) and usual break , continue .
               
#### Equal sign 
 double equal sign ( == ) check equality
                     triple equal sign ( === ) check strict equality // counterpart of triple equal ( !== )
                     
##### Best practice 
Define your function before you call them :) 

#### Array
```javascript
var bla = [] ; ```
##### array method 
```javascript
bla.join() ; 
bla.reverse() ; 
bla.sort()```
  
###### 5+"5" = "55" 5 automatically converted to string !!
###### js converntion 
 variable name can me camelcase like var whatIsGoingOnGuys; but not this what_is_going .....
#### Convert
```javascript
int or float to string = 6 + "" = "6"
String to int or float = parseInt("10")  =10
parseFloat("10.5") =10.5
parseInt(15.6) = 15
parseInt("43s64") = 43 ```
                                  
####Function creation 
```javascript
 function blaBla(x,y){
     do something here ;
     return x,y;
   }```
###array declaration : var foo = new Array() ; 
				or var foo = new Array(size);
			      or var foo = new Array(value1,value2);
			      or var foo =[value1 , value 2 ] ;
			      var foo[0] = value ;
			      
   String array :  var foo = new Array(size);
   				foo[0] = "hello hiren  :) " ;
   		 or       names = new Array(“Henry J. Tillman”, “Sherlock Holmes”);
            or        names = [“Henry J. Tillman”, “Sherlock Holmes”];
tips : use array.length for adding a item to the end of an array
      var hiren = ["12 june" ];
      hiren[hiren.lenght] = "Tai Na" ;
      hiren[hiren.length] = "12 August" ;            


** use only 1 window.onload function per page . If there are multiple js scirpt , last one will be applicable

###Create new Object : 
var person = new Object();  OR var person = {} ; 
person.name = "Hiren" ;     OR person.[age] = "Hiren" ; //usefull for variable property
person.age = 19 ;
Shorthand : var person = {name : "Hiren" ,
                          age : "19"
                          } ;
Create method :
var person = {
  sayname : function(){
    alert("afa");
  }
}

exmample of passing argument in object :
function displayInfo(args){
  var output = "" ;
  if ( typeod args.name = "string") {
      output += "Name: " + args.name + "\n" ;
      }
  if (typeof args.age = "number"){
    output += "Age: " + agrs.age + "\n" ;
    }
    alert(output) ;
  }
displayInfo({
  name : "Hiren" ,
  age : 19 
}) ;

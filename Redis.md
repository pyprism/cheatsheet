####Redis datastructures
```
string , list , hash , set and sorted set
```
#####String
######Set value
```
set <key name> <value>
set name "hiren"
```
######Get value
```
get <key name>
get name #return "hiren"
```
######Get value using range
```
getrange <key> <range>
getrange name 0 3 #return "hire"
```
######Set value using range
```
setrange <key> <position> <value> 
setrange name 5 RST
```
######Override value
```
getset <key> <new value>
getset name "Rater Santo Tara"
```
######Multiset value
```
mset <key> <value> <key> <value>
mset name "Rater Santo Tara" age 20
```
######Increment value (only works for numbers)
```
incr age ## increment age by 1
```
######Decrement value
```
decr <key>
```
######Increment and decrement by specific number
```
incrby <key> 5
decrby <key> 20
```
######Float increment (only for integer )
```
incrbyfloat <key> <float value> 
```
######Set expire time
```
setex <key> <time in second> <value>
setex name 4 hiren
```
######Only set value if doesnt exits
```
setnx <key> <value>
```
######Multi setnx
```
msetnx <key> <value> <key> <value>
```
######Length of a value
```
strlen <key>
```



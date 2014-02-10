###Redis datastructures
```
string , list , hash , set and sorted set
```
####String
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

#### List
######Lpush ( Left push )
```
lpush <list name or key >  <value> <value>
```
######Rpush ( Right push )
```
rpush <key or list name > <value> <value>
```
######Lpushx and Rpushx (push if the list is exits)
```
lpushx <list name or the key > <value>
rpushx <list name or the key > <value>
```
######Length of a list
```
llen <list name >
llen hiren
```
######Get values
```
lrange <list name> <starting position> <ending position>
```
Tips : For grabbing whole list use starting position = 0 and ending position = -1 

###### Pop from left or right side
```
lpop <value>
rpop <value>
```
######Remove value
```
lrem <list name> 2 <value>
```
######Insert middle 
```
linsert <list name> before <existing value> <new value>
linsert <list name> after <existing value> <new value>
```
######Get value using index
```
lindex <list name> <index no>
```
######Set value using index
```
lset <list name> <index number> <new value>
```
######Trim
```
ltrim <list name> <starting position> <ending position>
```
####Hash
######Set command
```
hset <key> <subkey> <value>
hset hiren age 20
```
######Get command
```
hget <key> <subkey>
```
######Get all value
```
hgetall <key>
```
######Return only keys or values
```
hvals <key>
hkeys <key>
```
######Check value existence 
```
hexits <key> <subkey>
```
######Increment
```
hincrby <key> <subkey>
hincrbyfloat <key> <subkey>
```
######Check length
```
hlen <key>
```
######Multiple get
```
hmget <key> <subkey> <subkey>
```
######Multipke set
```
hmset <key> <subkey> <value> <subkey> <value>
```
######Set if doesnt exits
```
hsetnx <key> <subkey> <value>
```
######Delete
```
hdel <key> <subkey>
```
####Set
######Add single or multiple value
```
sadd <set name> <value> <value>
```
######Remove value
```
srem <set name> <value>
```
######Show all members
```
smembers <set name>
```
######CHeck if already exists or not
```
sismember <setname> <value>
```
#####Check how many item in set
```
scard <set name>
```
######Take random item from set
```
sranmember <set name>
```
######Take random member out of the set
```
spop <set name>
```
######Check member defference in two set
```
sdiff <set name> <set name>
```
######Check difference and store in new set
```
sdiff <new set name>  <set name> <set name>
```
#####Intersection(common members) in both set
```
sinter <set 1> <set 2>
```
######Union between sets
```
sunion <set 1> <set 2>
```
######Store union result
```
sunionstore  <new set >  <set 1> <set 2>
```
######Move value from 1 set to another
```
smove <old set> <new set> <value>
```

##Other Commands

######Search all keys
```
keys *
```
######Search using specific pattern
```
keys hiren*
keys hire
```
######Check if key exist
```
exits <key name>
```
######Check type of a key
```
type <key name>
```
#####Delete key
```
del <key name>
```
######Move to different database
```
move <key name>  <database number>
move hiren 2
```
######Select database
```
select <database number>
select 1
```
######Expire
```
expire <key name> <Second>
```
######Time to live
```
ttl <keyname> <secound>
```








































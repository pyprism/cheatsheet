#####use $1  for 1st argument and  $* for all argument passing to script
#####use double quote " "
##### For debugging full script  use #!/bin/bash -x
##### for debugging specific part use  set +x to enable and set -x  to disable
#####Global variable $EDITOR
#####Initialize empty variable "varname =   "
###Conditional Expressions
```bash
[[ $str ]]  => Returns true if string is not empty
[[ $str = "hiren" ]]  => Check if string equals to "hiren"
[[ $str="hiren"]]  => always return true , because lack of space !
[[ -e $filename ]] => check if variable holds a file
[[ -d $dir ]] => check if variable holds a directory
[[ ! $1 ]] => if 1st argument is empty 
```
###### for more details type " help test " or " help [[ "

###Arithmetic test
##### bash only support integers :O !
```bash
Equlity test
[[ arg1 OP agr2 ]]
Where OP is 
-eq : equality
-ne : not equal
-lt : less than
-gt : grrater than
```

##### And => && , OR => ||

###Input redirection
```bash
Input =>  <
Output =>  > and  >> (append end of a file )
```
###If Else
```bash
if [[ test ]]; then
    //code
elif [[ test ]]; then
    //code
else
    //hiren code :D
fi
```

###loop
######while =>   
```
while test; do
      //code
done
```

######until =>
```bash
until test; do
    //code
done
```
######similar to while loop, it continues as long as test returns false ! funny lol

######Classic for loop  =>
```bash
for VAR in WORDS; do
	// code
done
```
###### Dont quote WORDS in for loop
###### Example:
```bash
for i in u r a hiren;do
    echo $i;
done
```
######output
```bash
u
r
a
hiren
```
######C-Style For Loop
```bash
for (( init; test; update )); do
    ;; loop code
done
```
######Case statement
```bash
case WORD in
    pattern1)
        code for pattern1;;
    pattern2)
        code for pattern2
esac
```
######Example:
```bash
#!/bin/bash
case $1 in
    cat)
       echo "meow";;
    dog)
       echo "woof";;
    *)
       echo "hiren"
esac
```
#####Break and Continue
   1. break
       * quits the loop
   2. continue
       * skips rest of the current lopp
       * continues with the next iteration

#####Error handling on redirecting :P 
```bash
cat hiren 2> log.txt
cat hiren 2>> hiren.txt
```








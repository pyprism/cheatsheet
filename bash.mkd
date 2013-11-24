**use $1  for 1st argument and  $* for all argument passing to script
**use double quote " "
** For debugging full script  use #!/bin/bash -x
** for debugging specific part use  set +x to enable and set -x  to disable
**Global variable $EDITOR
**Initialize empty variable "varname =   "
##Conditional Expressions
	[[ $str ]]  => Returns true if string is not empty
	[[ $str = "hiren" ]]  => Check if string equals to "hiren"
	[[ $str="hiren"]]  => always return true , because lack of space !
	[[ -e $filename ]] => check if variable holds a file
	[[ -d $dir ]] => check if variable holds a directory
	[[ ! $1 ]] => if 1st argument is empty
	* for more details type " help test " or " help [[ "

##Arithmetic test
* bash only support integers :O !
	Equlity test
		[[ arg1 OP agr2 ]]
		Where OP is :
			-eq : equality
			-ne : not equal
			-lt : less than
			-gt : grrater than

# And => && , OR => ||

##Input redirection

Input =>  <
Output =>  > and  >> (append end of a file )

#loop
while =>   while test; do
			code
		  done

until =>  until test; do  #similar to while loop, it continues as long as test returns false ! funny lol
			code
		done

Classic for loop  =>  for VAR in WORDS; do
			// code
		      done
		** Dont quote WORDS

###Basic Types
 * bool
 * string
 * int, int8, int16, int32, int64
 * uint, uint8, unit16, unit32, unit64, unitptr
 * byte(unit8)
 * rune(int32), like a char
 * float32, float64
 * complex64, complex128

###Other Types
 * Array
 * Slice
 * Struct
 * Pointer
 * Fucntion
 * Interface
 * Map
 * Channel

#### Variable Declaration 
```
 var <var name> <type>
 var hiren string
 var a, b , c int
```
######Or
```
var hiren = "Yo :D!"
```
######Or 
```
hiren := "Shorthand Yo! :/ "
```
#####Multi Initialization
```
var <variable name> <type> = <value>
var hiren, nish, nan int= 1 , 2 , 3
```
######shortform  :D
```
hiren, nish, nan := 1, "srting",  false
```

#####Pointer
```
var <name> *<type>
var xoxo := "o_O"
var pointermama string = &xoxo
```
######Pointer assignment
```
*pointermama = "another value"
```
#####Struct
```
type <name> struct {
    <var name> <type>
}

//example
type Hiren struct {
    nan string
    nish string
}

//assinment
var prism = Hiren{ "Example", "example" }
//or
var prism = Hiren{ nish : "Example", nan: "example }
//or 
var prism = Hiren{}
prism.nan = "bla blah"
prism.nish = "yo yo "

//access 
fmt.Println(prism.nan)
```
#####Function
```
func Example(<name> <type>)<return type>{
   return bla bla
}

func Hiren(hiren string) string {
   return 'hello'
   }
```
######Multiple returns
```
func example(<name> <type>) ( multiple return type separated by comma){
   return <return value separated by comma>
}

func example(hiren string) (string, string) {
   return 'hi', 'hello'
   }
```
######Named returns
```
func example(<name> <type>) ( multiple return type with name separated by comma){
   return 
}

func example(hiren string) (hi string, hello string) {
   hi = "hi"
   hello = "holla"
   return
   }
```
######Variadic function
passing unlimited value in the fucntion
```
func example( yo name ...string) string {
   return name[0]
}
```
######Closure
```
function Xoxo(yo string) function() int{
   return func() int {
      return 1
      }
 }
```
#####Branching
######If
```
if <optional statment>; <conditions> { //brackets are not optional for on liner ! 
   //
}

 if a := 1; a == ! {
  //
 }else {
 //
 }
```
######Switch
>No default fall through
>Dont need an expression
>Cases can be expressions
```
exm := 'hiren'
switch exm {
  case 
}
```

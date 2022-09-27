## JS scope

global: define without variables
test = "sss";

functional: define with _var_
has hoising (floats up)
closest function

block scope: define with _let_
only inside the brackets

## Equality and types

prime types:

Boolean
number
String
Undefined
Object
function
symbol

examples:

var is20 = false; // boolean
typeof is20; // boolean

var age = 19;
typeof age; // number

var lastName = "Bae";
typeof lastName; // string

var fruits = ["Apple", "Banana", "Kiwi"];
typeof fruits; // object

var me = {firstName:"Sammie", lastName:"Bae"};
typeof me; // object

var nullVar = null;
typeof nullVar; // object

var function1 = function(){
console.log(1);
}
typeof function1 // function

var blank;
typeof blank; // undefined

## Truth / False check

Here are commonly used expressions that evaluate to false:
• false
• 0
• Empty strings ('' and "")
• NaN
• undefined
• null

Here are commonly used expressions that evaluate to true:
• true
• Any number other than 0
• Non-empty strings
• Non-empty object

"5" == 5 // returns true
"5" === 5 // returns false

only use with non-object types i.e numbers, booleans and strings





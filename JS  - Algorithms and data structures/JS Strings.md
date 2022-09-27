## String Primitive

.charAt(index)
.subStringAt(indexStart, IndexEnd)
.indexOf('string', 'indexStart')
.startsWith('string')
.endsWith('string')

## String Decomposition

var test1 = 'chicken,noodle,soup,broth';
test1.split(","); // ["chicken", "noodle", "soup", "broth"]

var test1 = 'chicken';
test1.split(""); // ["c", "h", "i", "c", "k", "e", "n"]

.replace('oldString', 'newString')

## Regular Expressions

i : case insensitive
g: global match
m: multiline matching

regExp :
.search() returns index of match
.match() returns all matches

.exec() test for matches in a string, return first match
.test() test for matches, return true or false

Basic RegEx:

^: Indicates the start of a string/line
\d: Finds any digit
[abc]: Finds any character between the brackets
[^abc]: Finds any character not between the brackets
[0-9]: Finds any digit between the brackets
[^0-9]: Finds any digit not between the brackets
(x|y): Finds any of the alternatives specified

ex:
var str = "JavaScript DataStructures";
var n = str.search(/DataStructures/);
console.log(n); // prints '11'

## Common Regex: 

1. Any Numeric Characters

var reg = /\d+/;
 reg.test("123"); // true
 reg.test("33asd"); // true
 reg.test("5asdasd"); // true
 reg.test("asdasd"); // false

2. Only Numeric Chars

/^\d+$/
 var reg = /^\d+$/;
 reg.test("123"); // true
 reg.test("123a"); // false
 reg.test("a"); // false

3. Floating Numerique Characters

/^[0-9]*.[0-9]*[1-9]+$/
 var reg = /^[0-9]*.[0-9]*[1-9]+$/;
 reg.test("12"); // false
 reg.test("12.2"); // true

4. Only AlphaNumerique

/[a-zA-Z0-9]/
 var reg = /[a-zA-Z0-9]/;
 reg.test("somethingELSE"); // true
 reg.test("hello"); // true
 reg.test("112a"); // true
 reg.test("112"); // true
 reg.test("^"); // false


5. Query String

/([^?=&]+)(=([^&]*))/

var uri = 'http://your.domain/product.aspx?category=4&product_id=2140& 
query=lcd+tv' ;

var queryString = {};
uri.replace(
new RegExp ("([^?=&]+)(=([^&]*))?" , "g" ),
function ($0, $1, $2, $3) { queryString[$1] = $3; }
);
console.log('ID: ' + queryString['product_id' ]); // ID: 2140
console.log('Name: ' + queryString['product_name' ]); // Name: undefined
console.log('Category: ' + queryString['category' ]); // Category: 4


## String Shortening

 var DICTIONARY = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789".split(");


- Encoding: 

var base= Dictionary
var encoded= ";

if( num === 0){
  return Dictionary[0];
}

while(num > 0){
  encoded += Dictionary[(num % base)]
  num = Math.floor(num / base)
}

return reverseWord(encoded)

- reverse Word

... look it up


## Encryption

SSL warning: This likely means the web site you are trying to access does not have the proper 
Secure Sockets Layer (SSL) certificate

RSA encryption:

Key gen: Public Key and Private Key - construction of both must be secret.
Encryption: Secret Message can be encrypted via PUBKey
Decryption: Only Private key can decrypt the message

Process algo: 
 - select p and q : large prime numbers
 - p-1 and q-1 = PHI

 - e = num > 3
 - d = (e * d) % phi = 1 

 encry process:

 m= message
 m^e %n = c
 c= encrypted message

 decry process: 

 c^d %n = m

Process Calculate d:

look up the algo

Typically the 
prime numbers chosen are very large for the RSA algorithm. This is because the prime 
factorization of large numbers takes a long time to compute. Today’s standard is to 
use a 4,096-bit prime product. Computing its prime factors would take years even for 
advanced computers to compute.
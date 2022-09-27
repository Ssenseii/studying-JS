## short circuit

var x = 1;

x == 10 && alert("x is 10")
x == 10 || alert("x is not 10")

# Arrays

## arr-like obj to arr

real arr = ['a','a','a']

var arr-like = {
0: 'a',
1: 'b',
2: 'c',
length: 3
};

conversion:

- Array.from
- for (const element of arr-like){
  arr.append(element);
  }
- [...arr-Like]
- arr = Object.values(arr-like)
- var arr = Object
  .keys(arr-like)
  .map((key) => arr-like(key))

## reducing values

const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce(
(previousValue, currentValue) => previousValue + currentValue ,
initialValue
);

console.log(sumWithInitial);

### flattening an array of objects;

array.reduce(function(obj, current) {
obj[current.key] = current.value;
return obj;
}, {});

### map using reduce

function map(list, fn) {
return list.reduce(function(newList, item) {
return newList.concat(fn(item));
}, []);
}
// Usage:
map([1, 2, 3], function(n) { return n \* n; });
// → [1, 4, 9]

### min - max

var arr = [4, 2, 1, -10, 9]
arr.reduce(function(a, b) {
return a < b ? a : b
}, Infinity);
// → -10

### finding unique values

arr.reduce((prev, number) => {
if(prev.indexOf(number) === -1) {
prev.push(number);
}
return prev;
}, []);
// → [1, 2, 5, 9]

## Mapping values

['one', 'two', 'three', 'four'].map(value => value.length);
// → [3, 3, 5, 4]

## Filtering object Arrays

let odd = numbers.filter(n => n % 2 !== 0); // can be shortened to (n => n % 2)
let young = people.filter(person => person.age < 35);

var young = people.filter((obj) => {
var flag = false;
Object.values(obj).forEach((val) => {
if(String(val).indexOf("J") > -1) {
flag = true;
return;
}
});
if(flag) return obj;
})

read about flattening if you don't get this.

## Sorting arrays

how sort works:

function compareFn(a, b) {
if (a is less than b by some ordering criterion) {
return -1;
}
if (a is greater than b by the ordering criterion) {
return 1;
}
// a must be equal to b
return 0;
}

.sort() is impure
since it sorts the original

### alpha sort;

['s', 't', 'a', 'c', 'K', 'o', 'v', 'E', 'r', 'f', 'l', 'W', '2', '1'].sort((a, b) => {
return a.localeCompare(b);
});

** warning ** : it will throw an error if an array element is not a string.

safe version: ['s', 't', 'a', 'c', 'K', 1, 'v', 'E', 'r', 'f', 'l', 'o', 'W'].sort((a, b) => {
return a.toString().localeCompare(b);
});

### length sort;

["zebras", "dogs", "elephants", "penguins"].sort(function(a, b) {
return b.length - a.length;
});

[100, 1000, 10, 10000, 1].sort(function(a, b) {
return a - b;
});

### Date sort

var dates = [
new Date(2007, 11, 10),
new Date(2014, 2, 21),
new Date(2009, 6, 11),
new Date(2016, 7, 23)
];
dates.sort(function(a, b) {
if (a > b) return -1;
if (a < b) return 1;
return 0;
});
// the date objects can also sort by its difference
// the same way that numbers array is sorting
dates.sort(function(a, b) {
return b-a;
});

### iteration

difference in for in vs for of

let myArray = [3, 5, 7];
myArray.foo = "hello";
for (var i in myArray) {
console.log(i); // logs 0, 1, 2, "foo"
}
for (var i of myArray) {
console.log(i); // logs 3, 5, 7
}

### array.prototype...

#### .keys

let myArray = [1, 2, 3, 4];
for (let i of myArray.keys()) {
let twoValue = myArray[i] _ 2;
console.log("2 _ value is: %d", twoValue);
}

#### .forEach

[1, 2, 3, 4].forEach(function(value, index, arr) {
var twoValue = value _ 2;
console.log("2 _ value is: %d", twoValue);
});

#### .every

/ [].every() stops once it finds a false result
// thus, this iteration will stop on value 7 (since 7 % 2 !== 0)
[2, 4, 7, 9].every(function(value, index, arr) {
console.log(value);
return value % 2 === 0; // iterate until an odd number is found
});

==

var arr = [2, 4, 7, 9];
for (var i = 0; i < arr.length && (arr[i] % 2 !== 0); i++) { // iterate until an odd number is
found
console.log(arr[i]);
}

#### .some

// [].some stops once it finds a false result
// thus, this iteration will stop on value 7 (since 7 % 2 !== 0)
[2, 4, 7, 9].some(function(value, index, arr) {
console.log(value);
return value === 7; // iterate until we find value 7
});

## Destructuring an Array

const triangle = [3, 4, 5];
const [length, height, hypotenuse] = triangle;
length === 3; // → true
height === 4; // → true
hypotneuse === 5; // → true

using ...

const [b,c, ...xs] = [2, 3, 4, 5];
console.log(b, c, xs); // → 2, 3, [4, 5]

example calculate a surface area:

function area([length, height]) {
return (length \* height) / 2;
}

const triangle = [3, 4, 5];
area(triangle); // → 6

## Removing duplicate elements

var uniqueArray = ['a', 1, 'a', 2, '1', 1].filter(function(value, index, self) {
return self.indexOf(value) === index;
}); // returns ['a', 1, 2, '1']

## Array Comparison

JSON.stringify(array1) === JSON.stringify(array2)

## Reversing arrays

[1, 2, 3, 4].reverse();

** imp **

var arr1 = [11, 22, 33];
var arr2 = arr1.reverse();
console.log(arr2); // [33, 22, 11]
console.log(arr1); // [33, 22, 11]

#### deep reverse

function deepReverse(arr) {
arr.reverse().forEach(elem => {
if(Array.isArray(elem)) {
deepReverse(elem);
}
});
return arr;
}

var arr = [1, 2, 3, [1, 2, 3, ['a', 'b', 'c']]]; --> deep array

## Cloning Arrays

arrayToClone = [1, 2, 3, 4, 5];
clone1 = Array.from(arrayToClone);
clone2 = Array.of(...arrayToClone);
clone3 = [...arrayToClone] // the shortest way

## concating array

var array3 = [...array1, ...array2]

var arrConc = arr1.concat("c", "d", arr2);
'this works too'

_wihtout copying first array_

longArray.push(...shortArray)

if its too long: ie > 100,000

shortArray.forEach(function (elem) {
longArray.push(elem);
});

## finding a value inside an array

let bob = people.find(function(person) {
return person.name === "bob";
})

## Convert a String to an Array

var strArray = "StackOverflow".split("");
// strArray = ["S", "t", "a", "c", "k", "O", "v", "e", "r", "f", "l", "o", "w"]

## removing an item from an array

### front

array.shift()

### back

array.pop()

## add an item to an array

### front

array.unshift(1, 2);

### back

array.push()

### by Index (from, to)

var array = [1, 2, 3, 4];
array.splice(1, 2);

## finding max and min

var maxValue = Math.max(...myArray); // 99
var minValue = Math.min(...myArray); // 1

## create a new array

Array.of(21, "Hello", "World");
ar arr5 = new Array("foo");

## Some and Every explained

[false, false].some(function(value) {
 return value;
});
// Result: false
[false, true].some(function(value) {
 return value;
});
// Result: true
[true, true].some(function(value) {
 return value;
});
// Result: true
And examples for .every
[false, false].every(function(value) {
 return value;
});
// Result: false
[false, true].every(function(value) {
 return value;
});
// Result: false
[true, true].every(function(value) {
 return value;
});
// Result: true

## test array items for equality

[1, 2, 1].every(function(item, i, list) { return item === list[0]; }); // false
[1, 1, 1].every(function(item, i, list) { return item === list[0]; }); // true

## copy part of an array

// Let's say we have this Array of Alphabets
var arr = ["a", "b", "c", "d"...];
// I want an Array of the first two Alphabets
var newArr = arr.slice(0, 2); // newArr === ["a", "b"]




---




# Objects


## shallow clonning 

const existing = { a: 1, b: 2, c: 3 };
const { ...clone } = existing;

## Object.freeze

var obj = {
 foo: 'foo',
 bar: [1, 2, 3],
 baz: {
 foo: 'nested-foo'
 }
};

Object.freeze(obj);

// Cannot add new properties
obj.newProperty = true;

// Cannot modify existing values or their descriptors
obj.foo = 'not foo';
Object.defineProperty(obj, 'foo', {
 writable: true
});

// Cannot delete existing properties
delete obj.foo;

// Nested objects are not frozen
obj.bar.push(4);
obj.baz.foo = 'new foo';


## Object Cloning

*deep cloning*

unction deepClone(obj) {
 function clone(obj, traversedObjects) {
 var copy;
 // primitive types
 if(obj === null || typeof obj !== "object") {
 return obj;
 }
 // detect cycles
 for(var i = 0; i < traversedObjects.length; i++) {
 if(traversedObjects[i] === obj) {
 throw new Error("Cannot clone circular object.");
 }
 }
 // dates
 if(obj instanceof Date) {
 copy = new Date();
 copy.setTime(obj.getTime());
 return copy;
 }
 // arrays
 if(obj instanceof Array) {
 copy = [];
 for(var i = 0; i < obj.length; i++) {
 copy.push(clone(obj[i], traversedObjects.concat(obj)));
 }
 return copy;
 }
 // simple objects
 if(obj instanceof Object) {
 copy = {};
 for(var key in obj) {
 if(obj.hasOwnProperty(key)) {
 copy[key] = clone(obj[key], traversedObjects.concat(obj));
 }
 }
 return copy;
 }
 throw new Error("Not a cloneable object.");
 }
 return clone(obj, []);
}


## Object properties iteation

for (var property in object) {
 // always check if an object has a property
 if (object.hasOwnProperty(property)) {
 // do stuff
 }
}

## Object Assign

add new properties:


var user = {
 firstName: "John"
};
Object.assign(user, {lastName: "Doe", age:39});
console.log(user); // Logs: {firstName: "John", lastName: "Doe", age: 39}


or create a shallow copy

var obj = Object.assign({}, user);
console.log(obj); // Logs: {firstName: "John", lastName: "Doe", age: 39}

or combine properties from many objects

var obj1 = {
 a: 1
};
var obj2 = {
 b: 2
};
var obj3 = {
 c: 3
};
var obj = Object.assign(obj1, obj2, obj3);
console.log(obj); // Logs: { a: 1, b: 2, c: 3 }
console.log(obj1); // Logs: { a: 1, b: 2, c: 3 }, target object itself is changed


## Object rest and spread "..."

let obj = { a: 1 };
let obj2 = { ...obj, b: 2, c: 3 }


## Object defineProperty

Object.defineProperties(obj, {
 property1: {
 value: true,
 writable: true
 },
 property2: {
 value: 'Hello',
 writable: false
 } 
});


## get and Set

Treat a property as a combination of two functions, one to get the value from it, and another one to set the value in
it

You cannot assign a value or writable to a descriptor that has get or set

var person = { name: "John", surname: "Doe"};
Object.defineProperty(person, 'fullName', {
 get: function () {
 return this.name + " " + this.surname;
 },
 set: function (value) {
 [this.name, this.surname] = value.split(" ");
 }
});

console.log(person.fullName); // -> "John Doe"

person.surname = "Hill";
console.log(person.fullName); // -> "John Hill"

person.fullName = "Mary Jones";
console.log(person.name) // -> "Mary


## Dynamic Variable Property name

var dictionary = {
 lettuce: 'a veggie',
 banana: 'a fruit',
 tomato: 'it depends on who you ask',
 apple: 'a fruit',
 Apple: 'Steve Jobs rocks!' // properties are case-sensitive
}

var word = prompt('What word would you like to look up today?')
var definition = dictionary[word]

## Object.seal

Object.seal prevents the addition or removal of properties from an object. Once an object has been sealed its
property descriptors can't be converted to another type. Unlike Object.freeze it does allow properties to be
edited.


var obj = { foo: 'foo', bar: function () { return 'bar'; } };
Object.seal(obj)
obj.newFoo = 'newFoo';
obj.bar = function () { return 'foo' };
obj.newFoo; // undefined
obj.bar(); // 'foo'

## Convert object's values to array

var array = Object.keys(obj)
 .map(function(key) {
 return obj[key];
 });
console.log(array); // ["hello", "this is", "javascript!"]


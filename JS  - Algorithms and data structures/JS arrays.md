# Arrays

## Insertion

var array1 = [1,2,3,4];
array1.push(5); //array1 = [1,2,3,4,5]
array1.push(7); //array1 = [1,2,3,4,5,7]
array1.push(2); //array1 = [1,2,3,4,5,7,2]

## Deletion

var array1 = [1,2,3,4];
array1.pop(); //returns 4, array1 = [1,2,3]
array1.pop(); //returns 3, array1 = [1,2]

## Access

var array1 = [1,2,3,4];
array1[0]; //returns 1
array1[1]; //returns 2

## Iteration

for ( var i=0, len=array1.length; i<len; i++ ) {
console.log(array1[i]);
}

var counter=0;
while(counter<array1.length){
// insert code here
counter++;
}

## for in / for of

for in can print index, or print element by index
for of can print all elements of array

## forEach()

var array1 = ['all','cows','are','big'];

array1.forEach( function (element, index){
console.log(element);
});

array1.forEach( function (element, index){
console.log(array1[index]);
});

## Slice(begin, end)

var array1 = [1,2,3,4];
array1.slice(1,2); //returns [2], array1 = [1,2,3,4]
array1.slice(2,4); //returns [3,4], array1 = [1,2,3,4]

array1.slice(); //returns [1,2,3,4], array1 = [1,2,3,4]
->
returns copy of array but can't compare

or use: var array1 = [1,2,3,4];
var array2 = Array.from(array1);

## .splice(begin,size,element1,element2…)

var array1 = [1,2,3,4];
array1.splice(); //returns [], array1 = [1,2,3,4]
array1.splice(1,2,5,6,7); //returns [2,3],array1 = [1,5,6,7,4]

## .concat()

var array1 = [1,2,3,4];
array1.concat(); //returns [1,2,3,4], array1 = [1,2,3,4]
array1.concat([2,3,4]); //returns [1,2,3,4,2,3,4],array1 = [1,2,3,4]

## Spread Operator

function addFourNums(a, b, c, d) {
return a + b + c + d;
}
var numbers = [1, 2, 3, 4];
console.log(addFourNums(...numbers)); // 10

## Min / Max

var array1 = [1,2,3,4,5];
Math.max(array1); // 5

var array2 = [3,2,-123,2132,12];
Math.min(array2); // -123

## Find sum of 2 elements in an array

function findSumbetter(arr, target){
var hashtable = {};

for(var i = 0; i < arr.length ; i++){
var currentElement = arr[i],
different = taget - currentElement;

    if(hashTable[currentElement] != udnefined){
      return [i, hashtable[weight - currentElement]];
    } else {
      hashtable[difference] = i;
    }

}
return -1;
}

## rewriting the entier slice function

function arraytSlice(array, beginIndex, endIndex){
if(! beginIndex && ! endIndex){
return array;
}

var partArr: [];

...
}

## Find the median of two sorted arrays

function medianofArray(array)'
var length= array.length;

if(lenght % 2== 1){
return array[math.floor(length/2)]
}else{
return (array[length/2]+ array[(length/2)-1]) / 2
}

say we have arr1: [2,3,4]
arr2: [5,6,7];

median = (max(arr1[0], arr2[0]) + min(arr1[1], arr2[1])) / 2;

## Find K elements in sorted arrays

function comElements(kArray){
var hashMap= {};
last, answer = [];

for(var i = 0; i < kArray.length; i++ ){
... look up the algorithm
}
}

## Javascript Functional Array Methods

### Map:

[1,2,3,4,5,6,7].map(function (value){
return value\*10;
});
// [10, 20, 30, 40, 50, 60, 70]

### Filter:

[100,2003,10,203,333,12].filter(function (value){
return value > 100;
});
// [2003, 203, 333]

### Reduce:

var sum = [0,1,2,3,4].reduce( function (prevVal, currentVal, index,
array) {
return prevVal + currentVal;
});
console.log(sum); // prints 10

## Multidimensional Arrays

function Matrix(rows, columns) {
var jaggedarray = new Array(rows);
for (var i=0; i < columns; i +=1) {
jaggedarray[i]=new Array(rows);
}
return jaggedarray;
}
console.log(Matrix(3,3));

var matrix3by3 = [[1,2,3],[4,5,6],[7,8,9]];
matrix3by3[0]; // [1,2,3]
matrix3by3[1]; // [4,5,6]
matrix3by3[1]; // [7,8,9]

matrix3by3[0][0]; // 1
matrix3by3[0][1]; // 2
matrix3by3[0][2]; // 3

matrix3by3[1][0]; // 4
matrix3by3[1][1]; // 5
matrix3by3[1][2]; // 6

## Path Finding

var board =
%e%%%%%%%%%\n
%...%.%...%\n
%.%.%.%.%%%\n
%.%.......%\n
%.%%%%.%%.%\n
%.%.....%.%\n
%%%%%%%%%x%

var rows= board.split('/n');

function generateColumnArr(arr){
return arr.split("");
}

var MazeMatrix = rows.map(generateColumnArr);

find entrance and exit;

function FindChar(char, mazematrix){
var row = MazeMatrix.length,
column = MazeMatrix[0].length;

for (var i =0; i < row; i++){
for(var j = 0; j < column; j++){
if(mazeMatrix[i][j] == char){
return [i, j];
}
}
}
}

function printMatrix(matrix) {
var mazePrintStr = "" ,
row = matrix.length,
column = matrix[0 ].length;

for (var i = 0 ; i < row; i++ ) {

for (var j = 0 ; j < column; j++ ) {
mazePrintStr += mazeMatrix[i][j];
}

mazePrintStr += "\n" ;

}
console.log(mazePrintStr);
}

## summary for iteration:

for (var prop in arr) Iterates by the index of the array element
for (var elem of arr) Iterates by the value of the array element
arr.forEach(fnc) Applies the fnc value on each element



# Searching and sorting

Searching and sorting are fundamental algorithms

This chapter focuses on searching and sorting for arrays. By
the end of this chapter, you will understand how to use common sorting and searching
algorithms for arrays

## Searching

### Linear Search

function linear Search(array?n){
for (var i = 0; i < arr.length; i++){
if (arr[i] == n){
return true;
}else{
return false;
}
}
}

Complexity of O(n)

let's sort the array and do a binary search.

### Binary Search

- works on sorted data

function BinarySearch(arr, n){
var LowIndex = 0;
highIndex = arr.length-1;

while (lowIndex <= highIndex){
var midIndex = math.floor(( highIndex + lowIndex ) / 2);
if(array[ midIndex ] == n){
return midIndex;
}else{
if(n < array[ midIndex ]){
lowIndex = midIndex;
}else{
highIndex = midIndex;
}
}
}

return -1;
}

## Sorting

### bubble Sort

time complexity: O(n²)
Space Complexity: O(1)

### Selection Sort

function SelectionSort(items){
var len = item.length,
min;

for(var i = 0; i < len; i++){
min = i;
for (j = j +1; j < len; j++){
if(items[j] < items[min]){
min = j;
}
}

    if(i != min){
      swap(items, i, min);
    }

}

return min;
}

### Insertion Sort

function InsertionSort(items){
var = items.length,
value,
i,
j;

for(i = 0; i < len, i++){
value = items[i];

    for (j = i-1; j > -1 && items[j] > value; j--){
      items[j+1] = items[j];
    }
    items[j+1] = value;

}
return items;
}

### QuickSort

Complexity O(nLog~2~(n)) --> worst case: O(n²)

function QuickSort(items){
return quickSortHelper(items, 0, items.length-1);
}

function QuickSortHelper(items, left, right){
var index;
if(items.length > 1){
index = Partion(items, left, right);

if(left < index - 1){
quickSortHelper(items, left, index - 1);
}
}
return items;
}

...

## COunt dort: counts by the occurence of a number

works only for numbers in a certai range,
Complexity of O(k+n)
uses hashmaps

function countSort(array){
var hash = {}, count Arr = [];

for (var = 0; i < arr.length; i++){
if(!hash[array[i]){
hash[array[i]] = 1;
}else{
hash[array[i]++;
}
}

for (var elem in hash){
for(var i = 0; i < hash[key]; i++){
countArr.push(parseInt(key));
}
}

return countArr;
}

countSort([6,1,23,2,3,2,1,2,2,3,3,1,123,123,4,2,3]); // [1, 2, 3, 4, 6, 23]

Time Complexity: O(k+n)
Space Complexity: O(k)
Use count sort when you’re sorting integers with a limited range. This will be the
fastest sort for this case

Quicksort O(nlog2(n)) O(nlog2(n))
Mergesort O(nlog2(n)) O(nlog2(n))
Bubble sort O(n2) O(n2)
Insertion sort O(n2) O(n2)
Selection sort O(n2) O(n2)
Count sort O(k + n) O(k)

Exercices: Use the impleùment square root of a function for an integer without using any math libraries;

function SQROOTNAIVE(number){
if(number == 0 || number == 1)
return number;

var index = 1, square = 1;

while(square < number){
if(square == number){
return square;
}
index++;
square = index \* index;
}
return index;
}

FInd if two elements in an array add up to a certain number;

function findTwoSum(array, sum) {

for(var i=0, arrayLength = array.length; i<arrayLength;i++){
for(var j=i+1;j<arrayLength;j++){
if(array[j]+array[i] == sum){
return true;
}
}
}
return false;
}



# Sets

var example = new Set();

it has one native property; size(integer)

## Insertion, Deletion and Contains

### Insertion: 

var exampleSet = new Set();
  exampleSet.add(1); // exampleSet: Set {1}
  exampleSet.add(1); // exampleSet: Set {1}
  exampleSet.add(2); // exampleSet: Set {1, 2}

### Deletion

var example = new Set();
example.add(1);
exaple.delete(1);

### Contains

var exampleSet = new Set();
  exampleSet.add(1); // exampleSet: Set {1}
  exampleSet.has(1); // true
  exampleSet.has(2); // false
  exampleSet.add(2); // exampleSet: Set {1, 2}
  exampleSet.has(2); // true

## Other utility functions

### Intersection

function intersectSets (setA, setB) {
   var intersection = new Set();
   for (var elem of setB) {
   if (setA.has(elem)) {
   intersection.add(elem);
   }
   }
   return intersection;
   }
   var setA = new Set([1, 2, 3, 4]),
   setB = new Set([2, 3]);
   intersectSets(setA,setB); // Set {2, 3}

### IsSuperSet

function IsSuperSet(setA, SubSetB){
  for(var elem of subset){
    if(!setA.has(elem)){
      return false;
    }
  }
  return true;
}

### union

function union(setA, setB){
  var union = newSet(setA);
  for(var elem of setB){
    union.add(elem);
  }
  return union;
}

var setA = new Set([1, 2, 3, 4]),
 setB = new Set([2, 3]),
 setC = new Set([5]);
 unionSet(setA,setB); // Set {1, 2, 3, 4}
 unionSet(setA,setC); // Set {1, 2, 3, 4, 5}
 

### Diference

function Difference Set(setA, setB){
  var difference = new set(setA);
  for (var eleme of setB){
    difference.delete(elem);
  }
}

A set is a fundamental data structure to represent unordered unique elements. In this 
chapter, JavaScript’s native Set object was introduced. The Set object supports insertion, 
deletion, and contains check, which all have a time complexity of O(1). With these built-in methods, other fundamental set operations such as intersection, difference, union, 
and superset check are implemented. These will enable you to implement algorithms 
with fast uniqueness checks in future chapters


# Exercices:

## Check for dublicates in an array:

function check for dublicates(arr){
  setFromArray = new Set(arr);
  return (setFromArray.size < arr.length)
}

## Return All unique numbers from seperate array:

function Unique(arr1, arr2){
  var uniqueSet = new Set(arr1.concat(arr2)).
  return Array.from(uniqueSet)
}


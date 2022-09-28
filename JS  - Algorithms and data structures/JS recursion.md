# Recursion

## Base case

function countDownToZero = () =>
{
  if(n < 0){
    return;
  } else {
    console.log(n);
    countDownToZero(n-1);
  }
}

countDownToZero(12);

## Devide-and-Conquer Method: 
 breakdown a function 

 example: Fibonacci Sequence

 iterative solution: 

function getNthFibo(n){
  if (n <= 0) return n;

  var sum = 0, 
  last = 1,
  lastLast = 0;

  for(i=0; i < n ;i++){
    sum = LastLast + Last;
    LastLast = Last;
    Last = sum;
  }
  return Sum;
}

recursive Solution: 

function getNthFibo(n){
  if (n <= 1){
    return n
  } else {
    return getNthFibo(n-1) + getNthFibo(n-2)
  }
}


  Tail recursion: 


function getNthFiboBetter(n, lastLast, Last){
  if(n==0){
    return LastLast;
  }
  if(n== 1){
    return Last;
  }
  return getNthFiboBetter(n-1, last, lastlast + last)
}

Pascal's Triangle:

function pascaletriangle(row, col){
  if( col == 0){
    return 1;
  }
  else if(row == 0){
    return 0;
  }else{
    return pascaleTriangle(row -1, col) + pascaleTriangle(row-1, col -1);
  }
}


exercices in recursion: 


function Base10toBinary(n){

var BinaryString = "";

  function BinarytoString(n){
    if(n<2){
      binaryString += n;
    }else{
      BinarytoString(Math.floor(n/2));
      BinarytoString(n%2);
    }
  }
binarytoString(n);

return BinaryString;
}


print all permutations of an array: 

function PermutateArray(arr){
  function swapper(i1, i2){
    let temp;
    temp = i1;
    i1 = i2;
    i2 = temp;
  }


  
}
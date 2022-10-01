1. Running Sum of 1d Array

## My iteration: 

var runningSum = function(nums) {
    var duplicate = Array.from(nums);
    
    for(var i = 1; i < nums.length; i++){
        
        for(var j = 0; j < i; j++){
            nums[i] = nums[i] + duplicate[j];    
        }
        
    }
    return nums;
};

## Better Solution

const runningSum = nums => {
    nums.reduce((a,c,i,arr) => arr[i] += a) 
    <!-- reduce((previousValue, currentValue, currentIndex, array) => { /* … */ } ) -->
    return nums
}


---

2. Highest Wealth

## MI

var maximumWealth = function(accounts) {
    
    var highestWealth = 0;
    
    for(var i = 0; i < accounts.length; i++){
    const wealth = accounts[i].reduce((partialSum, a) => partialSum + a, 0);
        
        if(wealth > highestWealth){
            highestWealth = wealth;
        }
    }
    
    return highestWealth;
    
};

## FS (without reduce)

//! function to find the sum of array
const sum = (arr) => {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
};

const maximumWealth = (accounts) => {
  let wealthy_customer = 0;
  for (let balance of accounts) {
    const curr_wealth = sum(balance); // we will get total balance of the person
    wealthy_customer = Math.max(wealthy_customer, curr_wealth);
  }
  return wealthy_customer;
};


---

3. Fizz Buzz

## MI

var fizzBuzz = function(n) {
    var arr = [];
    
    for(var i = 1; i <= n; i++){
        if(i % 15 == 0){
            arr[i-1] = "FizzBuzz";
        } else {
            if(i % 5 == 0){
                arr[i-1] = "Buzz";
            } else{
                if(i % 3 == 0){
                    arr[i-1] = "Fizz";
                } else {
                    arr[i-1] = i.toString();
                }
            }
        }
    }
    
    return arr;
};

## FS

var fizzBuzz = function(n) {
    return new Array(n).fill(0).map((a, i) => (++i % 3 ? '' : 'Fizz') + (i % 5 ? '' : 'Buzz') || '' + i);
};


---


## Steps to Zero

## MI

var numberOfSteps = function(num) {
    var count = 0;    
    
    while(num != 0){
    if (num % 2 == 0){
        num = num / 2;
        count++;
    } else {
        num = num - 1;
        count++;
    }   
    }
    
    return count;
};

## FS (Binary in Java)

int numberOfSteps (int num) {
		if(!num) return 0;
        int res = 0;
        while(num) {
            res += (num & 1) ? 2 : 1;
            num >>= 1;
        }
        return res - 1;
    }
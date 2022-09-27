# JS memory management

## Memory Leaks

A memory leak is a failure in a program to release discarded memory, causing impaired 
performance and sometimes even failure. Memory leaks can happen when JavaScript 
engines’ garbage collectors do not free memory properly.

## reference to an object

var foo = {
 bar1: memory(), // 5kb
 bar2: memory() // 5kb
 }

referencing one property will use 10kb... the whole object

## Leaking DOM

If a variable pointing to a DOM element is declared outside of an event callback, then it is in memory and leaks DOM if the element is deleted.

one way to avoid it: reference inside the event

var one = document.getElementById("one");

 one.addEventListener('click', function(){
 var two = document.getElementById("two");
 two.remove();
 });

## Global Window Object

avoid global variables whenever it is possible

## Limiting Object Reference
## Delete operator

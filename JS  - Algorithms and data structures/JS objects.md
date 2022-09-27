# Objects: 

## Prototypal Inheritance

function ExampleClass(){
  this.name = "javascript;
  this.sayName= function(){
    console.log(this.name);
  }}

  var example1 = new ExampleClass()
  example1.sayName()...

## Constuctor and Variables

function ExampleClass(name, size){
  this.name = name;
  this.size = size;
}

var example = new ExampleClass("Public", 5);
console.log(example); //{name: "Public",  size...}

## Clear Getters and Setters


function ExampleClass(name, size) {
 var privateName = name;
 var privateSize = size;

 this.getName = function() {return privateName;}
 this.setName = function(name) {privateName = name;}

 this.getSize = function() {return privateSize;}
 this.setSize = function(size) {privateSize = size;}
 }

 var example = new ExampleClass("Sammie",3);
 example.setSize(12);
 console.log(example.privateName); // undefined
 console.log(example.getName()); // "Sammie"
 console.log(example.size); // undefined
 console.log(example.getSize()); // 3


## Summary

there's wayy too much in Javascript objects to cover in this one file...
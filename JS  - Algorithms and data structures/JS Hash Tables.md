# Hash tables

a hash table is a fixed size data structure in which the size is defined at the start, this chapter explains how hash tables work by focusing on the hashing, the method of generating a unique key.

## intro:

- quick storage and retrieval of data on key-value pairs
 javascript works with hashes by adding a key property and its associated value

 hash tables have two functions: 
 put() -> used for storing data
 get() -> used for retrieving data

localStorage.setItem("testKey","testValue");
 location = location; // refreshes the page

 //-----------------------------------
 localStorage.getItem("testKey"); // prints "testValue"


## Hashing Techniques

most important part is a hash function: converting a specified key into an index for an array that stores all of your data.

requirements for a good hash function:
- deterministic: equal keys produce equal hash values
- efficiency: it should be O(1) in time.
- Uniform Distribution: It makes the most use of the array

The first technique for hashing is to use prime numbers. By using the modulus 
operator with prime numbers, a uniform distribution of the index can be guaranteed.

## Prime Number Hashing:

Prime hashing is cool, but it can cause collisions. that's why we use strategies to handle them.

### Probing

To work around occurring collisions, the probing hashing technique finds the next 
available index in the array. The linear probing technique resolves conflicts by finding 
the next available index via incremental trials, while quadratic probing uses quadratic 
functions to generate incremental trials.

- Linear Probing

The main disadvantage of linear probing is it easily creates clusters, which are bad 
because they create more data to iterate through.

- Quadratic Probing

Quadratic probing is a good technique for addressing the cluster issue. Quadratic 
probing uses perfect squares instead of incrementing by 1 each time, and this helps to 
evenly distribute across the available indices

## Rehashing / double-hashing

requirements;

- Different; it needs to be different to distribute it better
- efficient: it should be in O(1) time
- nonZero: it should nevr evaluate to zero. zero give the intial hash value

hash function commonly used: hash2(x) = R − (x % R)


## Hash table Implementation


# JS Numbers

JavaScript uses a 32-bit floating-point representation for numbers, as shown in Figure 3-1.
In this example, the value is 0.15625. The sign bit (the 31st bit) indicates that the number
is negative if the sign bit is 1. The next 8 bits (the 30th to 23rd bits) indicate the exponent
value, e. Finally, the remaining 23 bits represent the fraction value.

0 00000000 00000000000000000000000
Sign / expo / fraction

value = 1 x 2e(124-127) x 1.25 = 1 x 2(-3) x 1.25 = 0.15625

### Impressive Prime Algorithm

function isPrime(n){
if (n <= 1) return false;
if (n <= 3) return true;

// This is checked so that we can skip
// middle five numbers in below loop
if (n%2 == 0 || n%3 == 0) return false;

for (var i=5; i\*i<=n; i=i+6){
if (n%i == 0 || n%(i+2) == 0)
return false;
}
return true;
}

Time Complexity: O(sqrt(n))
This improved solution cuts the time complexity down significantly.

### fast Prime factorization

function primeFactors(n){
// Print the number of 2s that divide n
while (n%2 == 0) {
console.log(2);
n = n/2;
}

// n must be odd at this point. So we can skip one element
(Note i = i +2)
for (var i = 3; i\*i <= n; i = i+2) {
// While i divides n, print i and divide n
while (n%i == 0) {
console.log(i);
n = n/i;
}
}
// This condition is to handle the case when n is a prime number
// greater than 2
if (n > 2) {
console.log(n);
}
}
primeFactors(10); // prints '5' and '2'

### modular Exponentition

function modularExponentiation ( base, exponent, modulus ) {
if (modulus == 1) return 0;

var value = 1;

for ( var i=0; i < exponent; i++ ){
value = (value * base) % modulus;
}
return value;


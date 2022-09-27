# Big O

analyse in respect to time and space 'memory'

o(1) constant time.
O(n) does not change in respect to space - just takes time.
O(n2) Quadratic time
O(n3) Cubic time
o(log(n)) 


rules: 

- If f(n) is O(g(n)), then kf(n) is O(g(n))
- If f(n) is O(h(n)) and g(n) is O(p(n)), then f(n)+g(n) is O(h(n)+p(n))
- f(n) is O(h(n)) and g(n) is O(p(n)), then f(n)g(n) is O(h(n)p(n))
- If f(n) is O(g(n)) and g(n) is O(h(n)), then f(n) is O(h(n)).
- If f(n) is a polynomial of degree k, then f(n) is O(nk)
- log(nk) is O(log(n)) for any constant k > 0.


summary: 
Big-O is important for analyzing and comparing the efficiencies of algorithms. 
The analysis of Big-O starts by looking at the code and applying the rules to simplify 
the Big-O notation. The following are the most often used rules:
• Eliminating coefficients/constants (coefficient rule)
• Adding up Big-Os (sum rule)
• Multiplying Big-Os (product rule)
• Determining the polynomial of the Big-O notation by looking at loops 
(polynomial rule


notes: if it incremenets instead of adding: its O(log~incremental number
~(n))

---
layout: post
title: Computing the Parity of a word
---

This is an example of a new way of learning I want to try to implement I will
- Give a problem statement
- Give a complete set of related tools, some that may be used in the solution
- Allow the learner to attempt stringing the tools together for a solution
- Propose a simple solution
- Allow the learner to attempt to revise if needed
- Continue proposing more complex solutions as needed

# Problem Statement
Bit-wise parity refers to whether there is an odd or even number of 1s in a binary number. Odd means the parity is 1, even means 0. For example 1010's parity is 0 because it has two 1's. 1011's parity is 1 because it has three 1's. Create a function that returns a numbers parity. 

# Tools
The following is information you may want to use to implement this. Remember there is no CORRECT answer so you may not use all of these, and you may use other methods too!

## Bit-wise operators

### &	Bitwise AND
Compare two binary numbers and compare the bits. If both are a 1, that bit is one, otherwise it is a 0.

a = 10        1010 (Binary)
b = 4         0100 (Binary)
a & b = 0     0000 (binary)

### |	Bitwise OR	
Compare two binary numbers and compare the bits. If either are a 1, that bit is one, otherwise it is a 0.

a = 10        1010 (Binary)
b = 4         0100 (Binary)
a | b = 14    1110 (binary)

### ~	Bitwise NOT	
Flip all the bits.

a = 10        01010 (Binary)
~a = -11      10101 (Binary)

This might get confusing, You are basically doing -(a+1). 
If a binary number starts with a 1, it is negative. 
- Strip the 1 from the front
- Invert the binary (1's become 0's, 0's become 1's)
- Convert that to decimal 
- add one
- Make it negative

for example 10101...
- Strip the 1 from the front...     0101
- invert ...                        1010
- Copnvert to decimal...            10
- add one ...                       11
- Make it negative...               -11

This makes no sense without further reading, but it was chosen to do binary this way to avoid the posibility of negative zero. 

### ^	Bitwise XOR	
Compare two binary numbers and compare the bits. If one is 1 and the other is zero , it is 1 otherwise 0.

a = 10        1010 (Binary)
b = 4         0100 (Binary)
a ^ b = 14    1110 (binary)

### >>	Bitwise right shift	x>>
Shifts the bits of the number to the right and fills 0 on voids left( fills 1 in the case of a negative number) as a result. Similar effect as of dividing the number with some power of two.

### <<	Bitwise left shift	x<<
Shifts the bits of the number to the left and fills 0 on voids right as a result. Similar effect as of multiplying the number with some power of two.

## Masks
Masking is used when I want to select a subset from a list. Lets say I have an array of ["A", "B", "C", "D"] and I want to choose the forst and last item. I could use a mask of <1,0,0,1>, with 1 being "I need this" and 0 being "ignore me". Python's numpy has masking functions but also an & bitwise operator can apply a mask on a binary number.


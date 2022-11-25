---
layout: post
title: Computing the Parity of a word
comments: true
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

### How to enter binary into python
All int types in python can be treated as binary if you like. I highly suggest writing out your binary as a string and then passing it in with the base as an int.

```python
a = int('101', 2) #int(BinaryString, Base2)
print(a)
# prints 5
```

Python will preint a decimal by default, for debugging you may want to print binary like this:

```python
a = 5
print(format(a, 'b'))
# prints 101
```

### &	Bitwise AND
Compare two binary numbers and compare the bits. If both are a 1, that bit is one, otherwise it is a 0.

```python
a = 10        #1010 (Binary)
b = 4         #0100 (Binary)
print(a & b)  #0000 (binary)
#Prints zero
```

### |	Bitwise OR	
Compare two binary numbers and compare the bits. If either are a 1, that bit is one, otherwise it is a 0.

```python
a = 10        #1010 (Binary)
b = 4         #0100 (Binary)
print(a | b)  #1110 (binary)
#Prints 14
```
Note: It is pure coincidence that the bitwise OR in the above example is equivilent to adding the numbers.

### ~	Bitwise NOT	
Flip all the bits.

```python
a = 10        #01010 (Binary)
print(~a)     #10101 (Binary)
#Prints -11
```

Flipping the bits is REALLY CLOSE to negating a number.

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

```python
a = 10         #1010 (Binary)
b = 4          #0100 (Binary)
print(a ^ b)   #1110 (binary)
#Prints 14
```

### >>	Bitwise right shift	x>>
Shifts the bits of the number to the right and fills 0 on voids left( fills 1 in the case of a negative number) as a result. Similar effect as of dividing the number with some power of two.

```python
a = 10         #1010 (Binary)
print(a>>1)    #0101 (binary)
# prints 5
```

### <<	Bitwise left shift	x<<
Shifts the bits of the number to the left and fills 0 on voids right as a result. Similar effect as of multiplying the number with some power of two.

```python
a = 10         #1010 (Binary)
print(a<<1)    #10100 (binary)
# prints 20
```

### Masks
Masking is used when I want to select a subset from a list. Lets say I have an array of ["A", "B", "C", "D"] and I want to choose the forst and last item. I could use a mask of <1,0,0,1>, with 1 being "I need this" and 0 being "ignore me". Python's numpy has masking functions but also an & bitwise operator can apply a mask on a binary number.

Let's use a mask of 000000001, on the number 11. It will just grab the last binary digit.

```python
a = 11         #1011 (Binary)
print(a & int('1', 2))    #1 (binary)
#Prints 1
```

### Clear the lowermost set bit
This is more of a shortcut, utilizing the above tools. Often you may want to "zero out" the lowermost set bit (the lowermost 1). This is a good method of doing that:

```python
a = int('101', 2) # 5 in decimal
a &= a - 1
print(format(a, 'b'))
# prints 100
```

All we are doing here is using the AND operator with a number that we know will differ by the last bit (a-1). 

### Using a cache

There is always a tradeoff between Memory usage and Speed. If we want to increase the speed of a calculation we can often save some common scenarios in memory. Think back to the problem statement, what if I made a table of every single possible 16 bit number and put 1, or 0 for its parity. During runtime, there would be no need for calculation, you only have to look it up!

For example: lets make a table of all 2-bit parities

 Key          | Parity      |
| ----------- | ----------- |
| 00      | 0       |
| 01      | 1       |
| 10      | 1       |
| 11      | 0       |

# Problem statement again
Now that we have all the needed tools, Lets Look at the problem statement again--

Bit-wise parity refers to whether there is an odd or even number of 1s in a binary number. Odd means the parity is 1, even means 0. For example 1010's parity is 0 because it has two 1's. 1011's parity is 1 because it has three 1's. Create a function that returns a numbers parity. 

# First answer that comes to mind
Try to think of the first answer that comes to mind. It doesn't have to be elegant. The next section will give some examples

# Some simple answers
Here are some simple answers you may have thought of. These area all awesome and solve the problem! You could stop there, and to be clear depending on what the context of your program is, these answere very well may be good enough. 

## Simple Loop
If you are like me, you may want to ignore all the bitwise stuff just mentioned and treat this as a string. Count the "ones" and use modulo to check if you have everything paired:

This has O(n) time complexity, which is acceptable.

```python
    def parityLoop(self, num):
        """
        :type num: int
        :rtype: num: int (1, or 0)
        """

        num_text = format(num, 'b')  # Convert num to string
        number_of_ones = 0  # Parity begins at zero

        # Count the number of ones
        for digit in num_text:
            if digit == "1":
                number_of_ones += 1

        # Check the modulo
        if number_of_ones % 2 == 0:  # If its an even number
            return 1  # Parity
        else:
            return 0  # No Parity
```
## bitwise loop
Maybe you also thought loop, but wanted to keep this as a numerical instead of a string.

This has O(n) time complexity, which is acceptable.

```python
    def parityLoop(self, num):
        """
        :type num: int
        :rtype: num: int (1, or 0)
        """

        number_of_ones = 0

        while num:
            # Use a mask to get lowest bit
            lowest_bit = num & int('1', 2)  # We use masking to get the last bit

            if lowest_bit == 1:
                number_of_ones += 1

            # Now cut-off the lowest bit
            num >>= 1

        # Check the modulo
        if number_of_ones % 2 == 0:  # If its an even number
            return 1  # Parity
        else:
            return 0  # No Parity
```

## lowermost set bit
Maybe you remembered my tool above for the lowermost set bit. If you  just keep clearing the lowermost 1, then you can count the loops.

This has O(k) time complexity, if k = the number of set bits. This is the best so far. 

```python
    def parityLoop(self, num):
        """
        :type num: int
        :rtype: num: int (1, or 0)
        """

        result = 1

        while num:
            # use Xor, to "toggle" the result
            result ^= 1
            
            # Clear the lowermost 1
            num &= num -1
        
        return result
```

# More complex answers
Okay I believe we have squeezed a lot out of the simple answers. Now how could we squeeze even time out of our solutions if needed. Usually this comes down to cashing and managing data structures. Try to think of how you would do it before reading ahead.

## Caching
As hinted, we can cache some answers, Lets do all 16 bits numbers:

The method "ParityLoopCalculate" is literally the code from the above examples. 

time complexity O(n/L) with L = 16 for a 16 bit lookup table

```python
    def parityLoop(self, num):
        """
        :type num: int
        :rtype: num: int (1, or 0)
        """

        # This part would normally be done prior to running
        # 16 bit table would go from range(-32,768,32,767)
        arrayOfParities = []
        for i in range(-32768, 32767):
            parity = parityLoopCalculate(i)
            arrayOfParities.append(parity)

        MASK_SIZE = 16
        BIT_MASK = int('1111111111111111', 2)  # 16 set digits

        # this only works for a 64 bit number
        # Split it into four 16 bit numbers
        first_16_bits = num >> (3 * MASK_SIZE)
        second_16_bits = (num >> (2 * MASK_SIZE)) & BIT_MASK
        third_16_bits = (num >> MASK_SIZE) & BIT_MASK
        fourth_16_bits = num & BIT_MASK

        # Use Xor to compare
        final_parity = arrayOfParities[first_16_bits] ^ \
                       arrayOfParities[second_16_bits] ^ \
                       arrayOfParities[third_16_bits] ^ \
                       arrayOfParities[fourth_16_bits]

        return final_parity
```
Note: Dont try to run this, making the table takes way too long.

## splitting
This is one of those surprising answers that looks simple but is honestly difficult to come up with. If you start with a 64 bit number, what if you do an AND comparison of the first 32 bits with the second 32 bits. THen you were to split it in half again, and again. You would get the parity!

Time complexity is O(log n)

```python
def parityLoop(self, num):
    """
    :type num: int
    :rtype: num: int (1, or 0)
    """

    num ^= num >> 32
    num ^= num >> 16
    num ^= num >> 8
    num ^= num >> 4
    num ^= num >> 2
    num ^= num >> 1

    return num
```

# Conclusion
Dont beat yourself up if you didn't think of the complex solutions. No one starts these coding puzzles and immediately recognizes these. But remember what we did to get them. 

- We used a cache to speed up calculations during run-time
- We split the problem into sub-problems

These will be common tactics to solving other problems!


**Positional Number Systems**
- Numbers can be represented in any base
- Humans are used to base 10
- We can analyse numbers based on position and powers of 10.

![[Pasted image 20250108192456.png]]
- We should subscript number with their base, decimal numbers with 10 and binary numbers with 2

**Binary Numbers**
- Base 2 (binary) is usually used in computers
- The digits used in this base are 1 and 0
- A single binary digit is known as a bit


Example: Decimal Number vs Binary Number

Consider the number 13

Decimal:
![[Pasted image 20250108192724.png]]

Binary:
![[Pasted image 20250108192757.png]]
Follow the formula d x base

**Binary to Decimal Conversion**

1) Divide the given decimal number by 2, note remainder
2) Divided the obtained quotient by 2, note the remainder again
3) Repeat until 0 is the quotient
4) Write the remainders in such a way that the last remainder is written first, followed by the rest in reverse order. 
5) Result is the binary number of the given decimal

![[Pasted image 20250108193045.png]]

**Hexadecimal**
- Long binary numbers are hard to read
- Hexadecimal is base 16. Each digit can represent 4 bits. 
- Uses the characters 0123456789ABCDEF to represent decimal numbers 0..15 and binary numbers 0000 - 1111
![[Pasted image 20250108193248.png]]

**Octal**
- Octal is a number represented with base 8
- The octal representation uses the characters 0 1 2 3 4 5 6 7
- Each Octal character corresponds to three bits in binary
- Use same method as to convert decimal to octal as binary, but divide by 3
![[Pasted image 20250108193541.png]]

# Signed and Unsigned values#

**Bits, Bytes and Words**
- Bit - The most basic unit, a single binary digit
- Byte - A collection of 8 bits
- Word - Two or more adjacent bytes that are addressed and handled collectively
- The word size represents the data size that is handled more efficiently by a particular architecture
- The number of bits we use to represent a number defines the largest number we can store. 
- In modern computers, word sizes of 32 or 64 bits are usual. 

**Representing Positive Integers**
- Least significant bit (LSB) - The "smallest" bit in a word. The bit at position 0
- Most significant bit (MSB) - The "biggest" bit in a word. The bit at position 1
- In a 32 bit word, the MSB would be the digit at position 31, as indexing starts at 0

# Floating Point and Non-Numeric Data#

**Endianness**
- To identify the order in which bytes that constitute words are stored in memory
- When programming at a low level, you must know which your machine supports. 

**Calculating combinations**
- To work out how many different possible combinations there are of a certain word, raise the number of bits to 2 and minus 1. 
- For example: Calculate the number of unique permutations of a 3 bit word.
- Answer: 2^3 - 1


# Representing Negative Numbers#

Signed binary integer numbers may be expressed by
- Signed magnitude
- One's compliment
- Two's compliment

**Signed-Magnitude Representation:**

- Assign 1 bit to represent the sign (typically the left most bit)
- Use the rest of the bits to represent magnitude
- Disadvantages:
	- Using a special signed bit means we can represent fewer numbers
	- Both +0 and -0 are valid, causes problems for programmers
	- Arithmetic circuits are complicated by the calculation of a sign
- To calculate the range of number we can represent with N bits:
	- -(2^(n-1) - 1) to 2^(n-1) - 1


**Binary Addition**
- Use binary column addition, remember the following rules:
- 0 + 0 = 0
- 1 + 0 = 1
- 0 + 1 = 1
- 1 + 1 = 0 (carry a 1)
- 1 + 1 + 1 (carry a 1)
- If a 1 is carried on the last digit, this is an overflow error. Number is too big to be represented in the given number of bits. 

**Example:**
- Using signed magnitude arithmetic, find the sum of 75 and 46.
- Convert 75 and 46 to binary, and arrange in a column. Separate the sign bits from the magnitude bits.
- Check the sign bits. If the signs are the same, add and keep the sign. If they are different, subtract the smaller value from the larger value and assign the sign of the larger value. 
- Start with the right most bit and work left. 

**Binary Subtraction**
- Use column method, but with different rules to addition
- 0 - 0 = 0
- 1 - 0 = 1
- 1 - 1 = 0
- 0 - 1 = 1 (with a borrow of 1 from the next highest column)
- When borrowing occurs, the borrowed 1 is equivalent to 2 in binary)
- Example:
 ![[Pasted image 20250113115756.png]]

# Compliment Based Representation

- Signed magnitude representation easy to understand, but requires complicated computer implementations
- Another disadvantage is that there are 2 representations of 0. +0 and -0. 
- For these reasons, and others, computer systems use **compliment systems** for number representation

**What is Two's compliment?**
- Two's compliment is the radix (base) complement of the binary system. 
- The radix complement of a non-zero number N in base r with d digits is. 
- r^d - n
- MSB is regarded as sign bit, but it will be the minus of that column. For example: an 8 bit two's compliment will look like this:
- -128 64 32 16 8 4 2 1

To express a value in two's compliment
- If the number is positive, just convert it to binary. 
- If number is negative, flip all digits after the first one. 

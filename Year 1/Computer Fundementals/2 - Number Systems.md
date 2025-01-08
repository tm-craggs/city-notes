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

Signed bn
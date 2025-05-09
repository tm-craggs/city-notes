Memory abstraction in simplifying the memory for the memory management unit 

Every square of memory is a bit, and holds flip flops. How do we organise and allocate these squares.

Organise is cells/words/bytes, which could be a certain amount of bits in a row. It depends on how many bits the words hold. 

![[image.png|412x220]]

As chips has progressed they have had more bits per word. 

## Address Space

Virtual memory vs Physical Memory. 

Virtual memory does not have a physical location. Swapping them is known as memory mapping. 

Memory Management Unit - A hardware device that at run time, maps virtual to physical addresses there are many methods possible. The user programs deals with logical addresses and never sees the real physical addresses. Logical addresses are bound to physical addresses. 

Logical addresses are what the program sees, and are mapped to physical addresses. This is because if programs were competing for physical addresses, each program would have to know what is free and allocate themselves. Mapping addresses ensures isolation of programs. 

Simple dynamic relocation does not work in reality, as there is no limit to how high the physical addresses can go. It is not memory safe. We have to protect so that it does not go above or below. 

We can add a limit register, which is the maximum for each process. 

The physical address will be checked that it is higher than a base, held in a register. It will then check it is lower than another register holding the base + limit. If either of these are m
![image](https://github.com/user-attachments/assets/f23e09e6-c882-477c-8845-743943406c4b)# Memory-Management-Notes

Residence Memory- Is the actual useful memory in a RAM. Meaning if you have 4GB RAM you have 2^32 bits of residence memory(32 address buses).

**Process of data storage**

The address of any cell(1byte) in a RAM is made up of segment address(says which segment block of RAM memory is stored in-imagine as rows) and offset address(says which exact cell of a segment block the address points to). The Ox part is segment part and the digits after it are offset address.
Note that it grows upwards from stack.

![memorymap](https://github.com/user-attachments/assets/7f175fc0-e912-4bd1-aaa8-084bb7e748f8)

**Types of Storage in RAM**

All creating(new) and deletion(delete) of data happens in heap. Remember malloc and calloc. New creates space in memory.
Here there is also something interesting, delete process is there in case because of memory leaks(malicious attacks). Something called dangling pointer(pointer which points to address that has already been deleted) is dangerous.

Function data is stored in code part.

All global variable are stored in static memory part(doesnt change)
All local variable data is stored in stack memory part(yes the same as the LIFO thing).

![storagetypes](https://github.com/user-attachments/assets/9d80aa09-bb87-4cb6-9649-00e8dca12adb)

# Stack and Stack Frame


In below diagram it shows how some local variable is stored when a program is run. 

**Remember program always starts from where main() function is.**

We can see the inner function variables being stored on top of outer function.
These variables are stored in stack format(LIFO)
A stack frame is the stack of a single function.
So these frames are created when we run a program, but they eventually get pulled out when they are used and are not entered into the stack again. When the bottom variable(a) is pulled out the stack remains empty and is deleted once program is killed.

![stack/stackframe](https://github.com/user-attachments/assets/bac0de3b-681a-4987-9e39-5be45bdede61)

**FUNCTION ARGUMENTS ARE ALSO LOCAL VARIABLES AND STORED IN STACK**

For example consider func(arg1,arg2)
here arg1 and arg2 are also stored in stack and will be put into stack frame when function is called before all the local variables inside it.

**Stack and Recursion**

![stack&recursion](https://github.com/user-attachments/assets/d4a1ac8f-c5c5-4ca2-8def-53c8bb2cfcb6)

Here we see that x=5 at first but after going through sum function (see the explanation on right side) output is coming as something.
we are calling the sum function again and again in a loop until some conclusion is reached, this is called recursion.

Rest of the part in video 2 seems to be about just pointers and arrays.

![pointertoafunc](https://github.com/user-attachments/assets/f565a12d-4b5c-48ac-9ad7-17deccbaa241)

**Operation on Pointers**

![pointerops](https://github.com/user-attachments/assets/f76584ca-57e6-49ae-b0f9-dc3fa8d4cbea)

c points to a[0] (base address) which is at 1000
note that when we do c=c+2 it doesnt become 1002, it moves to 2 units ahead(because its an array so thats how pointers will work here), so now c points to a[2] which is at 1004.

**Dynamic storage**

![image](https://github.com/user-attachments/assets/1d30a8ce-7d77-481d-990f-820a143347ba)

Note that a is pointing to an object not any value thats why we have used this "new" keyword.

**Reference**

![reference](https://github.com/user-attachments/assets/cbc71411-1dba-48c1-bc2e-019741ab0560)

When we declare as a reference it means that both the original(a) and the reference(x) become the same thing. So any operation done to a will also happen to x and vice versa because they are same. Basically x and a have the same address or here x address has pointer which points to address of a.

![referencevspointer](https://github.com/user-attachments/assets/c3d10822-77b4-4123-8b2a-f21481addc1c)




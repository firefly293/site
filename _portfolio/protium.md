---
title: "Protium - A CPU Emulator"
excerpt: "A custom 16-bit CPU emulator written in C++ with its own custom assembly language.<br/><img src='/images/500x300.png'>"
collection: portfolio
---

Protium is a 16-bit CPU emulator written in C++ with its own custom assembly language comprising of 88 unique instructions. Some features it implements are registers, stack, subroutines, and more. Here is a program written in its assembly language that performs the factorial of a number using recursion:

```
; main part of program
inint a ; input number into A
setdst 0x09 0x50 ; set DST to 0x5009, which is the address of the factorial subroutine
call ; call the factorial subroutine
outint a ; the factorial subroutine will store the result in A, so after calling it output A
; start of factorial subroutine 
mov b a ; copy value of A into B
dec b ; decrement B, B will be what A is multiplied by each iteration
setc 0x02 0x00 ; set C to 2, B will be compared to C every iteration in order to break out when necessary
; start of loop
cmp b c ; compare B with 2
jisr 0x10 0x00 0x00 0x00 ; jump out of loop if B < 2
mul a a b ; a = a * b
dec b ; decrement B for next iteration
jmpr 0x00 0x00 0x0e 0x00 ; jump back to start of loop
ret ; return
```

For more details, documentation, and the source code of the project, visit [it's github repo](https://github.com/firefly293/protium).

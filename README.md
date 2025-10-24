# Ajith_factorial_mpmc_sa1

# FACTORIAL-OF-A-NUMBER
# FACTORIAL OF A NUMBER USING 8086

## AIM
To write and execute an Assembly language program to perform the factorial of a number using 8086.

---

## APPARATUS REQUIRED
- Personal computer with dosbox software

---

## ALGORITHM
Step-by-Step Algorithm

1.Start

2.Clear the AX register (AX = 0) and copy AL to BL.

3.Load SI with address 2000h. 

4.Read a byte from memory address 2000h into BL (BL = [2000h]).

5.Set AL = 1 (initial multiplier for factorial).

6.Loop:

Multiply AL by BL → store the result in AX.

Decrement BL by 1.

If BL ≠ 0, repeat the loop.

7.After the loop ends, store the result in AX at memory address 3000h.

8.Trigger interrupt 3 (int 3) for debugging.

9.End
---

## FLOWCHART
<img width="506" height="525" alt="image" src="https://github.com/user-attachments/assets/f3b47187-6f0f-490c-8704-f2973cb2b276" />


---

## PROGRAM
```asm
code segment
assume cs:code

start:
    xor ax,ax
    mov bl,al
    mov si,2000h
    mov bl,[si]
    mov al,01h

l1:
    mul bl
    dec bl
    jnz l1

    mov si,3000h
    mov[si],ax
    int 3

code ends
end start

```
OUTPUT

<img width="640" height="480" alt="Screenshot (267)" src="https://github.com/user-attachments/assets/bb6f463f-d90e-4750-917a-3e6198ffaa17" />


---
manual calculations:

<img width="591" height="454" alt="image" src="https://github.com/user-attachments/assets/33084ec2-9c0e-43d3-9ddd-6ac9a572aa3e" />

---

RESULT

Thus, the factorial of a number was calculated and executed successfully using 8086.

---



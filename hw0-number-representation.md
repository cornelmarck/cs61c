# HW0: Intro and number representation

https://inst.eecs.berkeley.edu//~cs61c/sp15/hw/00/hw0.html

## Number representation

### Unsigned
```text
Decimal |   Binary          |   Hexadecimal
10          0b0000 0000         0x0A
240         0b1111 0000         0XF0
11          0b0000 0111         0x0B
250         0b1111 0001         0xFA
256         0b1111 1111         0xFF
204         0b1100 1100         0xCC
-35         n/a                 n/a
128         0b1100 0000         0x80
105         0b0110 1001         0x69
```

### Two's Complement
```text
Decimal |   Binary          |   Hexadecimal
-10         0b1111 0110         0xF6
-17         0b1111 0000         0xF0
15          0b0000 1111         0x0F
-95         0b1010 0001         0xA1
250         n/a                 n/a
-1          0b1111 1111         0xFF
-86         0b1010 1010         0xCC
-35         0b1101 1101         0xDD
128         n/a                 n/a
105         0b0110 1001         0x69
```

## Picking representations

1. Temperature in degrees Celcius: Two's complement because temperature is negative when it freezes. 
2. Maximise the number range: Both, the range for unsigned [0, 2^n) has the same length as $[-2^{n-1}, 2^{n-1})$ for two's complement.
3. Number of boxes that a factory has shipped: Both, although two's complement is more practical since it allows a negative balance (e.g. when boxes are returned to the factory).

## Counting
1. $4^n$
2. $2^{n-1}$
3. 1
4. $2^n - 1$

## Overflow
```text
64 + 64 = 0b0110 0000 + 0b0110 0000 = 0b1000 0000           OVERFLOW
-127 + 30 = 0b1000 0000 + 0b0001 1110 = 0b1001 1110 = -97   CORRECT
-127 - 1 = 0b1000 0000 + 0b1111 1111 = 0b1 1111 1111        OVERFLOW
38 - 40 = 0b0010 0110 + 0b1101 1000 = 0b1111 1110 = -2      CORRECT

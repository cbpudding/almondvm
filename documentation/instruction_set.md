# Instructions

| Mnemonic | Format                      | Description                                        | C Representation   |
| -------- | --------------------------- | -------------------------------------------------- | ------------------ |
| `add.c`  | `add.c rel a, rel b, imm c` | Adds a number in memory to a constant              | `*a = *b + c;`     |
| `add.r`  | `add.r rel a, rel b, rel c` | Adds two numbers in memory together                | `*a = *b + *c;`    |
| `aloc.c` | `aloc.c rel a, imm b`       | Allocates a block of memory                        | `*a = malloc(b);`  |
| `aloc.r` | `aloc.r rel a, rel b`       | Allocates a block of memory                        | `*a = malloc(*b);` |
| `b.c`    | `b.c imm a`                 | Branch to a location in memory                     | `pc = a;`          |
| `b.r`    | `b.r rel a`                 | Branch to a location in memory                     | `pc = *a;`         |
| `bnz.c`  | `bnz.c rel a, imm b`        | Branch if the given value is non-zero              | `if(*a) pc = b;`   |
| `bnz.r`  | `bnz.r rel a, rel b`        | Branch if the given value is non-zero              | `if(*a) pc = *b;`  |
| `bz.c`   | `bz.c rel a, imm b`         | Branch if the given value is zero                  | `if(!*a) pc = b;`  |
| `bz.r`   | `bz.r rel a, rel b`         | Branch if the given value is zero                  | `if(!*a) pc = *b;` |
| `drf.i`  | `drf.i rel a, ind b`        | Read a value from an indirect pointer              | `*a = **b;`        |
| `drf.r`  | `drf.r ind a, rel b`        | Write the given value to an indirect pointer       | `**a = *b;`        |
| `free`   | `free rel a`                | Deallocates a block of memory                      | `free(*a);`        |
| `get.c`  | `get.c imm a, rel b`        | Read a value from a stream                         | `read(a, b, 1);`   |
| `get.r`  | `get.r rel a, rel b`        | Read a value from a stream                         | `read(*a, b, 1);`  |
| `hlt.c`  | `hlt.c imm a`               | Stop the program with the given return value       | `exit(a);`         |
| `hlt.r`  | `hlt.r rel a`               | Stop the program with the given return value       | `exit(*a);`        |
| `mov`    | `mov rel a, imm b`          | Sets the value in memory to the given value        | `a = b;`           |
| `put.c`  | `put.c imm a, rel b`        | Write the given value to a stream                  | `write(a, b, 1);`  |
| `put.r`  | `put.r rel a, rel b`        | Write the given value to a stream                  | `write(*a, b, 1);` |
| `ref`    | `ref rel a, rel b`          | Creates an indirect pointer to something in memory | `*a = &b;`         |
| `sub.r`  | `sub.r rel a, rel b, rel c` | Subtract a value in memory from another            | `*a = *b - *c;`    |
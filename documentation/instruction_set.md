# Arithmetic Instructions (alu.*)

| Mnemonic   | Example            | Description                                   | C Representation |
| ---------- | ------------------ | --------------------------------------------- | ---------------- |
| `alu.add`  | `alu.add x, y, z`  | Calculates the sum of two numbers             | `x = y + z;`     |
| `alu.and`  | `alu.and x, y, z`  |
| `alu.div`  | `alu.div x, y, z`  |
| `alu.mod`  | `alu.mod x, y, z`  |
| `alu.mul`  | `alu.mul x, y, z`  |
| `alu.nand` | `alu.nand x, y, z` |
| `alu.nor`  | `alu.nor x, y, z`  |
| `alu.not`  | `alu.not x, y`     |
| `alu.or`   | `alu.or x, y, z`   |
| `alu.sla`  | `alu.sla x, y, z`  |
| `alu.sll`  | `alu.sll x, y, z`  |
| `alu.sra`  | `alu.sra x, y, z`  |
| `alu.srl`  | `alu.srl x, y, z`  |
| `alu.sub`  | `alu.sub x, y, z`  | Calculates the difference between two numbers | `x = y - z;`     |
| `alu.xnor` | `alu.xnor x, y, z` |
| `alu.xor`  | `alu.xor x, y, z`  |

# Control Flow Instructions (ctl.*)

| Mnemonic   | Example            | Description                                                                                          | C Representation          |
| ---------- | ------------------ | ---------------------------------------------------------------------------------------------------- | ------------------------- |
| `ctl.b`    | `ctl.b x`          | Unconditionally branches to another part of the program                                              | `*(x)();`*                |
| `ctl.beq`  | `ctl.beq x, y, z`  | Branches to another part of the program if the first two operands are equal                          | `if(x == y) { *(z)(); }`* |
| `ctl.bge`  | `ctl.bge x, y, z`  | Branches to another part of the program if the first operand is greater than or equal to the second  | `if(x >= y) { *(z)(); }`* |
| `ctl.bgt`  | `ctl.bgt x, y, z`  | Branches to another part of the program if the first operand is greater than the second              | `if(x > y) { *(z)(); }`*  |
| `ctl.bl`   | `ctl.bl x`         | Unconditionally branches to another part of the program and pushes the return address onto the stack |
| `ctl.ble`  | `ctl.ble x, y, z`  | Branches to another part of the program if the first operand is less than or equal to the second     | `if(x <= y) { *(z)(); }`* |
| `ctl.bleq` | `ctl.bleq x, y, z` |
| `ctl.blge` | `ctl.blge x, y, z` |
| `ctl.blgt` | `ctl.blgt x, y, z` |
| `ctl.blle` | `ctl.blle x, y, z` |
| `ctl.bllt` | `ctl.bllt x, y, z` |
| `ctl.blne` | `ctl.blne x, y, z` |
| `ctl.blt`  | `ctl.blt x, y, z`  | Branches to another part of the program if the first operand is less than the second                 | `if(x < y) { *(z)(); }`*  |
| `ctl.bne`  | `ctl.bne x, y, z`  | Branches to another part of the program if the first two operands are not equal                      | `if(x != y) { *(z)(); }`* |
| `ctl.hlt`  | `ctl.hlt x`        | Stops program execution and returns the given value                                                  | `exit(x);`                |

\* Not all instructions can be accurately represented using the C programming language.

# Memory Instructions (mem.*)

| Mnemonic  | Example        | Description                                               | C Representation       |
| --------- | -------------- | --------------------------------------------------------- | ---------------------- |
| `mem.alc` | `mem.alc x, y` | Allocates a block of memory and maps it to the heap       | `x = malloc(y);`       |
| `mem.dea` | `mem.dea x`    | Deallocates a block of memory and unmaps it from the heap | `free(x);`             |
| `mem.ld`  | `mem.ld x, y`  | Loads a symbol from memory                                | `x = *y;`              |
| `mem.mov` | `mem.mov x, y` | Copies the value from one symbol to another               | `x = y;`               |
| `mem.pop` | `mem.pop x`    | Pops a symbol off the top of the stack                    | `x = stk[--sp];`*      |
| `mem.psh` | `mem.psh x`    | Pushes a symbol onto the top of the stack                 | `stk[sp++] = x;`*      |
| `mem.st`  | `mem.st x, y`  | Stores the symbol in memory                               | `*x = y;`              |
| `mem.swp` | `mem.swp x, y` | Swaps the value of two symbols                            | `t = x; x = y; y = t;` |

\* Not all instructions can be accurately represented using the C programming language.

# Stream Instructions (stm.*)

| Mnemonic   | Example         | Description | C Representation |
| ---------- | --------------- | ----------- | ---------------- |
| `stm.flsh` | `stm.flsh x`    |
| `stm.get`  | `stm.get x, y`  |
| `stm.pos`  | `stm.pos x, y`  |
| `stm.put`  | `stm.put x, y`  |
| `stm.seek` | `stm.seek x, y` |
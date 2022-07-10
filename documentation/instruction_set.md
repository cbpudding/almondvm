# Arithmetic Instructions (alu.*)

| Mnemonic   | Example            | Description                                                  | C Representation | Substitute                                           |
| ---------- | ------------------ | ------------------------------------------------------------ | ---------------- | ---------------------------------------------------- |
| `alu.add`  | `alu.add x, y, z`  | Calculates the sum of two numbers                            | `x = y + z;`     | *None*                                               |
| `alu.and`  | `alu.and x, y, z`  | Calculates the bitwise AND of two numbers                    | `x = y & z;`     | *None*                                               |
| `alu.div`  | `alu.div x, y, z`  | Calculates the quotent from the given dividend and divisor   | `x = y / z;`     | *None*                                               |
| `alu.mod`  | `alu.mod x, y, z`  | Calculates the remainder from the given dividend and divisor | `x = y % z;`     | *None*                                               |
| `alu.mul`  | `alu.mul x, y, z`  | Calculates the product of two numbers                        | `x = y * z;`     | *None*                                               |
| `alu.nand` | `alu.nand x, y, z` | Calculates the bitwise NAND of two numbers                   | `x = ~(y & z);`  | `alu.and t, y, z` / `alu.not x, t`                   |
| `alu.neg`  | `alu.neg x, y`     | Calculates the two's complement of a number                  | `x = -y;`        | *None*                                               |
| `alu.nor`  | `alu.nor x, y, z`  | Calculates the bitwise NOR of two numbers                    | `x = ~(y \| z);` | `alu.or t, y, z` / `alu.not x, t`                    |
| `alu.not`  | `alu.not x, y`     | Calculates the bitwise NOT of a number                       | `x = ~y;`        | *None*                                               |
| `alu.or`   | `alu.or x, y, z`   | Calculates the bitwise OR of two numbers                     | `x = y \| z;`    | `alu.not t, y` / `alu.not u, z` / `alu.nand v, t, u` |
| `alu.rol`  | `alu.rol x, y, z`  |
| `alu.ror`  | `alu.ror x, y, z`  |
| `alu.sla`  | `alu.sla x, y, z`  |
| `alu.sll`  | `alu.sll x, y, z`  | Calculates the logical shift of a number                     | `x = y << z;`    | *None*                                               |
| `alu.sra`  | `alu.sra x, y, z`  |
| `alu.srl`  | `alu.srl x, y, z`  | Calculates the logical shift of a number                     | `x = y >> z;`    | *None*                                               |
| `alu.sub`  | `alu.sub x, y, z`  | Calculates the difference between two numbers                | `x = y - z;`     | `alu.neg t, z` / `alu.add x, y, t`                   |
| `alu.xnor` | `alu.xnor x, y, z` | Calulcates the bitwise Exclusive NOR of two numbers          | `x = ~(y ^ z);`  | `alu.xor t, y, z` / `alu.not x, t`                   |
| `alu.xor`  | `alu.xor x, y, z`  | Calculates the bitwise Exclusive OR of two numbers           | `x = y ^ z;`     |

# Control Flow Instructions (ctl.*)

| Mnemonic   | Example            | Description                                                                                                                                      | C Representation                              | Substitute |
| ---------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------- | ---------- |
| `ctl.b`    | `ctl.b x`          | Unconditionally branches to another part of the program                                                                                          | `*(x)();`*                                    | *None*     |
| `ctl.beq`  | `ctl.beq x, y, z`  | Branches to another part of the program if the first two operands are equal                                                                      | `if(x == y) { *(z)(); }`*                     | *None*     |
| `ctl.bge`  | `ctl.bge x, y, z`  | Branches to another part of the program if the first operand is greater than or equal to the second                                              | `if(x >= y) { *(z)(); }`*                     |
| `ctl.bgt`  | `ctl.bgt x, y, z`  | Branches to another part of the program if the first operand is greater than the second                                                          | `if(x > y) { *(z)(); }`*                      | *None*     |
| `ctl.bl`   | `ctl.bl x`         | Unconditionally branches to another part of the program and pushes the return address onto the stack                                             | `stk[sp++] = pc + 1; *(x)();`*                |
| `ctl.ble`  | `ctl.ble x, y, z`  | Branches to another part of the program if the first operand is less than or equal to the second                                                 | `if(x <= y) { *(z)(); }`*                     |
| `ctl.bleq` | `ctl.bleq x, y, z` | Branches to another part of the program and pushes the return address onto the stack if the first two operands are equal                         | `if(x == y) { stk[sp++] = pc + 1; *(z)(); }`* |
| `ctl.blge` | `ctl.blge x, y, z` | Branches to another part of the program and pushes the return address onto the stack if the first operand is greater than or equal to the second | `if(x >= y) { stk[sp++] = pc + 1; *(z)(); }`* |
| `ctl.blgt` | `ctl.blgt x, y, z` | Branches to another part of the program and pushes the return address onto the stack if the first operand is greater than the second             | `if(x > y) { stk[sp++] = pc + 1; *(z)(); }`*  |
| `ctl.blle` | `ctl.blle x, y, z` | Branches to another part of the program and pushes the return address onto the stack if the first operand is less than or equal to the second    | `if(x <= y) { stk[sp++] = pc + 1; *(z)(); }`* |
| `ctl.bllt` | `ctl.bllt x, y, z` | Branches to another part of the program and pushes the return address onto the stack if the first operand is less than the second                | `if(x < y) { stk[sp++] = pc + 1; *(z)(); }`*  |
| `ctl.blne` | `ctl.blne x, y, z` | Branches to another part of the program and pushes the return address onto the stack if the first two operands are not equal                     | `if(x != y) { stk[sp++] = pc + 1; *(z)(); }`* |
| `ctl.blt`  | `ctl.blt x, y, z`  | Branches to another part of the program if the first operand is less than the second                                                             | `if(x < y) { *(z)(); }`*                      | *None*     |
| `ctl.bne`  | `ctl.bne x, y, z`  | Branches to another part of the program if the first two operands are not equal                                                                  | `if(x != y) { *(z)(); }`*                     |
| `ctl.br`   | `ctl.br`           | Unconditionally branches to the address on top of the stack                                                                                      | `*(stk[sp--])();`                             |
| `ctl.hlt`  | `ctl.hlt x`        | Stops program execution and returns the given value                                                                                              | `exit(x);`                                    | *None*     |

\* Not all instructions can be accurately represented using the C programming language.

# Memory Instructions (mem.*)

| Mnemonic  | Example        | Description                                               | C Representation       | Substitute                                       |
| --------- | -------------- | --------------------------------------------------------- | ---------------------- | ------------------------------------------------ |
| `mem.alc` | `mem.alc x, y` | Allocates a block of memory and maps it to the heap       | `x = malloc(y);`       | *None*                                           |
| `mem.dea` | `mem.dea x`    | Deallocates a block of memory and unmaps it from the heap | `free(x);`             | *None*                                           |
| `mem.mov` | `mem.mov x, y` | Copies the value from one symbol to another               | `x = y;`               | `alu.add x, y, 0`                                |
| `mem.pop` | `mem.pop x`    | Pops a symbol off the top of the stack                    | `x = stk[--sp];`*      | *None*                                           |
| `mem.psh` | `mem.psh x`    | Pushes a symbol onto the top of the stack                 | `stk[sp++] = x;`*      | *None*                                           |
| `mem.swp` | `mem.swp x, y` | Swaps the value of two symbols                            | `t = x; x = y; y = t;` | `mem.mov t, x` / `mem.mov x, y` / `mem.mov y, t` |

\* Not all instructions can be accurately represented using the C programming language.

# Stream Instructions (stm.*)

| Mnemonic   | Example         | Description | C Representation | Substitute |
| ---------- | --------------- | ----------- | ---------------- | ---------- |
| `stm.flsh` | `stm.flsh x`    |
| `stm.get`  | `stm.get x, y`  |
| `stm.pos`  | `stm.pos x, y`  |
| `stm.put`  | `stm.put x, y`  |
| `stm.seek` | `stm.seek x, y` |
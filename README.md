# Learning uxn 
Some notes I took while following [this
tutorial](https://compudanzas.net/uxn_tutorial.html) for
[uxn](https://wiki.xxiivv.com/site/uxn.html). More notes as comments in the
source files.

# Day 1 - the basics
- [day 1, the basics](https://compudanzas.net/)

## Runes
- `|` abolute pad rune: next written element will be written at this location.
  - if address is 1 byte assumes i/o memory space, if 2 bytes main memory
- `#` shorthand for the LIT opcode
  - can only be used with one or two bytes

# Day 2 - the screen
- [day 2, the screen](https://compudanzas.net/uxn_tutorial_day_2.html)

The 6th bit of an instruction is a flag for short mode:

    00100000
      ^

Indicated by adding a '2' to the instruction, like so: 
  
    LIT2 02

When set, the instruction will be executed using pairs of bytes instead of
single bytes.

- high byte: deeper in the stack
- low byte: closer to the top of the stack

Instead of 

    LIT 02 LIT 30 ADD  

we can use LIT in short mode, like so:

    LIT2 02 30 ADD

We can also just write the literal hex rune with a short instead of a byte:

    #0230 ADD

)

# notes on Introduction to Zig book
[link](https://pedropark99.github.io/zig-book/)
glhf :)
# chapter 1: Introducing Zig
## what is zig?
Zig wants to be a modern C - simpler

"Focus on debugging your application rather than debugging your programming language knowledge"

zig doesn't want you to spend much of your time learning the actual language, which sounds great to me!
## hello world in zig
created a new directory, cd into it and do `zig init`
### understanding the project files
a src directory is created with `main.zig` and `root.zig`. each file is a seperate zig __module__

the main() function in the main file is the entrypoint of the executable

however, if you're building a library you're supposed to delete the main file and just work in the root.zig file. the root.zig module is the "root source file of your library"
# resuming notes here
## 1.4 creating new object in Zig
he is calling variables "objects"
### const vs var
there is const and var, if you try to mutate a const it doesn't compile
### undefined objects
in zig you have to initalized a variable when you declare it. however, if you want to, you can initialize it to 'undefined'.
### object MUST be used
unused vars won't compile

if you want to, you can just assigne it to an underscore and the value will be discarded
    however, once a value is discarded it can't be used any more
### all variable objects MUST be mutated
otherwise compiler will throw error
## 1.5 primitive data types
- [u | i][8 - 128]
- f[16 - 128]
- bool
- C ABI compalible types: c_long, c_char, c_short, c_ushort, c_int, c_uint, etc.
- pointer dize ints: isize, usize
## 1.6 arrays
must have the same type for all elements

```zig
const ns = [4]u8{48, 24, 12, 6};
const ls = [_]f64{432.1, 87.2, 900.05};
```

array size is static

indexing:
```zig
const ns = [4]u8{48, 24, 12, 6};
try stdout.print("{d}\n", .{ ns[2] });
```

slicing: same syntax as rust
```zig
const ns = [4]u8{48, 24, 12, 6};
const sl = ns[1..3]; // this would contain element 1 and 2, uses the half-inclusive range

// easy to make a slice of a whole array:
const sl = ar[0..ar.len];
// equal to
const sl = ar[0..]; // can you also omit the start of the range?


```

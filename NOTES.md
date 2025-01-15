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

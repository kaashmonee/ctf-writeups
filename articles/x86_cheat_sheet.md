# What is a computer?

So before we start going into the specifics of x86 assembly, I think it might be worth while to discuss, you know, what a computer actually *is*. Well, whatever you're reading this on is a computer. And a computer's one and only job is to follow a set of instructions that you give it. So doing really simple things liking typing on a keyboard or moving your mouse all boil down to a giant list of instructions. But of course, it doesn't have to be that way. You can yourself type up a bunch of instructions to make your computer do something, and if you're reading this, you probably have. You've probably, at the very least written or *seen* C or C-like code. Here is an example: 
```c
int main () {
    printf("Hello world!\n");
    return 0;
}
```
If you've taken a programming class or done some basic programming, this will probably look pretty familiar to you. But have you ever wondered what's going on under the hood? It's pretty interesting...
All this human readable C code can be represented by slightly less readable (but very much still readable!) assembly. Assembly describes what is happening at the memory and processor level. Understanding assembly is somewhat fulfilling in its own right...it'll give you a greater appreciation for the incredibly complex work that your computer is doing right now, as you scroll through this page! So let's dive in and find out what it is... 

# What is assembly?
Here is that C code turned into assembly!
```s
	.file	"testing.c"
	.section	.rodata
.LC0:
	.string	"Hello world!"
	.text
	.globl	main
	.type	main, @function
main:
.LFB0:
	.cfi_startproc
	pushq	%rbp
	.cfi_def_cfa_offset 16
	.cfi_offset 6, -16
	movq	%rsp, %rbp
	.cfi_def_cfa_register 6
	movl	$.LC0, %edi
	call	puts
	movl	$0, %eax
	popq	%rbp
	.cfi_def_cfa 7, 8
	ret
	.cfi_endproc
.LFE0:
	.size	main, .-main
	.ident	"GCC: (Ubuntu 5.4.0-6ubuntu1~16.04.9) 5.4.0 20160609"
	.section	.note.GNU-stack,"",@progbits
```
Woah! There's a lot going on here! What in the world is happening? Well, we won't go into the details in this section, but this is just here to illustrate the "mechanical" nature of assembly. 

Say you need to build a house in real life. You have a boss or some guy who tells you what to do, and you do it exactly. He might tell you to move a brick here, move a brick there, replace brick A with brick B, and so on. You are quite literally moving things around in the limited amount of space that you have to build whatever your boss wants you to do. Assembly is pretty much the same. Higher level languages like C, C++, Java, (don't even get me started on Python), obscure a whole lot of what's going on. They don't tell you that just like you, a computer has to move things around, move data around in memory, add things, and subtract things to build whatever *you* tell it to. And this is what assembly does. Observe instructions like `movl`, `popq`, `call`, etc. `movl` does exactly what you think it does: it moves something `movl A, B` moves something from `A` to `B`. What `A` and `B` are we'll get into later. `popq` just, well, *pops* something, or just removes it. This language will be familiar to you if you've ever heard of the "stack" data structure. In any event, the important thing is, assembly gets rid of all the seeming "magic" you think is happening in the higher level languages and will show you the ugly truth. But understanding it will make you appreciate higher level languages so much more.

# What is x86?

# What are the different syntaxes?

# What is the basic idea behind assembly?

# What are the different registers?

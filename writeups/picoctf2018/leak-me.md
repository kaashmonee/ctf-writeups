## leak-me - Points: 200 - (Solves: 3966)

### Problem: Can you authenticate to this service and get the flag? Connect with nc 2018shell2.picoctf.com 31045.
This problem gives us a source and a binary.

#### Where to Start
Let's run it! What happens?
We are given a prompt where we are to enter our name and some "password" that it will check somehow. So far so good. We know that the program takes user input, which is the most likely mode of attack for us, and we know that it detects that our original password is wrong, which means that there's some sort of password verification going on somewhere. This is probably the text inside the `password.txt` file, but you can verify that for yourself. 

Now, into the source.
The first `flag()` function doesn't seem like it does much, other than check that the problem is correctly set up. It's more for the problem writers than it is for us.

Let's move onto main. In `main`, we see roughly that 



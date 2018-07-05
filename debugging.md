Debugging
---
> _"There is no freedom quite like the freedom of being constantly underestimated."– Scott Lynch_

When I first started programming, I used  print statements. Having to write this
book, I took a look at some of my earliest code samples, and it turns out that most
of it was commented out  print statements used for checking the value of variables.
Note that I started off writing C using Notepad, and compiling all that through the
command line, so no green run button and no IDE. I knew about GDB, but it was so
hard to even set a simple breakpoint that I stuck to my  print statements. Most of the
bugs I had encountered so far had been obvious bugs staring at me in the face. After
a few mishaps, I started to print everything that I could so that I could take a look at
where the program was and what was happening, making sure not to underestimate
bugs or the extent of my own stupidity.
In this chapter, we are going to be talking about PyCharm's powerful debugging
tools and use them to understand, examine, and yes, debug our programs. We are
going to:
- Take a look at how we can run Python scripts in running mode and
debugging mode
- Understand the different components of the debugging toolset
- Use variables and watches to make sure we miss nothing
- Utilize frames to zoom in and out of different layers of a program—from
your scripts right down to the Python standard library
- Evaluate expressions at breakpoints
- Use the Python console and Python prompt to gain a better understanding of 
program execution
Running, debugging, and setting breakpoints
---
You can run a  .py file in two modes: running and debugging. If you run a program,then even if you set breakpoints (points at which PyCharm will stop program
execution), nothing will happen. It's only when you run it in debug mode that
breakpoints become effective. The way I like to run or debug my programs is
through the **Resume Program** action:
![](/assets/0601.png)
You can then choose any of the different ways to run/debug your program. By
default, if you press Enter, you will go into debug mode, if you press _Shift + Enter_,
the program will just run. You can also choose coverage by pressing the left arrow:
![](/assets/0602.png)
As soon as you start debugging, a window appears underneath and you have
so many options that it's hard to make sense of it all. Let's focus on managing
breakpoints for now. To the bottom-left of the window, you can see a bunch
of buttons:
![](/assets/0603.png)
This is the View Breakpoints button. This allows you to see different types of
breakpoints that are available to you:
![](/assets/0604.png)
The breakpoint we set is a line breakpoint, but by default, in debug mode, program
execution will suspend when you get an exception. You can actually disable this, but
this only makes sense when you're looking for certain exceptions. Say, you only want
to catch  _TypeError_ exceptions:
![](/assets/0605.png)
You add  TypeError to your list of exceptions; you can also add exceptions that are
only available in your project. So, with that added, we now have:
![](/assets/0606.png)
Unfortunately, you do not have the same fine-grained control as you do with line
breakpoints, where you can evaluate expressions to pause execution. But, it still
allows you to narrow your focus on certain exception types:
![](/assets/0607.png)
In the preceding example, the breakpoint will only execute if the  Person object
is  None . If this condition is true, this will be logged to the console, and so will the
expression. In this case, it will simply print the string.
You can of course toggle all the breakpoints in debug mode as well:
![](/assets/0608.png)
This will render your line breakpoints moot.
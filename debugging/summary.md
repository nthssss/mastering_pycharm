Summary
---
I hope I was able to convince you of the value in PyCharm's debugging toolset.
We looked at a lot of the tools that I find useful in my everyday work . We covered
debugging tools and how we can use them in our own workflow.

I didn't discuss any of the common tools that are ubiquitous in any debugger, just
the ones that I find make PyCharm special.

One thing I must note is that whenever you debug code, the script will run slower
since PyCharm imports some helper functions before actually running your code. If
you take a closer look at frames when you debug a program, you will see, at the very
bottom, that a function from  pydevd.py is called. Thus, if you're looking at execution
times when you debug a program using PyCharm, you will find them a lot slower
than when you actually run them in PyCharm or the interpreter.

We also looked at PyCharm's new profiler that allows to see a nice colorized call
graph as well as giving you the ability to jump to source. If we so wished, we could
also save the files for others to view.

Finally, make absolutely sure that you turn on the collection of runtime
information when you debug since it will help you with type information,
that is, better code completion.
# Selling Haskell in the pub

_Summary: A Haskell sales pitch without any code._

I often find myself in a pub, without pen or paper, trying to persuade someone to [try Haskell](https://www.haskell.org/). In these situations I tend to use three arguments:

**Low cost abstractions:** In Haskell the [cost of creating a helper function](http://ericlippert.com/2016/02/03/north-of-house/) is low, because the syntax for functions is very concise (a single line) and the optimiser often removes all overhead of the function (by inlining it). The power of such helper functions is greatly [enhanced by higher-order functions](http://www.joelonsoftware.com/items/2006/08/01.html). In many languages each function must be top-level (within a file or class), but Haskell permits functions local to a small block, providing encapsulation and less necessity for [good names](http://www.slideshare.net/pirhilton/how-to-name-things-the-hardest-problem-in-programming). In most languages there is a much higher cost per function, and thus trivial functions are insufficiently valuable. By reducing the cost, Haskell encourages both less repetition and describing problems in a more abstract way, which is very helpful for taming program complexity.

**Refactoring works:** In Haskell, refactoring is easy, safe and common. Most projects involve writing a chunk of code, then continually changing it as the project evolves. In other languages most refactorings have [complex side conditions](https://blogs.msdn.microsoft.com/ericlippert/2011/01/13/not-as-easy-as-it-looks/) that must be met. In Haskell, most refactorings are simple, and even [refactoring tools](https://github.com/ndmitchell/hlint#readme) can have complex refactorings [mechanically proven correct](http://arxiv.org/abs/1306.1340). Any code which violates the expected side-conditions is [considered "dangerous"](http://stackoverflow.com/questions/19371636/am-i-abusing-unsafeperformio) and libraries are expected to [provide robust abstractions](https://tommd.wordpress.com/static-buffers-considered-harmful/). The [static type checker](https://tech.coursera.org/blog/2014/02/18/why-we-love-scala-at-coursera/#type-safety) ensures that most refactorings have been carried correctly. It is common to change a fundamental type in the middle of millions of lines of code, quickly make the changes required and have a high degree of confidence that it still works. The ability to easily refactor means that code can evolve with the project, without [accumulating technical debt](https://en.wikipedia.org/wiki/Technical_debt).

**Language polygots:** There are few programmers who know _only_ Haskell. I know Haskell programmers who are also experts in Perl, PHP, C, Javascript, C++, Fortran, R, Algol - pretty much any language you care to name. In contrast, when my wife has attended other programming language meetups, many of the participants knew only that language. There are many reasons Haskell programmers know lots of languages, not least because Haskell has rarely been taught as a first language. I find it interesting that many people who are experts in both Haskell and other languages typically prefer Haskell.

In response to these arguments, if people are starting to get convinced, they usually ask:

* Are there lots of libraries? [Yes, 9000+](http://hackage.haskell.org/). There are more R libraries for statistics, more Perl libraries for Bioinformatics etc - but most of the standard stuff is covered. Wrapping a C library with the [foreign function interface (FFI)](https://wiki.haskell.org/Foreign_Function_Interface) isn't too hard.
* What's the performance like? It's usually somewhere between C and Python. If you carefully optimise you can get [close to the performance of C](http://lambda.jstolarek.com/2013/04/haskell-as-fast-as-c-a-case-study/). The profiling tools are reasonable. Performance is not usually a problem, but can be solved with C and FFI if it is.

Many of the above arguments are also supportive of other statically typed functional languages. I tend to find my pub interventions are usually aimed at Python/Java/C++/PHP programmers, where I'd consider it a win if they tried O'Caml or Scala instead.
# Daily Thinking I

I'm nobody, just someone fond of computer systems and programming (in diverse paradigms). Elegant, reusable, efficient code is always my love. I've been coding for four years, most of the time writing ugly code, at least from my current point of view.

Last summer, very fortunately, due to my intership, I was exposed to a new language (that language is far from being new, but never known by me before). What's more, that language is not a common one -- it was ***Scala***!!

Well, many seasoned engineers and programmers have long heard of Scala, but I was not one of them (still not one of them now!). Why is Scala so special? It's the very first language that shows the practicality of combining OOP and FP, once considered two incompatible paradigms.

Wait, how about OCaml? The first letter of it, "O", has demonstrated it's an OOP language; besides, it's also a famous (extremely well-known) FP language. More importantly, OCaml was introduced in 1996, 8 years ahead of the introduction of Scala. Hence, obviously who learned from whom.

I admit, this argument makes sense. Worse still, as someone that just studied OCaml, it's shameful to claim OCaml is inappropriate for industrial use (on the contrary, OCaml is a very practical and industrial language, with effciency deeply embedded in its design and implementation, something even Scala can't defeat; I also want to remind you that OCaml multicore is coming this year!).

As far as I'm concerned, I will try to give my understanding about why Scala is the first one to assume the crown of successfully combining OOP and FP.

Maybe the primary reason is, Scala is more like a mixture of OOP and FP, while OCaml looks more like an FP language decorated with OOP features. I'm going to give some detailed example about this.

Scala stemmed from renovating Java (note that although most Scala programs run on JVM, Scala can also be translated into JS or native assembly code); as a consequence, Scala owns virtually all the OOP features of Java, from class to interface, to inheritance (subtyping), to means of encapsulation. It's frequently seen in the industry that fledgling Scala programmmers just emulate Java, without even basic knowledge of FP; how can you imagine an OCaml programmer behave like this?

Admittedly, programming only in imperative style is entirely allowable (but may not be feasible in large project, or you can say the feasibility is only theoretical), but far less inconvenient than programming in functional style. As a metaphor, writing Haskell (a famous purely functional language) in OCaml is easier than writing C or Java in OCaml. At this moment, I guess you've already understood what I mean.

Some frequenly used features in OOP is missing in OCaml, e.g., static members of classes. Also, in OOP languages, people bundle variables and functions with classes; in OCaml, besides this way, more libraries bunble types, values, and functions (most pure functions) with modules, and modules can be arguments and return values of functions too!

Also, OCaml code looks rather exotic for OOP programmers. In OOP languages, methods are chained with dots, like ```obj.methodA(arg0, arg1).methodB(arg2, arg3)```; or more specifically, let's see how to sum the square of all elements of a list -- in Scala, you write ```list.map(x => x * x).reduce((a, b) => a + b)```. In contrast, people use pipelines in OCaml to chain function calls; again, take the aforementioned example (summing the square of all elements of a list) -- in OCaml (with Core in place of Stdlib), you write ```list |> List.map ~f: (fun x -> x * x) |> List.reduce ~f: (fun a b -> a + b)```. Looks like the difference is just that dots are replaced with pipelines. Yes, this is not a great distinction between these two great languages (I truly love both of them! The creator of both languages are geniuses and masters).

From my perspective, the core feature that differentiate these two languages is type inference. Anyone exposed to OCaml must have been astonished by its powerful type inference. Explicit types barely appear in OCaml code, most types of arguments and function return values can be deduced by the compiler (and shown by the IDE in real time). Meanwhile, to support this, operators and ordinary functions (thus methods excluded) are forbidden from overloading. Even plus operators for integers and floating points are distinct.

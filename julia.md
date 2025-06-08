+ Reinterpret vector of vectors
  - `reduce(hcat,v)` es mejor que simplemente `hcat(v...)`
  - si los vectores internos son SVectors, es más piola usar `reshape(reinterpret(...))` Eso tiene costo virtualmente nulo, porque no realoca. 

# Interesting posts

+ [Why Julia?](https://discourse.julialang.org/t/julia-motivation-why-werent-numpy-scipy-numba-good-enough/2236/2): Why Julia vs Python. Why Python cannot be as fast as Julia.

+ [Heap vs. Stack](https://discourse.julialang.org/t/presentation-on-heap-vs-stack/117505): A presentation where the issues of heap vs stack is tackled.

+ [Heap vs. Stack](https://discourse.julialang.org/t/a-nice-explanation-of-memory-stack-vs-heap/53915): Another discusion with a nice explanation from [The Rust Book](https://doc.rust-lang.org/book/ch04-01-what-is-ownership.html#the-stack-and-the-heap). 
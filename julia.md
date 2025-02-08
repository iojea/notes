+ Reinterpret vector of vectors
  - `reduce(hcat,v)` es mejor que simplemente `hcat(v...)`
  - si los vectores internos son SVectors, es más piola usar `reshape(reinterpret(...))` Eso tiene costo virtualmente nulo, porque no realoca. 

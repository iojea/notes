# Ideas para modificar el programa de Cálculo Numérico.
  
## Situación actual

Entre las principales críticas que se suelen hacer a la materia podemos destacar:
+ Se la percibe como alejada de aplicaciones reales. Esto no es así y mucha gente reconoce el valor de la materia al cursar materias subsiguientes o al encontrarse con problemas concretos que se abordaron en CN. Aún así, este es un indicador de que la materia no logra transmitir satisfactoriamente los temas. 
+ Se la suele ver como una sucesión de temas inconexos. Esto tampoco es así, pero es evidente que no estamos logrando mostrar adecuadamente la relación profunda entre los temas. 
+ Hay algunos contenidos que parecen repetitivos. Principalmente Gram-Schmidt, a lo que se dedica bastante tiempo (en especial porque es fácil obtener ejercicios de parcial a partir de ahí).
+ Faltan temas _modernos_ (entendiéndose por tales algunos métodos iterativos para sistemas, aplicaciones de cuadrados mínimos, transformada de Fourier, etc.)
+ Física está cambiando su plan y su objetivo es eliminar Cálculo. A cambio piden una materia _para físicos_ que incluya muchísimos temas que se dan en Cálculo. Sin embargo, no quieren saber nada con Cálculo. Esto da cuenta de que la materia no es bien considerada (i.e.: no está logrando su objetivo).
+ Matemática Aplicada esencialmente ha perdido su materia de Introducción a la Computación. El DC no la dicta más y manda a los matemáticos a cursar Introducción a la Programación (ex Algoritmos I), una materia absolutamente insatisfactoria. Otras materias del DC serían más adecuadas, pero no es posible aprovecharlas. Algoritmos II tiene 15 horas de cursada y Algoritmos III está en una crisis por el cambio de plan y todo indica que al menos por ahora es una materia sin rumbo. 

## Matices
Se han hecho algunas modificaciones en Cálculo, que han implicado el agregado de SVD, QR y Diferencias Finitas. Estos cambios, sin embargo son parciales. Por un lado, los temas de la materia son demasiados y es necesario recortarlos por algún lado. Al no ser temas tradicionales (y no estar en el apunte), SVD y QR tienden a verse de manera reducida o relegarse a la práctica. Diferencias Finitas sí se da, principalmente porque facilita el armado de un ejercicio de parcial, pero el tema queda demasiado comprimido y es difícil que sea algo más que un enlatado con poca profundidad y sobre todo con poca comprensión de los detalles.

Cambiar la materia no es tan sencillo porque, como decíamos, los temas son muchos y en la práctica ya exceden lo que razonablemente puede darse en un cuatrimestre. Es decir: nos gustaría _agregar_ temas, pero a la vez es necesario _sacar_ temas, sólo para que el plan actual funcione. Los temas actuales son, además, los temas básicos de cualquier libro de introducción al Análisis Numérico. Por lo tanto, tampoco son tan fáciles de descartar.

Es importante remarcar que buena parte de la inercia de la materia está dada por las difultades para evaluar: probar el mal condicionamiento de una matriz buscando una singular cercana y aplicando equivalencia de normas, probar convergencia de un método iterativo, probar que una forma bilineal es un producto interno y a partir de él hallar una base de polinomios ortogonales, etc. Son todos temas cuya inclusión en una materia de Cálculo Numérico puede ser debatible, pero que tienen un peso importante en la nuestra materia principalmente porque facilitan la confección de exámenes. Teniendo esto en cuenta, cualquier cambio que se planifique debe poner el foco en las prácticas, en el formato de evaluación y en el tipo de ejercicios que podrían ir a los parciales.

## Propuestas

### Temas a eliminar
Las observaciones anteriores conducen a proponer no sólo un cambio de temas, sino una modificación general en el enfoque de la materia. Sin embargo, dado que el tiempo es una variable central para el desarrollo racional de la materia, comienzo resaltando los temas que podrían eliminarse. 

+ Distintas normas. Si bien trabajar con distintas normas matriciales tiene sentido es algo que demanda bastante tiempo y que finalmente no se explota dentro del contexto de la materia. Es sólo un tema que se da y se puede evaluar, pero en la práctica luce como alejado de los algoritmos y las aplicaciones concretas. Es más razonable limitar Cálculo al trabajo con norma 2 y postergar el tratamiento de otras normas a Análisis Numérico. Por un lado, en AN los estudiantes tienen más madurez y pueden incorporar algunas sutilezas mucho más rápido. Por el otro, el tipo de trabajo que se hace en AN se presta mucho más a apreciar las facilidades prácticas de trabajar con distintas normas, así como las diferencias cualitativas entre, por ejemplo, tener estimaciones en norma 2 o en norma infinito. Cabe remarcar, que en CN seguirá apareciendo la norma infinito (de funciones, en interpolación, por ejemplo). 

+ Métodos de Jacobi y Gauss-Seidel. Son métodos clásicos incluidos en casi todos los libros. Su utilidad práctica en la actualidad es reducida y aparece en el contexto de otros métodos más complejos: precondicionamiento, métodos multigrilla, etc.. Dado que estos temas no se ven en Cálculo Numérico, Jacobi, Gauss-Seidel e incluso SOR (si se ve) quedan expuestos simplemente como métodos alternativos para resolver sistemas cuadrados, cosa que no resulta realista. En este contexto, creo que no tiene mucho sentido darlos.

+ Cholesky. Si bien se le dedica poco tiempo, contribuye a generar la idea de que la materia es una pila de temas inconexos. Lo que se da, se ve sin contexto, lo que ayuda a convertirlo en un mero nombre. Este tema es mucho más adecuado en Optimización, donde verdaderamente se resuelven sistemas con matrices simétricas definidas positivas. Además abre la puerta a otros temas más interesantes, como _Positive Factorizations_. 

+ Productos internos y ortogonalidad. Estos temas son muy relevantes y juegan un papel crucial en infinidad de aplicaciones. Sin embargo, dentro del contexto de la materia quedan expuestos de manera bastante artificial. La ortogonalidad de los polinomios de Legendre es usada para la construcción de cuadraturas gaussianas. Pero fuera de eso tanto la práctica como los exámenes se centran en la construcción de polinomios ortogonales con productos internos sin mayor sentido. Esto repite temas de Álgebra Lineal o Mate II (F) y más que resaltarla termina ocultando la relación con las aplicaciones.

+ Métodos multipaso. Lo que hoy en día se ve realmente de métodos multipaso es muy poco y muy superficial, de modo que difícilmente es aprovechado por los estudiantes. Creo que dar una idea más sólida del funcionamiento de los métodos de un paso es suficiente para un curso introductorio y que puede sacarse más provecho de otros temas (como DFT), que del agregago de métodos multipaso. 

### Temas a agregar
+ SVD y QR. Estos temas ya son formalmente parte de la materia. Pero son más bien un apéndice: métodos alternativos a LU o posibles métodos para cuadrados mínimos. La SVD tiene muchas aplicaciones y su presentación es sencilla (se puede dar todo el tema en dos clases). Además, brinda poderosas herramientas teóricas. Por ejemplo: al tener la descomposición se obtienen la norma 2 de la matriz y su número de condición en norma 2. Resultados que en la versióna actual de la materia demandan bastante desarrollo (expresiones para la norma 2 de matrices simétricas y para la norma 2 de matrices generales), se demuestran en una línea a partir de la SVD. QR es el algoritmo por defecto para sistemas rectangulares (cuadrados mínimos).

+ DFT y FFT. La transformada discreta de Fourier se inserta naturalmente en el contexto de cuadrados mínimos e interpolación, al hacer interpolación por polinomios trigonométricos. Es un ejemplo elecuente acerca de la importancia de la ortogonalidad y de cómo puede ser explotada teórica y algorítmicamente. La FFT introduce la técnica algorítmica de divide and conquer en todo su esplendor. Abre la puerta a diversas aplicaciones directas que se pueden hacer en la práctica con mínimo tiempo destinado a explicaciones: interpretación del desarrollo en frecuencias, filtrado, limpieza de ruido, compresión por selección de frecuencias.

+ Algoritmos basados en subespacios de Krylov. En lugar de Jacobi/Gauss-Seidel, pueden darse métodos más modernos que realmente sean utilizados en software para la resolución de sistemas. Estos temas pueden incluir todos o alguno de los siguientes: Gradiente Conjugado, GMRES, Lanczos (para autovalores). Nuevamente tenemos algoritmos que muestran cómo explotar la ortogonalidad, sin necesidad de repetir cuentas de ortogonalización o producto interno vistas en Álgebra Lineal.

### Programa

Podríamos pensar en 5 grandes tópicos, que se desarrollarían en 6 guías prácticas (desdoblando en dos la parte de Álgebra Lineal). Marco con un asterísco temas que podrían excluirse directamente del programa, en el caso de que resulte demasiado extenso (lo más probable).

Además, la profundidad de los temas es regulable. Por ejemplo: respecto de Fourier podríamos hacer: una clase para introducir la idea de interpolación trigonométrica, plantear el sistema a resolver, señalar las propiedades de ortogonalidad del problema. Una segunda clase para explicar cómo interpretar los resultados obtenidos y desarrollar el algoritmo FFT. Si hiciera falta, en media clase más se puede probar la complejidad de la FFT. La práctica acompañaría implementando un algoritmo naif,  luego una versión simple de la FFT y finalmente usando la FFT en aplicaciones. El tema admite infinitos caminos para la profundización, pero no hace falta seguirlos. Basta con presentar el tema y usarlo en el contexto de los problemas que naturalmente trata la materia. 

El orden de los temas no tiene por qué respetarse. Por ejemplo: Fourier puede insertarse en el medio de la Parte I, como caso particular de cuadrados mínimos (separando las dos partes de Álgebra Lineal). Las partes IV y V podrían darse al principio, de modo de asegurar su desarrollo. De hecho, comenzar por Ecuaciones Ordinarias tiene una ventaja desde el punto de vista computacional: los algoritmos de un paso (Euler), son buenos ejemplos para introducir rudimentos de programación. Sólo requieren definir una función y un ciclo (for). También ayudan a ir incorporando nociones elementales para la aplicación numérica de métodos iterativos (tolerancias, por ejemplo.).

#### Parte I: Álgebra Lineal Numérica
La idea es seguir con bastante fidelidad el libro de Trefethen. Allí, el primer capítulo (titulado _Fundamentals_) es sobre SVD y el segundo sobre QR con aplicación a cuadrados mínimos. El tercer capítulo habla de condicionamiento. El enfoque es mucho más amplio que el condicionamiento de matrices y se relaciona con la propagación de errores. Además, facilita la distinción entre el mal condicionamiento intrínseco de un problema y la inestabilidad de un algoritmo. Creo que ese encuadre es más apropiado y da ideas más profundas que el del simple condicionamiento de matrices, que queda reducido a un caso particular. En ese mismo capítulo se introducen los rudimentos de la representación de punto flotante (dado que será una fuente ineludible de error en todo método computacional). Luego, en un capítulo breve, se desarrollan LU y Cholesky. El capítulo quinto da algoritmos para cálculo de autovalores (potencia y algoritmo QR) y el sexto desarrolla métodos iterativos basados en la iteración de Arnoldi (GMRES y Lanczos). Nuestra materia debería hacer una selección de estos temas y graduar la profundidad con la que se desarrollan. Yo sugeriría:

+ SVD
+ QR - Cuadrados Mínimos.
+ Condicionamiento. Esto se podría dar como tema específico, con algunos ejercicios dedicados, pero podría retomarse en varios puntos del resto de la materia. Aquí se incluiría también punto flotante. Ejemplos de los efectos del sistema de punto flotante pueden también distribuirse en las prácticas subsiguientes (e.g.: la inexactitud de la derivación numérica usando pasos demasiado pequeños).
+ LU - Sistemas cuadrados.
+ GMRES.
+ Lanczos (*)

#### Parte II: Aplicaciones del Álgebra Lineal Numérica
+ Interpolación e interpolación a trozos.
+ Derivación numérica (diferencias finitas), interpretado como derivación de un polinomio interpolador. Esto puede desarrollarse un poco, hasta resolver problemas con valores de contorno (u''=f), o no. También puede reemplazarse por completo por una clase introduciendo el método forward de diferenciación automática (números duales), con aplicación posterior por ejemplo en el método de Newton.  
+ Integración numérica. Integración gaussiana (Gauss-Legendre).

#### Parte III: Transformada de Fourier
+ Se introduce como ejemplo especial de interpolación/cuadrados mínimos.
+ Interpretación (detección de notas musicales, por ejemplo), compresión, filtrado.

#### Parte IV: Ecuaciones Ordinarias
+ Métodos de un paso. Método de Euler y métodos de Runge-Kutta. Idea de adaptavidad (por uso de dos RK anidados).
+ Uso de un solver. Resolución de sistemas.
+ Eventos.
+ Métodos implícitos.

#### Parte V: Ecuaciones no lineales
+ Métodos de Bisección y Newton, introducidos a partir de las ecuaciones no lineales que aparecen en los métodos implícitos. El objetivo central es comparar el funcionamiento de métodos explícitos vs métodos implícitos sobre ecuaciones _stiff_.
+ Métodos de punto fijo (*).


#### Prácticas

Como señalé más arriba, la confección de las prácticas es la tarea principal para lograr un cambio satisfactorio. Las prácticas deben presentar situaciones interesantes en donde los temas aparezcan de manera significativa. De este modo, deben darle a los auxiliares el elementos para el armado de exámenes y tps (o el método de evaluación que se elija). Será una tarea difícil. Pero además, creo que es fundamental que los temas aparezcan de manera recurrente, y se ilumen unos a otros siempre que se pueda. Por ejemplo: incluir algún ejercicio en el que se ilustre el efecto de la aritmética de punto flotante en todas las guías que se pueda, incluir ejercicios para estimar el condicionamiento de un problema siempre que se pueda, utilizar Newton como instrumento para hacer funcionar métodos implícitos, etc. Esto es importante para romper la sensación de que la materia está formada por una larguísima secuencia de temas aislados. 


# Clase 1 (Figus, sin funciones)

Escribir una rutira en la que:
- Se genere una variable `album`, que sea una lista de 6 casilleros, en principio rellena de ceros
- Se defina un ciclo que repita el mismo _procedimiento_ hasta que el album se llene (todos los casilleros tengan un 1).
- El _procedimiento_ debe consistir en:
  - generar una variable `dado` que reciba un número aleatorio entre 0 y 5.
  - poner un 1 en el casillero `dado` del album
- Además, debe haber un contador `i` que cada vez que se tire el `dado` aumente en 1.

### Tests:
- Verificar que exista la variable `album` y que su longitud sea 6.
- Verificar que la suma de album de 6.
- Verificar que exista la variable `dado` y que contenga un índice válido, entre 0 y 5. (Correr varias veces).
- Verificar que exsta la variable `i` y que contanga un número entre 6 y 70. (Correr varias veces).

# Clase 2 (Figus de verdad)

1. Implementar la función `cuantas_figus(figus_total)` que reciba la cantidad total de figuritas de un álbum (`figus_total`), realice la simulación de llenado y devuelva la cantidad de figuritas que fue necesario comprar para llenar el álbum. Se asume que las figuritas se compran de a una. Escribir un ciclo controlado por un contador `j` en el que la función se corra 1000 veces para un álbum de 6 figuritas y se calcule el promedio de figuritas necesarias para llenar el álbum en esas 1000 pruebas. Este promedio debe almacenarse en una variable de nombre `promedio`.

### Tests:
- Verificar que `promedio` esté entre 14 y 16.
- Verificar que la variable `j` valga 1000.

2. (_Este incluye una variante del anterior que se aparta un poco de la consigna, pero es más completo. Eventualmente se puede fraccionar en tres entregas_).
Implementar las siguientes funciones:
 - `cuantas_figus(album)`: debe recibir una lista `album` y simular el llenado, asumiendo que se compran figuritas de a una. Debe devolver la cantidad de figuritas que fue necesario comprar.
 - `limpiar_album(album)`: debe recibir una lista `album` y llenarla de ceros (reiniciar el álbum.
 - `promedio(figus_total, n_albumes)`: debe recibir dos números,  crear un álbum de `figus_total` casilleros y definir un contador `cantidad` en el que se acumule la cantidad de figus compradas. Luego, realizar un ciclo de `n_albumes` pasos en el que:
   - Se limpie el album usando la función `limpiar_album`,
   - Se llene el album usando la función `cuantas_figus`
   - Se sume a `cantidad` el número de figuritas necesarias para llenar el álbum.
   Finalmente, debe devolver el promedio de figuritas necesarias para llenar un álbum (`cantidad`/`figus_total`)

### Tests:
 - Definir álbumes de 6, 10 y 150 casilleros, llenos de unos, pasarlos por `limpiar_album` y verificar que luego queden limpios.
 - Implementar una versión eficiente de `promedio`, correrla con `figus_total=6`, `n_albums=1_000_000` y verificar que el promedio de en torno a 14.7. Debería estar entre 14.6 y 14.8.
 - Repetir el ítem anterior para `figus_total = 10`. El promedio debería estar entre 29.2 y 29.4.
 - Correr la versión de `promedio` implementada por el estudiante con `figus_total=6`, `n_albums=1000` y verificar que el promedio esté entre 14 y 16.
 - Correr la versión de `promedio` implementada por el estudiante con `figus_total=10` y  `n_albums=1000` y verificar que el promedio esté entre 28 y 30.
 
# Clase 3 (Diez Mil)

1. Implementar la función `tirar_cubilete()` que no reciba parámetros y devuelva una lista de 5 casilleros con números al azar entre 1 y 6.

### Tests:
 - Correr la función tres veces  y verificar:
    - que devuelva una lista de 5 casilleros
    - que el contenido de la lista sean números de 1 a 6
    - que los resultados sean distintos

2. Implementar la función `puntos_por_unos(cubilete)` que reciba una lista de cinco dados y devuelva el puntaje que aportan los unos que aparecen en el cubilete. Las reglas son: cada 1 suma 100 puntos, pero tres unos suman 1000 y 5 unos sumann 10000. De este modo, al cubilete `[1,2,3,1,1]` le corresponden 1000 puntos, pero al cubilete `[1,1,6,1,1]` le corresponden 1100 puntos.

#### Tests
  - Verificar que la función devuelva un entero.
  - Probar la función con cubiletes con los cubiletes `[1,5,5,5,5]`, `[1,1,5,5,5]`, `[1,1,1,5,5]`, `[1,1,1,1,5]`, `[1,1,1,1,1]` y verificar que el puntaje en cada caso sea el correcto.
  - Verificar que el cubilete no haya sido modificado por la función.

3. Implementar la función `acumular_puntajes(puntos_jugada,puntos_totales)`. Se espera que los argumentos `puntos_jugada` y `puntos_totales` sean listas de la misma longitud. La función debe sumar casillero a casillero ambas listas y acumular el resulado en `puntos_totales` y no debe devolver nada. 

### Tests
  - Probar la función con `puntos_jugada = [1000,50,1150,200]`, `puntos_totales=[5500,1750,2100,3500]` y con `puntos_jugada = [150,250,300]`, `puntos_totales=[350,1100,2350]` y verificar que `puntos_totales` actualice sus valores correctamente.
  - Verificar que la función devuelva `None`.

#*COMPRENDE*

 Checkpoint de Comprensión — Responder como equipo antes de APLICA
 
**C1. Una función hash produce el valor 7 para dos claves distintas. ¿Cómo se llama ese evento? ¿Es un error de programación o algo esperado?**

      -Este evento se conoce formalmente como una Colisión Hash, y es un evento totalmente esperado y matemáticamente inevitable.
        El universo de claves posibles (por ejemplo, strings con nombres de películas infinitos) es infinitamente mayor que el número finito de casillas (buckets) 
        disponibles en la memoria física del servidor. No es una falla del programador; por ello, las estructuras de datos implementan técnicas
        como el encadenamiento o el direccionamiento abierto para manejar estos empates sin perder información.

**C2. El dict tiene 10 000 elementos y 15 000 buckets. ¿Cuál es el factor de carga? ¿Está en zona segura de rendimiento?**

      -El Factor de Carga (a) se calcula dividiendo la cantidad de elementos almacenados entre el número total de casillas (buckets) disponibles.
      a=elementos/buckets = 10,000/15,000=0.66     está en una zona de rendimiento excelente

**C3. ¿Por qué d["MX-999"] puede romper el programa pero d.get("MX-999") no? ¿En qué situación preferirías el primero?**

      -La diferencia esta en el control de excepciones ante claves inexistentes:
       d["MX-999"]: Si la clave no existe en el diccionario, Python frena la ejecución del hilo y lanza un error crítico de tipo KeyError,
       rompiendo el flujo del programa si no se encuentra dentro de un bloque try-except.
           d.get("MX-999"): Es un método seguro. Si la clave no existe, no rompe el código; simplemente intercepta la ausencia y retorna un valor por defecto
       Se prefiere cuando la ausencia de la clave representa una anomalía grave del sistema o un error de consistencia de datos en la base de datos de StreamMX


**C4. La Ing. Sofía pide "mostrar el top 5 de películas mejor evaluadas". ¿Puede el dict dar eso eficientemente? Justifiquen con complejidad.**

      -No, el diccionario tradicional o dict no puede resolver este requerimiento de forma eficiente por sí solo.
      Esto degrada la complejidad de un excelente $\mathcal{O}(1)$ a un costo de $\mathcal{O}(n \log n)$ (donde $n$ es el tamaño total del catálogo)



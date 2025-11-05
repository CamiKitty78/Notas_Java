# Notas_Java: Aplicando la Orientación a Objetos

# Resumen de Pasos Java #2

##### **1. Clases y objetos (Programación Orientada a Objetos - POO)**

Aprendimos a definir clases en Java que representan entidades del mundo real, como **Titulo** o **Serie**.

Cada clase tiene **atributos** (variables que guardan datos) y métodos (acciones o comportamientos).

* Ejemplo:

      public class Serie extends Titulo {
        private int temporadas;
        private boolean activa;
          }
  
Aquí **Serie** hereda de **Titulo**, lo que demuestra el uso de **herencia**.

##### **2. Herencia**

**Serie** extiende la clase **Titulo**, lo que significa que hereda sus atributos y métodos.

 Esto evita duplicar código y permite que una serie sea un tipo especial de título.

  * Aprendiste a usar **extends** para establecer esta relación.
* Ejemplo:

        public class Serie extends Titulo { ... }

##### **3. Interfaces**

**Clasificable.java** define una interfaz, que es un contrato que obliga a las clases que la implementan a definir ciertos métodos.

Esto fomenta el **polimorfismo** y la **flexibilidad del código.**

* Ejemplo:

      public interface Clasificable {
        int getClasificacion();
        }
  
Cualquier clase que implemente **Clasificable** debe definir cómo calcular su clasificación.

##### **4. Polimorfismo y uso de interfaces**

La clase **FiltroRecomendaciones.java** muestra cómo aplicar **polimorfismo:**
puede recibir objetos de distintos tipos (por ejemplo, **Serie**, **Pelicula**, etc.) siempre que implementen la interfaz **Clasificable**.

* Ejemplo:

          public void filtra(Clasificable clasificable) {
          int clasificacion = clasificable.getClasificacion();
          }

Así, el método puede funcionar con diferentes clases sin necesidad de saber exactamente cuál es.

##### **5. Encapsulamiento**

En las clases (**Titulo**, **Serie**), los atributos están **privados** (**private**) y se accede a ellos mediante **getters** y **setters**.

Esto protege los datos y controla cómo se modifican.

* Ejemplo:

        private String nombre;
          public String getNombre() {
            return nombre;
          }

        public void setNombre(String nombre) {
          this.nombre = nombre;
            }

##### **6. Métodos y cálculos**

En **CalculadoraDeTiempo.java**, aprendiste a crear métodos que realizan **operaciones con objetos** y **acumulan resultados**.

Por ejemplo, sumar la duración total de una lista de títulos.

* Conceptos clave:
  
 
*  	Uso de **parámetros en métodos**.
*  	Uso de **atributos acumuladores**.

* Ejemplo:

      public void incluye(Titulo titulo) {
      tiempoTotal += titulo.getDuracionEnMinutos();
      }

##### **7. Uso de condiciones y lógica**

En **FiltroRecomendaciones.java**, también se aplican estructuras condicionales (**if** / **else**) para tomar decisiones según la clasificación.

Esto enseña **control de flujo** y **evaluación de condiciones** en Java.

## **Resumen de pasos - RadioAlura**

###### **1. Clases y objetos (Programación Orientada a Objetos - POO)**

En esta aplicación creamos clases que representan distintos tipos de audios: canciones y podcasts.

Cada clase tiene **atributos (información)** y **métodos** (acciones).

* Ejemplo:

      public class Audio {
      private String titulo;
      private int totalDeReproducciones;
      private int totalDeMeGusta;
      }

Aquí, **Audio** es una clase base que sirve como modelo para los demás tipos de contenido.

**Concepto aprendido:** cómo definir clases con atributos privados y métodos públicos (encapsulamiento).

###### **2. Herencia**
  
Las clases **Cancion** y **Podcast** heredan de la clase base **Audio**.

Esto significa que comparten sus atributos y comportamientos, pero también pueden tener sus propias características

* Ejemplo:

        public class Cancion extends Audio { ... }
        public class Podcast extends Audio { ... }

Esto evita duplicar código y permite reutilizar comportamientos comunes (como **reproducir()** y **meGusta()**).

###### **3. Encapsulamiento**

Todos los atributos se declaran privados y se acceden mediante **getters** y **setters**.
De esta manera, se protege la información interna de cada clase.

* Ejemplo:

        private String titulo;
        public String getTitulo() {
        return titulo;
        }
        public void setTitulo(String titulo) {
        this.titulo = titulo;
        }

**Concepto aprendido:** proteger los datos y controlar cómo se modifican los atributos.

###### **4. Polimorfismo y métodos sobrescritos**

Las clases hijas (**Cancion** y **Podcast**) sobrescriben el método **getClasificacion()** de la clase **Audio**.

Cada una define su propia forma de calcular la clasificación según sus datos.

* Ejemplo:

      @override
      public int getClasificacion() {
       if (getTotalDeMeGusta() > 500){
      return 8;} else {
       return 4;}
      }

**Concepto aprendido:** El polimorfismo permite que diferentes clases respondan de forma distinta al mismo método (**getClasificacion()**).

###### **5. Uso de condiciones y lógica**

Dentro de los métodos sobrescritos y en otras clases, se usan estructuras if / else para tomar decisiones.

Por ejemplo, determinar si un audio es muy popular o solo “uno de los favoritos”.

* Ejemplo:

      if (audio.getClasificacion() >= 8) {
        System.out.println(audio.getTitulo() + " es uno de los favoritos del momento");
      } else {
        System.out.println(audio.getTitulo() + " también es uno de los favoritos");
      }

**Concepto aprendido:** control de flujo y toma de decisiones en Java.

###### **6. Clases auxiliares y métodos con parámetros**

La clase **MisFavoritos** recibe objetos de tipo Audio y decide si son populares.

Esto demuestra el uso de **parámetros** en métodos y la posibilidad de trabajar con **diferentes tipos de objetos** que comparten la misma clase base.

* Ejemplo:

      public void adiciona(Audio audio) {
      }

**Concepto aprendido:** cómo pasar objetos como parámetros y aplicar lógica común a distintas clases hijas.

###### **7. Clase Principal y simulación**

En Principal.java se crean y manipulan objetos de las clases Cancion y Podcast.
Se simulan reproducciones, “me gusta” y se muestran resultados en consola.

⦁	Ejemplo:

        Cancion miCancion = new Cancion();
        miCancion.setTitulo("Forever");
        miCancion.setArtista("Kiss");

        Podcast miPodcast = new Podcast();
        miPodcast.setTitulo("Cafe.Tech");
        miPodcast.setPresentador("Gabriela Aguiar");

**Concepto aprendido:** cómo crear objetos, llamar métodos y simular el comportamiento de una aplicación real.

###### **8. Conclusión general**

Este ejercicio permitió practicar los **principios fundamentales de la POO en Java:**

⦁	**Clases y objetos:** modelar entidades reales.
⦁	**Herencia:** compartir código entre clases relacionadas.
⦁	**Encapsulamiento:** proteger los datos internos.
⦁	**Polimorfismo:** permitir distintos comportamientos con un mismo método.
⦁	**Condicionales y métodos:** controlar la lógica del programa.



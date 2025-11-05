# Notas_Java: Creando tu primera aplicación
Notas de Resumenes de lo aprendido en cada curso de Back-End en Java 

# Resumen Programas Java Curso #1

### **1. Main.java**

Explicación paso a paso:

       public class Main {
       public static void main(String\[] args) {

               System.out.println("Bienvenido(a) a Screen Match");
               System.out.println("Película: Matrix");
       }

Muestra mensaje en consola
**System.out.println()** sirve para imprimir texto.
      
      int fechaDeLanzamiento = 1999;
      boolean incluidoEnElPlan = true;
      double notaDeLaPelicula = 8.2

Declara variables con diferentes tipos de datos:

**int:** números enteros.
**boolean:** verdadero/falso.
**double:** números decimales.

      double media = (8.2 + 6.0 + 9.0) / 3;
      System.out.println(media);

Calcula el **promedio** de tres notas y lo muestra.

      String sinopsis = """
             Matrix es una paradoj*
              La mejor película del fin del milenio
              Fue lanzada en:
              """ + fechaDeLanzamiento;
      System.out.println(sinopsis);
      
Usa un **text block** (""" ... """) para escribir texto en varias líneas.
Luego concatena (+) la variable **fechaDeLanzamiento.**

      int clasificacion = (int) (media / 2);
      System.out.println(clasificacion);

Convierte el resultado decimal de media / 2 a un entero con **(int).**

**Resumen:**

* Imprime mensajes.
* Declara variables.
* Calcula promedio.
* Muestra texto en bloque.
* Hace una conversión de tipo.

### **2. Lectura.java**

**Función:** Permite al usuario escribir datos desde el teclado.
**Explicación:**
           
      Scanner teclado = new Scanner(System.in);

Crea un objeto **Scanner** para leer texto ingresado por el usuario.

      System.out.println("Escribe el nombre de tu pelicula favorita");
      String pelicula = teclado.nextLine();

Lee una cadena de texto (nombre de la película).

      System.out.println("Escribe la fecha de lanzamiento");
      int fechaDeLanzamiento = teclado.nextInt();

Lee un número entero.

      System.out.println("Por último dinos que nota le das a esta pelicula");
      double nota = teclado.nextDouble();

Lee un número decimal.

      System.out.println(pelicula);
      System.out.println(fechaDeLanzamiento);
      System.out.println(nota);

Muestra los valores que el usuario escribió.

**Resumen:**

* Usa **Scanner** para recibir entradas del usuario.
* Lee y muestra texto, números enteros y decimales.

### **3. Decisiones.java**

**Función:** Demuestra cómo usar condiciones **if** y operadores lógicos.
**Explicación:** 

      int fechaDeLanzamiento = 1999;
      boolean incluidoEnElPlan = true;
      double notaDeLaPelicula = 8.2;
      String tipoPlan = "plus";

Variables base para tomar decisiones.

      if (fechaDeLanzamiento >= 2022) {
          System.out.println("Peliculas más populares");
      } else {
          System.out.println("Peliculas Retro que aún valen la pena ver");
      }
      
Condicional simple:

Si la película es reciente (>=2022), muestra “populares”.
Si no, muestra “retro”.
   
      if (incluidoEnElPlan \&\& tipoPlan.equals("plus")) {
    System.out.println("Disfrute de su pelicula");
      } else {
    System.out.println("Pelicula no disponible para su plan actual");
      }

Condición doble:

* Usa **\&\&** (AND lógico).
* Usa **.equals()** para comparar cadenas de texto.
                  Solo si ambas condiciones se cumplen, puede ver la película.

**Resumen:**

* Usa **if / else** para decisiones.
* Practica operadores lógicos **(\&\&)** y comparación de texto **(equals)**.

### **4. Loops.java**

**Función:** Calcula el promedio de notas usando un bucle **for**.
**Explicación:**

      Scanner teclado = new Scanner(System.in);
      double nota = 0;
      double mediaEvaluaciones = 0;

Se prepara para leer tres notas del usuario.

      for (int i = 0; i < 3; i++) {
          System.out.println("Escribe la nota que le darías a la película Matrix");
          nota = teclado.nextDouble();*
          mediaEvaluaciones = mediaEvaluaciones + nota;
          }

El ciclo **for** se repite 3 veces.

Cada vez:

1. Pide una nota.
2. La suma a la variable **mediaEvaluaciones.**

            System.out.println("La Media de evaluaciones para Matrix es:" + mediaEvaluaciones / 3);

Al terminar, calcula y muestra el promedio.

**Resumen:**

* Usa **for** para repetir acciones un número fijo de veces.
* Suma valores y calcula promedios

### **5.Evaluaciones.java**

**Función:** Hace lo mismo que **Loops.java**, pero usando **while**.
**Explicación:** 

      Scanner teclado = new Scanner(System.in);
      double nota = 0;
      double mediaEvaluaciones = 0;
      double totlEvaluaciones = 0;

Variables para leer notas y calcular promedio.

      while (nota != -1) {
            System.out.println("Escribe la nota que le darías a la película Matrix");
          nota = teclado.nextDouble();

El ciclo **continúa mientras la nota no sea -1**.

El -1 sirve para **salir del bucle.**

      if (nota != -1){
            mediaEvaluaciones += nota;
            totlEvaluaciones++;
      *}*

Si no es -1, suma la nota y cuenta una evaluación más.

      System.out.println("La Media de evaluaciones para Matrix es:" + mediaEvaluaciones / totlEvaluaciones);

Calcula y muestra el promedio actual.

**Resumen:**

* Usa **while** para repetir indefinidamente hasta que el usuario escriba -1.
* Acumula notas y calcula promedio dinámico.

## **Desafio.java**

**Función:**

Simula un **cajero automático** o sistema bancario básico, donde le usuario puede consultar su saldo, retirar o depositar dinero, hasta que decida salir.

**Explicación paso a paso:** 

      import java.util.Scanner;

Importa la clase **Scanner**, necesaria para leer datos que el usuario escriba en la consola.

      public class Desafio {
                static void main() {

Declara la clase principal llamada Desafio y un método **main()** donde se ejecuta todo el programa.

**Variables iniciales:**

      String nombre = "Cami Barrera";
      String tipoDeCuenta = "Corriente";
      double saldo = 1599.99;
      int opcion = 0;

Define variables básicas:

* **nombre:** nombre del cliente.
* **tipoDeCuenta**: tipo de cuenta bancaria.
* **saldo:** dinero disponible.
* **opcion:** almacena la opción elegida por el usuario.

Mostrar información inicial:

      System.out.println("\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*");
      System.out.println("\\nNombre del Cliente: " + nombre);
      System.out.println("Tipo de Cuenta: " + tipoDeCuenta);
      System.out.println("Saldo Disponible: " + saldo + "$");
      System.out.println("\\n\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*");

Imprime los datos del cliente y el saldo en pantalla, con formato visual.

**Menú interactivo:**

              \*\*\* Escriba el número de la opción deseada \*\*\*
              1 - Consultar saldo
              2 - Retirar
              3 - Depositar
              9 - Salir
              """;

 Usa un bloque de texto **(""" ... """)** para crear el menú de opciones con un formato bonito.

Bucle principal del programa:

      Scanner teclado = new Scanner(System.in);
      while (opcion != 9) {
            System.out.println(menu);
            opcion = teclado.nextInt();

Se crea un objeto **Scanner** para leer datos.
El bucle **while** se repite hasta que el usuario elija la opción 9 (salir).
En cada ciclo, se muestra el menú y se espera una opción numérica.

Estructura **switch**:

Aquí el programa elige qué hacer según el número introducido:

      switch (opcion) {

Evalúa el valor de **opcion** y ejecuta el bloque correspondiente.
         
**Opción 1 – Consultar saldo**

      case 1:
              System.out.println("El saldo actualizado es:" + saldo + "$");
          break;
             
Muestra el saldo actual del cliente.
**break** detiene el bloque del **switch**.

**Opción 2 – Retirar dinero**

    case 2:
          System.out.println("¿Cuál es el valor que desea retirar?");
             double valorAlRetirar = teclado.nextDouble();
             if (valorAlRetirar > saldo){
                     System.out.println("Saldo Insuficiente");
                } else {
                       saldo = saldo - valorAlRetirar;
                        System.out.println("Saldo Actualizado es:" + saldo + "$");
                      }
                     break;

Pide la cantidad a retirar.
Si el valor supera el saldo, muestra “Saldo insuficiente”.
Si hay suficiente dinero, resta el valor al saldo actual.

**Opción 3- Depositar dinero**

       case 3:
              System.out.println("Valor a depositar");
              double valorDepositar = teclado.nextDouble();
              saldo += valorDepositar;
              System.out.println("Saldo Actualizado es:" + saldo + "$");
              break;

Solicita la cantidad a depositar.
Suma el valor al saldo y muestra el nuevo total.

**Opción 9- Salir**

       case 9:
               System.out.println("Saliendo del programa, gracias por utilizar nuestros servicios");
               break;

Finaliza el programa mostrando un mensaje de despedida.

**Cualquier otro número**

       default:
               System.out.println("Opción no válida");

Si el usuario escribe un número que no está en el menú, el programa avisa que la opción es incorrecta.



       








      
      


      

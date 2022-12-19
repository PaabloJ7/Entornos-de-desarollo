## HERRAMIENTAS DE DESAROLLO



#### 1.Ejecuta el programa "Hola mundo" en los siguientes lenguajes:

- Bash

  ```bash
  #!/usr/bin/env bash
  
  echo "Hola mundo"
  ```

  

- Javascript (nodejs)

  ```javascript
  #!/usr/bin/env node
  
  console.log('Hola mundo');
  ```

  

- Python

  ```python
  #!/usr/bin/env python
  
  print "Hola Mundo"
  ```

  

- C

  ```c
  #include <stdio.h>
  
  int main()
  {
      printf("¡Hola, mundo!");
      return 0;
  }
  ```

  

  

- Java

  ```java
  class Hola
  {
      public static void main(String[] args)
      {
          System.out.println("Hola Mundo");
      }
  }
  ```

  

- Ensamblador (nasm)

```assembly
section .data

msg     db "¡Hola Mundo!", 0Ah
len     equ     $ - msg  

section .text

global _start

_start:
        mov     eax, 04h
        mov     ebx, 01h
        mov     ecx, msg
        mov     edx, len
        int     80h
        mov     eax, 01h
        mov     ebx, 00h
        int     80h
```



#### 2.Para cada uno de los lenguajes anteriores, indica el proceso realizado para conseguir ejecutar el código: ¿compilación o interpretación?

- bash = Interpretado
- python = Interpretado
- javascript (nodejs) = Compilado
- C = Compilado
- java = Compilado
- ensamblador (nasm) = Compilado



#### 4.Investiga y averigua que extensión tienen los archivos de código fuente de los siguientes lenguajes:

- bash = .sh

- python = .py

- javascript = .js

- C = .c

- java = .java

- ensamblador (nasm) = .asm

  

#### 5.Scripts ejecutables para los lenguajes interpretados. Edita los scripts para los siguientes lenguaje

- Bash - ./hola.sh

  ```bash
  #!/usr/bin/env bash
  
  echo "Hola mundo"
  ```

  

- Javascript (nodejs) ./hola.js

  ```javascript
  #!/usr/bin/env node
  
  console.log('Hola mundo');
  ```

  

- Python ./hola.py

  ```python
  #!/usr/bin/env python
  
  print "Hola Mundo"
  ```

  

- C ./hola    

  ```c
  #include <stdio.h>
  
  int main()
  {
      printf("¡Hola, mundo!");
      return 0;
  }
  ```

  

  

- Java   java  Hola  

  ```java
  class Hola
  {
      public static void main(String[] args)
      {
          System.out.println("Hola Mundo");
      }
  }
  ```

  

- Ensamblador (nasm)  ./hola  

```assembly
section .data

msg     db "¡Hola Mundo!", 0Ah
len     equ     $ - msg  

section .text

global _start

_start:
        mov     eax, 04h
        mov     ebx, 01h
        mov     ecx, msg
        mov     edx, len
        int     80h
        mov     eax, 01h
        mov     ebx, 00h
        int     80h
```



#### 6. ¿Qué extensión tienen los archivos de código objeto?

La extensión es `.obj`



#### 7. Lenguaje C. Código en varios archivos. Obtener el código objeto a partir del código fuente de los 3 archivos siguientes:

```c
//-------------
// datos.c
//-------------

char *mensaje="Hola a todos y todas";
int  num1 = 8;
int  num2 = 10;
//-------------
// suma.c
//-------------

int suma (int a, int b) {
  return a + b;
}
//-------------
// main.c
//-------------

#include <stdio.h>

int suma (int a, int b);

extern char *mensaje;
extern int  num1, num2;

int main(){
  printf("%s\n", mensaje);
  printf("%d\n", suma (num1, num2) );
  return 0;
}
```

#### 8. Lenguaje C. Código en varios archivos. Obtener el código binario ejecutable a partir del código objeto de los 3 archivos anteriores:

```c
gcc  -o  programa  main.o  datos.o  suma.o
```

#### 11. Bibliotecas. Define que se entiende por biblioteca o librería y los tipos que existen.

Las librerías de programación son conjuntos de archivos de código que se utilizan para desarrollar software. Su objetivo es facilitar la programación, al proporcionar funcionalidades comunes, que ya han sido resueltas previamente por otros programadores.

Existen librerías estáticas y librerías dinámicas.

#### 12. Bibliotecas. ¿Qué tipo es el más utilizado actualmente? ¿Por qué?

Las mas usadas son las librerias dinámicas.



#### 13. Bibliotecas. Crea una biblioteca dinámica en C que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente.

```c
int suma (int sumando1, int sumando2);

int resta  (int minuendo, int sustraendo);

int multiplicacion (int  numero1, int numero2);

float division (int dividendo, int divisor);
```

#### 14. Bibliotecas. Crea una biblioteca dinámica en Java que proporcione las funciones para sumar, restar, multiplicar y dividir 2 números enteros. Crea un programa que haga uso de ella y comprueba que se ejecuta correctamente.

```java
int suma (int sumando1, int sumando2) {
	return (sumando1+sumando2);
}


int resta  (int minuendo, int sustraendo) {
	return (minuendo-sustraendo);
}


int multiplicacion (int  numero1, int numero2) {
	return (numero1*numero2);
}


float division (int dividendo, int divisor) {
	return (dividendo/(float)divisor);
}
```

#### 15. Bibliotecas. Busca información y explica las ventajas y desventajas de usar bibliotecas estáticas.

Ventajas:

1. No es necesario proporcionar las bibliotecas correspondientes al publicar el programa.

2. Biblioteca de carga rápida

Desventajas:

1. La biblioteca está empaquetada en la aplicación, lo que resulta en una gran biblioteca.

2. La biblioteca ha cambiado y es necesario volver a compilar el programa.

#### 16. Bibliotecas. Busca información y explica las ventajas y desventajas de usar bibliotecas dinámicas.

**Ventajas**

1) Ahorre más memoria y reduzca el intercambio de páginas;
2) El archivo so es independiente del archivo EXE, siempre que la interfaz de salida permanezca igual (es decir, el nombre, los parámetros, el tipo de valor de retorno y la convención de llamada no cambien), reemplazar el archivo so no causará el archivo EXE Cualquier impacto, mejorando así la capacidad de mantenimiento y la escalabilidad;
3) Los programas escritos en diferentes lenguajes de programación pueden llamar a la misma para que funcionen siempre que sigan la convención de llamada de función;
4) Es adecuado para el desarrollo de software a gran escala, lo que hace que el proceso de desarrollo sea independiente y menos acoplado, lo que es conveniente para el desarrollo y las pruebas entre diferentes desarrolladores y organizaciones de desarrollo.

**Desventajas**

1) El archivo ejecutable generado por el enlace estático es de gran tamaño y contiene el mismo código común, lo que causa desperdicio;
2) La aplicación que usa la biblioteca de enlaces dinámicos no es autónoma, y el módulo del que depende también debe existir. Si usa enlaces dinámicos al cargar, la DLL no existe cuando se inicia el programa. El sistema terminará el programa y dará un mensaje de error. Con el enlace dinámico en tiempo de ejecución, el sistema no terminará, pero debido a que la función exportada no está disponible, el programa no se cargará; la velocidad es más lenta que el enlace estático. Después de actualizar un determinado módulo, si el nuevo módulo no es compatible con el módulo anterior, se arrancará todo el software que necesita el módulo para ejecutarse.



#### 17. Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo ejecutable para código fuente en C con make. Haz uso de un buildfile.

#### 18. Build. Automatiza el proceso de compilación de ejecutable y biblioteca, su enlazado y la generación del archivo .jar para código fuente en Java con Ant. Haz uso de un buildfile.

#### 

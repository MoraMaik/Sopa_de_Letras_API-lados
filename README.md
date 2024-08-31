# Sopa de Letras | API-lados

API-lados es un grupo conformado por dos ingenieros civiles y un ingeniero químico que busca presentar el desarrollo y la solución de su Proyecto Final de la materia Programación de Computadores. El objetivo es explicar el programa trabajado durante el semestre 2024-1, el cual, a grandes rasgos, está inspirado en crear una aplicación que emule una **sopa de letras**, utilizando *Python*.

<p align="center">
  <a href="https://postimg.cc/rdT79scf">
    <img src="https://i.postimg.cc/W4qjTqyc/Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg" alt="Whats-App-Image-2024-02-28-at-9-47-06-AM.jpg">
  </a>
</p>
_______________________
1. Estructura del repositorio

sopa_de_letras/


│   ├── 01_introduccion

│   ├── 02_instalacion     Sigue estos pasos para instalar y ejecutar el proyecto.   (MICHAEL)

│   ├── 03_estructura         (CAROLINA)

│   ├── 04_funcionalidades           (ALEJANDRO)

│   ├── 05_ejemplos (video)    (MICHAEL)



2. Detalles archivos y carpetas
   
Título del proyecto
Descripción breve
Características principales
Guía de instalación rápida
Ejemplo de uso
Enlaces a documentación detallada

_______________________
# Introducción

## Sopa de Letras en Python

Este proyecto es una implementación de una Sopa de Letras en Python, creada como parte del curso de programacion de computadores dirigido por el Ingeniero Felipe Gonzales. La Sopa de Letras es un juego clásico en el que se deben encontrar palabras ocultas en una cuadrícula de letras. El objetivo principal de este proyecto es reforzar conceptos de programación aprendidos durante el curso, estructuras de datos, y algoritmos, de una manera interactiva.

## Objetivos del Proyecto

- **Código original**: programa elaborado por el grupo API_lados
- **Uso de herramientas vistas en el curso** 
- **Mejora de Habilidades**: Desarrollar habilidades en el uso de estructuras de datos, manejo de matrices y algoritmos de búsqueda.


## Funcionalidades del Programa

El programa de Sopa de Letras cuenta con las siguientes funcionalidades:

- **Generación Automática**: Crea sopas de letras de
- **Tamaño de la sopa de letras**: Matriz del tamaño de la sopa de letras (Min: 10x10, Max: 20x20), esta relacionado a la dificultad.
- **Ingreso de las palabras**: Lista de coordenadas, Strings.
- **Nivel de dificultad**: Asociado a cantidad de palabras, verticales, horizontales, diagonal. 3 niveles (Facil, Medio, dificil)

*Caracteristicas extra*:
  
- **Cuenta regresiva**
- **Sombreado o cambio visual de las palabras encontradas**
- **Interfaz grafica con estructura**
 
_______________________

# Instalacion

Sigue estos pasos para instalar y ejecutar el proyecto

## **Requisitos**
Antes de comenzar, asegúrate de tener instalado lo siguiente:

+ Python 3.8+: La última versión de Python puede descargarse desde python.org o Microsoft Store.
+ pip: El gestor de paquetes de Python, que generalmente se incluye con Python 3.8+.
+ pygame: Biblioteca para crear aplicaciones multimedia en Python

## **Instrucciones de Instalación**

1. **Descarga el Repositorio**

Puedes descargar el repositorio como un archivo ZIP desde GitHub o clonar el repositorio en tu máquina local:


**Opción 1**: Descargar ZIP

+ Ubicate en el [Repositorio](http://https://github.com/MoraMaik/Sopa_de_Letras_API-lados "Repositorio")
  
+ Haz clic en el botón "Code" y selecciona "Download ZIP".
+ Extrae el contenido del archivo ZIP en tu máquina local.

2. **Instala las Dependencias**

Instala las dependencias necesarias (pygame, sys)  usando pip:

```code
pip install pygame
```

```code
pip install sys
```

3. Asegúrate de tener las Imágenes Necesarias

Asegúrate de tener las imágenes `house-solid.png` y `stopwatch-solid.png` en el directorio raíz del proyecto. Si no las tienes, puedes descargarlas y guardarlas en el directorio del proyecto.

## Ejecucion el Programa

Una vez instaladas las dependencias, puedes ejecutar el programa de la siguiente manera:
1. Ejecutar el Programa Principal

Corre el archivo principal del proyecto para generar y visualizar la Sopa de Letras:
```code
python src/main.py
```

2. Interacción con el Programa

Al ejecutar el programa, se abrirá una ventana con el menú principal donde podrás seleccionar el nivel de dificultad: Fácil, Medio o Difícil. Utiliza el mouse para interactuar con la interfaz y seleccionar las palabras en la sopa de letras.

**Problemas Comunes y Soluciones**
+ Error al instalar dependencias: Asegúrate de que pip está actualizado ejecutando pip install --upgrade pip.
+ Imágenes no encontradas: Verifica que las imágenes `house-solid.png` y `stopwatch-solid.png` están en el directorio raíz del proyecto y que los nombres son correctos.

Con estos pasos, deberías poder instalar y ejecutar el programa de Sopa de Letras en Python sin problemas. Si encuentras algún problema, no dudes en abrir un issue en el repositorio de GitHub.

### Nota Adicional

+ Si encuentras problemas con la instalación de Pygame en diferentes sistemas operativos, consulta la [documentación oficial de Pygame](http://https://www.pygame.org/docs/ "documentación oficial de Pygame")
 para obtener instrucciones detalladas y específicas para tu sistema operativo.

_______________________
# Estructura

El código del proyecto se encuentra organizado en distintos niveles de dificultad como se mencionó anteriormente, por lo que cada uno de estos ( fácil, medio y difícil) tiene su estructura bien definida. Para poder explicarlo detalladamente, a continuación se encuentran todos los ítems que en conjunto reflejan el cuerpo de la sopa de letras.


**1. Importaciones**

``` python
import pygame
import sys
```

Decidimos utilizar Pygame, la cual se carcateriza por ser una biblioteca que permite la realización de juegos en python, proporcionando funcionalidades como lo son gráficos y manejo de eventos.

- Inicialización:
``` python
pygame.init()
```

- Creación de la ventana:
``` python
ventana = pygame.display.set_mode((ANCHO, ALTO))
pygame.display.set_caption("Sopa de letras")
```

- Carga de imágenes:
``` python
icono = pygame.image.load('house-solid.png')
icono = pygame.transform.scale(icono, (30, 30))
```

- Manejo de eventos:
``` python
for evento in pygame.event.get():
    if evento.type == pygame.QUIT:
        pygame.quit()
        sys.exit()
```

- Dibujo de la pantalla:
``` python
ventana.fill(COLOR_FONDO)
pygame.draw.rect(ventana, COLOR_BOTONES, rect_facil, border_radius=10)
ventana.blit(texto, (ANCHO // 2 - texto.get_width() // 2, 225 - texto.get_height() // 2))
```
  
- Actualizar en pantalla:
``` python
pygame.display.flip()
```

En cuánto a sys que se caracteriza por brindar herramientas para poder interactuar con pyhton se utilizó exclusivamente para asegurar que el programa se cierre adecuadamente cuando el usuario quiera salir de este y presione "X".

- Salir del programa:
``` python
sys.exit()
``` 



``` mermaid
``` 












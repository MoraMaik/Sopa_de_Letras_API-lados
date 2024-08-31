# Sopa de Letras | API-lados
API-lados un grupo conformado por dos Ingenieros Civiles y un Ingeniero Químico que buscan presentan el desarrollo y solucion de su *Proyecto Final* de la materia Progrmacion de Computadores, con el fin de explicar el Programa trabajado durante el semestre 2024-1, el cual, a grandes rasgos, esta inspirado en crear una aplicacion que emule una Sopa de Letras, usando *Python*.
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

Este proyecto es una implementación de una Sopa de Letras en Python, creada como parte del curso de programacion de computadores dirigido por el Ingeniero Felipe Gonzales. La Sopa de Letras es un juego clásico en el que se deben encontrar palabras ocultas en una cuadrícula de letras. El objetivo principal de este proyecto es reforzar conceptos de programación aprendidos durante el curso, estructuras de datos, y algoritmos, a través de la construcción de una aplicación interactiva y entretenida.

## Objetivos del Proyecto

- **Código original**: programa elaborado por el grupo API_lados
- **Uso de herramientas vistas en el curso** 
- **Aprendizaje Activo**: Facilitar el aprendizaje práctico de Python mediante la implementación de un juego interactivo.
- **Mejora de Habilidades**: Desarrollar habilidades en el uso de estructuras de datos, manejo de matrices y algoritmos de búsqueda.


## Funcionalidades del Programa

El programa de Sopa de Letras cuenta con las siguientes funcionalidades:

- **Generación Automática**: Crea sopas de letras de
- **Tamaño de la sopa de letras**: Matriz del tamaño de la sopa de letras (Min: 10x10, Max: 20x20), esta relacionado a la dificultad.
- **Ingreso de las palabras**: Lista de coordenadas, Strings.
- **Nivel de dificultad**: Asociado a cantidad de palabras, verticales, horizontales, diagonal. 3 niveles (Facil, Medio, dificil)

Caracteristicas extra:
  
- **Cuenta regresiva**
- **Sombreado o cambio visual de las palabras encontradas**
- **Interfaz grafica con estructura**
- **Posiblidad de ingresar palabras para generar la sopa de letras (a partir de un diccionario)**: Se puede cambiar las palabras dentro del codigo  

_______________________

# Instalacion

Sigue estos pasos para instalar y ejecutar el proyecto

## **Requisitos**
Antes de comenzar, asegúrate de tener instalado lo siguiente:

+ Python 3.8+: La última versión de Python puede descargarse desde python.org o Microsoft Store.
+ pip: El gestor de paquetes de Python, que generalmente se incluye con Python 3.8+.
+ pygame: Biblioteca para crear aplicaciones multimedia en Python

## **Instrucciones de Instalación**

1. **Descarga o Clona el Repositorio**

Puedes descargar el repositorio como un archivo ZIP desde GitHub o clonar el repositorio en tu máquina local:


**Opción 1**: Descargar ZIP

+ Ubicate en el [Repositorio](http://https://github.com/MoraMaik/Sopa_de_Letras_API-lados "Repositorio")
  
+ Haz clic en el botón "Code" y selecciona "Download ZIP".
+ Extrae el contenido del archivo ZIP en tu máquina local.

**Opción 2**: Clonar el repositorio

+ Abre una terminal y ejecuta el siguiente comando:

```code

git clone https://github.com/MoraMaik/Sopa_de_Letras_API-lados.git

```

2. **Configura el Entorno Virtual (opcional pero recomendado)**

Crea un entorno virtual para gestionar las dependencias del proyecto:

```code

python -m venv venv

```

Activa el entorno virtual:

+ En Windows:

```code
venv\Scripts\activate
```

+ En MacOS y Linux:

```code
source venv/bin/activate
```

3. **Instala las Dependencias**

Instala las dependencias necesarias (pygame, sys)  usando pip:

```code
pip install pygame
```

```code
pip install sys
```
4. **Ejecuta el Programa**

### Notas Adicionales

+ Si encuentras problemas con la instalación de Pygame en diferentes sistemas operativos, consulta la [documentación oficial de Pygame](http://https://www.pygame.org/docs/ "documentación oficial de Pygame")
 para obtener instrucciones detalladas y específicas para tu sistema operativo.

+ Si el entorno virtual está activado, recuerda desactivarlo después de usarlo con el comando deactivate.


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












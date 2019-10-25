
# Especificación de requerimientos de software
## para el sistema de inscripcion del ITAM
Version 1.0  

Preparado por Alessandro, Sebastian Gonzales and Andrés Cruz  

42-inscripciones

25 Octubre 2019





# Tabla de contenidos

1. [Introducción](#introducción)
2. [Descripción general](#descripción-general)
3. [Requerimientos de interfaz externa](#requerimientos-de-interfaz-externa)
4. [Características del sistema](#características-del-sistema)
5. [Requerimientos no funcionales](#requerimientos-no-funcionales)
6. [Otros requerimientos](#otros-requerimientos)

## 1.Introducción
### 1.1 Proposito
Desarrollar un sistema de software al Instituto Tecnológico Autónomo de México para que sus alumnos puedan inscribir materias, dar de baja materias y aplicar a listas de espera.
### 1.2 Convenciones del documento

En este documento utilizaremos una escala del 1 al 5 para definir el tamaño de un feature.


### 1.3 Audiencia objetivo

Este documento tiene como público objetivo a ingenieros de software. En este sentido es importante que el documento logre claridad y completez en la definicíon de las especificaciones del sistema.


### 1.4 Scope del producto

El sistema debe ser desplegado para toda la comunidad estudiantil del itam. Conforme a esto, debe poder atender las peticiones de alta y baja de materias así como las listas de espera. Además, debe permitir la visualización de los cursos para lograr los objetivos anteriores.



## Descripción general
## Requerimientos de interfaz externa
## Características del sistema
### Iniciar sesión en el sistema
#### Descripción y prioridad
El usuario ingresa su usuario y contraseña, es validado y manda un mensaje de error o a la página de inicio.
Incluye un link para restaurar la contraseña si el usuario la ha olvidado.
Es de prioridad alta, ya que es escencial para el uso del sistema.
#### Secuencias de estímulo y respuesta
En la pantalla hay 2 cajas de texto donde el usuario ingresará su clave única y nip, al hacer click en el botón de "Log In" el sistema valida la informacíon ingresada y de ser correcta redirige a la página pricipal, de lo contrario muestra un mensaje de error.
Al hacer click en el link "olvidé mi contraseña" el sistema redirigirá a la página de reestablecer contraseña.
#### Requerimientos funcionales
##### Requerimiento 1
Al hacer click en el botón "Log In" el sistema valida que los campos de clave única y nip no estén vacíos, de ser así desplegará un mensaje pidiendo que se proporcione la información reqerida.
##### Requerimiento 2
Si los campos no están vaciós, el sistema valida la información con la base de datos del itam, si la validación falla despliega un mensaje de error, de otro modo guarda la sesión y redirige al usuario a la página principal.
##### Requerimiento 3
Al hacer click en el link "olvidé mi contraseña" el sistema redirigirá al usuario a la página de recuperacion de contraseñas.
### Dar de alta materias
### Dar de baja materias
## Requerimientos no funcionales
## Otros requerimientos

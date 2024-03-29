﻿
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



## 2 Descripción general

### 2.1	Perspectiva del producto

El producto busca brindar a los estudiantes del ITAM un portal web donde puedan dar de alta materias, actualizar sus horarios y eliminar clases que ya no quieran llevar. El sistema debe ser sencillo y eficiente para reducir el tiempo que llevael proceso de registro para un estudiante. La seguridad es fundamental para que el sistema pueda actualizar las bases de datos del ITAM sin poner en riesgo la información de los usuarios.

### 2.2 Funciones del producto

A continuación se presenta una breve descripción de las funcionalidades generales del producto.

- Registro de usuarios
El usuario es capaz de registrarse en el sistema para iniciar a administrar sus materias.
- Login de usuarios
El usuario es capaz de ingresar al sistema con correo y contraseña porsteriormente a su registro.
- Alta de materias
El usuario debe de ser capaz de dar de alta sus materias.
- Actualización de materias
El usuario debe de ser capaz de actualizar sus materias.
- Eliminación de materias
El usuario debe de ser capaz de dar de baja sus materias.
- Configuración de perfil
El usuario debe de ser capaz de modificar la información básica de su perfil

### 2.3 Usuarios y características

A continuación se presenta una breve descripción de los usuarios que van a interactuar con el producto

- Estudiantes de nuevo ingreso
Nuevos estudiantes en el ITAM, están por cursar su primer semestre en el ITAM y su horario es establecido por control escolar.
- Estudiantes por egresar
Estudiantes que no son de primer ingreso, y siguen avanzando en su carrera en el ITAM

### 2.4 Ambiente operativo

Para el proyecto vamos a utilizar una intancia T2 Micro de AWS. Las instancias T2 son tipos de instancias de Amazon EC2 diseñadas para disminuir radicalmente los costos de las aplicaciones que se benefician de la capacidad para ampliarse para alcanzar el rendimiento pleno de los núcleos cuando resulta necesario. Las instancias T2 se pueden usar en la capa gratuita de AWS, que incluye 750 horas de instancias t2.micro de Linux y Windows al mes durante un año para clientes nuevos de AWS.

El sistema operativo a utilizar es Linux.

### 2.5 Restricción de diseño e implementación
### 2.6 Documentación del usuario
### 2.7 Suposiciones y dependencias

## Requerimientos de interfaz externa
## 4 Características del sistema

### 4.1 Iniciar sesión en el sistema

#### 4.1.1 Descripción y prioridad

El usuario ingresa su usuario y contraseña, es validado y manda un mensaje de error o a la página de inicio.

Incluye un link para restaurar la contraseña si el usuario la ha olvidado.

Es de prioridad alta, ya que es escencial para el uso del sistema.

#### 4.1.2 Secuencias de estímulo y respuesta

En la pantalla hay 2 cajas de texto donde el usuario ingresará su clave única y nip, al hacer click en el botón de "Log In" el sistema valida la informacíon ingresada y de ser correcta redirige a la página pricipal, de lo contrario muestra un mensaje de error.

Al hacer click en el link "olvidé mi contraseña" el sistema redirigirá a la página de reestablecer contraseña.

#### 4.1.3 Requerimientos funcionales

##### Requerimiento 1

Al hacer click en el botón "Log In" el sistema valida que los campos de clave única y nip no estén vacíos, de ser así desplegará un mensaje pidiendo que se proporcione la información reqerida.

##### Requerimiento 2

Si los campos no están vaciós, el sistema valida la información con la base de datos del itam, si la validación falla despliega un mensaje de error, de otro modo guarda la sesión y redirige al usuario a la página principal.

##### Requerimiento 3

Al hacer click en el link "olvidé mi contraseña" el sistema redirigirá al usuario a la página de recuperacion de contraseñas.

### 4.2 Dar de alta materias

#### 4.2.1 Descripción y prioridad
El usuario encuentra la materia que desea inscribir, la selecciona y hace click en el botón "Registrar", el sistema valida que el usuario cumpla los requisitos y de ser el caso inscribe al alumno, de lo contrario manda un mensaje de error.

Es de prioridad alta ya que es la función principal del sistema.
#### 4.2.2 Secuencias de estímulo y respuesta

Al dar click en "Registrar" el sistema valida que el alumno cumpla los requisitos de la materia, de ser así guarda la inscripcion en la base de datos, de lo contrario despliega un mensaje de error.
#### 4.2.3 Requerimientos funcionales

##### Requisito 1
El sistema valida que la materia este abierta o manda error
##### Requisito 2
El sistema revisa que el alumno cumpla los requisitos para la materia o manda error
##### Requisito 3
El sistema registra al alumno inscrito en la materia en la base de datos.
### 4.3 Dar de baja materias
#### 4.3.1 Descripción y prioridad

El usuario elije una de las materias en las que ya está inscrito y el sistema lo desinscribe.
Es de prioridad media, ya que no es escencial para el uso del sistema, pero es importante.

#### 4.3.2 Secuencias de estímulo y respuesta

El usuario elije una materia de la lista de sus inscripciones y hace click en el boton "Eliminar".
El sistema modifica la base de datos adecuadamente.
#### 4.3.3 Requerimientos funcionales

##### Requerimiento 1


El sistema verifica que se haya elegido una materia valida o manda error
##### Requerimiento 2

El sistema verifica que el alumno está inscrito en dicha materia o manda error
##### Requerimiento 3

El sistema elimina al alumno de la materia
## 5.Requerimientos no funcionales
### 5.1 Requerimientos de rendimiento
El sistema debe ser capaz de atender las peticiones de los alumnas en su máxima carga. En los 3 días que los alumnos se inscriben, el sistema debe tener poca latencia y disponibilidad del 100%;
### 5.2 Requerimientos de seguridad

La cuenta de cada alumno solo debe poder ser accedida por el mismo. Es muy importante asegurar el proceso de autenticación puesto que fallar en este aspecto puede tener consecuencias negativas para el alumno. Así mismo, ningun alumno debe poder acceder información que no le corresponda


### 5.3 Reglas del negocio
Cada alumno puede visualizar todos los cursos, pero no le debe ser posible dar de alta materias que no pertenezcan a su plan de estudios o que se den en un horario que choque con una materia previamente seleccionada. Así mismo, cada alumno tiene un límite de materias que puede inscribir definido por su carga académica.


## Otros requerimientos

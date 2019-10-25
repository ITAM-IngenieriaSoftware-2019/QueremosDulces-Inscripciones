# QueremosDulces-Inscripciones

# Software Requirements Specification for Inscripciones ITAM 

Preparado por QueremosDulces, integrantes:
- Jorge Enrique Gatica Fernández
- José Francisco Altamirano Zevallos
- Luis Gerardo Godfrey Castañeda

## Equipo QueremosDulces

Creado el 4 de Octubre del 2019

# Tabla de Contenidos

1. Introducción
   1. Propósito
   1. Convenciones
   1. Público y recomendaciones de lectura
   1. Alcance del producto     
   1. Referencias      
2. Descripción
   1. Perspectiva del producto      
   1. Funcionamiento general
      - Alta de materias
      - Baja de materias
      - Listas de Espera
      - Prerrequisitos
      - Revisar horario
      - Recuperar contraseña
      - Iniciar Sesión
   1. Tipos de usuarios y sus características     
   1. Ambiente de operación     
   1. Limitaciones de diseño y operación      
   1. Documentación para el usuario
   1. Dependencias y supuestos
3. Requisitos de Interfaz externa
   1. Interfaz de Usuario
   2. Interfaz de Hardware
   3. Interfaz de Software
   4. Interfaces de Comunicación
4. Funcionalidades del Sistema
   1. Sesión del alumno
      - Login
      - Recuperar contraseña
      - Cambiar contraseña
      - Perfil
      - Error
   1. Swag 1
   1. Swag 2

# 1. Introducción

## 1.1. Propósito

      <p> La creación de esta nueva página de inscripciones se hace con el enfoque de mejorar la que existe actualmente y que está disponible para estudiantes y administrativos desde el portal de grace ITAM. <br>
      Para esto, se busca mejorar la experiencia del usuario durante el proceso de inscripciones al: remover pantallas innecesarias, utilizar referencias cruzadas de información y la implementación de ayuda durante el proceso para aumentar la accesibilidad del producto. <br>
      Considerando todo lo previamente dicho, este producto sería la versión 2.0 del sistema de inscripciones actual, al empezar desde 0 el sistema y añadir/remover funcionalidades según se puedan adaptar al producto. </p>
      
## 1.2 Convenciones

      <p> Para el formato de texto de este documento, se utilizó el lenguaje Markdown debido a su integración con Github. <br>
      Para la estructuración, se utilizó el formato especificado por la IEEE para la creación de documentos de especificación de requerimientos de software. <br>
      Para las estimaciones se sigue un formato de estilo Pokemon, el cual se estructura de la siguiente manera: Magikarp (baja), Pikachu (media), Charizard (grande), Mewtwo (Enorme). </p>
      
## 1.3 Público y recomendaciones de lectura

      <p> Este documento esta escrito con un enfoque dirigido a un público de programadores/desarrolladores para facilitar su comprensión sobre los requerimientos para la implementación de las funciones especificadas; también esta pensado para coordinadores o administradores del equipo de trabajo, para favorecer la comprensión de la escala, necesidades, problemáticas y enfoque del proyecto <br>
      Para la lectura, se recomienda que esta siga un orden lineal para la mejor comprensión de todas las partes y el porque estan implementadas de esta manera. <br>
      Sin embargo, de haber algún problema de comprensión, se recomienda fuertemente que el lector se diriga a la sección 1.5, donde hallará referencias útiles para la mejor comprensión de las temáticas tratadas; y de la misma manera, se refiera al Apéndice A de la sección 6, donde encontrará un glosario para palabras poco comunes. <br>
      Por último, se estructurará de la siguiente manera el documento a continuación presentado: Introducción al lector, Introducción al proyecto, Profundización en los requerimientos de interfaz, Funcionalidades del sistema, Requerimientos para las áreas relacionadas al proyecto y otros requerimientos no especificados previamente. </p>
      
## 1.4 Alcance del producto

      <p> El producto tiene como objetivo ser una plataforma que facilite el proceso de inscripción al usuario y la gestión de grupos a los administrativos; conseguiría esto mediante la añadidura de nuevas funcionalidades, remoción de las obsoletas y optimización de las existentes. <br>
      Esto ayudaría al ITAM a tener una mejor plataforma y a evitar costos innecesarios al automatizar múltiples procesos </p>
      
## 1.5 Referencias

      <p> Wiegers, K. (1999). Software Requirements Specification. [ebook] Available at: https://drive.google.com/file/d/15UdWMiunZWb1OsIafbTSl1qdl2_EUgeH/view [Accessed 19 Oct. 2019].</p>

# 2. Descripción

## 2.1 Perspectiva del producto

      <p> Este producto surge como un reemplazo al sistema actual de inscripciones utilizado por el ITAM, esto se debe a que el sistema existente está desactualizado (Utiliza protocolos antiguos), es ineficiente (duplica información y no guarda la necesaria), no es amigable con el usuario y se le podrían agregar múltiples mejoras del tipo "Quality of life" </p>
      
## 2.2 Funcionamiento general

      - Alta de materias
      - Baja de materias
      - Listas de Espera
      - Prerrequisitos
      - Revisar horario
      - Recuperar contraseña
      - Iniciar Sesión
      
## 2.3 Tipos de usuarios y sus características

      <p> Los usuarios principales son alumnos, los cuales utilizarían el producto al inscribirse al inicio de semestre y darse de baja/consultar materias a lo largo de este. <br>
      Otro grupo de usuarios son los administrativos escolares, los cuales utilizarían el producto para revisar solicitudes de ruptura de seriación de materias, apertura y cierre de grupos y asignación de horarios y salones. <br>
      El último grupo de usuarios serían los encargados del mantenimiento de la página, los cuales cuidarían que no se saturen los servidores, arreglar bugs y cualquier otra tarea de mantenimiento del producto que surga. </p>
      
## 2.4 Ambiente de operación

      <p> Debido a las características de la plataforma de inscripciones ya existente, la nueva plataforma debe de poder ser visualizada de igual manera en cualquier navegador desde el cual se acceda, ya sea versión movil o de escritorio. <br>
      Además de esto, la plataforma debe de poder coexistir con el sistema de grace que tiene el ITAM, ya que es ahí donde estaría alojado el producto. </p>
      
## 2.5 Limitaciones de diseño y operación

      <p> Para este proyecto, hay múltiples limitantes que afectarán al desarrollo, estas serían las siguientes: </p>
      - Políticas del ITAM 
         <p> Se debe de cumplir con los protocolos de seguridad que tiene el ITAM</p>
      - Limitaciones de hardware
         <p> El servidor tiene un tamaño relativamente pequeño para el número de alumnos que lo usan (en el horario donde más gente se inscribe, se hace en extremo lento y ha llegado a caerse). </p>
      - Base de datos preexistente del ITAM
         <p> Ya existe una base de datos previamente creada por el ITAM siguiendo los estándares establecidos en su momento; además esta contiene información bastante antigua, razón por la cual no se puede rehacer y la nueva plataforma debe de adaptarse al sistema ya existente. </p>
      - Tiempo
         <p> El tiempo de desarrollo está limitado a 2 meses. </p>
      - Ligero
         <p> La plataforma debe de utilizar la menor cantidad de recursos posible, para que tanto cualquier pieza de hardware desde la que se acceda a la paltaforma lo pueda ejecutar sin problema alguno, como para que el servidor no reciba demasiada carga. </p>
         
## 2.6 Documentación para el usuario

      <p> Al usuario, se le dará un manual especialmente diseñado para ayudarlo con el uso de la nueva plataforma, este se dividirá en 2 secciones; en la primera será un instructivo ilustrado paso a paso sobre como realizar todos los procesos, y la segunda una lista de preguntas hechas de manera frecuente, además de un contacto en caso de que se tengan dudas. <br>
      Este manual reemplazaría al actualmente existente que se distribuye por via electrónica todos los semestres.</p>
      
## 2.7 Dependencias y supuestos

      <p> Debido a que todos los recursos utilizados para la plataforma serían propios del ITAM, se asume que se conocen las limitantes de todos los recursos y en que podrían fallar; sin embargo, por esto mismo, sería posible que el proyecto sufra severos retrasos si hay algo de información pertinente a esto que no se compartió con el equipo de desarrollo. </p>

# 3. Requisitos de Interfaz externa

## 3.1 Interfaz de Usuario

La vista del usuario se compondrá de varias pantallas. La primera de ellas será la pantalla de inicio, desde la cual se podrán ver las distintas actividades a realizar, así como el inicio de sesión. 

Cada una de las funcionalidades tendrá su propia pantalla, desde la cuál se tendrá acceso a todas las distintas opciones requeridas para el correcto desempeño de la actividad planeada.

## 3.2 Interfaz de Hardware

## 3.3 Interfaz de Software

## 3.4 Interfaces de Comunicación

# 4. Funcionalidades del Sistema

Emprenderemos un camino sobre cada una de las funcionalidades que debera de cumplir (hasta el momento) nuestro sistema, con el objetivo de poder alcanzar la mayor eficiencia posible para el usuario(alumnos o profesores) y a los desarrolladores.
Por ende, es necesario hacer una división de cada uno de los usuarios para encontrar puntos a mejorar y después a desarrollar. 

## 4.1. Sesión del alumno

En esta sección nos encargaremos de documentar todas las actividades fundamentales para un usuario promedio ( alumno del itam inscrito ) para que pueda iniciar sesión y poder inscribir o quitar cada una de las materias deseadas para ese semestre.



# 5. Otros requerimientos




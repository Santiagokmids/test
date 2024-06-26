# Manual de Uso

## Te Motion Intel
**Versión:** 1.0

**Fecha última actualización:** 17 de junio del 2024

**Autores**: [Juan Fernando Martínez](https://github.com/JuanF2019), [Diana Olano](https://github.com/DianaSofiaOlano), [Juan José Osorio](https://github.com/juanosorio0219), [Luis Miguel Ossa](https://github.com/Itsumohitoride) y [Santiago Trochez](https://github.com/Santiagokmids).

### **Índice**

1. [Introducción](#Introducción)
2. [Requisitos del Sistema](#Requisitos-del-Sistema)
   1. [Requisitos Mínimos](#Requisitos-Mínimos)
   2. [Requisitos Recomendados](#Requisitos-Recomendados)
4. [Instalación](#Instalación)
   1. [Descarga de la Aplicación](#Descarga-de-la-Aplicación)
   3. [Instalación de componentes externos](#Instalación-de-componentes-externos)
   4. [Proceso de Instalación](#Proceso-de-Instalación)
   5. [Resolución de Problemas Comunes](#Resolución-de-Problemas-Comunes)
6. [Funcionamiento](#Funcionamiento)
   1. [Tutorial](#Tutorial)
   2. [Login](#Login)
   3. [Identificación de cámara](#Identificación-de-cámara)
   5. [Formulario del paciente](#Formulario-del-paciente)
   5. [Selección del tipo de prueba](#Selección-del-tipo-de-prueba)
   6. [Grabación](#Grabación)
   7. [Historial](#Historial)
   8. [Archivo guardado](#Archivo-guardado)
   9. [Archivo de logs](#Archivo-de-logs)
10. [Sobre la implementación actual de los adapters](#Sobre-la-implementación-actual-de-los-adapters)
11. [Cámaras compatibles](#Cámaras-compatibles)
12. [Resolución de dudas](#Resolución-de-dudas)
13. [Actualizaciones](#Actualizaciones)

### Introducción
                
Bienvenido al Manual de Usuario de la aplicación **Te-motion Intel**. Esta aplicación está diseñada para el grupo de investigación **i2t** con el propósito de trackear el esqueleto de una persona usando la cámara **Intel&reg; Realsense D455**(y predecesoras) o la **Orbbec Astra Pro**, para así obtener las coordenadas **x**, **y** y **z** de cada articulación del cuerpo. 

Estas variables pueden ser obtenidas a partir de dos pruebas, las cuales son **Análisis de marcha** y **Timed Up and Go**. 
Al obtener las coordenadas, la aplicación genera y guarda un archivo en formato **JSON** con toda la información de la captura y los datos, tanto del paciente como de la persona que realizó la medición. Esta información luego es enviada a un servidor que procesa estas variables y realiza cálculos que permiten mejorar el diagnóstico de una persona con posible enfermada de Parkinson.

El objetivo de este manual es proporcionar instrucciones detalladas y claras para ayudarle a instalar, configurar y utilizar la aplicación de manera eficiente. 

Esperamos que encuentre este manual útil y que le ayude a aprovechar al máximo las características y funcionalidades de la aplicación **Te-motion Intel**.


#### Requisitos Mínimos
- **Sistema Operativo:** Windows 10/11
- **Procesador:** Intel Core i3 o equivalente
- **Memoria:** 8 GB de RAM
- **Almacenamiento:** 500 MB de espacio libre en disco

#### Requisitos Recomendados
- **Sistema Operativo:** Windows 10/11
- **Procesador:** Intel Core i3 o superior
- **Memoria:** 16 GB de RAM
- **Almacenamiento:** 1 GB de espacio libre en disco

### Instalación

### Instalación

#### Descarga de la Aplicación
Para descargar **Te-motion Intel**, diríjase a **[releases](https://github.com/i2tResearch/mhealth-emotion-intel/releases)** y descargue la versión más reciente de la aplicación, ya sea para su versión de **Windows** o **Linux**.

#### Instalación de componentes externos para Windows
- **Orbbec camara driver** Si va a hacer uso de la cámara Orbbec Astra Pro se requiere la instalación del driver para la cámara.
   - Puede descargarlo de la página oficial de Orbbec: [Orbbec Camara Driver](https://www.orbbec.com/developers/astra-sdk/) dando click click donde dice: **Orbbec Camera Driver for Windows** 
   - Para instalar de doble click sobre el archivo descargado y siga las instrucciones en pantalla.
- **Microsoft Visual C++ Redistributable**:
   - Pueden ser descargadas desde la página oficial de [Microsoft](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170) o desde el link directo para arquitectura x64 dando click [aquí](https://aka.ms/vs/17/release/vc_redist.x64.exe)
   - Para instalar de doble click sobre el archivo descargado y siga las instrucciones en pantalla.
- **Python:** Para poder sacar el máximo provecho al software, por favor instale:
   - [Python 3.11](https://www.python.org/downloads/release/python-3119/)

      Si no sabe cómo instalar **python**, puede ver el siguiente [tutorial](https://elpythonista.com/como-instalar-python#:~:text=con%20c%C3%B3digo%20Java.-,%C2%BFC%C3%B3mo%20instalar%20el%20int%C3%A9rprete%20de%20Python%3F,-El%20int%C3%A9rprete%20de)

      Si ya tiene **python** instalado pero no sabe qué versión tiene:
      - Abra la consola de su dispositivo
      - Digite en la consola:
        ```
        python --version
        ```
        Y así de fácil podrá ver la versión que tiene instalada.

      Para la ejecución del script de envío de datos a vimov debe instalar el paquete `requests` ejecutando el siguiente comando en su consola:

        ```
        pip install requests
        ```

#### Proceso de Instalación
1. **Windows**:

   1. Para descargar e inicar la aplicación:

      - En el Release más reciente, dé clic en la siguiente opción para descargar la aplicación:

        ![1](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/6686cdd8-c48d-42e4-8afb-5f7aec33784b)
        > Opción que permite descargar la aplicación completa.
   
      - Una vez que descargue los archivos, tendrá a su disposición una carpeta **.zip** que tendrá que descomprimir o extraer en su directorio de **Descargas**. Después de extraerla, tendrá un directorio de la siguiente forma:

        ![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/bdc4f6ac-183a-4852-a56c-684d9377191e)
        > Contenido del directorio luego de haberlo descomprimido.
   
      - Ahora diríjase a la siguiente dirección para encontrar el ejecutable o .exe de la aplicación:

        ![2](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/c33c76e9-de74-4016-a455-701b9f74972a)
        > Contenido del directorio que contiene el archivo .exe de la aplicación.
        
      - Por último, podrá dar clic al archivo .exe y la aplicación se ejecutará con exito.

      - **IMPORTANTE**: si desea que la aplicación se ejecute siempre que se inicie sesión en su dispositivo, puede ver el siguiente [tutorial](https://www.xataka.com/basics/como-hacer-que-programa-se-ejecute-al-iniciar-windows-11-forma-automatica) para configurarlo de manera correcta.

   2. Para programar la tarea que envía datos al sistema VIMOV:

      - Lo primero que debe hacer es buscar en su buscador de Windows **Programador de tareas** o **Task scheduler**, dependiendo del idioma en el que esté su sitema operativo. La aplicación debe verse así:

        ![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/15954475-eef0-4272-a811-0c73dd3d2dbd)
        > Logo de la aplicación para programar una tarea.
      - Luego, cuando abra la aplicación, dará clic en la siguiente opción:

        ![3](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/6f883157-9ea6-4a74-860f-29bf328d42ff)
        > Opción para crear una tarea.
      - Cuando presione clic aquí, se encontrará con una sección en donde escribirá detalles generales de la tarea, como su nombre y descripción.

        ![4](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/45816a2b-4b85-4dc3-aab0-793ba0f79319)
        > Sección para ingresar detalles generales de la tarea a crear.
      - Después de ingresar los datos necesarios, podrá irse al apartado de desencadenadores. Aquí, se configura la frecuencia a ejecutar de la tarea a programar. Para agregar la frecuencia, dé clic en la opción **Nuevo**. Luego de hacer esto, se encontrará con el siguiente apartado:

        ![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/7daae864-a2e8-40b7-a55a-49c6f47060e4)
        > Apartado para configurar las veces que se va a ejecutar la tarea.
      Cuando configure este apartado, presione **aceptar**.

      - Ahora, podrá ir al apartado de acciones. Aquí, como en el apartado anterior, deberá presionar el botón **Nuevo**. Luego de esto, se encontrará con un apartado en donde podrá elegir la acción a realizar y el script o ejecutable que se ejecutará.

        ![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/33a9ea0a-c298-4164-95b8-c062b23e23bc)
        > Apartado para agregar una acción.
         **IMPORTANTE**: el script que debe accionar se encuentra aquí:

         ![5](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/46280b8f-b760-407c-b7a2-a63680a19754)
         > Script que se debe programar para ejecutar la tarea.
   
         Además, tendrá que ingresar al script y cambiar los siguientes campos por las direcciones que corresponden en su dispositivo:

         ![6](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/3c262e82-8239-4dcd-b4fb-d6ee6ea7cbd8)
         > Campos que debe editar para que correspondan a las direcciones de su dipositivo.
  
         Después de asegurarse que todo esté correcto, puede presionar el botón **aceptar**.

      - Ahora, podrá ir directamente al apartado de configuración y ahí, es recomendable que deje este apartado con la siguiente configuración:

        ![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/1951ec02-2654-47ae-8e3d-bf952a6cff10)
        > Apartado de configuración de la tarea a programar.
   Después de esto, podrá ejecutar la aplicación sin problema alguno, asegurándose que todo va a funcionar correctamente, desde el inicio de la misma hasta el envío de datos al sistema VIMOV.


2. **Linux**:
   1. Actualmente en desarrollo

#### Resolución de Problemas Comunes en Windows
- **No se puede ejecutar la aplicación**: Verifique que el antivirus de su sistema le permita ejecutar aplicaciones de externos.
- **Aplicación no funciona con cámara Intel&reg; Realsense D435 o D455**: Verifique que la cámara se encuentre conectada a un puerto **USB 3.1.**

### Funcionamiento

#### Tutorial

Cuando abra la aplicación, se encontrará con la siguiente pantalla:
![image](https://github.com/Santiagokmids/test/assets/72984873/1e15bb9a-a9c9-4b41-ab34-9bbbfb2bcd99)
> Inicio de la aplicación

Esta da inicio al pequeño tutorial en donde se le explicará cómo prepararse para que así la cámara pueda realizar las mediciones de manera correcta. En este punto tiene dos opciones a elegir, las cuales son: seguir el tutorial o saltarlo. Si presiona **Siguiente** se le enviará al segundo paso del tutorial, y si presiona **[Saltar](#Login)**, se le enviará a la pantalla del login.

Después de presionar el botón **Siguiente** veremos la siguiente pantalla:

![image](https://github.com/Santiagokmids/test/assets/72984873/8aff0c56-7b3d-4e05-8900-8ca5167bf98b)
> Segundo paso del tutorial 

En esta pantalla se encontrará con la información que le dirá cómo debe estar su espacio para cuando quiera realizar la prueba de **"Análisis de marcha"**. Aquí se le informa a cuántos metros debe ubicar al paciente con respecto a la cámara y a cuántos centímetros debe ubicar el paciente respecto a la pared y la cámara respecto al suelo. A diferencia de la pantalla anterior, aquí contamos con 3 opciones. La primera de izquierda a derecha es **"Atrás"**, la cual nos permite dirigirnos al primer paso del tutorial. El botón **[Saltar](#Login)** sigue con su misma función y el botón **"Siguiente"** nos enviará al tercer paso del tutorial.

![image](https://github.com/Santiagokmids/test/assets/72984873/7eb710c4-651e-4556-823d-633c458daa30)
> Tercer paso del tutorial

En esta pantalla podemos encontrar la información sobre cómo debe estar su espacio para cuando quiera realizar la prueba de **"Timed Up and Go"**. Se le dice que debe seguir las mismas instrucciones que el paso anterior y que adicionalmente, tenga una silla a su disposición para que el paciente se pueda sentar. Además, aquí contamos con las mismas 3 opciones que la pantalla anterior, donde el botón **[Saltar](#Login)** conserva su función, mientras que el botón **"Atrás"** envía al segundo paso del tutorial y el botón **"Siguiente"** envía al cuarto paso del mismo.

![image](https://github.com/Santiagokmids/test/assets/72984873/022e4b76-171b-4afe-92af-31856e4a3bd9)
> Cuarto paso del tutorial

La presente pantalla nos da información acerca de cómo debe estar la luz del lugar donde vamos a realizar la medición. Se le hace saber de manera gráfica de qué manera se debe ver la grabación al momento de capturar un esqueleto, sin que se pierda ninguna articulación. Al igual que en la pantalla anterior, contamos con tres opciones. El botón **[Saltar](#Login)** conserva su función, el botón **"Atrás"** envía al tercer paso del tutorial y el botón **"Siguiente"** envía al quinto y último paso del tutorial.

![image](https://github.com/Santiagokmids/test/assets/72984873/0b27560c-d2c8-4f9e-9b42-347cca90fcb7)
> Quinto paso del tutorial

Esta pantalla hace alusión al último paso del tutorial. Aquí se le informa sobre cómo debe ser la vestimenta del paciente o persona que va a ser medida, esto con el fin de que al realizar la medición, la cámara no presente inconvenientes para capturar la información de las articulaciones. Se le recomienda remangar las vestimentas que generen ruido en la parte inferior de la persona, como lo podría ser un vestido o un pantalón demasiado ancho. A diferencia de las pantallas anteriores, aquí solo contamos con dos opciones. La que dice **"Atrás"** nos envía al cuarto paso del tutorial, mientras que la opción **"Empezar"** nos dirige a la pantalla de login o inicio de sesión de la aplicación.

#### Login

Ahora, después de haber saltado o visto todo el tutorial, llegaremos a la pantalla de login o inicio de sesión, la cual se ve así:

![image](https://github.com/Santiagokmids/test/assets/72984873/710a7bdc-6773-4af4-9bdd-1dfcffe24b36)
> Pantalla de login o inicio de sesión

En este punto usted podrá ingresar el nombre completo y el número de identificación de la persona que va a realizar la medición, esto para que en cada medición se tenga presente quién fue su respectivo medidor. El número de identificación no debe contener letras o puntos, este campo sólo acepta valores numéricos. En caso de que usted ingrese algún valor que no sea numérico y dé clic al botón **"Identificarse"**, se encontrará con el siguiente aviso:

![image](https://github.com/Santiagokmids/test/assets/72984873/abd27852-5da2-4b29-8de0-219ad7936799)
> Aviso de valores mal diligenciados en el login

En caso contrario, si usted ingresó valores numéricos y presiona el botón **"Identificarse"**, será enviado a la siguiente pantalla, la cual le informa que debe conectar una cámara para poder continuar.

Como puede ver, en la esquina izquierda la pantalla, tendrá un botón. Este le permitirá dirigirse al **[Historial](#Historial)** de mediciones que se han realizado anteriormente con ese mismo dispositivo.

#### Identificación de cámara

Al principio, verá cómo la aplicación está identificando que tenga una cámara conectada, por lo que se encontrará con la siguiente pantalla:

![image](https://github.com/Santiagokmids/test/assets/72984873/72855668-75c5-4ed1-b2dc-3edbfe49f001)
> Pantalla que le informa que no se encuentra una cámara, pero que aún así se está buscando una

Si la aplicación no es capaz de identificar una cámara, seguirá buscando hasta que usted conecte una. En caso contrario, si se encuentra que hay una cámara conectada, la pantalla ahora mostrará la siguiente información:

![image](https://github.com/Santiagokmids/test/assets/72984873/dc9b5412-9def-4d74-8ede-1f165e31ee9e)
> Pantalla que informa que ya se ha encontrado una cámara, por lo que ahora puede continuar

En ambas pantallas, tendrá la opción de ir de nuevo al login, esto a partir del botón **"<-"**. Por otro lado, en el momento en que se identifica una cámara, tendrá disponible la opción **"Siguiente"**, la cual al darle clic, le enviará a la pantalla para seleccionar el tipo de prueba que va a realizar.

**Para tener en cuenta:** Por favor conecte la cámara por medio de un puerto **USB 3.1** para que así obtenga el mejor rendimiento posible de la misma. Si va a usar la cámara **Intel&reg; Realsense D435**, es **indispensable** que la conecte a este puerto, porque de otra forma, la cámara no será capaz de funcionar en la aplicación.  

#### Formulario del paciente

Ahora, se encontrará con una de las pantallas más importantes de la aplicación, que es la del formulario del paciente. Al iniciar, verá lo siguiente:

![image](https://github.com/Santiagokmids/test/assets/72984873/7e42394b-a4aa-40aa-99cb-34825456ebf9)
> Inicio del formulario del paciente donde se ve el campo para ingresar su nombre

Aquí podrá ingresar el nombre del paciente o persona a la que se le va a realizar la medición. El apartado de **Nombre** tiene un **"*"** debido a que el campo es obligatorio. Después de ingresar este campo, puede bajar con el scroll del mouse o directamente presionar la tecla **tab** del teclado para dirigirse al siguiente campo del formulario, el cual es **Apellidos**

![image](https://github.com/Santiagokmids/test/assets/72984873/8ece407b-782b-4952-a1d5-dc809a2bbd25)
> Formulario del paciente donde se ve el campo para ingresar sus apellidos

En esta parte del formulario, tendrá que ingresar el/los apellido(s) del paciente. Al igual que el campo de texto anterior, el campo de **Apellidos** es obligatorio.
Después de diligenciar este campo de texto, puede bajar con el scroll del mouse o presionar la tecla **tab** del teclado para dirigirse al siguiente campo del formulario, el cual es **Cédula**

![image](https://github.com/Santiagokmids/test/assets/72984873/2fed65f8-d568-406f-a4b9-5e095131c315)
> Formulario del paciente donde se ve el campo para ingresar su cédula

Aquí podrá ingresar la cédula o número de identificación del paciente. Al igual que los campos anteriormente diligenciados, este también es **obligarorio**. Después de ingresar este campo, puede bajar con el scroll del mouse o directamente presionar la tecla **tab** del teclado para dirigirse al siguiente campo del formulario, el cual es **Fecha de Nacimiento**, específicamente en el campo **día** o **DD**

![image](https://github.com/Santiagokmids/test/assets/72984873/bf62bfbb-0901-4e06-af96-18c2162dfec0)
> Formulario del paciente donde se ven los campos para ingresar la fecha de nacimiento. Está el día(DD), el mes(MM) y el año(AAAA)

En este momento del formulario, podrá ingresar la fecha de nacimiento del paciente que va a ser medido. Aquí podrá ingresar el **día(DD)**, el **mes(MM)** y el **año(AAAA)**, cada valor en un campo diferente. 
Es importante tener en cuenta que estos 3 campos sólo aceptan valores numéricos. Además, en esta parte, a medida que vaya ingresando valores, el cursor irá cambiando de campo automáticamente, esto significa que al ingresar dos valores en el campo de **día(DD)**, será directamente enviado al campo de **mes(MM)**, y aquí, al ingresar dos valores, será enviado al campo de **año(AAAA)**. En este último campo, al ingresar cuatro valores, será enviado inmediatamente al siguiente campo del formulario, el cual es **"Observaciones"**. Al igual que los campos anteriores, la Fecha de nacimiento es obligatoria.

![image](https://github.com/Santiagokmids/test/assets/72984873/aff6347f-1fb3-47bf-890c-a88f6b40b8ec)
> Formulario del paciente donde se ve el campo de observaciones

Este ya es el último apartado del formulario. Aquí tendrá que ingresar información que pueda ser relevante del paciente que va a ser medido. Este campo también es obligatorio y no tiene limitaciones de escritura. 

Al final del formulario se encuentra el botón **"Guardar"**. Si presiona este botón sin haber llenado todos los campos del formulario, se encontrará con el siguiente aviso:

![image](https://github.com/Santiagokmids/test/assets/72984873/1cb1d5c7-1c70-40e1-acbd-4b34bb0b58c5)
> Aviso que informa que antes de guardar la información del paciente, debe llenar todos los campos obligatorios

Asimismo, si al dar clic en **"Guardar"** ha llenado todos los campos del formulario pero presenta inconsistencias en la fecha, como por ejemplo que haya ingresado caracteres en lugar de números, que la fecha no tenga un formato válido o que el año de nacimiento del paciente sea menor a **1910**, se encontrará con el siguiente aviso:

![image](https://github.com/Santiagokmids/test/assets/72984873/7bea4bb8-9e7b-4cfb-bef8-9acf1a46fbf7)
> Aviso que informa que la fecha de nacimiento del paciente no es válida

Si usted diligenció todos los campos y la fecha de nacimiento que ingresó es correcta, al dar clic en el botón **"Guardar"** será dirigido a la siguiente pantalla, la cual es:


#### Selección del tipo de prueba

Ahora podrá seleccionar el tipo de prueba que va a realizar, por lo que se le presenta la siguiente pantalla:

![image](https://github.com/Santiagokmids/test/assets/72984873/333a4084-76a8-4f51-993c-abcce65c2f82)
> Pantalla donde se le presenta los dos tipos de medición que puede realizar para que seleccione uno

En este apartado usted tendrá la opción de elegir **"Análisis de marcha"** o **"Timed Up and Go"**, dependiendo de la medición que desea realizar. Sólo puede elegir una opción, y en caso de no seleccionar ninguna y presionar el botón **"Siguiente"**, se encontrará con el siguiente aviso:

![image](https://github.com/Santiagokmids/test/assets/72984873/6e77fb7f-6193-41a8-b216-462988af4a4c)
> Aviso que informa que debe seleccionar un tipo de prueba si desea continuar

Si selecciona una opción y presiona el botón **"Siguiente"**, será enviado al siguiente apartado, el cual es el apartado de grabación.

#### Grabación

Esta pantalla es la más importante de toda la aplicación, ya que es aquí donde usted puede realizar el tracking de esqueletos de los pacientes. Lo que verá en un principio será:

![image](https://github.com/Santiagokmids/test/assets/72984873/f3dc0125-4e04-4227-a803-b41ff193487b)
> Pantalla de grabación

Aquí puede observar que esta pantalla tiene varios apartados. El primero y el principal es:

![image](https://github.com/Santiagokmids/test/assets/72984873/dd7cc9d4-68ce-4c7c-ad23-8cbf33b6c46b)
> Apartado de grabación

Como puede observar, aquí se tiene una vista de lo que captura la cámara en tiempo real con su respectivo tracking al esqueleto de una persona. En la parte superior derecha, puede ver la información de los **Frames por segundo (FPS)** que se están capturando actualmente, y en la parte inferior, se puede ver un pequeño apartado con el botón ⏺️ en la mitad.
Si da clic en este botón, se empezará a tomar datos de las articulaciones que actualmente se están capturando, y además, este apartado ahora se verá así:

![image](https://github.com/Santiagokmids/test/assets/72984873/b020ce58-4bfc-4118-97bb-7acb6843ef61)
> Apartado de botones cuando se da clic al botón de iniciar grabación

**Después de que empiece la grabación, no podrá ir de nuevo a la ventana anterior.** 

Ahora aparecen 2 botones. El de la izquierda es el botón ⏹️, el cual me permite **parar** por completo la grabación y guardar los datos recolectados en un archivo en formato JSON. El otro botón es ⏸️, el cual me permite **pausar** la grabación.

Si doy clic al botón de **pausa**, ahora el apartado se verá así:

![image](https://github.com/Santiagokmids/test/assets/72984873/65edd4dd-8fed-4340-903f-dadba952798c)
> Apartado de botones cuando se le da clic al botón de pausar grabación


Ahora puede ver que el botón de pausa ha cambiado por un nuevo botón. Este nuevo botón es ⏺️, cuya función es la misma que anteriormente se mencionó (Empezar grabación). El otro botón sigue teniendo la misma función (Parar grabación). 

Es con esto que se llega al bucle. Si presiono ⏺️, este botón empieza la grabación y es reemplazado por el botón ⏸️. Si presiono el botón ⏸️, este pausa la grabación y es reemplazado por el botón ⏺️. Así sucesivamente hasta que tome la decisión de **parar** la captura o presionar el botón ⏹️ para guardar la medición. 

Al presionar el botón **parar**, lo primero que hace la aplicación es mostrar el siguiente mensaje:

![image](https://github.com/Santiagokmids/test/assets/72984873/c2bed450-c3b1-42f1-9464-bc9b2988189e)
> Mensaje que informa que la aplicación está guardando el archivo en formato JSON con la información obtenida de la captura

Si presiono el botón de **parar** y no se pudo trackear u obtener la cantidad suficiente de articulaciones, la aplicación me enviará el siguiente aviso después del mensaje anterior:

![image](https://github.com/Santiagokmids/test/assets/72984873/43f7d7b8-3a22-4b86-ab18-715658c18931)
> Aviso que me informa que la grabación no capturó la cantidad suficiente de datos

Al mostrar este aviso, la aplicación te envía de nuevo al formulario del paciente y elimina cualquier información de la captura que haya sido guardada. 

Si por el contrario, la aplicación pudo trackear la cantidad suficiente de información, al presionar el botón **parar** y después de mostrar el mensaje de que se está guardando el archivo, se mostrará la siguiente información:

![image](https://github.com/Santiagokmids/test/assets/72984873/e1743b53-4710-4689-aff4-2a1f653bb9e0)
> Mensaje que informa que se guardó con éxito el archivo JSON con la información de la medición realizada y dónde se guardó

Al guardar el archivo, la aplicación te enviará de nuevo al apartado de **[Selección del tipo de prueba](#Selección-del-tipo-de-prueba)** para que inicies una nueva captura con un nuevo paciente.

Otro apartado que tiene esta pantalla es el apartado de información. Este apartado es el que aparece al lado izquierdo de la pantalla

![image](https://github.com/Santiagokmids/test/assets/72984873/39255891-6bdd-4856-91d4-e88bec0b0693)
> Apartado de información en la pantalla de grabación

Si usted da clic en cualquier zona de este apartado, se desplegará un menú hamburguesa, en donde podrá ver lo siguiente:

![image](https://github.com/Santiagokmids/test/assets/72984873/66b6390a-7d1f-49c8-a4f3-a8ce094d7d70)
> Apartado de información desplegado 

Aquí se puede dar clic a alguna de las tres opciones que se nos presentan. Si se da clic al botón **"Datos"** se desplegará la siguiente información:

![image](https://github.com/Santiagokmids/test/assets/72984873/d6c1f46f-9814-40b5-a57b-44eca3093e6b)
> Apartado de información luego de dar clic en Datos

En este apartado se logra ver la información del paciente que está siendo medido, como su nombre y número de cédula o de identificación

Si se da clic en el botón **["Historial"](#Historial)** se le enviará al historial de pacientes que ha sido medido en el mismo dispositivo.

Si se da clic en el botón **"[Info](#Tutorial)"** se le presentará al medidor de nuevo la información sobre cómo tiene que preparar su espacio para la medición, todo el tutorial. Si este presiona el botón saltar o continua el flujo del tutorial, este al finaliza lo enviará de nuevo al apartado de [Grabación](#Grabación).

Por último, en caso de que usted no haya conectado bien la cámara o que la cámara que tiene conectada no tenga flujos RGB y no sea compatible con el sistema, le saldrá el siguiente error:

![image](https://github.com/Santiagokmids/test/assets/72984873/d6e1095c-c09f-47a0-b5f2-2425903e4db4)
> Error que informa que no tiene una cámara compatible para realizar la grabación

Asegúrese que tiene conectada bien la cámara en un puerto **USB 3.1** y luego, presione el botón **Atrás (<-)**. Así, podrá volver a dar click en **Siguiente** y el sistema de nuevo intentará abrir la cámara. Si el error persiste, verifique que la cámara es una Intel&reg; o que es la Orbbec Astra Pro.

#### Historial

En este apartado, usted podrá ver la información de las personas que han sido medidas en el dispositivo que está usando. Podrá ver su número de identificación o cédula, nombre, fecha en que se realizó la medición, ubicación del archivo donde se guardó la medición y por último, si este se ha subido o no al sistema VIMOV.
Además, cuenta con dos opciones en la esquina superior derecha, donde podrá ir hacia una página anterior a la que ya está (en caso de que no se encuentr en la página 1) o ir una página más adelante si así lo desea.

La pantalla del historial se verá de la forma:

![image](https://github.com/Santiagokmids/test/assets/72984873/35afc403-c605-44d2-bcab-b184e3a921de)
> Pantalla de historial

#### Archivo guardado

Después de que se haya terminado de hacer la captura y de guardar el archivo, podrás ir a la ruta que te mostró la aplicación para encontrarlo. Esta ruta apunta al directorio **Captures** que se encuentra en el apartado **Descargas** de tu sistema. El nombre de este archivo se compone de la siguiente forma: **Nombre del Paciente - [Fecha de captura]_id de la captura.json**. 

En tu explorador de archivos se verá de la forma:

![image](https://github.com/Santiagokmids/test/assets/72984873/749b11a3-c59f-497c-ac69-868972c8e1ba)
> Archivo en formato JSON guardado luego de terminar una captura

#### Archivo de logs

Para que puedas tener un completo conocimiento de los errores que se puedan presentar en la aplicación, dispones de un directorio llamado **logs**, que se encuentra en la misma dirección donde está el ejecutable del proyecto. Dentro de este directorio, encontrarás archivos que dentro de sí, tendrán los errores que pudieron ocurrir mientras el aplicativo se encontraba en funcionamiento. Estos errores son útiles para reconocer dónde se presentó el error y cómo arreglarlo.

Los archivos **logs** se verán así:

![image](https://github.com/Santiagokmids/test/assets/72984873/f6d1ba38-661f-48e7-a206-c9b98f329177)
> Archivos logs generados por la aplicación

### Resolución de dudas

Si presenta alguna duda o problema al momento de instalar o ejecutar la aplicación, no dude en ponerse en contacto con cualquiera de los autores de este software.

### Cómo integrar una nueva cámara

En caso de que se quiera integrar una nueva cámara al sistema, se tendrán que seguir los siguientes pasos:

- Crear una clase adapter como la clase **IntelRealsenseCameraAdapter.cpp** ya presente en el aplicativo, cuyas funciones serán las de manejar e interactuar con la cámara. Esta clase deberá estar presente en el siguiente directorio:

  ![image](https://github.com/Santiagokmids/test/assets/72984873/af757740-f051-4c91-9e21-fc7095076b72)
  > Directorio que debe contener la clase Adapter de la cámara a integrar 

- Otro aspecto clave para esta clase es que debe incluir los encabezados necesarios para poder adaptar el funcionamiento de la cámara con el del aplicativo. Estos encabezados son:

  ![image](https://github.com/Santiagokmids/test/assets/72984873/4300139f-7560-40bd-a97d-b2cf21ff6eba)
  > Encabezados que permitirán adaptar la cámara con el aplicativo

- En esta clase tendrá que agregar cuatro métodos fundamentales, los cuales son **iniciar cámara**, **cerrar cámara**, **pasar cada articulación a un nombre estándar** y **procesar el siguiente frame**. Con estos métodos usted podrá realizar una integración correcta de una nueva cámara. Si desea apoyarse en un ejemplo, puede ver los métodos presentes en la clase **IntelRealsenseCameraAdapter.cpp**.

  **Tenga en cuenta que dependiendo del SDK de cada cámara, puede tener que agregar más métodos a su clase. Sin embargo, los cuatro métodos anteriormente mencionados siempre deben estar, ya que estos son los que aseguran una correcta interacción con la cámara.**

- Luego, otro aspecto que debe tener en cuenta son las dependencias. Si no agrega las dependencias necesarias para que la cámara funcione, será imposible integrarla. Cuando ya cuente con las dependencias de la cámara, agrege un directorio con el nombre de la cámara en la ruta:

  ![1](https://github.com/Santiagokmids/test/assets/72984873/1f70be19-ff3c-4d09-9132-c317d25864e8)
  > Ruta de donde se debe agregar un directorio con el nombre de la cámara para almacenar las dependencias
  
  Dentro del directorio creado, tendrá que ingresar archivos que permitirán usar la cámara. Si no tiene muy claro qué archivos debe ingresar, puede dirigirse al directorio **mhealth-emotion-intel\mhealth-emotion-intel\dependencies\realsense2**, donde podrá ver la estructura y los archivos necesarios para un correcto funcionamiento.

- Después de tener la clase adapter implementada, tendrá que llamarla desde la clase **CaptureWorker.cpp**, la cual está presente en el siguiente directorio:

  ![image](https://github.com/Santiagokmids/test/assets/72984873/254e6973-02cc-40b0-ac23-6d44ce9f441f)
  > Directorio que contiene a la clase CaptureWorker.cpp
  
  En esta clase lo único que tendrá que hacer es agregar un condicional en el método **initializeCamera_worker**, esto para que cuando la cámara sea igual a la nueva, se llame a su constructor y se inicialice una nueva instancia de la misma. Un ejemplo de esta tarea lo puede ver claramente aquí:

  ![image](https://github.com/Santiagokmids/test/assets/72984873/297e144e-8ce2-4769-827c-4a80d1740309)
  > Condicional que inicializa la clase IntelRealsenseCameraAdapter siempre que la variable camera sea igual a INTEL_REALSENSE

- Antes de realizar el llamado a captureWorker, se tiene que agregar el nombre de la cámara en el encabezado **Camera.h** que contiene el nombre de cada una de ellas. Este encabezado está aquí:

  ![image](https://github.com/Santiagokmids/test/assets/72984873/8ed6c2e8-dbb2-418f-80b1-2f943a9e67e3)
  > Encabezado que contiene los nombres de las cámaras que funcionan en el aplicativo.

- Por último, tendrá que configurar el programa para que en la clase **cameramenu.cpp**, específicamente en el método **setup_capture_objects**, se identifique qué cámara se tiene conectada y dependiendo de esto, emita una señal a captureWorker con el nombre respectivo de la cámara, como se tiene aquí:

  ![image](https://github.com/Santiagokmids/test/assets/72984873/0af59c57-93a1-46a4-a01b-eb137c438685)
  > Línea de código donde se emite una señal al captureWorker con el nombre de la cámara Intel_Realsense

### Sobre la implementación actual de los adapters

Como se mencionó anteriormente en caso que el SDK no soporte todas las articulaciones se deberá manejarlas manualmente dentro de las implementaciones, a continuación se describe como se manejaron para los adapters de las cámaras Intel Realsense:

- `IntelRealsenseCameraAdapter` con el modelo Movenet:   
   - `StandardJointType::SPINE_BASE`: Promedio entre LEFT_HIP y RIGHT_HIP.
   - `StandardJointType::BODY_CENTER`: Igual a SPINE_BASE.
   - `StandardJointType::SHOULDER_SPINE`: Promedio de LEFT_SHOULDER Y RIGHT_SHOULDER.
   - `StandardJointType::HEAD`: Promedio de LEFT_EAR y RIGHT_EAR.
   - `StandardJointType::NECK`: Promedio de SHOULDER_SPINE y HEAD.
   - `StandardJointType::MID_SPINE`: Promedio de SHOULDER_SPINE y SPINE_BASE.
   - `StandardJointType::LEFT_HAND`: confidence=-1.0, x=0.0, y=0.0, z=0.0, tracking_state: NOT_TRACKED.
   - `StandardJointType::RIGHT_HAND`: confidence=-1.0, x=0.0, y=0.0, z=0.0, tracking_state: NOT_TRACKED.
- `IntelRealsenseLIPSCameraAdapter` con el modelo LIPS (En la rama experimental_lips):
   - `StandardJointType::SPINE_BASE`: Promedio entre LEFT_HIP y RIGHT_HIP.
   - `StandardJointType::BODY_CENTER`: Igual a SPINE_BASE.
   - `StandardJointType::SHOULDER_SPINE`: Equivalente a `lips::LIPSBODYPOSE_KEYPOINT_ENUM::LIPSBODYPOSE_NECK`.
   - `StandardJointType::HEAD`: Promedio de LEFT_EAR y RIGHT_EAR.
   - `StandardJointType::NECK`: Promedio de SHOULDER_SPINE y HEAD.
   - `StandardJointType::MID_SPINE`: Promedio de SHOULDER_SPINE y SPINE_BASE.
   - `StandardJointType::LEFT_HAND`: confidence=-1.0, x=0.0, y=0.0, z=0.0, tracking_state: NOT_TRACKED.
   - `StandardJointType::RIGHT_HAND`: confidence=-1.0, x=0.0, y=0.0, z=0.0, tracking_state: NOT_TRACKED.

### Cámaras compatibles

Las cámaras que funcionan en este software son las siguientes:

- Cámara **[Intel&reg; Realsense D455](https://www.intelrealsense.com/depth-camera-d455/)**.
- Cámara **[Intel&reg; Realsense D435](https://www.intelrealsense.com/depth-camera-d435/)**.
- Cámara **[Orbbec Astra Pro](https://shop.orbbec3d.com/Astra-Pro-Plus)**.

Además, también es posible que sea compatible con las cámaras que cumplen con al menos uno de estos requisitos:

- Cámaras compatibles con el SDK **[Intel Realsense 2.0](https://www.intelrealsense.com/sdk-2/)** que cuenten con un sensor de profundidad y RGB y soporten una resolución de profundidad de 848x640@30fps.
- Cámaras compatibles con el SDK **[Orbbec Astra SDK](https://www.orbbec.com/developers/astra-sdk/)** que soporten un flujo de tipo body `(astra::BodyStream)`.

Si desea agregar una cámara a la aplicación que no cumpla con estos requisitos, por favor revise [Cómo integrar una nueva cámara](#Cómo-integrar-una-nueva-cámara).


### Resolución de dudas

Si presenta alguna duda o problema al momento de instalar o ejecutar la aplicación, no dude en ponerse en contacto con cualquiera de los autores de este software.

### Muchas gracias por llegar hasta aquí

Muchas gracias por usar este software. Esperamos sea de su agrado, y más importante, sea de suma utilidad para usted.

# Manual de Uso

## Te Motion Intel
**Versión:** 1.0

**Fecha:** 27 de mayo del 2024

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
   4. [Selección del tipo de prueba](#Selección-del-tipo-de-prueba)
   5. [Formulario del paciente](#Formulario-del-paciente)
   6. [Grabación](#Grabación)
   7. [Archivo guardado](#Archivo-guardado)
   8. [Archivo de logs](#Archivo-de-logs)
8. [Resolución de dudas](#Resolución-de-dudas)
9. [Actualizaciones](#Actualizaciones)

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

#### Descarga de la Aplicación
Para descargar **Te-motion Intel**, diríjase a releases y descargue la versión más reciente de la aplicación.

#### Instalación de componentes externos
Para poder sacar el máximo provecho al software, por favor instale:
- [Python 11](https://www.python.org/downloads/release/python-3119/)

  Si no sabe cómo instalar **python**, puede ver el siguiente [tutorial](https://elpythonista.com/como-instalar-python#:~:text=con%20c%C3%B3digo%20Java.-,%C2%BFC%C3%B3mo%20instalar%20el%20int%C3%A9rprete%20de%20Python%3F,-El%20int%C3%A9rprete%20de)

#### Proceso de Instalación
1. **Windows**:
   - Ejecute el archivo .exe descargado y listo, podrá usar con éxito la aplicación.
     
   ![1](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/2bab2a82-ec22-4c53-a864-0ed54bb24c3b)


#### Resolución de Problemas Comunes
- **No se puede ejecutar la aplicación**: Verifique que el antivirus de su sistema le permita ejecutar aplicaciones de externos.

### Funcionamiento

#### Tutorial

Cuando abra la aplicación, se encontrará con la siguiente pantalla:
![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/e81998a5-5add-411d-9c32-c6fe08f0f777)
> Inicio de la aplicación

Esta da inicio al pequeño tutorial en donde se le explicará cómo prepararse para que así la cámara pueda realizar las mediciones de manera correcta. En este punto tiene dos opciones a elegir, las cuales son: seguir el tutorial o saltarlo. Si presiona **Siguiente** se le enviará al segundo paso del tutorial, y si presiona **[Saltar](#Login)**, se le enviará a la pantalla del login.

Después de presionar el botón **Siguiente** veremos la siguiente pantalla:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/f3cf0b7c-a511-4792-a317-d74b930a1c74)
> Segundo paso del tutorial 

En esta pantalla se encontrará con la información que le dirá cómo debe estar su espacio para cuando quiera realizar la prueba de **"Análisis de marcha"**. Aquí se le informa a cuántos metros debe ubicar al paciente con respecto a la cámara y a cuántos centímetros debe ubicar el paciente respecto a la pared y la cámara respecto al suelo. A diferencia de la pantalla anterior, aquí contamos con 3 opciones. La primera de izquierda a derecha es **"Atrás"**, la cual nos permite dirigirnos al primer paso del tutorial. El botón **[Saltar](#Login)** sigue con su misma función y el botón **"Siguiente"** nos enviará al tercer paso del tutorial.

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/20b57151-aceb-434a-9b64-be047bd38e5c)
> Tercer paso del tutorial

En esta pantalla podemos encontrar la información sobre cómo debe estar su espacio para cuando quiera realizar la prueba de **"Timed Up and Go"**. Se le dice que debe seguir las mismas instrucciones que el paso anterior y que adicionalmente, tenga una silla a su disposición para que el paciente se pueda sentar. Además, aquí contamos con las mismas 3 opciones que la pantalla anterior, donde el botón **[Saltar](#Login)** conserva su función, mientras que el botón **"Atrás"** envía al segundo paso del tutorial y el botón **"Siguiente"** envía al cuarto paso del mismo.

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/d2599bca-9553-4353-9b9a-f176dde3bdae)
> Cuarto paso del tutorial

La presente pantalla nos da información acerca de cómo debe estar la luz del lugar donde vamos a realizar la medición. Se le hace saber de manera gráfica de qué manera se debe ver la grabación al momento de capturar un esqueleto, sin que se pierda ninguna articulación. Al igual que en la pantalla anterior, contamos con tres opciones. El botón **[Saltar](#Login)** conserva su función, el botón **"Atrás"** envía al tercer paso del tutorial y el botón **"Siguiente"** envía al quinto y último paso del tutorial.

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/04e1f650-4a19-421b-8d08-e26f643191b0)
> Quinto paso del tutorial

Esta pantalla hace alusión al último paso del tutorial. Aquí se le informa sobre cómo debe ser la vestimenta del paciente o persona que va a ser medida, esto con el fin de que al realizar la medición, la cámara no presente inconvenientes para capturar la información de las articulaciones. Se le recomienda remangar las vestimentas que generen ruido en la parte inferior de la persona, como lo podría ser un vestido o un pantalón demasiado ancho. A diferencia de las pantallas anteriores, aquí solo contamos con dos opciones. La que dice **"Atrás"** nos envía al cuarto paso del tutorial, mientras que la opción **"Empezar"** nos dirige a la pantalla de login o inicio de sesión de la aplicación.

#### Login

Ahora, después de haber saltado o visto todo el tutorial, llegaremos a la pantalla de login o inicio de sesión, la cual se ve así:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/7b7044cf-af4a-4017-887a-c372e942b4d7)
> Pantalla de login o inicio de sesión

En este punto usted podrá ingresar el nombre completo y el número de identificación de la persona que va a realizar la medición, esto para que en cada medición se tenga presente quién fue su respectivo medidor. El número de identificación no debe contener letras o puntos, este campo sólo acepta valores numéricos. En caso de que usted ingrese algún valor que no sea numérico y dé clic al botón **"Identificarse"**, se encontrará con el siguiente aviso:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/5fbce133-91f3-4bc2-97d4-ddae21f10efb)
> Aviso de valores mal diligenciados en el login

En caso contrario, si usted ingresó valores numéricos y presiona el botón **"Identificarse"**, será enviado a la siguiente pantalla, la cual le informa que debe conectar una cámara para poder continuar.

#### Identificación de cámara

Al principio, verá cómo la aplicación está identificando que tenga una cámara conectada, por lo que se encontrará con la siguiente pantalla:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/b9e508b4-1e04-4c64-ad7b-e5b4e35c6368)
> Pantalla que le informa que no se encuentra una cámara, pero que aún así se está buscando una

Si la aplicación no es capaz de identificar una cámara, seguirá buscando hasta que usted conecte una. En caso contrario, si se encuentra que hay una cámara conectada, la pantalla ahora mostrará la siguiente información:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/9fe95aa0-00c0-4c78-9d9e-807b806523a5)
> Pantalla que informa que ya se ha encontrado una cámara, por lo que ahora puede continuar

En ambas pantallas, tendrá la opción de ir de nuevo al login, esto a partir del botón **"<-"**. Por otro lado, en el momento en que se identifica una cámara, tendrá disponible la opción **"Siguiente"**, la cual al darle clic, le enviará a la pantalla para seleccionar el tipo de prueba que va a realizar.


#### Selección del tipo de prueba

Ahora podrá seleccionar el tipo de prueba que va a realizar, por lo que se le presenta la siguiente pantalla:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/a2656781-2c34-4ecc-87f6-39f47bb153d6)
> Pantalla donde se le presenta los dos tipos de medición que puede realizar para que seleccione uno

En este apartado usted tendrá la opción de elegir **"Análisis de marcha"** o **"Timed Up and Go"**, dependiendo de la medición que desea realizar. Sólo puede elegir una opción, y en caso de no seleccionar ninguna y presionar el botón **"Siguiente"**, se encontrará con el siguiente aviso:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/2c44bfd2-9bbc-4e34-b9e3-64286764340e)
> Aviso que informa que debe seleccionar un tipo de prueba si desea continuar

Si selecciona una opción y presiona el botón **"Siguiente"**, será enviado al siguiente apartado, el cual es el formulario del paciente.

#### Formulario del paciente

Ahora, se encontrará con una de las pantallas más importantes de la aplicación, que es la del formulario del paciente. Al iniciar, verá lo siguiente:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/0ae62c8e-51c5-4737-9867-b10b144fd54a)
> Inicio del formulario del paciente donde se ve el campo para ingresar su nombre

Aquí podrá ingresar el nombre del paciente o persona a la que se le va a realizar la medición. El apartado de **Nombre** tiene un **"*"** debido a que el campo es obligatorio. Después de ingresar este campo, puede bajar con el scroll del mouse o directamente presionar la tecla **tab** del teclado para dirigirse al siguiente campo del formulario, el cual es **Apellidos**

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/84250488-b965-410c-a1ab-3f71aa5c85de)
> Formulario del paciente donde se ve el campo para ingresar sus apellidos

En esta parte del formulario, tendrá que ingresar el/los apellido(s) del paciente. Al igual que el campo de texto anterior, el campo de **Apellidos** es obligatorio.
Después de diligenciar este campo de texto, puede bajar con el scroll del mouse o presionar la tecla **tab** del teclado para dirigirse al siguiente campo del formulario, el cual es **Cédula**

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/dd6b18cf-50f1-4cbe-ae66-5fcb3091d8bf)
> Formulario del paciente donde se ve el campo para ingresar su cédula

Aquí podrá ingresar la cédula o número de identificación del paciente. Al igual que los campos anteriormente diligenciados, este también es **obligarorio**. Después de ingresar este campo, puede bajar con el scroll del mouse o directamente presionar la tecla **tab** del teclado para dirigirse al siguiente campo del formulario, el cual es **Fecha de Nacimiento**, específicamente en el campo **día** o **DD**

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/e911af6d-8f8d-482b-a09d-6d72c5d7b71b)
> Formulario del paciente donde se ven los campos para ingresar la fecha de nacimiento. Está el día(DD), el mes(MM) y el año(AAAA)

En este momento del formulario, podrá ingresar la fecha de nacimiento del paciente que va a ser medido. Aquí podrá ingresar el **día(DD)**, el **mes(MM)** y el **año(AAAA)**, cada valor en un campo diferente. 
Es importante tener en cuenta que estos 3 campos sólo aceptan valores numéricos. Además, en esta parte, a medida que vaya ingresando valores, el cursor irá cambiando de campo automáticamente, esto significa que al ingresar dos valores en el campo de **día(DD)**, será directamente enviado al campo de **mes(MM)**, y aquí, al ingresar dos valores, será enviado al campo de **año(AAAA)**. En este último campo, al ingresar cuatro valores, será enviado inmediatamente al siguiente campo del formulario, el cual es **"Observaciones"**. Al igual que los campos anteriores, la Fecha de nacimiento es obligatoria.

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/c5aec06e-dc32-4f4b-9817-c19dde1e6049)
> Formulario del paciente donde se ve el campo de observaciones

Este ya es el último apartado del formulario. Aquí tendrá que ingresar información que pueda ser relevante del paciente que va a ser medido. Este campo también es obligatorio y no tiene limitaciones de escritura. 

Al final del formulario se encuentra el botón **"Guardar"**. Si presiona este botón sin haber llenado todos los campos del formulario, se encontrará con el siguiente aviso:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/c7ebf11d-02fe-4971-9164-675e01ea5539)
> Aviso que informa que antes de guardar la información del paciente, debe llenar todos los campos obligatorios

Asimismo, si al dar clic en **"Guardar"** ha llenado todos los campos del formulario pero presenta inconsistencias en la fecha, como por ejemplo que haya ingresado caracteres en lugar de números, que la fecha no tenga un formato válido o que el año de nacimiento del paciente sea menor a **1910**, se encontrará con el siguiente aviso:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/5274aafa-aa39-4883-956a-149b29da74db)
> Aviso que informa que la fecha de nacimiento del paciente no es válida

Si usted diligenció todos los campos y la fecha de nacimiento que ingresó es correcta, al dar clic en el botón **"Guardar"** será dirigido a la siguiente pantalla, la cual es:

#### Grabación

Esta pantalla es la más importante de toda la aplicación, ya que es aquí donde usted puede realizar el tracking de esqueletos de los pacientes. Lo que verá en un principio será:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/54b730a2-f243-47cc-beae-499a6cbc5cff)
> Pantalla de grabación

Aquí puede observar que esta pantalla tiene varios apartados. El primero y el principal es:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/5446d900-eb07-41e7-b31b-6dbec3683dd1)
> Apartado de grabación

Como puede observar, aquí se tiene una vista de lo que captura la cámara en tiempo real con su respectivo tracking al esqueleto de una persona. En la parte superior derecha, puede ver la información de los **Frames por segundo (FPS)** que se están capturando actualmente, y en la parte inferior, se puede ver un pequeño apartado con el botón ⏺️ en la mitad.
Si da clic en este botón, se empezará a tomar datos de las articulaciones que actualmente se están capturando, y además, este apartado ahora se verá así:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/3eb5dcf4-42a6-477b-9011-884a4355185b)
> Apartado de botones cuando se da clic al botón de iniciar grabación

Ahora aparecen 2 botones. El de la izquierda es el botón ⏹️, el cual me permite **parar** por completo la grabación y guardar los datos recolectados en un archivo en formato JSON. El otro botón es ⏸️, el cual me permite **pausar** la grabación.

Si doy clic al botón de **pausa**, ahora el apartado se verá así:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/b143198b-53fc-4f68-b199-c5e4d5a849eb)
> Apartado de botones cuando se le da clic al botón de pausar grabación

Ahora puede ver que el botón de pausa ha cambiado por un nuevo botón. Este nuevo botón es ⏺️, cuya función es la misma que anteriormente se mencionó (Empezar grabación). El otro botón sigue teniendo la misma función (Parar grabación). 

Es con esto que se llega al bucle. Si presiono ⏺️, este botón empieza la grabación y es reemplazado por el botón ⏸️. Si presiono el botón ⏸️, este pausa la grabación y es reemplazado por el botón ⏺️. Así sucesivamente hasta que tome la decisión de **parar** la captura o presionar el botón ⏹️ para guardar la medición. 

Al presionar el botón **parar**, lo primero que hace la aplicación es mostrar el siguiente mensaje:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/798d9969-ae62-464c-ab72-7ab9a54e2f83)
> Mensaje que informa que la aplicación está guardando el archivo en formato JSON con la información obtenida de la captura

Si presiono el botón de **parar** y no se pudo trackear u obtener la cantidad suficiente de articulaciones, la aplicación me enviará el siguiente aviso después del mensaje anterior:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/28ded502-2bb3-46c5-9a19-a49b6443cb23)
> Aviso que me informa que la grabación no capturó la cantidad suficiente de datos

Al mostrar este aviso, la aplicación te envía de nuevo al formulario del paciente y elimina cualquier información de la captura que haya sido guardada. 

Si por el contrario, la aplicación pudo trackear la cantidad suficiente de información, al presionar el botón **parar** y después de mostrar el mensaje de que se está guardando el archivo, se mostrará la siguiente información:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/e0d76a53-53b9-4417-8cb5-ce8fae4f4441)
> Mensaje que informa que se guardó con éxito el archivo JSON con la información de la medición realizada y dónde se guardó

Al guardar el archivo, la aplicación te enviará de nuevo al apartado de **[Selección del tipo de prueba](#Selección-del-tipo-de-prueba)** para que inicies una nueva captura con un nuevo paciente.

Otro apartado que tiene esta pantalla es el apartado de información. Este apartado es el que aparece al lado izquierdo de la pantalla

![1](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/5bbe2265-dd75-412a-9ffa-6760fa9e4abd)
> Apartado de información en la pantalla de grabación

Si usted da clic en cualquier zona de este apartado, se desplegará un menú hamburguesa, en donde podrá ver lo siguiente:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/24cb59ce-bd37-44cf-8d40-17422f4440b4)
> Apartado de información desplegado 

Aquí se puede dar clic a alguna de las tres opciones que se nos presentan. Si se da clic al botón **"Datos"** se desplegará la siguiente información:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/d21be99c-046c-4ee6-a7ae-45b4c3e40028)
> Apartado de información luego de dar clic en Datos

En este apartado se logra ver la información del paciente que está siendo medido, como su nombre y número de cédula o de identificación

Si se da clic en el botón **"Historial"** se mostrará el historial de pacientes que ha sido medido en el mismo dispositivo, esto de la siguiente forma:

IMAGEN DEL HISTORIAL

Si se da clic en el botón **"Info"** se le presentará al medidor la información sobre cómo tiene que preparar su espacio para la medición.

IMAGEN DE ESO

#### Archivo guardado

Después de que se haya terminado de hacer la captura y de guardar el archivo, podrás ir a la ruta que te mostró la aplicación para encontrarlo. El nombre de este archivo se compone de la siguiente forma: **Nombre del Paciente - [Fecha de captura]_id de la captura.json**. 

En tu explorador de archivos se verá de la forma:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/204fa40d-2872-4049-9188-5e3d522b4569)
> Archivo en formato JSON guardado luego de terminar una captura

#### Archivo de logs

Para que puedas tener un completo conocimiento de los errores que se puedan presentar en la aplicación, dispones de un directorio llamado **logs**, que se encuentra en la misma dirección donde está el ejecutable del proyecto. Dentro de este directorio, encontrarás archivos que dentro de sí, tendrán los errores que pudieron ocurrir mientras el aplicativo se encontraba en funcionamiento. Estos errores son útiles para reconocer dónde se presentó el error y cómo arreglarlo.

Los archivos **logs** se verán así:

![image](https://github.com/i2tResearch/mhealth-emotion-intel/assets/72984873/4ade60e8-5c4d-4d6d-934c-75b56e58c538)
> Archivo log generado por la aplicación

### Resolución de dudas

Si presenta alguna duda o problema al momento de instalar o ejecutar la aplicación, no dude en ponerse en contacto con cualquiera de los autores de este software.

### Actualizaciones

Este software puede presentar actualizaciones después de algunos meses, por lo que le recomendamos que esté atent@ de alguna nueva funcionalidad o resolución de bugs que se puedan dar.


### Muchas gracias por llegar hasta aquí

Muchas gracias por usar este software. Esperamos sea de su agrado, y más importante, sea de suma utilidad para usted.

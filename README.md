# 📎 Práctica de Laboratotio 1 - Unidades Booteables
## PROCESO DE BOOTEO
## Proceso de booteo con Rufus y ventoy 
Rufus y ventoy son programas gratuitos y de código abierto para Windows que sirven para crear memorias USB booteables.
El primer paso esta en descargar rufus y ventoy  desde la pagina, teniendo la  memoria conectada se abre rufus y se selecciona la usb que se quierfe bootear  es importante anteriormente tener la imagen  o archivo ISO descargado. Para terminar selecciona la imagen iso que vas a usar  y ya despues podras  tener una usb booteable este mismo proceso se realiza para bootear la usb con ventoy la diferencia esta en que con ventoy podemos tener varias ISOs
## BOOTLOADER y GRUB
Cuando un PC arranca, la BIOS/UEFI busca un dispositivo (disco duro, USB, CD) que tenga instrucciones de arranque.
Ahí es donde entra el bootloader (cargador de arranque).
 ## Funciones del bootloader en la memoria USB:
  -Recibir el control inicial de la BIOS/UEFI cuando se arranca desde la memoria.
  -Identificar y preparar el hardware básico (memoria RAM, discos, teclado, etc.).
  -Cargar el núcleo (kernel) del sistema operativo desde la memoria USB.
  -Transferir el control al sistema operativo para que termine de arrancar.
Sin bootloader, la memoria no sabría qué hacer después de que la BIOS/UEFI la elige, y el PC mostraría error de arranque.

## GRUB
GRUB (GRand Unified Bootloader) es uno de los bootloaders más usados, especialmente en sistemas Linux.
Características principales:
  -Permite arrancar distintos sistemas operativos (ejemplo: Linux, Windows, BSD) en un mismo PC (multiboot).
  -Tiene un menú interactivo para elegir qué sistema iniciar.
  -Puede cargar kernels de Linux directamente.
  -Es muy flexible y configurable mediante un archivo de configuración (grub.cfg).
En muchos USB booteables de Linux creados con Rufus o Ventoy, el bootloader que se instala o se ejecuta es GRUB.


## 📂 Sistemas de archivos compatibles

Los sistemas de archivos son estructuras utilizadas por los sistemas operativos para organizar, almacenar y gestionar archivos en dispositivos de almacenamiento como discos duros, USB o SSD. Definen cómo se guardan los datos, cómo se accede a ellos y cómo se manejan aspectos como el tamaño máximo de archivos o la seguridad.
Los "sistemas de archivos compatibles" se refieren a aquellos que pueden ser leídos y escritos en múltiples sistemas operativos (como Windows, Linux y macOS) sin requerir software adicional o con mínima configuración. Esto es útil para compartir datos entre plataformas diferentes, evitando problemas de incompatibilidad. Por ejemplo, un USB formateado en un sistema compatible puede usarse en cualquier computadora sin issues.








### 🔑 Tipos de Sistemas de Archivos Compatibles

#### 🟦 FAT32 (File Allocation Table 32)

Se caracterizan por ser uno de los sistemas mas antiguos y simples, introducido en el año 1996, Este organiza los archivos en una tabla de asignacion y es ideal para dispositivos portatiles como la USB o tarjetas SD.
Tiene una compatibilida alata ya que soporta la mayorioa de Windows, macOS (lectura/escritura), Linux (lectura/escritura nativa) y muchos dispositivos como cámaras o consolas. Y las limitaciones que precenta es que el tamaño maximo de archivo es de 4GB, con volumen de particion siendo de 8TB, es recomendado para el intercambio de archivos pequeños entre plataformas, pero no es recomensdarle utilizarlo para diiscos duros internos sa que carece de permisos para el sistema operativo de Windows.

  

#### 🟩 exFAT (Extended File Allocation Table)



Es la Evolución de FAT32, lanzada en 2006 por Microsoft. Diseñada para almacenamiento flash como USB y SSD, soporta archivos grandes y es ligera como FAT32. Pero si supera las limitaciones en el tamaño máximo de archivo/volumen muy alto (hasta 128 PB), pero menos seguridad que otros.Su compatibilidad es buena para Windows (7+ nativo), soporta todas las versiones de macOS soportan escritura y lectura de las unidades exFAT, Linux (con drivers o soporte reciente en kernels nuevos), esto facilita el uso de unidades en ambietes de trabajo con sistemas operativos mixtos.Se recomienda para USB con archivos grandes (videos, backups) entre Windows y macOS.


#### 🟥 NTFS (New Technology File System):

Es un sistema nativo de Windows desde 1993, con características avanzadas como compresión, encriptación y permisos detallados. La ventaja mas significativa es que los limites para el tamaño de los archivos y volumenes son tan grandes que el tamaño máximo es de archivo 16 TB (en práctica), volumen hasta 256 TB, pero devido a sus caracteristicas mas avanzadas ocupa mas almacenamiento no es recomendable para discos y memorias muy pequeñas en cuanto a la compatibilidad es excelente en Windows, macOS (lectura nativa, escritura con software como Paragon) y Linux (lectura/escritura con ntfs-3g).Es recomendado usar para discos internos en Windows, o con herramientas para cross-platform.

#### 🟨 ext4 (Fourth Extended Filesystem):
Es el sistema de archivos estándar en la mayoría de las distribuciones de Linux, evolución de ext3 y ext2, introducido en 2008. Se destaca por su robustez, rendimiento y funcionalidades como el journaling (registro por diario), que ayuda a prevenir la pérdida de datos en caso de fallos del sistema. Los límites son muy generosos, con un tamaño máximo de archivo de 16 TB y un tamaño máximo de volumen de 1 EB (Exabyte). Sin embargo, su principal limitación es la compatibilidad: es excelente y nativo en Linux, pero Windows y macOS no ofrecen soporte nativo para lectura o escritura, lo que requiere el uso de software de terceros para acceder a ellos. Es altamente recomendado para servidores, ordenadores con Linux y cualquier entorno donde la estabilidad y el rendimiento en sistemas basados en Linux sean críticos.

#### 🟪 APFS (Apple File System):
Desarrollado por Apple y lanzado en 2017, APFS es el sistema de archivos nativo para macOS, iOS, tvOS y watchOS. Fue diseñado para la era de las unidades de estado sólido (SSD) y el almacenamiento flash, ofreciendo optimizaciones específicas para ellos. Sus características avanzadas incluyen clones instantáneos (instantáneas), encriptación nativa, espacios compartidos y un manejo eficiente del espacio. En cuanto a sus límites, el tamaño máximo de archivo y volumen es de 8 EB (Exabytes), lo que lo hace adecuado para el almacenamiento de datos a gran escala. Su compatibilidad es exclusivamente dentro del ecosistema de Apple; es completamente nativo y optimizado para dispositivos macOS, iPhone, iPad, Apple TV y Apple Watch, pero no es compatible de forma nativa con Windows o Linux, lo que limita su uso en entornos multiplataforma fuera del software de terceros. Se recomienda su uso para todos los discos internos y externos de dispositivos Apple, aprovechando al máximo sus características de rendimiento y seguridad.

<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/49ed356e2a224432f813c62fde904aa5e0c0364b/Imagenes%20Digitales/FAT_EX_NTF%20.jpg" width="400" />
</p>


### 📊 Comparativa Rápida

| Sistema  | Compatibilidad | Tamaño Máx. Archivo | Uso Recomendado | Seguridad y Permisos|
|----------|------------------|-----------------------|-------------------|-------------------|
| **FAT32** | Windows (✔), macOS (✔), Linux (✔), otros dispositivos (✔) | 4 GB | USB y memorias para máxima compatibilidad |No, carece de características de seguridad y permisos modernos.|
| **NTFS** | Windows (✔), macOS (lectura ✔, escritura ❌), Linux (✔ con ntfs-3g) | 16 TB | Discos internos en Windows | 	Sí, soporte para permisos de usuario, encriptación y compresión.|
| **exFAT** | Windows (✔), macOS (✔), Linux (✔), muchos otros dispositivos | 16 TB | Almacenamiento portátil como memorias USB y tarjetas SD | No, no tiene permisos de usuario y es menos resistente a la corrupción de datos.|
| **ext4** | 	Linux (✔), Windows/macOS (❌ sin software)| 16 TB | Servidores y PCs con Linux | Sí, robusto sistema de permisos de usuario.|
APFS	|macOS (✔), Windows/Linux (❌ sin software) |	8 EB |	Discos internos de dispositivos Apple (Mac, iPhone, iPad) |	Sí, soporte para encriptación de disco completo y permisos de usuario.|

---


## 💽 Estructura de Particiones

### 💾 ¿Que es una Partición?

Una Partición es una división lógica y una herramienta de un **Disco de Almacenamiento (USB, SSD, Disco Duro)** que permite partir o dividir la memoria en espacios de manera Idependiente, permitiendo organizar y gestionar datos, multiples **Sistemas Operativos**, optimizar el rendimiento y seguridad del Almacenamiento. Cada partición funciona como un disco undeoenduente y se identifica en una **Tabla de Particiones** en la cual se guarda la información.

<img width="1358" height="219" alt="Captura de pantalla 2025-08-18 160857" src="https://github.com/user-attachments/assets/ce7cd76f-943b-48ff-a812-6cabb943a9b9" />

En la imagen se puede apreciar un buen ejemplo de particiones: por un lado, un disco SSD que contiene el sistema de arranque y Windows; y por otro, un disco duro mecánico dividido en varias particiones, algunas destinadas al almacenamiento de datos y otras al sistema operativo Ubuntu.

### 📚 Estructura de Particiones

Cuando se realiza una Partición la información de esta se guarda en un sector especial del disco, que depende del **Esquema de Partición** usado.

| Estructura | Características | Ventajas |
| ------------- | ------------- |------------- |
| **MBR (MASTER BOOT RECORT)** | (Ocupa **[512 bytes]** en el sector primario del disco.) (**Máx. 4** Particiónes Primarias.) (Una de las Particiones puede ser extendida a una **Unidad Lógica**.) (**Máx. 2TB** por Partición.) |Compatibilidad con **Sistemas Antiguos** y Sencillo de Implementar.|
| **GPT(GUID PRTITION TABLE)**  | (Estandar Moderno **UEFI**.) (**128** Particiones Primarias) (Soporta Discos de **9.4 ZB**) (**Copias de Seguridad** de la Tabla) | Soporta **Discos más pesados**, mayor **Seguridad e Integridad** y Identicadores únicos **GUID**. |

### 📌 Tipos de Particiones

Existen distintos tipos de particiones dependiendo de su **Esquema (MBR o GPT).**

| Tipo de Partición | Descripción | Restricción |
| ------------- | ------------- | ------------- |
| **Primaria**  | Partición Basica que permite Almacenar S.O. o Datos  | **Máx. 4** Primarias de MBR |
| **Extendida**  | Contenedor de Particiones Adicionales   | **Máx. 1 Disco** y no Almacena Datos directamente |
| **Lógica**  | Subdivisiones en la Extendida  | No pueden trabajar **Arranques** |

📎 En **GPT** solo existen particiones primarias, eliminando la necesidad de extendidas y lógicas.

---

## 📦 Instalar Paqueteria de Imagen Windows y Ubuntu
- Para la **Imagen de Ubuntu** la podremos encontrar en su pagina principal **[https://ubuntu.com/download]**, siempre escogeremos la version nueva o la que desee descargar.

<img width="1308" height="362" alt="image" src="https://github.com/user-attachments/assets/456b1ba8-62ba-4d26-9441-e565f1d9c214" />

<img width="1747" height="427" alt="image" src="https://github.com/user-attachments/assets/4fc5e199-4777-4f6f-bc10-ec0c64766713" />

- Para la **Imagen de Windows** en su ultima versión lo encontrremos en su pagina principal **[https://www.microsoft.com/es-es/software-download/windows11]**.
  
<img width="1168" height="583" alt="image" src="https://github.com/user-attachments/assets/069e262f-0a73-4974-bc6f-353ec702034d" />

- Luego debemos escoger el idioma del Sistema Opertaivo que deseamos descargar y luego de escogerlo nos dejara instalar nuestro **Sistema Operativo**.

<img width="1201" height="365" alt="image" src="https://github.com/user-attachments/assets/bd972c9e-1a28-45ec-94d9-3a53415a1416" />

<img width="810" height="145" alt="image" src="https://github.com/user-attachments/assets/fe3e4fc6-47aa-4f90-b1b5-94a7507e3f2a" />

- Y al final ya tendremos nuestros dos imagenes de los **Sistemas Operativos** que usaremos para esta practica.

<img width="801" height="187" alt="image" src="https://github.com/user-attachments/assets/c415cf34-4745-49fa-9b0d-f3e115792542" />

---
## 🔑 Creación de USB booteable con Rufus

#### **Descarga de la herramienta**
 - Se descargó la utilidad Rufus en el computador. Para este procedimiento se utilizó la versión 4.9.
   
<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/379c5f3c195d6558917f83d0375aea3031172716/image.png" width="400" />
</p>




#### **Configuracion de la instalación**
 - Una vez ejecutado Rufus, en el campo “Dispositivo” se seleccionó la memoria USB que se iba a formatear.
 - Posteriormente, en la opción “Selección de arranque” se cargó la imagen ISO de Ubuntu previamente
 - En el apartado de esquema de partición se eligió GPT, dado que el sistema de destino utiliza firmware UEFI moderno.
 - Se hizo clic en “Empezar” y se esperó a que Rufus finalizara la creación de la memoria USB booteable.
Durante este proceso, el contenido previo de la memoria fue eliminado.


<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/49ed356e2a224432f813c62fde904aa5e0c0364b/Imagenes%20Digitales/Configuracion_rufus.png" width="400" />
</p>

#### Resultado final
 - Una vez completada la instalación, la memoria quedó configurada como un medio de arranque de Ubuntu, lista para ser utilizada.

<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/379c5f3c195d6558917f83d0375aea3031172716/imagen_2025-08-17_020036485.png" width="400" />
</p>


#### Arranque desde la USB
 - Finalmente, se reinició el computador, se accedió al menú UEFI/BIOS y se seleccionó la memoria USB como dispositivo de arranque.

<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/49ed356e2a224432f813c62fde904aa5e0c0364b/Imagenes%20Digitales/Potada_UEFI.png" width="400" />
</p>

---

## 🔑 Creación de USB booteable con Ventoy

#### **Descarga de Ventoy**

 - Se busca la pagina de **Ventoy (https://www.ventoy.net/en/download.html)** y descargamos el archivo segun nuestro **Sistema Operativo**, en nuestro caso escogemos el Ventoy 1.1.07 para Windows.
 - 
<img width="1346" height="492" alt="image" src="https://github.com/user-attachments/assets/b722d6c4-bda3-4ffd-a000-910e8a939ff0" />

- Luego de descargar el archivo, se debe descomprimir la carpeta.

<img width="941" height="551" alt="image" src="https://github.com/user-attachments/assets/8005d11f-fe90-440f-8751-484d0b5276ca" />

- Al ingresar a la carpeta podremos observar varios archivos y carpetas, el de interes para descargar Ventoy es la aplicación del**Instalador Ventoy2Disk**

<img width="920" height="446" alt="image" src="https://github.com/user-attachments/assets/60bb6b42-3653-4d36-8c0c-c3b003588d4f" />

<img width="920" height="446" alt="image" src="https://github.com/user-attachments/assets/d786251f-2417-4bb0-8cc8-86f97a6ec1de" />

📎 Recomendamos ver el siguiente paso antes de Iniciar la Aplicación de **Ventoy2Disk**

#### **Booteable de Memoria con Ventoy**

- Antes de iniciar la Aplicacion de **Ventoy2Disk**, recomendamos ingresar la memoria (USB, PENDRIVE, UNIDAD EXTERNA) para que al momento de iniciar el programa este lo pueda reconocer y luego por segurdad **Ejecutaremos como Administrador**.

<img width="800" height="666" alt="image" src="https://github.com/user-attachments/assets/cd3ef5a9-005b-4740-bd16-e6809ae37e1f" />

📎 La memoria de uso dependera de los Sistemas Operativos que desee usar, en nuestro caso usaremos una de **16GB**, ya que las **Imagenes de los Sistemas Operativos** superan los 10GB 

- Al iniciar la Aplicación se nos abrira una ventada en la cual podremos **Visualizar el instalador y la Memoria a Elección**, tambien tendremos como adiccional la configuración del idioma y más opciones.

<img width="546" height="433" alt="image" src="https://github.com/user-attachments/assets/bb2c567e-db45-4490-9bca-4a2061c75340" />

- En el **Recuadro Azul escogeremos nuestra Memoria a Bootear**, en nuestro caso escogeremos la de **E: 16 GB**.
- Luego en el **Recuadro Rojo le daremos Install.**

<img width="546" height="433" alt="image" src="https://github.com/user-attachments/assets/c4ccd4ee-e4ff-4a4c-bbbd-71a0385390b5" />

- Despues de iniciar la instalación el programa pedira unas opciones, en las cuales aceptaremos para completar la correcta instalacción.

<img width="542" height="435" alt="image" src="https://github.com/user-attachments/assets/eb51eee4-df18-4022-a2b8-e12df71caabc" />

<img width="543" height="430" alt="image" src="https://github.com/user-attachments/assets/41555bff-ed9d-45ce-badf-aab2efa7c9bb" />

<img width="542" height="441" alt="image" src="https://github.com/user-attachments/assets/a71cbb82-bf1c-4314-8f9a-06ce14c4b312" />

- Para asegurarnos de que la instalación se realizó correctamente, Ventoy mostrará una ventana de confirmación y el sistema de nuestro PC notificará que la memoria USB ya cuenta con Ventoy

<img width="453" height="206" alt="image" src="https://github.com/user-attachments/assets/8a6a9620-f070-4d8e-a4dd-7407f4b48531" />

<img width="500" height="188" alt="image" src="https://github.com/user-attachments/assets/dfe6bbf5-d537-4874-8952-1f3c7c1026b1" />

- Luego de todos los pasos anteriores, lo unico que falta es agregar nuestros dos **Sistemas Operativos** a la memoria de Ventoy, en este caso guardaremos el **Windows 11 y el Ubuntu**

<img width="338" height="83" alt="image" src="https://github.com/user-attachments/assets/9246d637-bc86-41ce-aa70-f9455f1b2e68" />

<img width="1703" height="417" alt="image" src="https://github.com/user-attachments/assets/6afa06fa-76c5-43a5-9a31-14a2cd5b3994" />

- Y ya tendriamos nuestras imagenes en la **Memoria de Ventoy :D**.

<img width="758" height="661" alt="image" src="https://github.com/user-attachments/assets/a5075b18-e8b5-44be-a90d-b09569dea893" />
  
---
## 💻 Instalacion de UBUNTU
 - Después de preparar la memoria USB booteable con Rufus y configurarla como dispositivo de arranque en la BIOS/UEFI, se inició el instalador de Ubuntu.
<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/5a0ce5e26dd799b8994fd1535eea0f554614746d/Imagenes%20Digitales/Imagen%20de%20WhatsApp%202025-08-17%20a%20las%2003.11.21_11f1cf7d.jpg" width="400" />
</p>

 - Durante el asistente de instalación se siguieron los pasos correspondientes hasta llegar a la sección de particionado del disco.
 - Finalmente, tras un tiempo de espera en el que se copiaron los archivos y se configuró el sistema, la instalación se completó exitosamente, quedando listo para reiniciar el equipo e iniciar Ubuntu desde el gestor de arranque.
<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/4ae00ff856e059aebb83632f553680ec1885a451/Imagenes%20Digitales/Instalacion_completada.jpg" width="400" />
</p> 



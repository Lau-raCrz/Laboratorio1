# **Laboratotio 1 - Unidades Booteables**
## **Primer Punto**
>[!IMPORTANT]
>Luego agrego más :D
### **Particiones y sus Estructuras**
> Las particiones son uon una herramienta en la cual los Discos de Almacenamiento (USB, SSD, Disco Duro), se pueden paartir o dividir sus archivos en dos o mas secciones llamadas particiones. Esta division permite mejorar la organización de datos, instalar múltiples sistemas operativos y optimiza el rendimiento y la seguridad de nuestro almacenamiento.
### **Tipos de Particiones**
> :D

##  Tercer Punto

### Sistemas de archivos compatibles

Los sistemas de archivos son estructuras utilizadas por los sistemas operativos para organizar, almacenar y gestionar archivos en dispositivos de almacenamiento como discos duros, USB o SSD. Definen cómo se guardan los datos, cómo se accede a ellos y cómo se manejan aspectos como el tamaño máximo de archivos o la seguridad.
Los "sistemas de archivos compatibles" se refieren a aquellos que pueden ser leídos y escritos en múltiples sistemas operativos (como Windows, Linux y macOS) sin requerir software adicional o con mínima configuración. Esto es útil para compartir datos entre plataformas diferentes, evitando problemas de incompatibilidad. Por ejemplo, un USB formateado en un sistema compatible puede usarse en cualquier computadora sin issues.


## 🔑 Tipos de Sistemas de Archivos Compatibles

#### 🟦 FAT32 (File Allocation Table 32)

Se caracterizan por ser uno de los sistemas mas antiguos y simples, introducido en el año 1996, Este organiza los archivos en una tabla de asignacion y es ideal para dispositivos portatiles como la USB o tarjetas SD.
Tiene una compatibilida alata ya que soporta la mayorioa de Windows, macOS (lectura/escritura), Linux (lectura/escritura nativa) y muchos dispositivos como cámaras o consolas. Y las limitaciones que precenta es que el tamaño maximo de archivo es de 4GB, con volumen de particion siendo de 8TB, es recomendado para el intercambio de archivos pequeños entre plataformas, pero no es recomensdarle utilizarlo para diiscos duros internos sa que carece de permisos para el sistema operativo de Windows.

  
---

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


##  Instalacion de UBUNTU
 - Después de preparar la memoria USB booteable con Rufus y configurarla como dispositivo de arranque en la BIOS/UEFI, se inició el instalador de Ubuntu.
<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/5a0ce5e26dd799b8994fd1535eea0f554614746d/Imagenes%20Digitales/Imagen%20de%20WhatsApp%202025-08-17%20a%20las%2003.11.21_11f1cf7d.jpg" width="400" />
</p>
 - Durante el asistente de instalación se siguieron los pasos correspondientes hasta llegar a la sección de particionado del disco.



#**Faltaaa explicacion de Particion**

 
 - Finalmente, tras un tiempo de espera en el que se copiaron los archivos y se configuró el sistema, la instalación se completó exitosamente, quedando listo para reiniciar el equipo e iniciar Ubuntu desde el gestor de arranque.
<p align="center">
  <img src="https://github.com/Lau-raCrz/Laboratorio1/blob/4ae00ff856e059aebb83632f553680ec1885a451/Imagenes%20Digitales/Instalacion_completada.jpg" width="400" />
</p> 



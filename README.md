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

> Los sistemas de archivos son estructuras utilizadas por los sistemas operativos para organizar, almacenar y gestionar archivos en dispositivos de almacenamiento como discos duros, USB o SSD. Definen cómo se guardan los datos, cómo se accede a ellos y cómo se manejan aspectos como el tamaño máximo de archivos o la seguridad.
Los "sistemas de archivos compatibles" se refieren a aquellos que pueden ser leídos y escritos en múltiples sistemas operativos (como Windows, Linux y macOS) sin requerir software adicional o con mínima configuración. Esto es útil para compartir datos entre plataformas diferentes, evitando problemas de incompatibilidad. Por ejemplo, un USB formateado en un sistema compatible puede usarse en cualquier computadora sin issues.


## 🔑 Tipos de Sistemas de Archivos Compatibles

### 🟦 FAT32 (File Allocation Table 32)

Se caracterizan por ser uno de los sistemas mas antiguos y simples, introducido en el año 1996, Este organiza los archivos en una tabla de asignacion y es ideal para dispositivos portatiles como la USB o tarjetas SD.
Tiene una compatibilida alata ya que soporta la mayorioa de Windows, macOS (lectura/escritura), Linux (lectura/escritura nativa) y muchos dispositivos como cámaras o consolas. Y las limitaciones que precenta es que el tamaño maximo de archivo es de 4GB, con volumen de particion siendo de 8TB, es recomendado para el intercambio de archivos pequeños entre plataformas, pero no es recomensdarle utilizarlo para diiscos duros internos sa que carece de permisos para el sistema operativo de Windows.

  
---

### 🟩 exFAT (Extended File Allocation Table)



Es la Evolución de FAT32, lanzada en 2006 por Microsoft. Diseñada para almacenamiento flash como USB y SSD, soporta archivos grandes y es ligera como FAT32. Pero si supera las limitaciones en el tamaño máximo de archivo/volumen muy alto (hasta 128 PB), pero menos seguridad que otros.Su compatibilidad es buena para Windows (7+ nativo), soporta todas las versiones de macOS soportan escritura y lectura de las unidades exFAT, Linux (con drivers o soporte reciente en kernels nuevos), esto facilita el uso de unidades en ambietes de trabajo con sistemas operativos mixtos.Se recomienda para USB con archivos grandes (videos, backups) entre Windows y macOS.


### 🟩 NTFS (New Technology File System):

Es un sistema nativo de Windows desde 1993, con características avanzadas como compresión, encriptación y permisos detallados. La ventaja mas significativa es que los limites para el tamaño de los archivos y volumenes son tan grandes que el tamaño máximo es de archivo 16 TB (en práctica), volumen hasta 256 TB, pero devido a sus caracteristicas mas avanzadas ocupa mas almacenamiento no es recomendable para discos y memorias muy pequeñas en cuanto a la compatibilidad es excelente en Windows, macOS (lectura nativa, escritura con software como Paragon) y Linux (lectura/escritura con ntfs-3g).Es recomendado usar para discos internos en Windows, o con herramientas para cross-platform.



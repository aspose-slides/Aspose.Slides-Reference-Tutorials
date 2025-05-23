---
"date": "2025-04-18"
"description": "Aprenda a mejorar sus presentaciones personalizando viñetas SmartArt con imágenes usando Aspose.Slides para Java. Siga esta guía paso a paso para lograr un aspecto profesional."
"title": "Cómo personalizar viñetas SmartArt con imágenes usando Aspose.Slides para Java | Guía paso a paso"
"url": "/es/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo personalizar viñetas SmartArt con imágenes usando Aspose.Slides para Java

## Introducción

Crear presentaciones visualmente atractivas es crucial para captar la atención del público y comunicar eficazmente el mensaje. Un reto común al diseñar diapositivas es mejorar las viñetas en los gráficos SmartArt mediante imágenes personalizadas. Este tutorial le guiará para configurar una imagen como formato de relleno de viñetas en nodos SmartArt con Aspose.Slides para Java, lo que le permitirá mejorar sus presentaciones de forma profesional.

**Lo que aprenderás:**
- Configuración y uso de Aspose.Slides para Java
- Personalizar viñetas con imágenes en gráficos SmartArt
- Aplicaciones prácticas de esta personalización
- Solución de problemas comunes

Antes de sumergirnos en la implementación, asegúrese de tener todo listo.

## Prerrequisitos

Para seguir este tutorial, asegúrese de cumplir los siguientes requisitos previos:

1. **Bibliotecas y dependencias**Necesitará la biblioteca Aspose.Slides para Java versión 25.4 o posterior.
2. **Configuración del entorno**:
   - Un IDE compatible como IntelliJ IDEA o Eclipse
   - JDK 16 instalado en su máquina
3. **Requisitos previos de conocimiento**:Familiaridad con la programación Java y la estructura básica de presentaciones de PowerPoint.

## Configuración de Aspose.Slides para Java

Para comenzar, incluya la biblioteca Aspose.Slides en su proyecto utilizando uno de los siguientes métodos:

### Experto

Añade esta dependencia a tu `pom.xml` archivo:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Incluye esto en tu `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa

Alternativamente, descargue la biblioteca directamente desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

**Pasos para la adquisición de la licencia**Aspose ofrece una licencia de prueba gratuita, ideal para probar sus funciones. Puede solicitar una licencia temporal o adquirir una para eliminar las limitaciones de evaluación.

Para inicializar y configurar su entorno, cree una instancia del `Presentation` clase como se muestra:

```java
Presentation presentation = new Presentation();
```

## Guía de implementación

Esta sección dividirá el proceso en pasos manejables y explicará cómo lograr la funcionalidad deseada.

### Cómo agregar SmartArt con relleno de viñetas personalizado

#### Descripción general

Comenzaremos agregando una forma SmartArt a su diapositiva y personalizando sus viñetas usando un relleno de imagen.

#### Instrucciones paso a paso

**1. Inicializar el objeto de presentación**

```java
Presentation presentation = new Presentation();
```

*Objetivo*:Inicializa una nueva instancia de presentación donde agregarás los gráficos SmartArt.

**2. Agregar forma SmartArt**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Explicación*:Esta línea agrega una nueva forma SmartArt a la primera diapositiva en la posición (x=10, y=10) con dimensiones de 500x400 píxeles. `VerticalPictureList` El diseño se utiliza para la alineación vertical.

**3. Acceda y personalice el relleno de viñetas**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Objetivo*: Comprueba si el nodo tiene un `BulletFillFormat` propiedad. Si es así, carga una imagen y la establece como relleno para las viñetas.
*Parámetros*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`:La ruta a su archivo de imagen.
  - `PictureFillMode.Stretch`:Garantiza que la imagen llene completamente el área de la viñeta.

**4. Guarda tu presentación**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
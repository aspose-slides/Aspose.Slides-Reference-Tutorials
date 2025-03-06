---
title: Cambiar datos de objetos OLE en PowerPoint
linktitle: Cambiar datos de objetos OLE en PowerPoint
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo cambiar datos de objetos OLE en PowerPoint usando Aspose.Slides para Java. Una guía paso a paso para actualizaciones eficientes y sencillas.
weight: 14
url: /es/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introducción
Cambiar los datos de los objetos OLE en presentaciones de PowerPoint puede ser una tarea crucial cuando necesita actualizar el contenido incrustado sin editar manualmente cada diapositiva. Esta guía completa lo guiará a través del proceso utilizando Aspose.Slides para Java, una poderosa biblioteca diseñada para manejar presentaciones de PowerPoint. Si es un desarrollador experimentado o recién está comenzando, este tutorial le resultará útil y fácil de seguir.
## Requisitos previos
Antes de profundizar en el código, asegurémonos de que tiene todo lo que necesita para comenzar.
1.  Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema. Puedes descargarlo desde[sitio de oráculo](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides para Java: descargue la última versión desde[Página de descarga de Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): puede utilizar cualquier IDE de Java, como IntelliJ IDEA, Eclipse o NetBeans.
4.  Aspose.Cells para Java: esto es necesario para modificar los datos incrustados dentro del objeto OLE. Descárgalo desde[Página de descarga de Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  Archivo de presentación: tenga listo un archivo de PowerPoint con un objeto OLE incrustado. Para este tutorial, pongámosle el nombre`ChangeOLEObjectData.pptx`.
## Importar paquetes
Primero, importemos los paquetes necesarios en su proyecto Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Ahora, dividamos el proceso en pasos simples y manejables.
## Paso 1: cargue la presentación de PowerPoint
Para comenzar, necesita cargar la presentación de PowerPoint que contiene el objeto OLE.
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Paso 2: acceda a la diapositiva que contiene el objeto OLE
A continuación, obtenga la diapositiva donde está incrustado el objeto OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Paso 3: busque el objeto OLE en la diapositiva
Repita las formas de la diapositiva para localizar el objeto OLE.
```java
OleObjectFrame ole = null;
// Atravesando todas las formas para Ole frame
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Paso 4: extraiga los datos incrustados del objeto OLE
Si se encuentra el objeto OLE, extraiga sus datos incrustados.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Paso 5: Modifique los datos incrustados usando Aspose.Cells
Ahora, use Aspose.Cells para leer y modificar los datos incrustados, que en este caso probablemente sean un libro de Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modificar los datos del libro de trabajo
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Paso 6: guarde los datos modificados en el objeto OLE
Después de realizar los cambios necesarios, guarde el libro modificado nuevamente en el objeto OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Paso 7: guarde la presentación actualizada
Finalmente, guarde la presentación de PowerPoint actualizada.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusión
Actualizar datos de objetos OLE en presentaciones de PowerPoint usando Aspose.Slides para Java es un proceso sencillo una vez que lo divide en pasos simples. Esta guía lo guió a través de la carga de una presentación, el acceso y la modificación de datos OLE incrustados y el guardado de la presentación actualizada. Con estos pasos, puede administrar y actualizar de manera eficiente el contenido incrustado en sus diapositivas de PowerPoint mediante programación.
## Preguntas frecuentes
### ¿Qué es un objeto OLE en PowerPoint?
Un objeto OLE (vinculación e incrustación de objetos) permite incrustar contenido de otras aplicaciones, como hojas de cálculo de Excel, en diapositivas de PowerPoint.
### ¿Puedo utilizar Aspose.Slides con otros lenguajes de programación?
Sí, Aspose.Slides admite varios lenguajes, incluidos .NET, Python y C.++.
### ¿Necesito Aspose.Cells para modificar objetos OLE en PowerPoint?
Sí, si el objeto OLE es una hoja de cálculo de Excel, necesitará Aspose.Cells para modificarlo.
### ¿Existe una versión de prueba de Aspose.Slides?
 Sí, puedes conseguir un[prueba gratis](https://releases.aspose.com/) para probar las características de Aspose.Slides.
### ¿Dónde puedo encontrar la documentación de Aspose.Slides?
 Puede encontrar documentación detallada en el[Página de documentación de Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

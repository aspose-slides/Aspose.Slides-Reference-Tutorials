---
"description": "Aprenda a cambiar los datos de objetos OLE en PowerPoint con Aspose.Slides para Java. Una guía paso a paso para realizar actualizaciones de forma eficiente y sencilla."
"linktitle": "Cambiar datos de objetos OLE en PowerPoint"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Cambiar datos de objetos OLE en PowerPoint"
"url": "/es/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar datos de objetos OLE en PowerPoint

## Introducción
Cambiar los datos de objetos OLE en presentaciones de PowerPoint puede ser crucial si necesita actualizar el contenido incrustado sin editar manualmente cada diapositiva. Esta guía completa le guiará a través del proceso usando Aspose.Slides para Java, una potente biblioteca diseñada para gestionar presentaciones de PowerPoint. Tanto si es un desarrollador experimentado como si está empezando, este tutorial le resultará útil y fácil de seguir.
## Prerrequisitos
Antes de sumergirnos en el código, asegurémonos de que tienes todo lo que necesitas para comenzar.
1. Kit de desarrollo de Java (JDK): Asegúrese de tener el JDK instalado en su sistema. Puede descargarlo desde [El sitio de Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides para Java: Descargue la última versión desde [Página de descarga de Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): puede utilizar cualquier IDE de Java como IntelliJ IDEA, Eclipse o NetBeans.
4. Aspose.Cells para Java: Es necesario para modificar los datos incrustados en el objeto OLE. Descárguelo desde [Página de descarga de Aspose.Cells](https://releases.aspose.com/cells/java/).
5. Archivo de presentación: Prepare un archivo de PowerPoint con un objeto OLE incrustado. Para este tutorial, le asignaremos un nombre. `ChangeOLEObjectData.pptx`.
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
## Paso 1: Cargue la presentación de PowerPoint
Para comenzar, debe cargar la presentación de PowerPoint que contiene el objeto OLE.
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Paso 2: Acceda a la diapositiva que contiene el objeto OLE
A continuación, obtenga la diapositiva donde está incrustado el objeto OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Paso 3: Busque el objeto OLE en la diapositiva
Recorra las formas en la diapositiva para localizar el objeto OLE.
```java
OleObjectFrame ole = null;
// Recorriendo todas las formas para el marco Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Paso 4: Extraer los datos incrustados del objeto OLE
Si se encuentra el objeto OLE, extraiga sus datos incrustados.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Paso 5: Modificar los datos incrustados mediante Aspose.Cells
Ahora, use Aspose.Cells para leer y modificar los datos incrustados, que en este caso probablemente sea un libro de Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modificar los datos del libro de trabajo
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Paso 6: Guarde los datos modificados nuevamente en el objeto OLE
Después de realizar los cambios necesarios, guarde el libro modificado nuevamente en el objeto OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Paso 7: Guardar la presentación actualizada
Por último, guarde la presentación de PowerPoint actualizada.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusión
Actualizar datos de objetos OLE en presentaciones de PowerPoint con Aspose.Slides para Java es un proceso sencillo una vez que se divide en pasos sencillos. Esta guía le explicó cómo cargar una presentación, acceder y modificar datos OLE incrustados, y guardar la presentación actualizada. Con estos pasos, podrá administrar y actualizar eficientemente el contenido incrustado en sus diapositivas de PowerPoint mediante programación.
## Preguntas frecuentes
### ¿Qué es un objeto OLE en PowerPoint?
Un objeto OLE (vinculación e incrustación de objetos) permite incrustar contenido de otras aplicaciones, como hojas de cálculo de Excel, en diapositivas de PowerPoint.
### ¿Puedo usar Aspose.Slides con otros lenguajes de programación?
Sí, Aspose.Slides admite varios lenguajes, incluidos .NET, Python y C++.
### ¿Necesito Aspose.Cells para modificar objetos OLE en PowerPoint?
Sí, si el objeto OLE es una hoja de cálculo de Excel, necesitará Aspose.Cells para modificarlo.
### ¿Existe una versión de prueba de Aspose.Slides?
Sí, puedes conseguir uno [prueba gratuita](https://releases.aspose.com/) para probar las características de Aspose.Slides.
### ¿Dónde puedo encontrar la documentación de Aspose.Slides?
Puede encontrar documentación detallada en el [Página de documentación de Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
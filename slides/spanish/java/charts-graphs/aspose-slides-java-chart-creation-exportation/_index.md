---
date: '2026-02-09'
description: Aprende a crear gráficos y exportarlos a Excel usando Aspose.Slides para
  Java. Domina la visualización de datos, las diapositivas de informes empresariales
  y la generación de libros de trabajo.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Cómo crear un gráfico con Aspose.Slides Java
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear un gráfico usando Aspose.Slides para Java

**Domina las técnicas de visualización de datos con Aspose.Slides para Java**

En el panorama actual impulsado por los datos, *cómo crear un gráfico* programáticamente es una habilidad que puede transformar números crudos en historias visuales atractivas. Ya sea que esté construyendo una presentación de informe empresarial o un panel de análisis interactivo, Aspose.Slides para Java le brinda el poder de generar, personalizar y exportar gráficos directamente desde su código. En este tutorial aprenderá a crear objetos de gráfico, exportar datos del gráfico a Excel y vincular gráficos a libros de trabajo externos para una gestión de datos sin interrupciones.

## Quick Answers
- **¿Qué biblioteca se necesita?** Aspose.Slides for Java (v25.4+).  
- **¿Puedo exportar los datos del gráfico a Excel?** Sí – use `readWorkbookStream()` y escriba los bytes en un archivo *.xlsx*.  
- **¿Qué versión de Java se requiere?** JDK 16 o superior.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia permanente para producción.  
- **¿Qué tipo de gráfico se muestra?** Un gráfico de pastel, pero el mismo enfoque funciona para barras, líneas y otros tipos de gráficos.

## What is Aspose.Slides for Java?
Aspose.Slides for Java es una API pura de Java que permite a los desarrolladores crear, editar y convertir presentaciones de PowerPoint sin Microsoft Office. Soporta una gama completa de tipos de gráficos, enlace de datos y capacidades de exportación, lo que lo hace ideal para proyectos de **data visualization java**.

## Why use Aspose.Slides to create chart and export chart to Excel?
- **Sin instalación de Office** – funciona en cualquier servidor o entorno en la nube.  
- **Biblioteca de gráficos completa** – docenas de tipos de gráficos y control total de estilo.  
- **Exportación directa a Excel** – genera un libro de trabajo externo para análisis posteriores.  
- **Orientado al rendimiento** – bajo consumo de memoria y procesamiento rápido para presentaciones grandes.

## Prerequisites
Antes de comenzar, asegúrese de tener lo siguiente:

### Required Libraries and Versions
- **Aspose.Slides for Java** versión 25.4 o posterior

### Environment Setup Requirements
- Java Development Kit (JDK) 16 o superior  
- Un IDE como IntelliJ IDEA o Eclipse (o cualquier editor de texto que prefiera)

### Knowledge Prerequisites
- Habilidades básicas de programación en Java  
- Familiaridad con las herramientas de construcción Maven o Gradle

## Setting Up Aspose.Slides for Java
Agregue la biblioteca a su proyecto usando su sistema de compilación favorito.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, puede [descargar la última versión directamente](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
Aspose.Slides ofrece una licencia de prueba gratuita para explorar sus capacidades completas. También puede solicitar una licencia temporal o comprar una para uso prolongado. Siga estos pasos:

1. Visite la [página de compra de Aspose](https://purchase.aspose.com/buy) para obtener su licencia.  
2. Para una prueba gratuita, descargue de [Releases](https://releases.aspose.com/slides/java/).  
3. Solicite una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

Una vez que tenga el archivo de licencia, inicialícelo en su aplicación Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Step‑by‑Step Guide

### How to create chart – Load a Presentation
Cargar un archivo PowerPoint existente es el primer paso antes de poder agregar o modificar gráficos.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**Explicación:**  
- `Presentation` representa el archivo PowerPoint.  
- Siempre llame a `dispose()` para liberar los recursos nativos.

### How to create chart – Add a Pie Chart to a Slide
Ahora insertaremos un gráfico de pastel, que es perfecto para mostrar datos proporcionales.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Explicación:**  
- `addChart` inserta el gráfico en la primera diapositiva.  
- Los parámetros definen el tipo de gráfico, la posición X/Y y el tamaño.

### How to export chart to Excel – Export Chart Data
Exportar datos del gráfico permite a los analistas trabajar con los números en Excel, habilitando conocimientos más profundos.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Explicación:**  
- `readWorkbookStream()` extrae el libro de Excel subyacente del gráfico como un arreglo de bytes.  
- El arreglo de bytes se escribe en `externalWorkbook1.xlsx`, proporcionándole un archivo Excel listo para usar.

### How to create chart – Set External Workbook for Dynamic Data
Vincular un gráfico a un libro de trabajo externo le permite actualizar el gráfico simplemente editando el archivo Excel.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Explicación:**  
- `setExternalWorkbook` vincula el gráfico al archivo Excel especificado, permitiendo actualizaciones de datos en tiempo real sin reconstruir la diapositiva.

## Practical Applications
Aspose.Slides ofrece soluciones versátiles para varios escenarios del mundo real:

1. **Diapositivas de informes empresariales:** Genere automáticamente gráficos de rendimiento trimestral a partir de sus canalizaciones de datos.  
2. **Presentaciones académicas:** Convierta datos de investigación en visualizaciones claras sin crear gráficos manualmente.  
3. **Análisis financiero:** Exporte datos del gráfico a Excel para que los auditores verifiquen los números.  
4. **Analítica de marketing:** Visualice métricas de campañas y comparta libros de trabajo editables con las partes interesadas.

## Common Issues & Troubleshooting
- **`FileNotFoundException`** – Verifique que `dataDir` apunte a una carpeta válida y que la ruta de salida sea escribible.  
- **Fugas de memoria** – Siempre llame a `pres.dispose()` en un bloque `finally` para liberar los recursos nativos.  
- **El gráfico no aparece** – Asegúrese de que el índice de diapositiva (`get_Item(0)`) coincida con una diapositiva que realmente exista.

## Frequently Asked Questions

**P: ¿Puedo usar un tipo de gráfico diferente (p.ej., barra, línea) con el mismo código?**  
R: Sí. Reemplace `ChartType.Pie` por cualquier otro valor del enum `ChartType`, como `ChartType.Bar` o `ChartType.Line`.

**P: ¿Es posible actualizar el libro de trabajo externo después de crear el gráfico?**  
R: Absolutamente. Modifique el archivo Excel directamente; el gráfico vinculado reflejará los cambios la próxima vez que se abra la presentación.

**P: ¿Necesito una licencia separada para la función de exportación a Excel?**  
R: No. La capacidad de exportación a Excel está incluida en la licencia estándar de Aspose.Slides for Java.

**P: ¿Qué versiones de Java son compatibles?**  
R: Aspose.Slides for Java soporta JDK 16 y versiones posteriores; versiones anteriores pueden funcionar pero no están probadas oficialmente.

**P: ¿Cómo puedo incrustar el libro de Excel generado dentro del archivo PPTX?**  
R: Use `chart.getChartData().setExternalWorkbook(null)` para incrustar el libro, o mantenga el enlace externo para actualizaciones dinámicas.

**Última actualización:** 2026-02-09  
**Probado con:** Aspose.Slides for Java 25.4 (clasificador jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
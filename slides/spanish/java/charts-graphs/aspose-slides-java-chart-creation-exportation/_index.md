---
date: '2026-06-03'
description: Aprenda cómo exportar un gráfico a Excel y crear gráficos en Java usando
  Aspose.Slides for Java. Domine la visualización de datos, diapositivas de informes
  empresariales y la generación de libros de trabajo.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Exportar gráfico a Excel y crear gráficos con Aspose.Slides
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportar gráfico a Excel y crear gráficos con Aspose.Slides

**Domina las técnicas de visualización de datos con Aspose.Slides for Java**

En el panorama actual impulsado por los datos, *export chart to excel* programáticamente es una habilidad que puede convertir números crudos en historias visuales atractivas. Ya sea que estés creando una presentación de informe empresarial o un panel de análisis interactivo, Aspose.Slides for Java te brinda el poder de generar, personalizar y exportar gráficos directamente desde tu código. En este tutorial aprenderás a crear objetos de gráfico, exportar datos del gráfico a Excel y vincular gráficos a libros de trabajo externos para una gestión de datos sin problemas.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Slides for Java (v25.4+).  
- **¿Puedo exportar datos del gráfico a Excel?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **¿Qué versión de Java se requiere?** JDK 16 or higher.  
- **¿Necesito una licencia?** A free trial works for evaluation; a permanent license is required for production.  
- **¿Qué tipo de gráfico se muestra?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## ¿Qué es Aspose.Slides for Java?
Aspose.Slides for Java es una API pure‑Java que permite a los desarrolladores crear, editar y convertir presentaciones de PowerPoint sin Microsoft Office. Proporciona un conjunto completo de clases para la manipulación de diapositivas, generación de gráficos y conversión de formatos, habilitando soluciones de informes automatizados. Soporta **más de 50 tipos de gráficos**, enlace completo de datos y exportación directa a Excel, lo que lo hace ideal para proyectos de **data visualization java**.

## ¿Por qué usar Aspose.Slides para crear gráficos y exportar gráficos a Excel?
Exportar gráficos a Excel de forma rápida y fiable. Aspose.Slides elimina la necesidad de instalaciones de Office, ofrece **más de 50 estilos de gráficos integrados**, y procesa presentaciones **de hasta 300 MB en menos de 30 segundos** en hardware de servidor estándar. También obtienes generación nativa de libros de trabajo Excel, lo que permite a los analistas posteriores trabajar con números crudos sin copiar y pegar manualmente.

## Requisitos previos
Antes de profundizar, asegúrate de tener lo siguiente:

### Bibliotecas y versiones requeridas
- **Aspose.Slides for Java** versión 25.4 o posterior (compatible con JDK 16+)

### Requisitos de configuración del entorno
- Java Development Kit (JDK) 16 o superior  
- Un IDE como IntelliJ IDEA o Eclipse (o cualquier editor de texto que prefieras)

### Prerrequisitos de conocimientos
- Habilidades básicas de programación en Java  
- Familiaridad con herramientas de compilación Maven o Gradle

## Configuración de Aspose.Slides for Java
Agrega la biblioteca a tu proyecto usando tu sistema de compilación favorito.

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

Alternativamente, puedes [descargar la última versión directamente](https://releases.aspose.com/slides/java/).

### Pasos para obtener la licencia
Aspose.Slides ofrece una licencia de prueba gratuita para explorar todas sus capacidades. También puedes solicitar una licencia temporal o comprar una para uso prolongado. Sigue estos pasos:

1. Visita la [Aspose Purchase page](https://purchase.aspose.com/buy) para obtener tu licencia.  
2. Para una prueba gratuita, descarga desde [Releases](https://releases.aspose.com/slides/java/).  
3. Solicita una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

Una vez que tengas el archivo de licencia, inicialízalo en tu aplicación Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Guía paso a paso

### Cómo crear un gráfico – Cargar una presentación
Carga un archivo PowerPoint existente antes de poder agregar o modificar gráficos.  
La clase `Presentation` representa un archivo PowerPoint en memoria, exponiendo diapositivas, formas y objetos de gráfico.  
Carga tu archivo con `new Presentation("input.pptx")`, luego trabaja con la primera diapositiva usando `presentation.getSlides().get_Item(0)`. Siempre llama a `presentation.dispose()` en un bloque `finally` para liberar los recursos nativos.

### Cómo crear un gráfico – Añadir un gráfico de pastel a una diapositiva
Inserta un gráfico de pastel, perfecto para mostrar datos proporcionales.  
La interfaz `IChart` es el punto de entrada principal para la manipulación de gráficos; `addChart` crea un nuevo gráfico en la diapositiva objetivo. Proporciona el tipo de gráfico (`ChartType.Pie`), coordenadas X/Y y ancho/alto. Después de la creación, puedes personalizar títulos, leyenda y series de datos a través del objeto `ChartData`.

### Cómo exportar un gráfico a Excel – Exportar datos del gráfico
Exportar los datos del gráfico permite a los analistas trabajar con los números en Excel, habilitando insights más profundos.  
`readWorkbookStream()` devuelve el libro de trabajo Excel subyacente del gráfico como un arreglo de bytes. Llama a `chart.getChartData().readWorkbookStream()` para obtener el libro y escribe este arreglo en un archivo llamado `externalWorkbook1.xlsx` usando I/O estándar de Java. El archivo Excel resultante contiene los datos exactos usados por el gráfico, listo para un análisis adicional.

### Cómo crear un gráfico – Establecer libro de trabajo externo para datos dinámicos
Vincula un gráfico a un libro de trabajo externo para habilitar actualizaciones de datos en tiempo real sin reconstruir la diapositiva.  
`setExternalWorkbook()` enlaza el gráfico a un archivo Excel externo para actualizaciones dinámicas de datos. Usa `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` para enlazar el gráfico al archivo externo. Cuando el libro de trabajo Excel se edita, el gráfico refleja automáticamente los cambios la próxima vez que se abra la presentación, apoyando escenarios de informes dinámicos.

## Aplicaciones prácticas
Aspose.Slides ofrece soluciones versátiles para varios escenarios del mundo real:

1. **Diapositivas de informes empresariales:** Genera automáticamente gráficos de rendimiento trimestral a partir de tus canalizaciones de datos.  
2. **Presentaciones académicas:** Convierte datos de investigación en visualizaciones claras sin crear gráficos manualmente.  
3. **Análisis financiero:** Exporta datos del gráfico a Excel para que los auditores verifiquen los números, reduciendo errores manuales.  
4. **Analítica de marketing:** Visualiza métricas de campañas y comparte libros de trabajo editables con los interesados para la toma de decisiones colaborativa.  
5. **Generación automatizada de paneles:** Combina la API de creación de gráficos con trabajos programados para producir presentaciones actualizadas cada mañana.

## Problemas comunes y solución de problemas
- **`FileNotFoundException`** – Verifica que `dataDir` apunte a una carpeta válida y que la ruta de salida sea escribible.  
- **Memory leaks** – Siempre llama a `presentation.dispose()` en un bloque `finally` para liberar los recursos nativos.  
- **Chart not appearing** – Asegúrate de que el índice de diapositiva (`get_Item(0)`) coincida con una diapositiva existente, y que las dimensiones del gráfico estén dentro de los límites de la diapositiva.  
- **Excel export produces empty file** – Confirma que el gráfico realmente contenga series de datos antes de llamar a `readWorkbookStream()`.

## Preguntas frecuentes

**Q: ¿Puedo usar un tipo de gráfico diferente (p.ej., Bar, Line) con el mismo código?**  
A: Sí. Reemplaza `ChartType.Pie` con cualquier otro valor del enum `ChartType` como `ChartType.Bar` o `ChartType.Line`.

**Q: ¿Es posible actualizar el libro de trabajo externo después de crear el gráfico?**  
A: Absolutamente. Modifica el archivo Excel directamente; el gráfico vinculado reflejará los cambios la próxima vez que se abra la presentación.

**Q: ¿Necesito una licencia separada para la función de exportación a Excel?**  
A: No. La capacidad de exportar a Excel está incluida en la licencia estándar de Aspose.Slides for Java.

**Q: ¿Qué versiones de Java son compatibles?**  
A: Aspose.Slides for Java soporta JDK 16 y versiones posteriores; versiones anteriores pueden funcionar pero no están probadas oficialmente.

**Q: ¿Cómo puedo incrustar el libro de trabajo Excel generado dentro del archivo PPTX?**  
A: Usa `chart.getChartData().setExternalWorkbook(null)` para incrustar el libro, o mantén el enlace externo para actualizaciones dinámicas.

---

**Última actualización:** 2026-06-03  
**Probado con:** Aspose.Slides for Java 25.4 (clasificador JDK 16)  
**Autor:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Crear gráfico en Java con Aspose.Slides – Añadir y validar gráficos](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recuperar datos del libro de trabajo de gráficos PowerPoint usando Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Cómo actualizar el rango de datos del gráfico PowerPoint usando Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
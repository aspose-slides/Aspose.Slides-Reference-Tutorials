---
date: '2026-06-03'
description: Aprende cómo añadir gráficos con la aspose slides maven dependency, configurar
  etiquetas de datos y generar gráficos dinámicos en presentaciones Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Añadir y Configurar Gráficos en Presentaciones
  con Aspose.Slides for Java'
url: /es/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Añadir y Configurar Gráficos en Presentaciones Usando Aspose.Slides para Java

## Introducción
El **aspose slides maven dependency** permite a los desarrolladores Java crear, modificar y enriquecer archivos PowerPoint de forma programática sin necesidad de abrir PowerPoint. En muchos escenarios empresariales y académicos, insertar gráficos manualmente es lento y propenso a errores. Este tutorial le muestra paso a paso cómo añadir un Gráfico de Burbuja, enlazar etiquetas de datos a celdas de hoja de cálculo y guardar el resultado, todo aprovechando la aspose slides maven dependency de manera limpia y reproducible.

**Lo que aprenderás**
- Cómo añadir gráficos con la aspose slides maven dependency
- Configurar un proyecto Java usando Maven o Gradle
- Cargar una presentación existente e insertar un Gráfico de Burbuja
- Configurar etiquetas de datos usando referencias a celdas (add data labels chart)
- Guardar el archivo actualizado para su posterior distribución
- Casos de uso reales como generación dinámica de gráficos y flujos de trabajo de creación de presentaciones con gráficos

## Respuestas rápidas
- **¿Qué artefacto Maven añade capacidades de gráficos?** `com.aspose:aspose-slides:25.4` (o la última versión)  
- **¿Puedo enlazar etiquetas de datos a celdas estilo Excel?** Sí – use `ChartDataLabel` con `setDataLabelFormat` y referencias a celdas.  
- **¿Se requiere una licencia para producción?** Una licencia completa elimina la marca de agua de evaluación y desbloquea todas las funciones.  
- **¿Funcionará esto en Java 11+?** Absolutamente; la biblioteca es compatible con Java 8 hasta Java 21.  
- **¿Cuántos tipos de gráficos son compatibles?** Más de 70 tipos de gráficos distintos, incluidos Burbuja, Radar y Stock.

## ¿Qué es la aspose slides maven dependency?
El **aspose slides maven dependency** es un paquete compatible con Maven que proporciona una API completa para crear y editar archivos PowerPoint (PPTX, PPT, ODP) en Java. Al añadir esta dependencia a su `pom.xml` o `build.gradle`, obtiene acceso a más de 70 tipos de gráficos, más de 150 diseños de diapositivas y la capacidad de manipular formas, animaciones y metadatos sin necesidad de Office instalado.

## ¿Por qué usar la aspose slides maven dependency para la automatización de gráficos?
Aspose.Slides procesa presentaciones con miles de diapositivas en menos de un segundo en hardware de servidor estándar, soporta **más de 70 tipos de gráficos** y puede renderizar presentaciones de hasta **10 000 diapositivas** sin cargar todo el archivo en memoria. Estas capacidades cuantificadas la hacen ideal para la generación dinámica de gráficos a nivel empresarial, donde el rendimiento y la escalabilidad son innegociables.

## Requisitos previos
- **Kit de Desarrollo de Java (JDK)** 8 o superior (se recomienda Java 11+).  
- **Maven** 3.6+ **o** **Gradle** 6+.  
- Biblioteca **Aspose.Slides for Java** (la aspose slides maven dependency, versión 25.4 o posterior).  
- Familiaridad básica con colecciones Java y E/S de archivos.  
- Un archivo de licencia de evaluación o completa (`license.json`) si planea ejecutar el código más allá del período de prueba.

## ¿Cómo añadir un gráfico a una diapositiva usando Aspose.Slides?
Cargue la presentación objetivo, cree una nueva forma de gráfico en la diapositiva deseada y especifique el tipo de gráfico (Burbuja en este ejemplo). Toda la operación puede realizarse en **tres líneas concisas de código** una vez referenciada la biblioteca, lo que la hace perfecta para prototipos rápidos y pipelines de producción.

### Paso 1: Añadir la aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Estos fragmentos extraen la API completa de Aspose.Slides —incluido el soporte de gráficos— directamente de Maven Central.

### Paso 2: Cargar la presentación e insertar un Gráfico de Burbuja
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Paso 3: Configurar la serie de datos y etiquetas del gráfico
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Paso 4: Guardar la presentación modificada
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## ¿Cómo configurar etiquetas de datos usando referencias a celdas?
Las etiquetas de datos pueden enlazarse a valores de celdas externas, replicando la función “Vincular a celda” de Excel. Este enfoque elimina valores codificados y permite **generación dinámica de gráficos** donde el contenido de la etiqueta se actualiza automáticamente al cambiar los datos subyacentes. Al enlazar cada etiqueta a una celda específica del libro de trabajo, garantiza que cualquier modificación de los datos de origen se refleje instantáneamente en la presentación, reduciendo el esfuerzo de mantenimiento y minimizando el riesgo de información desactualizada.

### Respuesta directa
Llame a `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` y pase un `DataLabelFormat` que haga referencia a una dirección de celda como `"Sheet1!A2"`. Aspose.Slides resuelve la referencia en tiempo de ejecución, insertando el valor actual de la celda en la etiqueta del gráfico.

### Paso a paso
1. Identifique la serie que desea etiquetar.  
2. Obtenga el objeto `IDataLabel` para cada punto de datos.  
3. Use `setDataLabelFormat` con `DataLabelFormat` configurado para `CellReference`.  
4. Opcionalmente personalice la fuente, el color y las opciones de visualización.

## ¿Cómo guardar la presentación modificada?
Guardar consiste en una única llamada a método que escribe el objeto `Presentation` en memoria a una ruta de archivo o flujo de salida. También puede elegir el formato de salida (PPTX, PDF, ODP) pasando el enum `SaveFormat` correspondiente. Esta operación transmite el resultado directamente al disco, liberando todos los recursos nativos automáticamente cuando la instancia `Presentation` se cierra o sale de alcance, lo que ayuda a mantener bajo el uso de memoria incluso con presentaciones extensas.

### Respuesta directa
Ejecute `presentation.save("output.pptx", SaveFormat.Pptx)`; la biblioteca transmite el resultado directamente al disco, liberando todos los recursos nativos automáticamente cuando la instancia `Presentation` se cierra o sale de alcance.

## Aplicaciones prácticas
1. **Informes empresariales:** Generar automáticamente gráficos de ventas trimestrales a partir de una exportación de base de datos.  
2. **Clases académicas:** Incorporar datos de investigación en tiempo real en diapositivas de conferencias para cada sesión.  
3. **Presentaciones de ventas:** Construir paneles de rendimiento específicos para cada cliente al instante.  
4. **Gestión de proyectos:** Visualizar cronogramas estilo Gantt con etiquetas de datos dinámicas.  
5. **Analítica de marketing:** Insertar indicadores clave de campaña en presentaciones que se actualizan a medida que llegan nuevas métricas.

## Consideraciones de rendimiento
- **Gestión de memoria:** Use try‑with‑resources o `presentation.dispose()` explícito para liberar la memoria nativa rápidamente.  
- **Conjuntos de datos grandes:** Al manejar más de 10 000 puntos, rellene los datos del gráfico mediante `ChartDataWorkbook` para evitar cargar todo el conjunto en objetos Java.  
- **Seguridad en subprocesos:** Cada subproceso debe trabajar con su propia instancia `Presentation`; la API no es segura para subprocesos cuando se comparten objetos.

## Problemas comunes y soluciones
- **Problema:** “License file not found.”  
  **Solución:** Coloque `license.json` en el classpath y ejecute `License license = new License(); license.setLicense("license.json");` antes de usar cualquier API.  
- **Problema:** El gráfico aparece vacío después de guardar.  
  **Solución:** Asegúrese de que el libro de datos del gráfico se guarde con la presentación (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Problema:** Las etiquetas de datos muestran errores “#REF!”.  
  **Solución:** Verifique que la cadena de referencia a la celda coincida exactamente con el nombre de la hoja y la dirección, y que el libro de trabajo referenciado esté adjunto al gráfico.  

## Preguntas frecuentes

**P:** ¿Puedo añadir otros tipos de gráficos además de Burbuja?  
**R:** Sí, la enumeración `ChartType` incluye línea, barra, pastel, radar, stock y más de 70 tipos adicionales.

**P:** ¿La aspose slides maven dependency funciona con OpenJDK?  
**R:** Absolutamente; es totalmente compatible con OpenJDK 8‑21 y se ejecuta en todos los principales sistemas operativos.

**P:** ¿Cómo incrusto un gráfico desde un archivo Excel existente?  
**R:** Cargue el libro Excel con `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, luego vincule el `ChartDataWorkbook` del gráfico al libro antes de establecer referencias a celdas.

**P:** ¿Existe un límite en la cantidad de gráficos por diapositiva?  
**R:** Prácticamente no—Aspose.Slides puede manejar decenas de gráficos por diapositiva, limitado solo por la memoria disponible.

**P:** ¿A qué formatos puedo exportar la presentación final?  
**R:** PPTX, PPT, ODP, PDF, XPS, HTML, y formatos de imagen como PNG y JPEG están soportados.

## Recursos
- [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) – descargue los binarios más recientes de la biblioteca.  
- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) – referencia completa de la API y guías.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – página de descarga directa de los paquetes Maven/Gradle.  
- [Purchase a License](https://purchase.aspose.com/buy) – obtenga una licencia comercial completa.  
- [Free Trial](https://releases.aspose.com/slides/java/) – comience con una prueba para evaluar las funciones.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – solicite una clave temporal para una evaluación prolongada.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – obtenga ayuda de la comunidad y de ingenieros de Aspose.

## Conclusión
Ahora dispone de una guía completa, de extremo a extremo, para usar la **aspose slides maven dependency** y añadir, configurar y guardar gráficos en presentaciones Java. Siguiendo los pasos anteriores podrá automatizar la creación de gráficos, enlazar etiquetas a valores de celdas en tiempo real y generar presentaciones de calidad profesional a gran escala. Experimente con otros tipos de gráficos, explore las APIs de animación e integre este flujo de trabajo en sus pipelines de informes para obtener el máximo impacto.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Tutoriales relacionados

- [How to Create and Configure Presentations with Aspose.Slides Java&#58; A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Create PPTX Java with Aspose.Slides Maven – Automation Guide](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
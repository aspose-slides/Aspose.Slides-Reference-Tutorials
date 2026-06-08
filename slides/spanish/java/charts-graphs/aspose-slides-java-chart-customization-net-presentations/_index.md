---
date: '2026-06-08'
description: Aprenda cómo agregar series al chart y personalizar stacked column charts
  en presentaciones .NET usando Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Agregar series al chart con Aspose.Slides for Java en .NET
url: /es/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominar la personalización de gráficos en presentaciones .NET usando Aspose.Slides para Java

## Introducción
En el ámbito de las presentaciones basadas en datos, los gráficos son herramientas indispensables que convierten números crudos en historias visuales atractivas. Cuando necesitas **add series to chart** de forma programática, especialmente dentro de archivos de presentación .NET, la tarea puede resultar abrumadora. Afortunadamente, **Aspose.Slides for Java** ofrece una API potente y agnóstica al lenguaje que simplifica la creación y personalización de gráficos, incluso cuando tu formato objetivo es un .NET PPTX. Esta guía te lleva paso a paso por la adición de series, la construcción de un gráfico de columnas apiladas y el ajuste fino de aspectos visuales como el ancho de separación, para que puedas generar diapositivas dinámicas y ricas en datos que luzcan pulidas y profesionales.

## Respuestas rápidas
La clase `Presentation` representa un archivo PPTX, y `slide.getShapes().addChart(...)` inserta una forma de gráfico. Usa `chart.getChartData().getSeries().add(...)` para añadir una serie, y `setGapWidth()` ajusta el espaciado.

- **¿Cuál es la clase principal para iniciar una presentación?** `Presentation` – representa un archivo PPTX en memoria.  
- **¿Qué método añade un gráfico a una diapositiva?** `slide.getShapes().addChart(...)` crea el objeto de gráfico en la diapositiva.  
- **¿Cómo añades una nueva serie?** `chart.getChartData().getSeries().add(...)` inserta una nueva serie de datos.  
- **¿Puedes cambiar el ancho de separación entre barras?** Sí—llama a `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (el valor es un porcentaje).  
- **¿Necesito una licencia para producción?** Absolutamente—una licencia válida de Aspose.Slides for Java desbloquea todas las funciones y elimina las marcas de agua de evaluación.

## ¿Qué es “add series to chart”?
Añadir una serie a un gráfico significa insertar una nueva colección de puntos de datos que el gráfico representa como un elemento visual distinto (por ejemplo, un grupo de columnas separado). Cada serie puede tener sus propios valores, colores y formato, lo que permite la comparación lado a lado de varios conjuntos de datos.

## ¿Por qué usar Aspose.Slides para Java para modificar presentaciones .NET?
Aspose.Slides for Java te permite generar o editar archivos PPTX totalmente compatibles con los visores de PowerPoint .NET, sin necesidad de instalar Microsoft Office. Usa Aspose.Slides for Java cuando necesitas una solución del lado del servidor, multiplataforma, que cree o actualice archivos .NET PPTX, admita más de 50 tipos de gráficos y procese archivos de hasta 500 MB sin cargar todo el documento en memoria. Su API funciona en Java, Kotlin, Scala o cualquier lenguaje JVM, entregando el mismo resultado que esperan los desarrolladores .NET.

## Requisitos previos
- **Aspose.Slides for Java** library (versión 25.4 o posterior).  
- Maven, Gradle o una descarga manual del JAR.  
- Conocimientos básicos de Java y familiaridad con la estructura de archivos PPTX.  

## Configuración de Aspose.Slides para Java
### Instalación con Maven
Agrega la siguiente dependencia a tu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalación con Gradle
Incluye esta línea en tu archivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, descarga el último JAR desde la página oficial de lanzamientos: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Adquisición de licencia**  
Comienza con una prueba gratuita descargando una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/). Para uso en producción, adquiere una licencia completa para desbloquear todas las funciones y eliminar las marcas de agua de evaluación.

## Guía de implementación paso a paso
A continuación, cada paso incluye un fragmento de código conciso (sin cambios respecto al tutorial original) seguido de una explicación de lo que hace.

### Paso 1: Crear una presentación vacía
`Presentation` es la clase de punto de entrada que representa un archivo PowerPoint en memoria.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Comenzamos con un archivo PPTX limpio, lo que nos brinda un lienzo para añadir gráficos.*

### Paso 2: Añadir un gráfico de columnas apiladas a la diapositiva
`Chart` representa una forma de gráfico dentro de una diapositiva. `ChartType.StackedColumn` especifica un gráfico de columnas apiladas.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*El método `addChart` crea un **gráfico de columnas apiladas** y lo coloca en la esquina superior izquierda de la diapositiva.*

### Paso 3: Añadir series al gráfico (Objetivo principal)
`Series` encapsula una única serie de datos en un gráfico.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Aquí **add series to chart** — cada llamada crea una nueva serie de datos que aparecerá como un grupo de columnas separado.*

### Paso 4: Añadir categorías al gráfico
`Category` define una etiqueta del eje X para los datos del gráfico.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Las categorías actúan como etiquetas del eje X, dando significado a cada columna.*

### Paso 5: Poblar datos de la serie
`DataPoint` contiene un valor numérico para una serie en una categoría específica.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Los puntos de datos proporcionan a cada serie sus valores numéricos, que el gráfico representará como alturas de barra.*

### Paso 6: Establecer el ancho de separación para el grupo de series del gráfico
`SeriesGroup` controla propiedades de diseño para un grupo de series, como el ancho de separación.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Ajustar el ancho de separación mejora la legibilidad, especialmente cuando hay muchas categorías presentes.*

## Casos de uso comunes
- **Informes financieros** – comparar ingresos trimestrales entre unidades de negocio.  
- **Paneles de proyecto** – mostrar porcentajes de finalización de tareas por equipo.  
- **Analítica de marketing** – visualizar el rendimiento de campañas lado a lado.  
Estos escenarios se benefician del **ejemplo de gráfico de columnas apiladas** porque resaltan las contribuciones de categorías individuales a un total.

## Consejos de rendimiento
- **Reutiliza el objeto `Presentation`** al crear múltiples gráficos para reducir la sobrecarga de memoria.  
- **Limita el número de puntos de datos** a solo los necesarios para la historia visual; Aspose.Slides puede manejar 10 000 puntos, pero la velocidad de renderizado disminuye después de ~5 000.  
- **Dispón de los objetos** (`presentation.dispose()`) después de guardar para liberar recursos y evitar fugas de memoria.  

## Preguntas frecuentes
**Q: ¿Puedo añadir otros tipos de gráficos además de columnas apiladas?**  
A: Sí, Aspose.Slides admite gráficos de líneas, pastel, área, radar, burbuja y más de 50 tipos adicionales, todos accesibles mediante el mismo método `addChart`.

**Q: ¿Necesito una licencia separada para la salida .NET?**  
A: No, la misma licencia Java funciona para todos los formatos de salida, incluidos los archivos .NET PPTX.

**Q: ¿Cómo cambio la paleta de colores del gráfico?**  
A: Usa `series.getFormat().getFill().setFillType(FillType.Solid)` y luego establece el objeto `Color` deseado para cada serie.

**Q: ¿Es posible añadir etiquetas de datos programáticamente?**  
A: Absolutamente. Llama a `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` para mostrar el valor numérico en cada columna.

**Q: ¿Qué pasa si necesito actualizar una presentación existente?**  
A: Carga el archivo con `new Presentation("existing.pptx")`, modifica el gráfico usando las mismas llamadas API y guárdalo nuevamente en disco.

## Conclusión
Ahora tienes una guía completa, de extremo a extremo, sobre cómo **add series to chart**, crear un **gráfico de columnas apiladas** y afinar su apariencia en presentaciones .NET usando Aspose.Slides for Java. Experimenta con diferentes tipos de gráficos, colores y fuentes de datos para crear informes visuales impactantes que impresionen a los interesados y fomenten decisiones basadas en datos.

---

**Última actualización:** 2026-06-08  
**Probado con:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo crear gráficos de columnas apiladas basados en porcentajes en .NET usando Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Creación y manipulación maestra de series de gráficos con Aspose.Slides .NET para visualización de datos eficaz](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Eliminar puntos de datos específicos de series de gráficos con Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
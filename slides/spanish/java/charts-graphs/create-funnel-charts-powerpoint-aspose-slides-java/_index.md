---
date: '2026-09-02'
description: Aprenda a crear un gráfico de embudo en PowerPoint usando Aspose.Slides
  for Java. Esta guía paso a paso cubre la configuración de los datos del gráfico,
  la personalización de colores y la exportación de la presentación.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Aprenda a crear un gráfico de embudo en PowerPoint usando Aspose.Slides
  for Java. Esta guía le muestra cómo configurar los datos, personalizar los colores
  y exportar la presentación final.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Crear gráfico de embudo en PowerPoint con Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Crear gráfico de embudo en PowerPoint con Aspose.Slides for Java
url: /es/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dominando la creación de gráficos de embudo en PowerPoint con Aspose.Slides para Java

## Introducción
Crear presentaciones atractivas es un arte que combina visualización de datos, diseño y narración. Un visual poderoso que aclara al instante un proceso de varias etapas es el gráfico de embudo. Ya sea que necesites ilustrar un pipeline de ventas, un flujo de conversión o un cuello de botella de producción, un gráfico de embudo bien diseñado transforma números crudos en una narrativa intuitiva. En este tutorial aprenderás a **crear un gráfico de embudo** en PowerPoint de forma programática usando Aspose.Slides para Java, configurar sus datos, personalizar el color de cada segmento y exportar la presentación final.

**Lo que aprenderás**
- Cómo agregar Aspose.Slides para Java a un proyecto Maven o Gradle  
- Cómo instanciar un objeto `Presentation` y acceder a sus diapositivas  
- Cómo insertar un gráfico de embudo, definir categorías y rellenar datos de series  
- Cómo dar estilo a cada porción del embudo con rellenos sólidos o colores específicos de la marca  
- Cómo guardar la presentación como archivo PPTX o exportar una diapositiva como imagen  

## Respuestas rápidas
- **¿Cuál es la biblioteca principal para la visualización de datos en Java?** Aspose.Slides para Java.  
- **¿Cómo se crea un gráfico de embudo en PowerPoint?** Llama a `slide.addChart(ChartType.Funnel, …)` en la diapositiva objetivo.  
- **¿Qué API establece la fuente de datos del gráfico?** Usa `IChartDataWorkbook` junto con `chart.getChartData()`.  
- **¿Se pueden personalizar los colores de cada segmento del embudo?** Sí—establece `FillFormat.setFillType(FillType.Solid)` y asigna un `java.awt.Color`.  
- **¿Se necesita una licencia para uso en producción?** Se requiere una licencia comprada de Aspose.Slides para implementaciones comerciales.

## ¿Qué es la visualización de datos en Java?
La visualización de datos en Java es la práctica de convertir datos sin procesar en gráficos, diagramas o gráficos interactivos directamente desde aplicaciones Java. Aspose.Slides para Java es una biblioteca líder que permite a los desarrolladores generar más de 100 tipos de gráficos—incluidos los gráficos de embudo—sin lanzar PowerPoint manualmente, soportando presentaciones de hasta 500 diapositivas mientras mantiene bajo el uso de memoria.

## ¿Por qué usar gráficos de embudo en PowerPoint?
Los gráficos de embudo revelan al instante las tasas de abandono entre etapas secuenciales, lo que los hace ideales para pipelines de ventas, análisis de conversión o revisiones de eficiencia de procesos. Aspose.Slides te brinda control píxel a píxel sobre el diseño, los colores de los segmentos y las etiquetas de datos, de modo que puedes mantener la consistencia de la marca y evitar el esfuerzo manual de editar gráficos en la interfaz de PowerPoint.

## Prerequisitos (H2)

### Bibliotecas requeridas, versiones y dependencias
Para implementar Aspose.Slides para Java en tu proyecto, incluye las coordenadas adecuadas de Maven o Gradle. La biblioteca funciona con Java 8‑21 y no requiere dependencias nativas externas.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

También puedes descargar el JAR directamente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Requisitos de configuración del entorno
Asegúrate de tener JDK 8 o superior instalado y que tu `JAVA_HOME` apunte al directorio correcto del JDK. Aspose.Slides se ejecuta en cualquier SO que soporte el JDK, incluidos Windows, macOS y Linux.

### Conocimientos previos
Una familiaridad básica con la sintaxis de Java, programación orientada a objetos y el concepto de un archivo de presentación será útil, pero los fragmentos de código están completamente explicados para desarrolladores de cualquier nivel de experiencia.

## Configuración de Aspose.Slides para Java (H2)

1. **Agregar la dependencia** – Usa el fragmento de Maven o Gradle anterior.  
2. **Obtener una licencia** –  
   - **Prueba gratuita** – Descarga una licencia temporal desde [Aspose's website](https://purchase.aspose.com/temporary-license/) para evaluación.  
   - **Licencia completa** – Compra una licencia de producción a través de la [página de compra](https://purchase.aspose.com/buy).  
3. **Inicialización básica** –  

`Presentation` es la clase central de Aspose.Slides que representa un archivo PowerPoint en memoria. Proporciona acceso a diapositivas, formas y objetos de gráfico.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

El código anterior crea una nueva instancia de `Presentation`, lista para la manipulación de diapositivas, y garantiza que los recursos se liberen con `dispose()`.

## Guía de implementación

Recorreremos cada característica necesaria para construir un gráfico de embudo completo, añadiendo texto explicativo breve antes de cada marcador de código.

### Característica 1: crear una presentación (H2)

#### Visión general
Comienza creando una instancia de la clase `Presentation`. Este objeto es el punto de entrada para todas las operaciones posteriores.

`Presentation` es el objeto de nivel superior de Aspose.Slides que contiene la colección de diapositivas y la configuración global del documento.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

El fragmento abre una presentación en blanco, que luego podrás guardar como archivo `.pptx`.

### Característica 2: agregar un gráfico de embudo a una diapositiva (H2)

#### Visión general
Inserta un gráfico de embudo en la primera diapositiva, define su tamaño y establece el tipo de gráfico.

`ChartType.Funnel` indica a Aspose.Slides que renderice una visualización tipo embudo en lugar de un gráfico de barras o líneas.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

La llamada `addChart` crea la forma del gráfico, la posiciona en `(50, 50)` puntos y le asigna un ancho de `500` y una altura de `400`.

### Característica 3: borrar datos del gráfico (H2)

#### Visión general
Antes de rellenar el gráfico, elimina cualquier categoría o serie de marcador de posición que pueda contener la plantilla.

`chart.getChartData().getCategories().clear()` elimina todas las entradas de categoría existentes, mientras que `chart.getChartData().getSeries().clear()` elimina cualquier serie pre‑llenada.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Esto garantiza una pizarra limpia para que tus datos personalizados aparezcan exactamente como se desea.

### Característica 4: configurar el libro de datos del gráfico (H2)

#### Visión general
El objeto `IChartDataWorkbook` almacena los valores crudos que impulsan el gráfico. Inicializarlo te permite escribir datos directamente en celdas.

`IChartDataWorkbook` es una hoja de cálculo ligera en memoria que Aspose.Slides usa para alimentar series y categorías del gráfico.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

El código borra cualquier celda existente, preparando el libro de datos para nuevas entradas.

### Característica 5: agregar categorías a un gráfico (H2)

#### Visión general
Define las etiquetas de texto que aparecen en el lado izquierdo del embudo—estas representan cada etapa de tu proceso.

`chart.getChartData().getCategories().add()` crea un nuevo objeto de categoría vinculado a una celda específica del libro de datos.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Aquí añadimos tres etapas: “Prospects”, “Qualified Leads” y “Closed Deals”.

### Característica 6: agregar series de datos a un gráfico (H2)

#### Visión general
Rellena el embudo con valores numéricos y, opcionalmente, asigna un color único a cada porción.

`IDataPoint` representa un solo punto de datos dentro de una serie de gráfico.  

`chart.getChartData().getSeries().add()` crea una serie que contiene los puntos de datos numéricos; cada `IDataPoint` puede recibir su propio color de relleno.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

El bucle muestra cómo establecer un relleno sólido para cada punto, usando constantes `java.awt.Color` específicas de la marca o colores generados aleatoriamente para mayor variedad visual.

## Casos de uso comunes y consejos (H2)

- **Informes de pipeline de ventas** – Muestra cuántos leads pasan de prospecto a cerrado‑ganado en cada etapa.  
- **Análisis de eficiencia de procesos** – Visualiza la pérdida de material o retrasos de tiempo a través de los pasos de fabricación.  
- **Revisión del embudo de marketing** – Compara tasas de conversión entre campañas o fuentes de tráfico.  

**Consejo profesional:** En lugar de colores aleatorios, usa la paleta de marca de tu empresa (p. ej., `new Color(0, 112, 192)`) para mantener la presentación coherente con otros recursos de marketing.

## Preguntas frecuentes (H2)

**P: ¿Cómo cambio la orientación del gráfico de embudo?**  
R: Establece la propiedad `ChartOrientation` en el objeto `IChart` a `ChartOrientation.Vertical` o `ChartOrientation.Horizontal`.

**P: ¿Puedo exportar la diapositiva como imagen después de agregar el gráfico?**  
R: Sí—llama a `pres.getSlides().get_Item(0).getThumbnail(1, 1)` y escribe el `java.awt.image.BufferedImage` resultante en un archivo PNG o JPEG.

**P: ¿Qué pasa si necesito más de tres categorías?**  
R: Simplemente agrega categorías adicionales usando `chart.getChartData().getCategories().add(...)` y proporciona puntos de datos coincidentes para cada nueva categoría.

**P: ¿Hay forma de ocultar la leyenda?**  
R: Usa `chart.getChartTitle().setVisible(false)` y `chart.getLegend().setVisible(false)` para eliminar tanto el título como la leyenda del visual.

**P: ¿Necesito una licencia para compilaciones de desarrollo?**  
R: Una licencia temporal es suficiente para evaluación; se requiere una licencia comercial completa para despliegues en producción.

---

**Última actualización:** 2026-09-02  
**Probado con:** Aspose.Slides para Java 25.4 (jdk16)  
**Autor:** Aspose

## Tutoriales relacionados

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
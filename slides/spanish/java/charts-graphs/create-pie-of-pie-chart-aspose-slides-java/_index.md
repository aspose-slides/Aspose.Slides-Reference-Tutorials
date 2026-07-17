---
date: '2026-07-17'
description: Aprenda cómo agregar un gráfico a PowerPoint creando un gráfico Pie of
  Pie con Aspose.Slides para Java. Incluye configuración, código, personalización
  y guardado como PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Agregue un gráfico a PowerPoint con Aspose.Slides para Java. Esta
  guía muestra cómo crear, personalizar y guardar un gráfico Pie of Pie como PPTX
  en minutos.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Agregar gráfico a PowerPoint – Crear un gráfico Pie of Pie en Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Agregar gráfico a PowerPoint – Crear un gráfico Pie of Pie en Java con Aspose.Slides
url: /es/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Agregar gráfico a PowerPoint – Crear un gráfico Pie de Pie en Java con Aspose.Slides

## Gráficos y diagramas

### Introducción

En presentaciones modernas impulsadas por datos, **agregar un gráfico a PowerPoint** suele ser la forma más rápida de convertir números sin procesar en información visual. Un gráfico de pastel regular funciona bien para un pequeño número de categorías, pero cuando algunas porciones son diminutas se vuelven ilegibles. Un gráfico *Pie of Pie* resuelve este problema al extraer esas porciones pequeñas a un pastel secundario, manteniendo el gráfico principal limpio y los detalles accesibles.

En este tutorial aprenderás a **agregar un gráfico a PowerPoint** creando un gráfico Pie of Pie con Aspose.Slides para Java. Repasaremos la configuración del entorno, la creación del gráfico, la personalización de etiquetas, el ajuste de la posición de división y, finalmente, la guardado de la presentación como archivo PPTX. Al final estarás listo para incrustar gráficos sofisticados en cualquier presentación.

## Respuestas rápidas
En Aspose.Slides, `Presentation` representa un archivo PPTX, `ChartType.PieOfPie` selecciona el gráfico Pie of Pie, `setShowValue(true)` muestra los valores en las etiquetas y `save` escribe el archivo.

- **¿Cuál es la clase principal para la manipulación de PowerPoint?** `Presentation` – representa un archivo PPTX completo en memoria.  
- **¿Qué tipo de gráfico crea un pastel secundario para porciones pequeñas?** `ChartType.PieOfPie`.  
- **¿Cómo se muestran los valores en cada porción?** Establece `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **¿Puedes guardar el archivo directamente como PPTX?** Sí – llama a `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **¿Necesitas una licencia para el desarrollo?** Una prueba gratuita de 30 días funciona para pruebas; una licencia permanente elimina las marcas de agua de evaluación.

## ¿Qué es un gráfico Pie of Pie?

Un **gráfico Pie of Pie** es una visualización de pastel de dos niveles que aísla una o más porciones pequeñas en un pastel separado y enlazado, facilitando su lectura. Aspose.Slides admite este tipo de gráfico de forma nativa, permitiéndote controlar el tamaño de la división, la posición y el formato de las etiquetas.

## ¿Por qué agregar un gráfico a PowerPoint con Aspose.Slides?

Aspose.Slides puede generar, editar y renderizar archivos PowerPoint sin necesidad de tener Microsoft Office instalado. Soporta **más de 50 formatos de entrada y salida**, procesa presentaciones con **hasta 500 diapositivas** en menos de un segundo en hardware de servidor típico, y brinda **control total de la API** sobre el estilo de los gráficos, etiquetas de datos y diseño—perfecto para pipelines de informes automatizados.

## Requisitos previos

Antes de comenzar, asegúrate de tener:

- **Java Development Kit (JDK) 16+** instalado.
- Un IDE como **IntelliJ IDEA**, **Eclipse** o **NetBeans**.
- Maven o Gradle para la gestión de dependencias (consulta las secciones a continuación).
- Conocimientos básicos de Java y familiaridad con la construcción de proyectos.

## Configuración de Aspose.Slides para Java

### Información de instalación

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

**Descarga directa:** Puedes descargar la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Pasos para adquirir la licencia
- **Prueba gratuita:** Comienza con una prueba de 30 días para explorar todas las funciones.  
- **Licencia temporal:** Solicita una clave temporal para una evaluación prolongada.  
- **Compra:** Obtén una licencia permanente para uso en producción y eliminar las marcas de agua de evaluación.

### Inicialización y configuración básica
`Presentation` es el objeto principal para crear archivos PowerPoint, y `Chart` representa una forma de gráfico dentro de una diapositiva.

```java
Presentation presentation = new Presentation();
```  

Esto crea una presentación vacía lista para diapositivas y gráficos.

## Guía de implementación

### ¿Cómo agregar un gráfico a PowerPoint usando Aspose.Slides para Java?

Carga una nueva `Presentation`, agrega una diapositiva e inserta un `Chart` de tipo `PieOfPie`. La cadena de llamadas de la API es concisa: crea el gráfico, rellena los datos de la serie, ajusta la visibilidad de las etiquetas, configura el tamaño del pastel secundario y, finalmente, guarda. Todo el proceso suele caber en menos de 20 líneas de código, lo que lo hace ideal para la generación automática de informes.

### Creación de un gráfico 'Pie of Pie'

#### Visión general
Construiremos un gráfico Pie of Pie en la primera diapositiva, separaremos las porciones más pequeñas y etiquetaremos cada segmento con su valor.

#### Paso 1: Crear una instancia de la clase Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Esto inicializa el contenedor para todas las diapositivas y gráficos posteriores.

#### Paso 2: Agregar un gráfico 'Pie of Pie' en la primera diapositiva
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Aquí especificamos `ChartType.PieOfPie` y definimos la posición del gráfico (X, Y) y su tamaño (ancho, alto) en el lienzo de la diapositiva.

#### Paso 3: Configurar etiquetas de datos para mostrar valores de la serie
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Habilitar `showValue` hace que cada porción muestre su valor numérico, lo cual es esencial para una rápida interpretación de los datos.

#### Paso 4: Configurar el tamaño del segundo pastel y dividir por porcentaje
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Estas opciones te permiten decidir cuánto del gráfico se asigna al pastel secundario y qué porciones se mueven según un umbral de porcentaje.

#### Paso 5: Guardar la presentación en disco en formato PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Consejo profesional:** Usa una ruta absoluta o `Paths.get()` de Java para evitar separadores específicos de la plataforma.

## Problemas comunes y soluciones

La clase `License` carga un archivo de licencia para eliminar las restricciones de evaluación.

- **Advertencia de licencia faltante:** Si ves “Evaluation Only” en el gráfico, asegúrate de haber aplicado un archivo de licencia válido mediante `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **División de porción incorrecta:** Verifica que la propiedad `splitBy` esté establecida en `SplitBy.Percentage` y que `secondPieSize` sea un valor entre 0 y 100.
- **Datos no se muestran:** Confirma que la serie del gráfico contenga al menos un punto de datos; de lo contrario el gráfico se renderiza vacío.

## Preguntas frecuentes

`IChart` representa un objeto de gráfico que puede añadirse a una diapositiva.

**P: ¿Puedo generar múltiples gráficos en una sola presentación?**  
A: Sí, instancia un nuevo `IChart` para cada diapositiva o ubicación; la API permite objetos de gráfico ilimitados por archivo.

`SaveFormat.Pdf` especifica el formato de salida PDF para guardar.

**P: ¿Aspose.Slides admite guardar como PDF también?**  
A: Absolutamente – llama a `presentation.save("output.pdf", SaveFormat.Pdf)` para exportar la misma presentación a PDF.

`IPortion` representa una porción individual de un gráfico de pastel.

**P: ¿Cuál es el número máximo de puntos de datos que puede manejar un gráfico Pie of Pie?**  
A: La biblioteca admite hasta **10,000** puntos de datos por serie, limitado solo por la memoria disponible.

**P: ¿Es posible personalizar los colores de porciones individuales?**  
A: Sí, accede a cada `IPortion` mediante `chart.getChartData().getSeries().get_Item(0).getPortions()` y establece `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**P: ¿Cómo incrusto el PPTX generado en una aplicación web?**  
A: Después de guardar el archivo, envíalo directamente al cliente usando `HttpServletResponse` con `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Conclusión

Ahora tienes una receta completa y lista para producción para **agregar un gráfico a PowerPoint** creando un gráfico Pie of Pie con Aspose.Slides para Java. Experimenta con diferentes umbrales de división, formatos de etiquetas y esquemas de color para que coincidan con las directrices de tu marca. A continuación, explora otros tipos de gráficos—como barras apiladas o radar—para enriquecer aún más tus presentaciones automatizadas.

---

**Última actualización:** 2026-07-17  
**Probado con:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear gráfico dinámico Java – Tutoriales de gráficos PowerPoint para Aspose.Slides](/slides/java/charts-graphs/)
- [Cómo agregar un gráfico de pastel a PowerPoint con Aspose.Slides para Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Cómo agregar gráficos a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
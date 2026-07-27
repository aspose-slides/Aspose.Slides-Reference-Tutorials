---
date: '2026-07-27'
description: Cómo personalizar un gráfico usando Aspose.Slides para Java. Aprende
  a crear un gráfico de PowerPoint, dar estilo a series de dispersión y guardar presentaciones
  de manera eficiente.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Cómo personalizar un gráfico con Aspose.Slides para Java. Esta guía
  muestra cómo crear un gráfico de PowerPoint, dar estilo a puntos de dispersión y
  exportar presentaciones.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Cómo personalizar un gráfico: Gráfico de dispersión Aspose en Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Cómo personalizar un gráfico: Gráfico de dispersión Aspose en Java'
url: /es/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Personalizar gráfico de dispersión Aspose en Java

En este tutorial descubrirás **cómo personalizar un gráfico** — específicamente un gráfico de dispersión — utilizando la potente biblioteca Aspose.Slides para Java. Recorreremos la configuración del proyecto, la creación de un gráfico de dispersión, el ajuste de tipos de series y marcadores, y finalmente la guardado de la presentación. Al final, podrás generar programáticamente gráficos de dispersión de aspecto profesional y adaptar cada detalle visual para que coincida con tu marca o necesidades de informes.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Slides para Java (v25.4+).  
- **¿Qué versión de Java es compatible?** JDK 8 o superior.  
- **¿Puedo cambiar la forma de los marcadores?** Sí – usa `MarkerStyleType` para elegir estrellas, círculos, etc.  
- **¿Cómo guardo el archivo?** Llama a `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **¿Se requiere una licencia?** Una prueba gratuita funciona para desarrollo; se necesita una licencia comercial para producción.

## ¿Cómo personalizar un gráfico en Java con Aspose.Slides?
`Presentation` es la clase de Aspose.Slides que representa un archivo PowerPoint completo en memoria. Carga una nueva `Presentation`, agrega un gráfico de dispersión en la primera diapositiva, configura las series y los estilos de los marcadores, y luego llama a `save`. Ese flujo de trabajo único crea un gráfico totalmente estilizado en solo unas pocas líneas de código Java, listo para incluirse en cualquier presentación de PowerPoint.

## ¿Qué es “personalizar gráfico de dispersión aspose”?
Personalizar un gráfico de dispersión con Aspose significa definir programáticamente los datos del gráfico, su apariencia y comportamiento—todo, desde las coordenadas de los puntos hasta los símbolos de los marcadores—sin abrir PowerPoint manualmente. Este enfoque es ideal para informes automatizados, presentaciones basadas en datos o cualquier escenario donde necesites visualizaciones repetibles y de alta calidad.

## ¿Por qué personalizar gráficos de dispersión con Aspose.Slides?
Aspose.Slides brinda a los desarrolladores control total programático sobre la apariencia del gráfico, permitiendo la creación automatizada de visualizaciones de alta calidad, una integración fluida en pipelines de informes y la capacidad de personalizar cada elemento visual sin abrir PowerPoint manualmente, lo que ahorra tiempo y garantiza consistencia en todas las presentaciones.

- **Control total** – modifica tipos de series, estilos de marcadores, colores y más mediante código Java.  
- **Automatización** – genera docenas de gráficos al instante para paneles de control o informes por lotes.  
- **Multiplataforma** – funciona en cualquier SO que soporte Java, sin necesidad de instalar Office.  
- **Rendimiento** – API ligera que procesa **más de 150 tipos de gráficos** y maneja presentaciones de cientos de diapositivas sin cargar todo el archivo en memoria.

## Requisitos previos

Para seguir este tutorial, asegúrate de tener:

- **Aspose.Slides para Java** (v25.4 o posterior).  
- **Java Development Kit (JDK)** 8 + instalado.  
- Maven o Gradle para la gestión de dependencias (o puedes descargar el JAR manualmente).  
- Conocimientos básicos de Java y familiaridad con la herramienta de compilación que prefieras.

## Configuración de Aspose.Slides para Java

Integra la biblioteca en tu proyecto usando uno de los métodos a continuación.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

O descarga la última versión desde [Lanzamientos de Aspose](https://releases.aspose.com/slides/java/).

#### Adquisición de licencia
- **Prueba gratuita** – evaluación de 30 días.  
- **Licencia temporal** – período de prueba extendido.  
- **Licencia completa** – uso en producción con soporte premium.

## Guía paso a paso para personalizar el gráfico de dispersión Aspose

### 1️⃣ Preparar una carpeta para tus archivos de presentación
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Por qué es importante:* Asegurarse de que la carpeta de salida exista evita `FileNotFoundException` cuando guardes el PPTX más adelante.

### 2️⃣ Crear una nueva presentación y obtener la primera diapositiva
`Presentation` representa un documento PowerPoint y brinda acceso a diapositivas y formas. La clase `Presentation` representa un archivo PowerPoint completo en memoria.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Añadir un gráfico de dispersión con líneas suaves
`ChartType.ScatterWithSmoothLines` crea un gráfico de dispersión donde los puntos están conectados por líneas suaves.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Eliminar cualquier serie predeterminada y añadir la tuya
`IChartSeries` representa una serie de datos dentro de un gráfico.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Poblar la primera serie con puntos de datos
`addDataPointForScatterSeries` añade un único punto X‑Y a una serie de dispersión.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Personalizar el tipo de serie y la apariencia del marcador
`Marker` controla el símbolo visual usado para cada punto de datos en una serie de gráfico.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Guardar la presentación
`save` escribe la presentación en un archivo con el formato especificado.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Casos de uso comunes para gráficos de dispersión personalizados
- **Paneles financieros** – trazar precio de acciones vs. volumen.  
- **Investigación científica** – mostrar mediciones experimentales con marcadores de error.  
- **Gestión de proyectos** – comparar el esfuerzo planificado vs. real en tareas.  

## Consejos de rendimiento
- Llama a `pres.dispose()` después de guardar para liberar memoria nativa.  
- Para conjuntos de datos grandes, primero rellena el libro de trabajo y luego enlaza la serie para evitar refrescos UI repetidos.  
- Reutiliza una única instancia de `IChartDataWorkbook` al añadir muchas series para mantener bajo el consumo de memoria.

## Preguntas frecuentes

**P: ¿Cómo cambio el color de los marcadores?**  
R: Usa `series.getMarker().getFillFormat().setFillColor(Color)` donde `Color` es una instancia de `java.awt.Color` como `Color.RED`.

**P: ¿Puedo añadir más de dos series a un gráfico de dispersión?**  
R: Sí. Llama a `chart.getChartData().getSeries().add(...)` por cada serie adicional y rellena sus puntos según corresponda.

**P: ¿Es posible establecer una leyenda personalizada para cada serie?**  
R: Por supuesto. Después de crear una serie, invoca `series.getLegend().setText("Tu texto de leyenda")` para sobrescribir el nombre predeterminado.

**P: ¿Cómo puedo exportar el gráfico como imagen en lugar de PPTX?**  
R: Llama a `chart.getImage().save("chart.png", ImageFormat.Png)` después de configurar el gráfico. Esto genera un archivo PNG independiente.

**P: ¿Qué pasa si necesito animar los puntos de dispersión?**  
R: Aspose.Slides soporta efectos de animación. Usa `chart.getTimeline().getMainSequence().addEffect(...)` para añadir animaciones de entrada o énfasis al gráfico o a series individuales.

---

**Última actualización:** 2026-07-27  
**Probado con:** Aspose.Slides para Java 25.4 (clasificador jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Crear y personalizar gráficos de PowerPoint en Java usando Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Cómo crear un gráfico de burbujas en PowerPoint usando Aspose.Slides para Java (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Crear y personalizar gráficos con líneas de tendencia en Aspose.Slides para Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
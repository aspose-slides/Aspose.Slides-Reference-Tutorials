---
date: '2026-01-22'
description: Aprenda a personalizar los colores de los gráficos de pastel y a agregar
  un título al gráfico usando Aspose.Slides para Java. Incluye la configuración de
  Maven Aspose Slides y cómo guardar la presentación pptx.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'Cómo personalizar los colores de los gráficos de pastel en Java con Aspose.Slides:
  una guía completa'
url: /es/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creación de gráficos de pastel con Aspose.Slides para Java: Cómo **personalizar los colores de los gráficos de pastel** – Un tutorial completo

## Introducción
Contar historias basadas en datos cuando puedes **personalizar los colores de los gráficos de pastel** para que gráfico de pastel, añadirLo crear gráficos de pastel (how to create pie) y configurar un proyecto Java.
- Pasos para añadir el título del gráfico y gestionar los puntos de datos del gráfico de pastel.
- Técnicas para **personalizar los coloresose Slides.
- Guardar el archivo final como una presentación PPTX!

## Respuestas rápidas
- **¿Cómo añado un título al gráfico?** Usa `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **¿Qué herramienta de compilación funciona mejor?** Tanto Maven como Gradle son compatibles; Maven Aspose Slides es la más común.
- **¿Puedo cambiar los colores de las porciones?** Sí—establece `setColorVaried(true)` y ajusta el relleno de cada `DataPoint`.
- **¿En qué formato se guarda el archivo?** Usa `presentation.save("MyChart.pptx", SaveFormat.Pptx)`.
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia permanente para producción.

## Requisitos previos
- **Aspose.Slides para Java** ≥ 25.4 (se recomienda la última versión).
- **JDK 16+** instalado y configurado.
- Un IDE como IntelliJ IDEA, Eclipse o NetBeans.
- Conocimientos básicos de Java y familiaridad con Maven o Gradle.

## Configuración de Aspose.Slides para Java
Para comenzar a usar Aspose.Slides, agrega la biblioteca a tu proyecto.

**Maven** (maven aspose slides)  
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

**Descarga directa**  
Si prefieres no usar una herramienta de compilación, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Pasos para obtener la licencia
- **Prueba gratuita** – comienza a experimentar sin licencia.
- **Licencia temporal** – extiende el uso de la prueba.
- **Compra** – obtén una licencia completa para entornos de producción.

### Inicialización básica
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guía de implementación
A continuación se muestra un recorrido paso a paso que mantiene el código exactamente como la biblioteca original lo espera.

### Paso 1: Inicializar la presentación y la diapositiva
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Paso 2: Añadir un gráfico de pastel a la diapositiva
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Paso 3: Añadir el título del gráfico
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Paso 4: Mostrar etiquetas de datos para la primera serie
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Paso 5: Preparar la hoja de datos del gráfico
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Paso 6: Añadir categorías (puntos de datos del gráfico de pastel)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Paso 7: Añadir series y rellenar los puntos de datos
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Paso 8: **Personalizar los colores del gráfico de pastel** – El núcleo de este tutorial
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Paso 9: Configurar etiquetas de datos personalizadas
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Paso 10: Establecer ángulo de rotación y **guardar la presentación PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Problemas comunes y solución de errores
- **Colores desaparecen después de la exportación** – Asegúrate de que `setColorVaried(true)` se llame antes de modificar los puntos de datos individuales.
- **Los puntos de datos no se muestran** – Verifica que las categorías y series se limpien antes de agregar nuevas (ver Paso 5).
- **La licencia no se aplica** – Carga tu archivo de licencia antes de crear el objeto `Presentation` para evitar marcas de agua de prueba.

## Preguntas frecuentes

**P: ¿Puedo usar este código con versiones anteriores de JDK?**  
R: La biblioteca requiere JDK 16 o superior; las versiones anteriores no son compatibles.

**P: ¿Cómo cambio el título del gráfico después de crearlo?**  
R: Llama a `chart.getChartTitle().addTextFrameForOverriding("New Title")` y ajusta el formato del texto según sea necesario.

**P: ¿Es posible exportar a formatos distintos de PPTX?**  
Rado `SaveFormat`.

**P: ¿Qué pasa si quiero animar las porciones del pastel?**  
R: Usa la API `SlideShow` paraclusión listo para producción que muestra **cómo personalizar los colores de los gráficos de pastel**, añadir un título al Aspose.Slides para Java. Siéntete libre de experimentar con diferentes paletas de colores, conjuntos de datos y ángulos de rotación para que coincidan con el estilo de tu marca.

---

**Última actualización:** 2026-01-22  
**Probado con:** Aspose.Slides 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
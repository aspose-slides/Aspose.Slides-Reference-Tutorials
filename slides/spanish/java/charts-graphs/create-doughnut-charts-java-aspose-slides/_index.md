---
date: '2026-03-07'
description: Aprende cómo crear un gráfico de rosquilla en Java usando Aspose.Slides.
  Esta guía paso a paso cubre la configuración de la dependencia Maven de Aspose Slides,
  la configuración del gráfico y el guardado de presentaciones.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Crear gráfico de dona en Java con la guía de Aspose.Slides
url: /es/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear Doughnut Chart Java con la guía de Aspose.Slides

## Introducción

Crear un **doughnut chart** programáticamente puede convertir números crudos en una visual atractiva que cuenta una historia al instante. En Java, **Aspose.Slides** simplifica este proceso, permitiéndote generar gráficos listos para presentaciones sin abrir PowerPoint. En este tutorial aprenderás a **create doughnut chart java** paso a paso— desde configurar la dependencia Maven de Aspose Slides hasta personalizar series, categorías y, finalmente, guardar la presentación.

Al final de esta guía podrás incrustar doughnut charts dinámicos en cualquier archivo PPTX, perfecto para informes, paneles de control o presentaciones automatizadas.

### Respuestas rápidas
- **¿Qué biblioteca se usa?** Aspose.Slides for Java  
- **¿Tarea principal?** Create doughnut chart java in a PPTX file  
- **¿Cómo agregar la biblioteca?** Use the Maven Aspose Slides dependency (or Gradle)  
- **¿Versión mínima de Java?** JDK 16 or higher  
- **¿Puedo personalizar colores y etiquetas?** Yes, the API provides full formatting control  

## ¿Qué es un Doughnut Chart y por qué usarlo?

Un doughnut chart es una variación de un pie chart con un centro vacío, lo que permite mostrar múltiples series de datos en anillos concéntricos. Esto lo hace ideal para comparar partes de un todo a través de varias categorías—piense en ventas por región durante varios trimestres o asignaciones presupuestarias entre departamentos.

## ¿Por qué usar Aspose.Slides para Java?

- **No Office installation required** – generar archivos PPTX en cualquier servidor.  
- **Rich API** – control total sobre tipos de gráficos, puntos de datos y estilo.  
- **High performance** – optimizado para presentaciones grandes.  
- **Cross‑platform** – funciona en Windows, Linux y macOS.

## Requisitos previos

- **Bibliotecas requeridas:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **Configuración del entorno:**  
  - JDK 16 or higher.  
  - Your favorite IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Conocimientos previos:**  
  - Basic Java programming.  
  - Familiarity with Maven or Gradle for dependency management.

## Dependencia Maven de Aspose Slides

Agrega la siguiente dependencia Maven a tu `pom.xml`. Esta es la **maven aspose slides dependency** que necesitas para incorporar la biblioteca a tu proyecto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Si prefieres Gradle, usa el fragmento equivalente a continuación.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

También puedes descargar el JAR directamente desde la página oficial de lanzamientos:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Obtención de una licencia

Para eliminar la marca de agua de evaluación y desbloquear el conjunto completo de funciones:

- **Free trial** – comenzar con una licencia temporal.  
- **Temporary license** – solicitar una desde el [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – comprar para uso en producción.

Aplica la licencia en tu código:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guía de implementación

### Inicializando la presentación y agregando un Doughnut Chart

Primero, crea o carga una presentación y agrega un doughnut chart a la primera diapositiva.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configurando el libro de datos del gráfico y limpiando datos existentes

A continuación, obtén el libro de trabajo que respalda el gráfico y elimina cualquier serie o categoría predeterminada.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Agregando series al gráfico

Ahora agregaremos hasta 15 series. Cada serie puede personalizarse—aquí establecemos la explosión, el tamaño del agujero del doughnut y el ángulo de la primera porción.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Agregando categorías y puntos de datos

Crearemos 15 categorías y rellenaremos cada serie con un punto de datos. La última serie recibe un formato de etiqueta especial.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Guardando la presentación

Finalmente, escribe la presentación actualizada en disco.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Problemas comunes y soluciones

- **License not found** – Verifica que la ruta a `license.lic` sea correcta y que el archivo sea legible.  
- **Chart appears blank** – Asegúrate de haber limpiado las series/categorías existentes antes de agregar nuevas.  
- **Incorrect colors** – Comprueba que `FillType.Solid` esté configurado tanto para el relleno como para los formatos de línea.  
- **Performance with many series** – Limita la cantidad de series/categorías o reutiliza las celdas del libro de trabajo.

## Preguntas frecuentes

**Q: Can I generate a doughnut chart without a pre‑existing PPTX file?**  
A: Yes, instantiate `new Presentation()` to start from a blank slide deck.

**Q: Does Aspose.Slides support exporting to PDF?**  
A: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: How do I change the doughnut hole size?**  
A: Use `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` where value is 0‑100.

**Q: Is it possible to add data labels to all series, not just the last one?**  
A: Yes, move the label‑formatting block outside the `if (i == ...)` condition and apply it to each `dataPoint`.

**Q: What versions of Java are supported?**  
A: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the appropriate classifier.

---

**Última actualización:** 2026-03-07  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
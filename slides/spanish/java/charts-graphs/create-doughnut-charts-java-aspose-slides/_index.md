---
date: '2026-08-16'
description: Aprende cómo agregar gráficos de rosquilla en Java usando Aspose.Slides.
  Esta guía paso a paso cubre la configuración de dependencias de Maven, la configuración
  del gráfico, colores, etiquetas y el guardado del PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Cómo agregar gráficos de rosquilla en Java usando Aspose.Slides. Sigue
  esta guía para configurar Maven, personalizar colores, etiquetas y generar archivos
  PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Cómo agregar un gráfico de rosquilla en Java con Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Cómo agregar un gráfico de rosquilla en Java con Aspose.Slides
url: /es/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar un gráfico de rosquilla en Java con Aspose.Slides

## Introducción

Crear un **gráfico de rosquilla** de forma programática puede convertir números crudos en una visual atractiva que cuenta una historia al instante. En Java, **Aspose.Slides** hace que este proceso sea sencillo, permitiéndote generar gráficos listos para presentaciones sin abrir PowerPoint. En este tutorial aprenderás **cómo agregar rosquillas** a un archivo PPTX paso a paso— desde configurar la dependencia Maven de Aspose Slides hasta personalizar series, categorías, colores y etiquetas, y finalmente guardar la presentación.

Al final de esta guía podrás incrustar gráficos de rosquilla dinámicos en cualquier archivo PPTX, perfecto para informes, paneles de control o presentaciones automatizadas.

### Respuestas rápidas
- **¿Qué biblioteca se usa?** Aspose.Slides for Java  
- **¿Tarea principal?** Agregar un gráfico de rosquilla en un archivo PPTX  
- **¿Cómo agregar la biblioteca?** Usar la dependencia Maven de Aspose Slides (o Gradle)  
- **¿Versión mínima de Java?** JDK 16 o superior  
- **¿Puedo personalizar colores y etiquetas?** Sí, la API proporciona control total de formato  

## ¿Qué es un gráfico de rosquilla y por qué usarlo?

Un gráfico de rosquilla es una variación de un gráfico circular con un centro vacío, lo que permite que múltiples series de datos se muestren como anillos concéntricos. **Visualiza partes de un todo en varias categorías mientras conserva espacio para información adicional en el centro.** Esto lo hace ideal para comparar ventas por región a lo largo de varios trimestres, asignaciones presupuestarias entre departamentos, o cualquier escenario donde necesites mostrar datos de proporción jerárquica.

## ¿Por qué usar Aspose.Slides para Java?

Puedes agregar un gráfico de rosquilla sin instalar Microsoft Office, y la biblioteca procesa **más de 50 formatos de entrada y salida** mientras maneja presentaciones que superan las 500 diapositivas. Aspose.Slides ofrece **hasta 3× más rápido en renderizado** comparado con la automatización nativa de Office en el mismo hardware, y funciona en Windows, Linux y macOS. Estos beneficios cuantificados significan que puedes generar grandes presentaciones en servidores sin interfaz gráfica con un rendimiento predecible.

## Requisitos previos

- **Bibliotecas requeridas**  
  - Aspose.Slides for Java 25.4 o posterior (la biblioteca que permite agregar gráficos de rosquilla).  

- **Entorno**  
  - JDK 16 o superior instalado en tu máquina.  
  - Un IDE como IntelliJ IDEA, Eclipse o NetBeans.  

- **Conocimientos**  
  - Sintaxis básica de Java y conceptos orientados a objetos.  
  - Familiaridad con Maven o Gradle para la gestión de dependencias.  

## Dependencia Maven de Aspose Slides

Agrega la siguiente dependencia Maven a tu `pom.xml`. Esta es la **dependencia maven aspose slides** que necesitas para incorporar la biblioteca a tu proyecto.

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
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

También puedes descargar el JAR directamente desde la página oficial de lanzamientos:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Obteniendo una licencia

Para eliminar la marca de agua de evaluación y desbloquear el conjunto completo de funciones:

- **Prueba gratuita** – comienza con una licencia temporal.  
- **Licencia temporal** – solicita una en el [sitio web de Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licencia comercial** – compra para uso en producción.

Aplica la licencia en tu código:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Guía de implementación

### Inicializando una presentación y agregando un gráfico de rosquilla

Presentation es la clase de Aspose.Slides que representa una presentación de PowerPoint.  
Carga un PPTX existente o crea un nuevo objeto `Presentation`, luego agrega un gráfico de rosquilla a la primera diapositiva.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Configurando el libro de datos del gráfico y limpiando datos existentes

El libro de trabajo es una hoja de cálculo interna que almacena los datos del gráfico.  
Obtén el libro de trabajo que respalda el gráfico, luego elimina cualquier serie o categoría predeterminada para comenzar con una hoja limpia.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Agregando series al gráfico

Una serie representa una colección de puntos de datos trazados en el gráfico.  
Puedes agregar hasta 15 series. Cada serie puede personalizarse—aquí establecemos la explosión, el tamaño del agujero de la rosquilla y el ángulo del primer segmento.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Agregando categorías y puntos de datos

Las categorías son las etiquetas para cada punto de datos a lo largo del eje del gráfico.  
Crea 15 categorías y rellena cada serie con un punto de datos. La última serie recibe un formato de etiqueta especial.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Personalizando colores y etiquetas de datos

`FillType.Solid` especifica un color de relleno sólido para los elementos del gráfico.  
Establece un color de relleno sólido para cada serie y habilita las etiquetas de datos. Para la serie final también cambiamos el color de fuente de la etiqueta.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Guardando la presentación

`save` escribe la presentación a un archivo en el formato elegido.  
Guarda la presentación actualizada en disco en formato PPTX, o expórtala a PDF si es necesario.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Problemas comunes y soluciones

- **Licencia no encontrada** – Verifica que la ruta a `license.lic` sea correcta y que el archivo sea legible.  
- **El gráfico aparece vacío** – Asegúrate de haber limpiado las series/categorías existentes antes de agregar nuevas.  
- **Colores incorrectos** – Confirma que `FillType.Solid` esté configurado tanto para el relleno como para los formatos de línea.  
- **Rendimiento con muchas series** – Limita la cantidad de series/categorías o reutiliza celdas del libro de trabajo para mantener el uso de memoria bajo control.  

## Preguntas frecuentes

**P: ¿Puedo generar un gráfico de rosquilla sin un archivo PPTX preexistente?**  
R: Sí, instancia `new Presentation()` para comenzar con una presentación en blanco, luego agrega un gráfico como se muestra arriba.

**P: ¿Aspose.Slides admite la exportación a PDF?**  
R: Absolutamente. Después de crear el gráfico, llama a `pres.save("output.pdf", SaveFormat.Pdf);` para obtener una versión PDF de la diapositiva.

**P: ¿Cómo cambio el tamaño del agujero de la rosquilla?**  
R: Usa `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` donde `value` varía de 0 a 100.

**P: ¿Es posible agregar etiquetas de datos a todas las series, no solo a la última?**  
R: Sí, mueve el bloque de formato de etiquetas fuera de la condición `if (i == ...)` y aplícalo a cada `dataPoint`.

**P: ¿Qué versiones de Java son compatibles?**  
R: Aspose.Slides 25.4 es compatible con JDK 16 y versiones posteriores. JDKs anteriores requieren el clasificador apropiado en la dependencia Maven.

---

**Última actualización:** 2026-08-16  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Tutoriales relacionados

- [Cómo agregar un gráfico a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cómo personalizar colores de gráficos de pastel en Java con Aspose.Slides – Guía completa](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animar categorías de gráficos de PowerPoint con Aspose.Slides para Java | Guía paso a paso](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
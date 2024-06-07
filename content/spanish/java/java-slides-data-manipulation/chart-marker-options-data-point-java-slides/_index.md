---
title: Opciones de marcador de gráfico en puntos de datos en diapositivas de Java
linktitle: Opciones de marcador de gráfico en puntos de datos en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Optimice sus diapositivas Java con opciones de marcadores de gráficos personalizados. Aprenda a mejorar visualmente los puntos de datos utilizando Aspose.Slides para Java. Explore instrucciones paso a paso y preguntas frecuentes.
type: docs
weight: 14
url: /es/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Introducción a las opciones de marcador de gráficos en puntos de datos en diapositivas de Java

Cuando se trata de crear presentaciones impactantes, la capacidad de personalizar y manipular marcadores de gráficos en puntos de datos puede marcar la diferencia. Con Aspose.Slides para Java, tiene el poder de transformar sus gráficos en elementos dinámicos y visualmente atractivos.

## Requisitos previos

Antes de sumergirnos en la parte de codificación, asegúrese de cumplir con los siguientes requisitos previos:

- Entorno de desarrollo Java
- Biblioteca Aspose.Slides para Java
- Un entorno de desarrollo integrado (IDE) de Java
- Documento de presentación de muestra (p. ej., "Test.pptx")

## Paso 1: configurar el entorno

Primero, asegúrese de tener las herramientas necesarias instaladas y listas. Cree un proyecto Java en su IDE e importe la biblioteca Aspose.Slides para Java.

## Paso 2: cargar la presentación

Para comenzar, cargue su documento de presentación de muestra. En el código proporcionado, asumimos que el documento se llama "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Paso 3: crear un gráfico

Ahora, creemos un gráfico en la presentación. Usaremos un gráfico de líneas con marcadores en este ejemplo.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Paso 4: trabajar con datos de gráficos

Para manipular los datos del gráfico, debemos acceder al libro de trabajo de datos del gráfico y preparar la serie de datos. Borraremos la serie predeterminada y agregaremos nuestros datos personalizados.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Paso 5: agregar marcadores personalizados

Aquí viene la parte interesante: personalizar los marcadores en los puntos de datos. Usaremos imágenes como marcadores en este ejemplo.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Agregar marcadores personalizados a puntos de datos
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Repita para otros puntos de datos
// ...

// Cambiar el tamaño del marcador de serie de gráficos
series.getMarker().setSize(15);
```

## Paso 6: guardar la presentación

Una vez que haya personalizado los marcadores de su gráfico, guarde la presentación para ver los cambios en acción.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Código fuente completo para opciones de marcador de gráfico en puntos de datos en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Creando el gráfico predeterminado
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Obtener el índice predeterminado de la hoja de cálculo de datos del gráfico
int defaultWorksheetIndex = 0;
//Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Eliminar serie de demostración
chart.getChartData().getSeries().clear();
//Agregar nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Establecer la imagen
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Establecer la imagen
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Agregue un nuevo punto (1:3) allí.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Cambiar el marcador de serie del gráfico
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusión

Con Aspose.Slides para Java, puede mejorar sus presentaciones personalizando marcadores de gráficos en puntos de datos. Esto le permite crear diapositivas visualmente impactantes e informativas que cautiven a su audiencia.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tamaño del marcador para los puntos de datos?

 Para cambiar el tamaño del marcador para los puntos de datos, utilice el`series.getMarker().setSize()` método y proporcione el tamaño deseado como argumento.

### ¿Puedo utilizar imágenes como marcadores personalizados?

 Sí, puedes utilizar imágenes como marcadores personalizados para puntos de datos. Establece el tipo de relleno en`FillType.Picture` proporcione la imagen que desea utilizar.

### ¿Aspose.Slides para Java es adecuado para crear gráficos dinámicos?

¡Absolutamente! Aspose.Slides para Java proporciona amplias capacidades para crear gráficos dinámicos e interactivos en sus presentaciones.

### ¿Puedo personalizar otros aspectos del gráfico usando Aspose.Slides?

Sí, puede personalizar varios aspectos del gráfico, incluidos títulos, ejes, etiquetas de datos y más, utilizando Aspose.Slides para Java.

### ¿Dónde puedo acceder a la documentación y descargas de Aspose.Slides para Java?

 Puedes encontrar la documentación en[aquí](https://reference.aspose.com/slides/java/) y descargar la biblioteca en[aquí](https://releases.aspose.com/slides/java/).
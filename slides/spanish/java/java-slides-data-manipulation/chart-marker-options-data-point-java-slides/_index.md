---
"description": "Optimice sus presentaciones de Java con opciones personalizadas de marcadores de gráficos. Aprenda a mejorar visualmente los puntos de datos con Aspose.Slides para Java. Explore la guía paso a paso y las preguntas frecuentes."
"linktitle": "Opciones de marcador de gráfico en puntos de datos en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Opciones de marcador de gráfico en puntos de datos en diapositivas de Java"
"url": "/es/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opciones de marcador de gráfico en puntos de datos en diapositivas de Java


## Introducción a las opciones de marcadores de gráficos en puntos de datos en diapositivas de Java

A la hora de crear presentaciones impactantes, la posibilidad de personalizar y manipular los marcadores de gráficos en los puntos de datos puede marcar la diferencia. Con Aspose.Slides para Java, puede transformar sus gráficos en elementos dinámicos y visualmente atractivos.

## Prerrequisitos

Antes de sumergirnos en la parte de codificación, asegúrese de tener los siguientes requisitos previos:

- Entorno de desarrollo de Java
- Biblioteca Aspose.Slides para Java
- Un entorno de desarrollo integrado (IDE) de Java
- Documento de presentación de muestra (p. ej., "Test.pptx")

## Paso 1: Configuración del entorno

Primero, asegúrate de tener las herramientas necesarias instaladas y listas. Crea un proyecto Java en tu IDE e importa la biblioteca Aspose.Slides para Java.

## Paso 2: Cargar la presentación

Para empezar, cargue su documento de presentación de ejemplo. En el código proporcionado, asumimos que el documento se llama "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Paso 3: Creación de un gráfico

Ahora, creemos un gráfico en la presentación. En este ejemplo, usaremos un gráfico de líneas con marcadores.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Paso 4: Trabajar con datos de gráficos

Para manipular los datos del gráfico, necesitamos acceder al libro de datos del gráfico y preparar la serie de datos. Borraremos la serie predeterminada y agregaremos nuestros datos personalizados.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Paso 5: Agregar marcadores personalizados

Ahora viene la parte emocionante: personalizar los marcadores en los puntos de datos. En este ejemplo, usaremos imágenes como marcadores.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Agregar marcadores personalizados a los puntos de datos
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Repetir para otros puntos de datos
// ...

// Cambiar el tamaño del marcador de la serie del gráfico
series.getMarker().setSize(15);
```

## Paso 6: Guardar la presentación

Una vez que haya personalizado sus marcadores de gráficos, guarde la presentación para ver los cambios en acción.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Código fuente completo para opciones de marcadores de gráficos en puntos de datos en diapositivas de Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Creando el gráfico predeterminado
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Obtener el índice de la hoja de cálculo con datos del gráfico predeterminado
int defaultWorksheetIndex = 0;
//Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Eliminar la serie de demostración
chart.getChartData().getSeries().clear();
//Añadir nueva serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Establecer la imagen
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Establecer la imagen
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Tome la primera serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Añade allí un nuevo punto (1:3).
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
//Cambiar el marcador de la serie del gráfico
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusión

Con Aspose.Slides para Java, puedes mejorar tus presentaciones personalizando los marcadores de gráficos en los puntos de datos. Esto te permite crear diapositivas visualmente impactantes e informativas que cautivarán a tu audiencia.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tamaño del marcador para los puntos de datos?

Para cambiar el tamaño del marcador para los puntos de datos, utilice el `series.getMarker().setSize()` método y proporcione el tamaño deseado como argumento.

### ¿Puedo usar imágenes como marcadores personalizados?

Sí, puedes usar imágenes como marcadores personalizados para los puntos de datos. Configura el tipo de relleno en `FillType.Picture` y proporciona la imagen que deseas utilizar.

### ¿Es Aspose.Slides para Java adecuado para crear gráficos dinámicos?

¡Por supuesto! Aspose.Slides para Java ofrece amplias funciones para crear gráficos dinámicos e interactivos en tus presentaciones.

### ¿Puedo personalizar otros aspectos del gráfico usando Aspose.Slides?

Sí, puede personalizar varios aspectos del gráfico, incluidos títulos, ejes, etiquetas de datos y más, utilizando Aspose.Slides para Java.

### ¿Dónde puedo acceder a la documentación y descargas de Aspose.Slides para Java?

Puede encontrar la documentación en [aquí](https://reference.aspose.com/slides/java/) y descargar la biblioteca en [aquí](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
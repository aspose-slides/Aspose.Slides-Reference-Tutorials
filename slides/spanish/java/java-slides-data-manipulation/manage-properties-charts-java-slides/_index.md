---
"description": "Aprenda a crear gráficos impactantes y a administrar propiedades en diapositivas de Java con Aspose.Slides. Guía paso a paso con código fuente para presentaciones impactantes."
"linktitle": "Administrar gráficos de propiedades en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Administrar gráficos de propiedades en diapositivas de Java"
"url": "/es/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Administrar gráficos de propiedades en diapositivas de Java


## Introducción a la gestión de propiedades y gráficos en diapositivas de Java con Aspose.Slides

En este tutorial, exploraremos cómo administrar propiedades y crear gráficos en diapositivas de Java con Aspose.Slides. Aspose.Slides es una potente API de Java para trabajar con presentaciones de PowerPoint. Explicaremos el proceso paso a paso, incluyendo ejemplos de código fuente.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

## Cómo agregar un gráfico a una diapositiva

Para agregar un gráfico a una diapositiva, siga estos pasos:

1. Importe las clases necesarias y cree una instancia de la clase Presentación.

```java
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
```

2. Acceda a la diapositiva donde desea agregar el gráfico. En este ejemplo, accedemos a la primera diapositiva.

```java
// Acceder a la primera diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Agregue un gráfico con datos predeterminados. En este caso, agregamos un gráfico StackedColumn3D.

```java
// Agregar gráfico con datos predeterminados
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Configuración de datos del gráfico

Para configurar los datos del gráfico, necesitamos crear un libro de datos del gráfico y agregar series y categorías. Siga estos pasos:

4. Establecer el índice de la hoja de datos del gráfico.

```java
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;
```

5. Obtenga el libro de trabajo de datos del gráfico.

```java
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Añadir series al gráfico. En este ejemplo, añadimos dos series llamadas "Serie 1" y "Serie 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Añade categorías al gráfico. Aquí, añadimos tres categorías.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Configuración de propiedades de rotación 3D

Ahora, configuremos las propiedades de rotación 3D para el gráfico:

8. Establecer los ejes de ángulo recto.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Establezca los ángulos de rotación para los ejes X e Y. En este ejemplo, giramos X 40 grados e Y 270 grados.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Establezca el porcentaje de profundidad en 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Población de datos de series

11. Tome la segunda serie de gráficos y complétela con puntos de datos.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Rellenar datos de series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Ajuste de la superposición

12. Establezca el valor de superposición para la serie. Por ejemplo, puede establecerlo en 100 para que no haya superposición.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Guardar la presentación

Por último, guarde la presentación en el disco.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

¡Listo! Has creado correctamente un gráfico de columnas apiladas 3D con propiedades personalizadas usando Aspose.Slides en Java.

## Código fuente completo para administrar gráficos de propiedades en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
// Acceder a la primera diapositiva
ISlide slide = presentation.getSlides().get_Item(0);
// Agregar gráfico con datos predeterminados
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Configuración del índice de la hoja de datos del gráfico
int defaultWorksheetIndex = 0;
// Obtener la hoja de trabajo de datos del gráfico
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Añadir serie
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Agregar categorías
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Establecer propiedades de Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Tome la segunda serie de gráficos
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Ahora se están rellenando los datos de la serie
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Establecer valor de superposición
series.getParentSeriesGroup().setOverlap((byte) 100);
// Escribir presentación en disco
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Conclusión

En este tutorial, profundizamos en la gestión de propiedades y la creación de gráficos en diapositivas de Java con Aspose.Slides. Aspose.Slides es una robusta API de Java que permite a los desarrolladores trabajar con presentaciones de PowerPoint de forma eficiente. Cubrimos los pasos esenciales y proporcionamos ejemplos de código fuente para guiarte en el proceso.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico?

Puede cambiar el tipo de gráfico modificando el `ChartType` Parámetro al agregar el gráfico. Consulte la documentación de Aspose.Slides para conocer los tipos de gráficos disponibles.

### ¿Puedo personalizar los colores del gráfico?

Sí, puede personalizar los colores del gráfico configurando las propiedades de relleno de los puntos de datos de la serie o categorías.

### ¿Cómo agrego más puntos de datos a una serie?

Puede agregar más puntos de datos a una serie mediante el uso de `series.getDataPoints().addDataPointForBarSeries()` método y especificando la celda que contiene el valor de los datos.

### ¿Cómo puedo establecer un ángulo de rotación diferente?

Para establecer un ángulo de rotación diferente para los ejes X e Y, utilice `chart.getRotation3D().setRotationX()` y `chart.getRotation3D().setRotationY()` con los valores de ángulo deseados.

### ¿Qué otras propiedades 3D puedo personalizar?

Puede explorar otras propiedades 3D del gráfico, como la profundidad, la perspectiva y la iluminación, consultando la documentación de Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
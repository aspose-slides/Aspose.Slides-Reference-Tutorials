---
"description": "Aprenda a recuperar las dimensiones del área de un gráfico en Presentaciones de Java con Aspose.Slides para Java. Mejore sus habilidades de automatización de PowerPoint."
"linktitle": "Obtener el ancho y la altura del área de trazado del gráfico en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Obtener el ancho y la altura del área de trazado del gráfico en diapositivas de Java"
"url": "/es/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Obtener el ancho y la altura del área de trazado del gráfico en diapositivas de Java


## Introducción

Los gráficos son una forma eficaz de visualizar datos en presentaciones de PowerPoint. En ocasiones, puede que necesite conocer las dimensiones del área de trazado de un gráfico por diversas razones, como cambiar el tamaño o la posición de elementos dentro del gráfico. Esta guía le mostrará cómo obtener el ancho y la altura del área de trazado utilizando Java y Aspose.Slides para Java.

## Prerrequisitos

Antes de profundizar en el código, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargarla desde el sitio web de Aspose. [aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Configuración del entorno

Asegúrese de tener la biblioteca Aspose.Slides para Java añadida a su proyecto Java. Puede hacerlo incluyendo la biblioteca en las dependencias de su proyecto o añadiendo manualmente el archivo JAR.

## Paso 2: Crear una presentación de PowerPoint

Comencemos creando una presentación de PowerPoint y agregándole una diapositiva. Esta servirá como contenedor para nuestro gráfico.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Reemplazar `"Your Document Directory"` con la ruta al directorio de su documento.

## Paso 3: Agregar un gráfico

Ahora, agreguemos un gráfico de columnas agrupadas a la diapositiva. También validaremos el diseño del gráfico.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Este código crea un gráfico de columnas agrupadas en la posición (100, 100) con dimensiones (500, 350).

## Paso 4: Obtener las dimensiones del área de la parcela

Para recuperar el ancho y la altura del área de trazado del gráfico, podemos utilizar el siguiente código:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Ahora, las variables `x`, `y`, `w`, y `h` Contienen los valores respectivos para las coordenadas X, Y, ancho y alto del área de la gráfica.

## Paso 5: Guardar la presentación

Por último, guarde la presentación con el gráfico.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Asegúrese de reemplazar `"Chart_out.pptx"` con el nombre de archivo de salida deseado.

## Código fuente completo para obtener el ancho y la altura del área de trazado de un gráfico en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Guardar presentación con gráfico
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este artículo, explicamos cómo obtener el ancho y la altura del área de trazado de un gráfico en Java Slides mediante la API de Aspose.Slides para Java. Esta información puede ser útil al ajustar dinámicamente el diseño de los gráficos en presentaciones de PowerPoint.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico a algo distinto a columnas agrupadas?

Puede cambiar el tipo de gráfico reemplazando `ChartType.ClusteredColumn` con la enumeración del tipo de gráfico deseado, como por ejemplo `ChartType.Line` o `ChartType.Pie`.

### ¿Puedo modificar otras propiedades del gráfico?

Sí, puede modificar varias propiedades del gráfico, como datos, etiquetas y formato, mediante la API de Aspose.Slides para Java. Consulte la documentación para obtener más información.

### ¿Es Aspose.Slides para Java adecuado para la automatización profesional de PowerPoint?

Sí, Aspose.Slides para Java es una potente biblioteca para automatizar tareas de PowerPoint en aplicaciones Java. Ofrece funciones completas para trabajar con presentaciones, diapositivas, formas, gráficos y más.

### ¿Cómo puedo obtener más información sobre Aspose.Slides para Java?

Puede encontrar documentación extensa y ejemplos en la página de documentación de Aspose.Slides para Java [aquí](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
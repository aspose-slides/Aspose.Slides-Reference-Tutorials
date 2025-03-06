---
title: Obtenga ancho y alto del área de trazado del gráfico en diapositivas de Java
linktitle: Obtenga ancho y alto del área de trazado del gráfico en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a recuperar las dimensiones del área del trazado del gráfico en Java Slides usando Aspose.Slides para Java. Mejore sus habilidades de automatización de PowerPoint.
weight: 21
url: /es/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción

Los gráficos son una forma poderosa de visualizar datos en presentaciones de PowerPoint. A veces, es posible que necesite conocer las dimensiones del área de trazado de un gráfico por diversos motivos, como cambiar el tamaño o reposicionar elementos dentro del gráfico. Esta guía demostrará cómo obtener el ancho y el alto del área de trazado usando Java y Aspose.Slides para Java.

## Requisitos previos

 Antes de sumergirnos en el código, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargar la biblioteca desde el sitio web de Aspose.[aquí](https://releases.aspose.com/slides/java/).

## Paso 1: configurar el entorno

Asegúrese de tener la biblioteca Aspose.Slides para Java agregada a su proyecto Java. Puede hacer esto incluyendo la biblioteca en las dependencias de su proyecto o agregando manualmente el archivo JAR.

## Paso 2: crear una presentación de PowerPoint

Comencemos creando una presentación de PowerPoint y agregándole una diapositiva. Esto servirá como contenedor para nuestro gráfico.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Reemplazar`"Your Document Directory"` con la ruta a su directorio de documentos.

## Paso 3: agregar un gráfico

Ahora, agreguemos un gráfico de columnas agrupadas a la diapositiva. También validaremos el diseño del gráfico.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Este código crea un gráfico de columnas agrupadas en la posición (100, 100) con dimensiones (500, 350).

## Paso 4: Obtener las dimensiones del área de la parcela

Para recuperar el ancho y el alto del área de trazado del gráfico, podemos usar el siguiente código:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Ahora las variables`x`, `y`, `w` , y`h` contienen los valores respectivos para las coordenadas X, coordenadas Y, ancho y alto del área de trazado.

## Paso 5: guardar la presentación

Finalmente, guarde la presentación con el gráfico.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Asegúrate de reemplazar`"Chart_out.pptx"` con el nombre del archivo de salida que desee.

## Código fuente completo para obtener ancho y alto del área de trazado del gráfico en diapositivas de Java

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

En este artículo, cubrimos cómo obtener el ancho y el alto del área de trazado de un gráfico en Java Slides usando la API Aspose.Slides para Java. Esta información puede ser valiosa cuando necesita ajustar dinámicamente el diseño de sus gráficos dentro de presentaciones de PowerPoint.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el tipo de gráfico a algo que no sean columnas agrupadas?

 Puede cambiar el tipo de gráfico reemplazando`ChartType.ClusteredColumn` con la enumeración del tipo de gráfico deseado, como`ChartType.Line` o`ChartType.Pie`.

### ¿Puedo modificar otras propiedades del gráfico?

Sí, puede modificar varias propiedades del gráfico, como datos, etiquetas y formato, utilizando la API Aspose.Slides para Java. Consulte la documentación para obtener más detalles.

### ¿Aspose.Slides para Java es adecuado para la automatización profesional de PowerPoint?

Sí, Aspose.Slides para Java es una poderosa biblioteca para automatizar tareas de PowerPoint en aplicaciones Java. Proporciona funciones integrales para trabajar con presentaciones, diapositivas, formas, gráficos y más.

### ¿Cómo puedo obtener más información sobre Aspose.Slides para Java?

 Puede encontrar documentación extensa y ejemplos en la página de documentación de Aspose.Slides para Java.[aquí](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

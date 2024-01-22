---
title: Agregar barras de error en diapositivas de Java
linktitle: Agregar barras de error en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a agregar barras de error a gráficos de PowerPoint en Java usando Aspose.Slides. Guía paso a paso con código fuente para personalizar las barras de error.
type: docs
weight: 13
url: /es/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Introducción a agregar barras de error en diapositivas de Java usando Aspose.Slides

En este tutorial, demostraremos cómo agregar barras de error a un gráfico en una diapositiva de PowerPoint usando Aspose.Slides para Java. Las barras de error brindan información valiosa sobre la variabilidad o incertidumbre de los puntos de datos en un gráfico. Crearemos un gráfico de burbujas y le agregaremos barras de error. ¡Empecemos!

## Requisitos previos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puedes descargar la biblioteca desde[Aspose sitio web](https://downloads.aspose.com/slides/java).

## Paso 1: crea una presentación vacía

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Creando una presentación vacía
Presentation presentation = new Presentation();
```

En este paso, creamos una presentación vacía donde agregaremos nuestro gráfico con barras de error.

## Paso 2: crea un gráfico de burbujas

```java
// Crear un gráfico de burbujas
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Aquí, creamos un gráfico de burbujas y especificamos su posición y dimensiones en la diapositiva.

## Paso 3: Agregar barras de error y configurar el formato

```java
// Agregar barras de error y configurar su formato
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

En este paso, agregamos barras de error al gráfico y configuramos su formato. Puede personalizar las barras de error cambiando valores, tipos y otras propiedades.

- `errBarX` representa barras de error a lo largo del eje X.
- `errBarY` representa barras de error a lo largo del eje Y.
- Hacemos visibles las barras de error X e Y.
- `setValueType` especifica el tipo de valor para las barras de error (por ejemplo, Fijo o Porcentaje).
- `setValue` establece el valor de las barras de error.
- `setType` define el tipo de barras de error (por ejemplo, Más o Menos).
-  Establecemos el ancho de las líneas de la barra de error usando`getFormat().getLine().setWidth(2)`.
- `setEndCap`especifica si se incluyen tapas de extremo en las barras de error.

## Paso 4: guarde la presentación

```java
// Guardar presentación
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Finalmente, guardamos la presentación con las barras de error agregadas en una ubicación específica.

¡Eso es todo! Ha agregado con éxito barras de error a un gráfico en una diapositiva de PowerPoint usando Aspose.Slides para Java.

## Código fuente completo para agregar barras de error en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Creando una presentación vacía
Presentation presentation = new Presentation();
try
{
	// Crear un gráfico de burbujas
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Agregar barras de error y configurar su formato
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Guardar presentación
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusión

En este tutorial, hemos explorado cómo mejorar sus presentaciones de PowerPoint agregando barras de error a los gráficos usando Aspose.Slides para Java. Las barras de error brindan información valiosa sobre la variabilidad y las incertidumbres de los datos, lo que hace que sus presentaciones sean más informativas y visualmente atractivas.

## Preguntas frecuentes

### ¿Cómo puedo personalizar aún más la apariencia de las barras de error?

Puede personalizar las barras de error modificando sus propiedades, como el estilo de línea, el color y el ancho, como se demuestra en el Paso 3.

### ¿Puedo agregar barras de error a diferentes tipos de gráficos?

Sí, puede agregar barras de error a varios tipos de gráficos compatibles con Aspose.Slides para Java. Simplemente cree el tipo de gráfico deseado y siga los mismos pasos de personalización de la barra de errores.

### ¿Cómo puedo ajustar la posición y el tamaño del gráfico en la diapositiva?

 Puede controlar la posición y las dimensiones del gráfico ajustando los parámetros en el`addChart` método, como se muestra en el Paso 2.

### ¿Dónde puedo encontrar más información sobre Aspose.Slides para Java?

 Puedes consultar el[Documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para obtener información detallada sobre el uso de la biblioteca.
---
"description": "Aprenda a agregar barras de error a gráficos de PowerPoint en Java con Aspose.Slides. Guía paso a paso con código fuente para personalizar las barras de error."
"linktitle": "Agregar barras de error en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Agregar barras de error en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Agregar barras de error en diapositivas de Java


## Introducción a la adición de barras de error en diapositivas de Java mediante Aspose.Slides

En este tutorial, demostraremos cómo agregar barras de error a un gráfico en una diapositiva de PowerPoint con Aspose.Slides para Java. Las barras de error proporcionan información valiosa sobre la variabilidad o incertidumbre de los datos en un gráfico. Crearemos un gráfico de burbujas y le agregaremos barras de error. ¡Comencemos!

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargarla desde [Sitio web de Aspose](https://downloads.aspose.com/slides/java).

## Paso 1: Crea una presentación vacía

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Creando una presentación vacía
Presentation presentation = new Presentation();
```

En este paso, creamos una presentación vacía donde agregaremos nuestro gráfico con barras de error.

## Paso 2: Crea un gráfico de burbujas

```java
// Creación de un gráfico de burbujas
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

En este paso, añadimos barras de error al gráfico y configuramos su formato. Puedes personalizar las barras de error modificando valores, tipos y otras propiedades.

- `errBarX` representa barras de error a lo largo del eje X.
- `errBarY` Representa barras de error a lo largo del eje Y.
- Hacemos visibles las barras de error X e Y.
- `setValueType` Especifica el tipo de valor para las barras de error (por ejemplo, fijo o porcentaje).
- `setValue` Establece el valor de las barras de error.
- `setType` Define el tipo de barras de error (por ejemplo, Más o Menos).
- Establecemos el ancho de las líneas de la barra de error usando `getFormat().getLine().setWidth(2)`.
- `setEndCap` Especifica si se deben incluir tapas finales en las barras de error.

## Paso 4: Guardar la presentación

```java
// Guardar presentación
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Finalmente, guardamos la presentación con las barras de error añadidas en una ubicación específica.

¡Listo! Has añadido correctamente barras de error a un gráfico en una diapositiva de PowerPoint con Aspose.Slides para Java.

## Código fuente completo para agregar barras de error en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Creando una presentación vacía
Presentation presentation = new Presentation();
try
{
	// Creación de un gráfico de burbujas
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

En este tutorial, hemos explorado cómo mejorar sus presentaciones de PowerPoint añadiendo barras de error a los gráficos con Aspose.Slides para Java. Las barras de error proporcionan información valiosa sobre la variabilidad e incertidumbre de los datos, lo que hace que sus presentaciones sean más informativas y visualmente atractivas.

## Preguntas frecuentes

### ¿Cómo puedo personalizar aún más la apariencia de las barras de error?

Puede personalizar las barras de error modificando sus propiedades, como el estilo de línea, el color y el ancho, como se muestra en el Paso 3.

### ¿Puedo agregar barras de error a diferentes tipos de gráficos?

Sí, puedes agregar barras de error a varios tipos de gráficos compatibles con Aspose.Slides para Java. Simplemente crea el tipo de gráfico que desees y sigue los mismos pasos para personalizar las barras de error.

### ¿Cómo puedo ajustar la posición y el tamaño del gráfico en la diapositiva?

Puede controlar la posición y las dimensiones del gráfico ajustando los parámetros en el `addChart` método, como se muestra en el paso 2.

### ¿Dónde puedo encontrar más información sobre Aspose.Slides para Java?

Puedes consultar el [Documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/) para obtener información detallada sobre el uso de la biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
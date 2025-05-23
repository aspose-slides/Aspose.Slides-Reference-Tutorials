---
"description": "Cree gráficos de anillo con tamaños de orificio personalizados en Java Slides con Aspose.Slides para Java. Guía paso a paso con código fuente para personalizar gráficos."
"linktitle": "Diapositivas del agujero del gráfico de anillos en Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Diapositivas del agujero del gráfico de anillos en Java"
"url": "/es/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diapositivas del agujero del gráfico de anillos en Java


## Introducción al gráfico de anillos con un agujero en diapositivas de Java

En este tutorial, te guiaremos en la creación de un gráfico de anillos con un agujero usando Aspose.Slides para Java. Esta guía paso a paso te guiará en el proceso con ejemplos de código fuente.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargarla desde [Documentación de Aspose.Slides para Java](https://reference.aspose.com/slides/java/).

## Paso 1: Importar las bibliotecas necesarias

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Paso 2: Inicializar la presentación

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
```

## Paso 3: Crea el gráfico de anillos

```java
try {
    // Crea un gráfico de anillos en la primera diapositiva
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Establezca el tamaño del agujero en el gráfico de anillos (en porcentaje)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Guardar la presentación en el disco
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Desechar el objeto de presentación
    if (presentation != null) presentation.dispose();
}
```

## Paso 4: Ejecutar el código

Ejecute el código Java en su IDE o editor de texto para crear un gráfico de anillos con un tamaño de agujero específico. Asegúrese de reemplazar `"Your Document Directory"` con la ruta real donde desea guardar la presentación.

## Código fuente completo para el agujero del gráfico de anillos en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear una instancia de la clase Presentación
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Escribir presentación en disco
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusión

En este tutorial, aprendiste a crear un gráfico de anillos con un agujero usando Aspose.Slides para Java. Puedes personalizar el tamaño del agujero ajustando el... `setDoughnutHoleSize` parámetro del método.

## Preguntas frecuentes

### ¿Cómo puedo cambiar el color de los segmentos del gráfico?

Para cambiar el color de los segmentos del gráfico, puede utilizar el `setDataPointsInLegend` método en el `IChart` objeto y establezca el color deseado para cada punto de datos.

### ¿Puedo agregar etiquetas a los segmentos del gráfico de anillos?

Sí, puede agregar etiquetas a los segmentos del gráfico de anillos usando el `setDataPointsLabelValue` método en el `IChart` objeto.

### ¿Es posible agregar un título al gráfico?

¡Por supuesto! Puedes agregar un título al gráfico usando el `setTitle` método en el `IChart` objeto y proporcionar el texto del título deseado.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
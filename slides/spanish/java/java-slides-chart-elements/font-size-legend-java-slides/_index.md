---
"description": "Mejore sus presentaciones de PowerPoint con Aspose.Slides para Java. Aprenda a personalizar el tamaño de fuente de las leyendas y más con nuestra guía paso a paso."
"linktitle": "Leyenda del tamaño de fuente en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Leyenda del tamaño de fuente en diapositivas de Java"
"url": "/es/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Leyenda del tamaño de fuente en diapositivas de Java


## Introducción a la leyenda del tamaño de fuente en diapositivas de Java

En este tutorial, aprenderá a personalizar el tamaño de fuente de la leyenda de una diapositiva de PowerPoint con Aspose.Slides para Java. Le proporcionaremos instrucciones paso a paso y el código fuente para lograrlo.

## Prerrequisitos

Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto Java. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

## Paso 1: Inicializar la presentación

Primero, importe las clases necesarias e inicialice su presentación de PowerPoint.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Reemplazar `"Your Document Directory"` con la ruta real a su archivo de PowerPoint.

## Paso 2: Agregar un gráfico

A continuación, agregaremos un gráfico a la diapositiva y estableceremos el tamaño de fuente de la leyenda.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

En este código, creamos un gráfico de columnas agrupadas en la primera diapositiva y configuramos el tamaño de fuente del texto de la leyenda en 20 puntos. Puede ajustar el tamaño de fuente. `setFontHeight` valor para cambiar el tamaño de fuente según sea necesario.

## Paso 3: Personalizar los valores del eje

Ahora, personalicemos los valores del eje vertical del gráfico.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aquí se establecen los valores mínimo y máximo del eje vertical. Puede modificarlos según sus necesidades de datos.

## Paso 4: Guardar la presentación

Por último, guarde la presentación modificada en un nuevo archivo.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Este código guarda la presentación modificada como "output.pptx" en el directorio especificado.

## Código fuente completo para la leyenda del tamaño de fuente en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

Ha personalizado correctamente el tamaño de fuente de la leyenda en una diapositiva de PowerPoint en Java con Aspose.Slides para Java. Puede explorar más a fondo las capacidades de Aspose.Slides para crear presentaciones interactivas y visualmente atractivas.

## Preguntas frecuentes

### ¿Cómo cambio el tamaño de fuente del texto de la leyenda en un gráfico?

Para cambiar el tamaño de fuente del texto de la leyenda en un gráfico, puede utilizar el siguiente código:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

En este código, creamos un gráfico y establecemos el tamaño de fuente del texto de la leyenda en 20 puntos. Puedes ajustar el tamaño de fuente. `setFontHeight` valor para cambiar el tamaño de fuente.

### ¿Puedo personalizar otras propiedades de la leyenda en un gráfico?

Sí, puede personalizar varias propiedades de la leyenda de un gráfico con Aspose.Slides. Algunas de las propiedades comunes que puede personalizar incluyen el formato del texto, la posición, la visibilidad y más. Por ejemplo, para cambiar la posición de la leyenda, puede usar:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Este código establece que la leyenda aparezca en la parte inferior del gráfico. Consulte la documentación de Aspose.Slides para obtener más opciones de personalización.

### ¿Cómo establezco valores mínimos y máximos para el eje vertical en un gráfico?

Para establecer valores mínimos y máximos para el eje vertical en un gráfico, puede utilizar el siguiente código:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Aquí desactivamos el escalado automático de ejes y especificamos los valores mínimo y máximo del eje vertical. Ajuste los valores según sea necesario para los datos del gráfico.

### ¿Dónde puedo encontrar más información y documentación sobre Aspose.Slides?

Puede encontrar documentación completa y referencias de API para Aspose.Slides para Java en el sitio web de documentación de Aspose. Visite [aquí](https://reference.aspose.com/slides/java/) para obtener información detallada sobre el uso de la biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
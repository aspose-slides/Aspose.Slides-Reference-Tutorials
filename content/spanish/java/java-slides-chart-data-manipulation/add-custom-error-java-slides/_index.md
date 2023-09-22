---
title: Agregar error personalizado en diapositivas de Java
linktitle: Agregar error personalizado en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a agregar barras de error personalizadas a gráficos de PowerPoint en Presentaciones Java usando Aspose.Slides. Guía paso a paso con código fuente para una visualización precisa de los datos.
type: docs
weight: 11
url: /es/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Introducción a la adición de barras de error personalizadas en diapositivas de Java usando Aspose.Slides

En este tutorial, aprenderá cómo agregar barras de error personalizadas a un gráfico en una presentación de PowerPoint usando Aspose.Slides para Java. Las barras de error son útiles para mostrar la variabilidad o la incertidumbre en los puntos de datos de un gráfico.

## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:

- Biblioteca Aspose.Slides para Java instalada y configurada en su proyecto.
- Un entorno de desarrollo Java configurado.

## Paso 1: crea una presentación vacía

Primero, cree una presentación de PowerPoint vacía.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Creando una presentación vacía
Presentation presentation = new Presentation();
```

## Paso 2: agregue un gráfico de burbujas

A continuación, agregaremos un gráfico de burbujas a la presentación.

```java
// Crear un gráfico de burbujas
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Paso 3: agregue barras de error personalizadas

Ahora, agreguemos barras de error personalizadas a la serie de gráficos.

```java
// Agregar barras de error personalizadas y configurar su formato
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Paso 4: configurar los datos de las barras de error

En este paso, accederemos a los puntos de datos de la serie de gráficos y estableceremos los valores de las barras de error personalizadas para cada punto.

```java
// Acceder a puntos de datos de series de gráficos y configurar valores de barras de error para puntos individuales
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Configuración de barras de error para puntos de series de gráficos
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Paso 5: guarde la presentación

Finalmente, guarde la presentación con las barras de error personalizadas.

```java
// Guardar presentación
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

¡Eso es todo! Ha agregado con éxito barras de error personalizadas a un gráfico en una presentación de PowerPoint usando Aspose.Slides para Java.

## Código fuente completo para agregar error personalizado en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Creando una presentación vacía
Presentation presentation = new Presentation();
try
{
	// Crear un gráfico de burbujas
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	//Agregar barras de error personalizadas y configurar su formato
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Acceder a puntos de datos de series de gráficos y configurar valores de barras de error para puntos individuales
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Configuración de barras de error para puntos de series de gráficos
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Guardar presentación
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusión

En este completo tutorial, ha aprendido cómo mejorar sus presentaciones de PowerPoint agregando barras de error personalizadas a los gráficos usando Aspose.Slides para Java. Las barras de error brindan información valiosa sobre la variabilidad y la incertidumbre de los datos, lo que hace que sus gráficos sean más informativos y visualmente atractivos.

## Preguntas frecuentes

### ¿Cómo personalizo la apariencia de las barras de error?

 Puede personalizar la apariencia de las barras de error modificando las propiedades del`IErrorBarsFormat` objeto, como estilo de línea, color de línea y ancho de la barra de error.

### ¿Puedo agregar barras de error a otros tipos de gráficos?

Sí, puede agregar barras de error a varios tipos de gráficos admitidos por Aspose.Slides para Java, incluidos gráficos de barras, gráficos de líneas y gráficos de dispersión.

### ¿Cómo configuro diferentes valores de barra de error para cada punto de datos?

Puede recorrer los puntos de datos y establecer valores de barra de error personalizados para cada punto, como se muestra en el código anterior.

### ¿Es posible ocultar barras de error para puntos de datos específicos?

 Sí, puede controlar la visibilidad de las barras de error para puntos de datos individuales configurando el`setVisible` propiedad de la`IErrorBarsFormat` objeto.
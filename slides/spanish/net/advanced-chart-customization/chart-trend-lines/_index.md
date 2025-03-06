---
title: Explorando las líneas de tendencia del gráfico en Aspose.Slides para .NET
linktitle: Líneas de tendencia del gráfico
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a agregar varias líneas de tendencia a los gráficos usando Aspose.Slides para .NET en esta guía paso a paso. ¡Mejore sus habilidades de visualización de datos con facilidad!
weight: 12
url: /es/net/advanced-chart-customization/chart-trend-lines/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


En el mundo de la visualización y presentación de datos, la incorporación de gráficos puede ser una forma poderosa de transmitir información de manera efectiva. Aspose.Slides para .NET proporciona un conjunto de herramientas rico en funciones para trabajar con gráficos, incluida la capacidad de agregar líneas de tendencia a sus gráficos. En este tutorial, profundizaremos en el proceso de agregar líneas de tendencia a un gráfico paso a paso usando Aspose.Slides para .NET. 

## Requisitos previos

Antes de comenzar a trabajar con Aspose.Slides para .NET, deberá asegurarse de cumplir con los siguientes requisitos previos:

1. Aspose.Slides para .NET: Para acceder a la biblioteca y usarla, debe tener instalado Aspose.Slides para .NET. Puedes obtener la biblioteca en el[pagina de descarga](https://releases.aspose.com/slides/net/).

2. Entorno de desarrollo: debe tener configurado un entorno de desarrollo, preferiblemente utilizando un entorno de desarrollo integrado .NET como Visual Studio.

3. Conocimientos básicos de C#: Es beneficioso tener una comprensión fundamental de la programación en C#, ya que usaremos C# para trabajar con Aspose.Slides para .NET.

Ahora que hemos cubierto los requisitos previos, analicemos paso a paso el proceso de agregar líneas de tendencia a un gráfico.

## Importando espacios de nombres

Primero, asegúrese de importar los espacios de nombres necesarios a su proyecto C#. Estos espacios de nombres son esenciales para trabajar con Aspose.Slides para .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Paso 1: crea una presentación

En este paso, creamos una presentación vacía para trabajar.

```csharp
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";

// Cree un directorio si aún no está presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Creando una presentación vacía
Presentation pres = new Presentation();
```

## Paso 2: agregue un gráfico a la diapositiva

A continuación, agregamos un gráfico de columnas agrupadas a una diapositiva.

```csharp
// Crear un gráfico de columnas agrupadas
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Paso 3: agregue líneas de tendencia al gráfico

Ahora agregamos varios tipos de líneas de tendencia a la serie de gráficos.

### Agregar una línea de tendencia exponencial

```csharp
// Agregar una línea de tendencia exponencial para la serie de gráficos 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Agregar una línea de tendencia lineal

```csharp
// Agregar una línea de tendencia lineal para la serie de gráficos 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Agregar una línea de tendencia logarítmica

```csharp
// Agregar una línea de tendencia logarítmica para la serie de gráficos 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Agregar una línea de tendencia de media móvil

```csharp
// Agregar una línea de tendencia de promedio móvil para la serie de gráficos 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Agregar una línea de tendencia polinómica

```csharp
// Agregar una línea de tendencia polinómica para la serie de gráficos 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Agregar una línea de tendencia eléctrica

```csharp
// Agregar línea de tendencia de energía para la serie de gráficos 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Paso 4: guarde la presentación

Después de agregar líneas de tendencia al gráfico, guarde la presentación.

```csharp
// Guardar presentación
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

¡Eso es todo! Ha agregado con éxito varias líneas de tendencia a su gráfico usando Aspose.Slides para .NET.

## Conclusión

Aspose.Slides para .NET es una biblioteca versátil que le permite crear y manipular gráficos con facilidad. Siguiendo esta guía paso a paso, puede agregar diferentes tipos de líneas de tendencia a sus gráficos, mejorando la representación visual de sus datos.

### Preguntas frecuentes

### ¿Dónde puedo encontrar la documentación de Aspose.Slides para .NET?
 Puedes acceder a la documentación[aquí](https://reference.aspose.com/slides/net/).

### ¿Cómo puedo descargar Aspose.Slides para .NET?
 Puede descargar Aspose.Slides para .NET desde la página de descarga[aquí](https://releases.aspose.com/slides/net/).

### ¿Hay una prueba gratuita disponible para Aspose.Slides para .NET?
 Sí, puedes probar Aspose.Slides para .NET gratis visitando[este enlace](https://releases.aspose.com/).

### ¿Dónde puedo comprar Aspose.Slides para .NET?
 Para comprar Aspose.Slides para .NET, visite la página de compra[aquí](https://purchase.aspose.com/buy).

### ¿Necesito una licencia temporal de Aspose.Slides para .NET?
 Puede obtener una licencia temporal para Aspose.Slides para .NET en[este enlace](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

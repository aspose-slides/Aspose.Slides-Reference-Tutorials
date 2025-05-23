---
"date": "2025-04-15"
"description": "Aprenda a automatizar la creación de gráficos circulares en presentaciones .NET con Aspose.Slides, mejorando la visualización de datos sin esfuerzo."
"title": "Cómo crear y personalizar gráficos circulares en presentaciones .NET con Aspose.Slides"
"url": "/es/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear y personalizar gráficos circulares en presentaciones .NET con Aspose.Slides

## Introducción
Crear presentaciones atractivas e informativas es crucial para una comunicación eficaz, ya sea que se presenten datos en el trabajo o se expongan los últimos hallazgos de un proyecto. Una forma eficaz de visualizar datos es mediante gráficos circulares, que pueden representar concisamente partes de un todo. Sin embargo, crear manualmente estos gráficos en programas de presentación como PowerPoint puede llevar mucho tiempo y carecer de la flexibilidad necesaria para las actualizaciones dinámicas.

Aquí es donde Aspose.Slides para .NET entra en juego. Esta completa biblioteca permite crear, modificar y aplicar estilo a presentaciones mediante programación, lo que la convierte en una herramienta invaluable para desarrolladores que desean automatizar su flujo de trabajo y garantizar la coherencia entre presentaciones.

En este tutorial, exploraremos cómo usar Aspose.Slides para .NET para crear y personalizar gráficos circulares en tus presentaciones. Aprenderás a:
- **Crear una presentación y acceder a las diapositivas**
- **Agregar y configurar gráficos circulares**
- **Personalizar datos y series de gráficos**
- **Sectores de gráficos circulares de estilo**
- **Agregar etiquetas personalizadas**
- **Configurar las propiedades de visualización y guardar la presentación**

¿Listo para crear gráficos circulares increíbles fácilmente? ¡Comencemos!

## Prerrequisitos
Antes de comenzar, asegúrese de tener la siguiente configuración en su lugar:

### Bibliotecas requeridas
- Aspose.Slides para .NET (versión 21.11 o posterior recomendada)

### Configuración del entorno
- Un entorno de desarrollo que ejecute .NET Framework o .NET Core/5+/6+
- Un editor de código como Visual Studio

### Requisitos previos de conocimiento
- Comprensión básica de la programación en C#
- Familiaridad con conceptos orientados a objetos

## Configuración de Aspose.Slides para .NET
Para empezar, necesitará instalar la biblioteca Aspose.Slides. Puede hacerlo mediante cualquiera de los siguientes métodos:

**CLI de .NET**
```bash
dotnet add package Aspose.Slides
```

**Consola del administrador de paquetes**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet**
- Abra su proyecto en Visual Studio.
- Vaya a "Herramientas" > "Administrador de paquetes NuGet" > "Administrar paquetes NuGet para la solución".
- Busque "Aspose.Slides" e instale la última versión.

### Pasos para la adquisición de la licencia
Para usar Aspose.Slides, puedes empezar con una prueba gratuita descargando una licencia temporal. Visita [El sitio web de Aspose](https://purchase.aspose.com/temporary-license/) Para obtenerla. Para uso continuo, considere comprar una licencia completa.

### Inicialización y configuración básicas
Una vez instalado, inicialice la clase Presentación, que representa su archivo PPTX:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Guía de implementación
Desglosaremos el proceso de creación de gráficos circulares en secciones fáciles de manejar. Cada sección está diseñada para centrarse en una función específica, lo que le permitirá ampliar sus conocimientos gradualmente.

### Crear una presentación y acceder a las diapositivas
**Descripción general:** Empieza creando una nueva presentación y accediendo a su primera diapositiva. Esto prepara el terreno para añadir gráficos y otros elementos.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Crear una instancia de la clase Presentation que representa un archivo PPTX
    Presentation presentation = new Presentation();
    
    // Acceder a la primera diapositiva
    ISlide slides = presentation.Slides[0];
}
```

### Agregar y configurar un gráfico circular
**Descripción general:** Aprenda cómo agregar un gráfico circular a su diapositiva y configurar su título para el contexto.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Crear una instancia de la clase Presentation que representa un archivo PPTX
    Presentation presentation = new Presentation();
    
    // Acceder a la primera diapositiva
    ISlide slides = presentation.Slides[0];
    
    // Agregar gráfico con datos predeterminados a la diapositiva
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Título del cuadro de configuración
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Personalizar datos y series de gráficos
**Descripción general:** Personalice las categorías y series de datos para adaptarlas a sus requisitos específicos.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Crear una instancia de la clase Presentation que representa un archivo PPTX
    Presentation presentation = new Presentation();
    
    // Acceder a la primera diapositiva
    ISlide slides = presentation.Slides[0];
    
    // Agregar gráfico con datos predeterminados a la diapositiva
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Establecer la primera serie en Mostrar valores
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Configuración del índice de la hoja de datos del gráfico
    int defaultWorksheetIndex = 0;
    
    // Obtener la hoja de trabajo de datos del gráfico
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Eliminar series y categorías generadas por defecto
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Añadiendo nuevas categorías
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Añadiendo nueva serie
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Ahora se están rellenando los datos de la serie
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Personalizar estilos de sectores de gráficos circulares
**Descripción general:** Dale estilo a sectores individuales de tu gráfico circular para mejorar el atractivo visual y enfatizar puntos de datos clave.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Crear una instancia de la clase Presentation que representa un archivo PPTX
    Presentation presentation = new Presentation();
    
    // Acceder a la primera diapositiva
    ISlide slides = presentation.Slides[0];
    
    // Agregar gráfico con datos predeterminados a la diapositiva
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Obtener la serie del gráfico
    IChartSeries series = chart.ChartData.Series[0];
    
    // Personalización de estilos de sector para cada punto de datos de la serie
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Establecer el borde del sector
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Establecer el borde del sector
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Establecer el borde del sector
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Agregar etiquetas personalizadas al gráfico circular
**Descripción general:** Mejore su gráfico circular agregando etiquetas personalizadas para una representación de datos más clara.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Ajuste la posición de la etiqueta según sea necesario
    }
}
```

### Conclusión
Ya aprendió a crear y personalizar gráficos circulares en presentaciones .NET con Aspose.Slides. Esta automatización puede optimizar significativamente sus visualizaciones de datos, ahorrando tiempo y garantizando la coherencia en todas las presentaciones.

Para explorar más a fondo las capacidades de Aspose.Slides para .NET, considere profundizar en funciones adicionales como la creación de otros tipos de gráficos o la integración de elementos de diseño más complejos en sus diapositivas.

¡Feliz codificación!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
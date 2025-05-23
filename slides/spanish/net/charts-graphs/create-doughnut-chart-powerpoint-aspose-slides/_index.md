---
"date": "2025-04-15"
"description": "Aprenda a crear gráficos de anillos dinámicos y visualmente atractivos en presentaciones de PowerPoint utilizando la poderosa biblioteca Aspose.Slides para .NET."
"title": "Cómo crear un gráfico de anillos en PowerPoint con Aspose.Slides para .NET"
"url": "/es/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear un gráfico de anillos en PowerPoint con Aspose.Slides para .NET
Crear gráficos visualmente atractivos es esencial para una presentación de datos eficaz. Los gráficos de anillos son perfectos para ilustrar partes de un todo, lo que los hace ideales para la visualización de datos porcentuales. Este tutorial le guiará en la creación de un gráfico de anillos dinámico en PowerPoint con la potente biblioteca Aspose.Slides para .NET.

## Introducción
Las presentaciones suelen requerir representaciones visuales de conjuntos de datos complejos, donde los gráficos de barras o líneas tradicionales pueden resultar insuficientes. El gráfico de anillos se presenta como una herramienta versátil para comunicar eficazmente datos porcentuales con estilo y claridad. En este tutorial, exploraremos cómo Aspose.Slides para .NET simplifica la creación de estos gráficos directamente en PowerPoint.

**Lo que aprenderás:**
- Configuración de Aspose.Slides para .NET
- Instrucciones paso a paso para crear un gráfico de anillos
- Cómo añadir series y categorías a su gráfico
- Configuración de etiquetas de datos para una mayor claridad
- Guardando la presentación final

Veamos cómo puede aprovechar Aspose.Slides para .NET para mejorar sus presentaciones con gráficos de anillos personalizados.

## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente en su lugar:
- **Biblioteca Aspose.Slides para .NET**:Disponible a través de NuGet o descarga directa.
- **Entorno de desarrollo**Se recomienda Visual Studio para proyectos .NET.
- Conocimientos básicos de C# y familiaridad con la estructura de PowerPoint.

## Configuración de Aspose.Slides para .NET
Para empezar a crear gráficos, primero debe configurar la biblioteca Aspose.Slides en su proyecto. Aquí tiene varias maneras de instalarla:

**Usando la CLI .NET:**

```bash
dotnet add package Aspose.Slides
```

**Uso de la consola del administrador de paquetes:**

```powershell
Install-Package Aspose.Slides
```

**A través de la interfaz de usuario del Administrador de paquetes NuGet:**
Busque "Aspose.Slides" e instale la última versión.

Una vez instalado, puedes empezar a configurar tu proyecto. Si no conoces Aspose.Slides, considera obtener una licencia temporal o una prueba gratuita para explorar todas sus funciones sin limitaciones.

### Inicializar su proyecto
A continuación te mostramos cómo puedes inicializar Aspose.Slides en tu aplicación:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Crear una instancia de la clase Presentación
        Presentation presentation = new Presentation();
        
        // Tu código para manipular la presentación va aquí
        
        // Guardar la presentación
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Guía de implementación
### Creación de un gráfico de anillos
#### Descripción general
Primero, crearemos un gráfico de anillos vacío en una diapositiva de PowerPoint. Esto servirá como base para agregar datos y personalizar su apariencia.

**Paso 1: Agregar un gráfico de anillos**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Agregue un gráfico de anillos a la primera diapositiva en la posición (10, 10) con tamaño (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Borrar series y categorías existentes
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Desactivar la leyenda para una apariencia más limpia
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explicación:**
- **añadir gráfico**: Inserta un nuevo gráfico de anillos en la diapositiva.
- **obtenerLibroDeDatosDeGráficos**:Proporciona acceso a las celdas de datos en el gráfico para su manipulación.

### Agregar series y categorías
#### Descripción general
A continuación, completaremos su gráfico con datos significativos agregando series y categorías.

**Paso 2: Agregar series de datos**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Añadir serie
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Personalización del agujero de dona y el ángulo de inicio
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Agregar categorías
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Dar formato al relleno y a la línea del punto de datos
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explicación:**
- **agregar**: Inserta nuevas series y categorías en el gráfico.
- **establecer tamaño del agujero de la dona**Configura el tamaño del agujero de dona, mejorando su atractivo visual.

### Configuración de etiquetas de datos
#### Descripción general
Las etiquetas de datos contextualizan los datos de tus gráficos. Personalízalas para mejorar su legibilidad.

**Paso 3: Personalizar las etiquetas de datos**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Personalización de etiquetas de datos
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Explicación:**
- **Etiqueta de datos I**:Personaliza las etiquetas de datos para mayor claridad y presentación.
- **establecerTextoCentral**, **mostrarPorcentaje**: Mejore la legibilidad de la etiqueta centrando el texto y mostrando porcentajes.

## Conclusión
Siguiendo esta guía, ha aprendido a crear un gráfico de anillos dinámico en PowerPoint con Aspose.Slides para .NET. Esta potente biblioteca permite una amplia personalización, lo que le permite adaptar sus gráficos con precisión a las necesidades de su presentación.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
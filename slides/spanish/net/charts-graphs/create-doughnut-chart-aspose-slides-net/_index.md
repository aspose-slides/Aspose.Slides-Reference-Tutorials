---
"date": "2025-04-15"
"description": "Aprenda a crear gráficos de anillos dinámicos con Aspose.Slides para .NET. Siga esta guía para obtener instrucciones paso a paso, incluyendo la configuración y las funciones avanzadas."
"title": "Guía paso a paso&#58; Crear un gráfico de anillos con Aspose.Slides .NET | Gráficos y tablas"
"url": "/es/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Guía paso a paso: Crear un gráfico de anillos con Aspose.Slides .NET

## Introducción

Imagina que tienes que presentar los resultados del análisis de datos a tu equipo o clientes y necesitas una forma atractiva de visualizar la información. Descubre el gráfico de anillos: una herramienta versátil que transforma cifras brutas en información fácilmente comprensible. Con Aspose.Slides para .NET, crear un gráfico de anillos personalizado en tus diapositivas de presentación es sencillo y eficiente. Esta guía te guiará en el uso de Aspose.Slides para crear un gráfico de anillos visualmente atractivo, con configuraciones de series personalizadas.

**Lo que aprenderás:**
- Configuración de su entorno de desarrollo con Aspose.Slides para .NET
- Creación y personalización de gráficos de anillos en presentaciones
- Implementar funciones avanzadas como nombres de categorías y líneas guía
- Optimización del rendimiento para grandes conjuntos de datos

Analicemos en profundidad los requisitos previos que necesitas para comenzar.

## Prerrequisitos

Antes de implementar esta función, asegúrese de que su entorno de desarrollo esté configurado correctamente. Este tutorial presupone conocimientos básicos de programación .NET y familiaridad con Visual Studio o un IDE similar.

### Bibliotecas y versiones requeridas
- **Aspose.Slides para .NET**:Asegure la compatibilidad con la última versión comprobando su [documentación oficial](https://reference.aspose.com/slides/net/).

### Requisitos de configuración del entorno
- Un entorno .NET funcional.
- Acceso a un editor de código, como Visual Studio.

### Requisitos previos de conocimiento
- Comprensión básica de C# y .NET Framework.
- Familiaridad con los conceptos de software de presentación (opcional pero útil).

## Configuración de Aspose.Slides para .NET

Para empezar a usar Aspose.Slides en tu proyecto, necesitas instalarlo mediante NuGet. Estos son los métodos disponibles:

**Usando la CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Usando el Administrador de paquetes:**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet:**
Busque "Aspose.Slides" e instale la última versión.

### Pasos para la adquisición de la licencia

1. **Prueba gratuita**:Empieza con un [prueba gratuita](https://releases.aspose.com/slides/net/) para explorar las funcionalidades básicas.
2. **Licencia temporal**: Obtenga una licencia temporal si necesita acceso a todas las funciones para fines de evaluación visitando [aquí](https://purchase.aspose.com/temporary-license/).
3. **Compra**:Para uso comercial, compre una licencia en [Sitio web de Aspose](https://purchase.aspose.com/buy).

Una vez instalado y licenciado, inicialice Aspose.Slides en su proyecto:
```csharp
using Aspose.Slides;

// Inicializar Aspose.Slides para .NET
var presentation = new Presentation();
```

## Guía de implementación

### Crear una nueva presentación y agregar un gráfico de anillos

#### Descripción general
Comenzaremos creando una nueva presentación y agregando un gráfico de anillos a la primera diapositiva. Esta sección explica cómo cargar una presentación existente, acceder a las diapositivas e insertar gráficos.

**Paso 1: Cargar o crear una presentación**
Primero, especifique el directorio de su documento y cargue una presentación existente:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Si no tiene un archivo existente, cree uno nuevo con `new Presentation()`.

**Paso 2: Acceda a la primera diapositiva**
Obtenga acceso a la primera diapositiva donde agregaremos nuestro gráfico:
```csharp
ISlide slide = pres.Slides[0];
```

**Paso 3: Agregar un gráfico de anillos**
Agregue un gráfico de anillos en coordenadas y dimensiones específicas:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuración del libro de trabajo de datos

#### Descripción general
Esta sección explica cómo configurar el libro de datos asociado con su gráfico de anillos.

**Paso 4: Acceder y borrar los datos existentes**
Acceda al libro de datos del gráfico. Luego, borre las series o categorías existentes:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Paso 5: Deshabilitar leyenda y agregar serie**
Deshabilite la leyenda para mantener el gráfico limpio y luego agregue hasta 15 series con configuraciones personalizadas:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Agregar categorías y puntos de datos

#### Descripción general
Ahora, vamos a completar el gráfico con categorías y puntos de datos para cada serie.

**Paso 6: Agregar categorías**
Recorra el bucle para agregar 15 categorías:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Paso 7: Rellenar puntos de datos**
Agregar puntos de datos para cada serie dentro de la categoría actual:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Personalizar la apariencia
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Configurar el formato de etiqueta para la última serie
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Configurar la visualización de etiquetas
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Guardar la presentación

**Paso 8: Guardar el archivo**
Por último, guarde su presentación en un directorio específico:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
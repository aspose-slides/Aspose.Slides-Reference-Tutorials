---
"date": "2025-04-15"
"description": "Aprenda a mejorar sus presentaciones con gráficos de dispersión usando Aspose.Slides para .NET. Siga esta guía completa para crear y personalizar gráficos eficazmente."
"title": "Cómo agregar gráficos de dispersión a presentaciones con Aspose.Slides .NET&#58; guía paso a paso"
"url": "/es/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar gráficos de dispersión a presentaciones con Aspose.Slides .NET: guía paso a paso

## Introducción
¿Quieres mejorar tus presentaciones integrando gráficos de dispersión fácilmente? Con la potencia de Aspose.Slides para .NET, crear y personalizar gráficos es pan comido. Este tutorial te guiará para añadir gráficos de dispersión a tus diapositivas con Aspose.Slides para .NET. Al dominar estas técnicas, presentarás los datos de forma más eficaz y crearás presentaciones visualmente atractivas.

**Lo que aprenderás:**
- Configuración de Aspose.Slides para .NET en su proyecto
- Crear una nueva presentación y acceder a su primera diapositiva
- Cómo agregar gráficos de dispersión con líneas suaves a las diapositivas
- Borrar series existentes y agregar nuevas a los gráficos
- Modificar puntos de datos y estilos de marcadores para una mejor visualización
- Guardar la presentación en un directorio específico

Comencemos repasando los requisitos previos.

## Prerrequisitos
Antes de implementar Aspose.Slides para .NET, asegúrese de tener lo siguiente:
- **Biblioteca Aspose.Slides para .NET**:Versión 23.7 o posterior.
- **Entorno de desarrollo**:Visual Studio 2019 o más reciente con .NET Framework 4.6.1+ o .NET Core/5+.
- **Conocimientos básicos de C#**:Familiaridad con la programación orientada a objetos en C#.

## Configuración de Aspose.Slides para .NET
Para empezar a usar Aspose.Slides, necesitas instalar la biblioteca en tu proyecto. Sigue estos pasos:

**Usando la CLI .NET:**
```bash
dotnet add package Aspose.Slides
```

**Uso de la consola del administrador de paquetes:**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet:**
- Busque "Aspose.Slides" e instale la última versión.

### Adquisición de licencias
Puedes empezar con una prueba gratuita o solicitar una licencia temporal para explorar todas las funciones. Para comprarla, sigue estos pasos:
1. Visita [Comprar Aspose.Slides](https://purchase.aspose.com/buy) para comprar una licencia completa.
2. Para obtener una licencia temporal, visite [Página de licencia temporal](https://purchase.aspose.com/temporary-license/).

Una vez que haya obtenido su archivo de licencia, agréguelo a su proyecto usando:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Guía de implementación
Desglosaremos la implementación en secciones lógicas según las características.

### Crear una presentación y agregar diapositiva
Esta sección demuestra cómo crear una presentación y acceder a su primera diapositiva.

#### Descripción general
Comience creando una instancia de la `Presentation` Clase que representa tu archivo de PowerPoint. Acceder a las diapositivas es sencillo con este modelo de objetos.

#### Pasos de implementación
**Paso 1: Inicializar la presentación**
```csharp
using Aspose.Slides;

// Crear una nueva presentación
t Presentation pres = new Presentation();
```
Este código inicializa un nuevo documento de presentación.

**Paso 2: Acceder a la primera diapositiva**
```csharp
// Acceda a la primera diapositiva de la presentación
ISlide slide = pres.Slides[0];
```
Aquí, `pres.Slides[0]` accede a la primera diapositiva. 

### Agregar gráfico de dispersión a la diapositiva
Ahora agreguemos un gráfico de dispersión a su presentación.

#### Descripción general
Agregar gráficos puede ayudarte a representar datos visualmente en presentaciones. Aspose.Slides facilita la incorporación de varios tipos de gráficos, incluyendo diagramas de dispersión.

#### Pasos de implementación
**Paso 1: Crear y agregar un gráfico de dispersión**
```csharp
using Aspose.Slides.Charts;

// Cree y agregue un gráfico de dispersión predeterminado con líneas suaves
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Este fragmento agrega un gráfico de dispersión en la posición y el tamaño especificados.

### Borrar y agregar series a los datos del gráfico
#### Descripción general
Es posible que necesites personalizar tu gráfico borrando series existentes y añadiendo nuevas. Esta sección explica esa función.

#### Pasos de implementación
**Paso 1: Acceder al libro de trabajo de datos del gráfico**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Borrar cualquier serie preexistente
chart.ChartData.Series.Clear();
```
Este código borra los datos existentes para comenzar de cero con una nueva serie.

**Paso 2: Agregar nueva serie**
```csharp
// Añade una nueva serie llamada "Serie 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Añade otra serie llamada "Serie 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Estos pasos agregan dos nuevas series al gráfico.

### Modificar los puntos de datos de la primera serie y el estilo del marcador
#### Descripción general
Personalice los puntos de datos y los estilos de marcadores para una mejor visualización de sus gráficos de dispersión.

#### Pasos de implementación
**Paso 1: Acceder y agregar puntos de datos**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Sumar los puntos de datos (1, 3) y (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Paso 2: Modificar el estilo del marcador**
```csharp
// Cambiar el tipo de serie y modificar el estilo del marcador
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Modificar los puntos de datos de la segunda serie y el estilo del marcador
#### Descripción general
De manera similar, personalice la segunda serie para adaptarla a sus necesidades de presentación.

#### Pasos de implementación
**Paso 1: Acceder y agregar múltiples puntos de datos**
```csharp
// Acceda a la segunda serie de gráficos
series = chart.ChartData.Series[1];

// Agregar múltiples puntos de datos
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Paso 2: Modificar el estilo del marcador**
```csharp
// Cambiar el tamaño del marcador y el símbolo para la segunda serie
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Guardar presentación
Por último, guarde su presentación en un directorio específico.

#### Pasos de implementación
**Paso 1: Definir directorio**
Asegúrese de que el directorio de salida exista. Si no, créelo:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Guardar la presentación
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Este código guarda su archivo de presentación en una ubicación específica.

## Conclusión
Ya ha añadido correctamente gráficos de dispersión a sus presentaciones con Aspose.Slides para .NET. Continúe explorando las funciones y personalizaciones adicionales disponibles en la biblioteca para mejorar sus habilidades de visualización de datos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
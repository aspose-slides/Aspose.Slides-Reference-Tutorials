---
date: '2026-06-03'
description: Aprenda cómo crear gráficos en presentaciones .NET y agregar un gráfico
  a una diapositiva con Aspose.Slides for Java. Siga esta guía paso a paso para la
  visualización de datos.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Crear gráficos en .NET usando Aspose.Slides for Java
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráficos en .NET usando Aspose.Slides para Java

## Introducción
Crear presentaciones atractivas a menudo implica integrar representaciones visuales de datos, como gráficos, para mejorar la comprensión y el compromiso de la audiencia. **Si deseas crear gráficos en .NET**, Aspose.Slides para Java te ofrece una API potente e independiente del lenguaje que funciona sin problemas dentro de aplicaciones .NET. En este tutorial aprenderás a inicializar una presentación, agregar una variedad de tipos de gráficos, gestionar el libro de datos del gráfico y formatear los datos de la serie, incluido el manejo de valores negativos. Al final podrás generar gráficos en archivos de presentación de forma programática y añadir un gráfico a una diapositiva con solo unas pocas líneas de código.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Crear gráficos en presentaciones .NET usando Aspose.Slides para Java.  
- **¿Qué versión de la biblioteca se requiere?** Aspose.Slides para Java 25.4 o posterior.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Puedo usar Maven o Gradle?** Sí, se admiten ambos sistemas de compilación.  
- **¿Qué tipos de gráficos están disponibles?** Columnas agrupadas, línea, pastel, barra, área y más.

## ¿Cómo crear gráficos en presentaciones .NET con Aspose.Slides para Java?
La clase `Presentation` representa un archivo PowerPoint y proporciona métodos para manipular sus diapositivas. Carga un nuevo objeto `Presentation`, llama a `slides.addEmptySlide()` para obtener una diapositiva y luego usa `slide.getShapes().addChart()` para insertar el tipo de gráfico deseado en las coordenadas que especifiques. Después de añadir el gráfico, rellena su libro de datos con series y categorías, aplica cualquier formato (como colores para valores negativos) y, finalmente, guarda la presentación en un archivo .pptx. Este flujo te permite **crear gráficos en .NET** con un conjunto conciso de llamadas a la API.

## ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una API multiplataforma que permite a los desarrolladores crear, modificar y renderizar archivos PowerPoint sin Microsoft Office. Soporta **más de 50 formatos de entrada y salida** y puede procesar presentaciones con miles de diapositivas manteniendo el uso de memoria por debajo de 200 MB.

## ¿Por qué usar Aspose.Slides para Java en un proyecto .NET?
Aspose.Slides para Java se ejecuta en la Máquina Virtual Java y puede ser llamado desde .NET mediante un wrapper nativo, ofreciendo a los desarrolladores .NET acceso a un motor de gráficos maduro, procesamiento de alto rendimiento de grandes conjuntos de datos y plena compatibilidad con código Java existente sin reescribir la lógica.

## Requisitos previos
Antes de sumergirte en la creación de gráficos con Aspose.Slides para Java, repasemos lo que necesitas:

### Bibliotecas y versiones requeridas
- **Aspose.Slides para Java**: Versión 25.4 o posterior.

### Requisitos de configuración del entorno
- Un entorno de desarrollo que admita aplicaciones .NET.  
- Comprensión básica de conceptos de programación Java.

### Conocimientos previos
- Familiaridad con la creación de presentaciones en un contexto de aplicación .NET.  
- Entendimiento de dependencias Java y su gestión (Maven/Gradle).

## Configuración de Aspose.Slides para Java
Para comenzar a usar Aspose.Slides, debes incluirlo como dependencia en tu proyecto. Así es como puedes hacerlo:

### Maven
El fragmento de dependencia Maven agrega Aspose.Slides para Java a tu proyecto.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluye esta línea en tu archivo `build.gradle` para obtener la biblioteca desde Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, puedes descargar la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Pasos para la adquisición de licencia
- **Prueba gratuita**: Comienza con una licencia temporal para explorar las funciones.  
- **Compra**: Adquiere una licencia para uso ilimitado en producción.

#### Inicialización básica y configuración
La inicialización de `Slides` requiere establecer la licencia y crear una instancia de `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Esta configuración garantiza que la gestión de recursos se maneje de manera eficaz.

## Guía de implementación
Te guiaremos paso a paso en la implementación de las funcionalidades.

### Inicializando la presentación
**Descripción general:**  
Crear una instancia de presentación establece la base para todas las operaciones posteriores. Esta característica muestra cómo comenzar desde cero usando Aspose.Slides.

#### Paso 1: Importar paquetes necesarios
`Presentation` y clases relacionadas forman parte del espacio de nombres `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Paso 2: Crear un nuevo objeto Presentation
Instancia un objeto `Presentation` y envuélvelo en un bloque try‑with‑resources para garantizar su liberación.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Esto asegura que el objeto de presentación se libere correctamente después de su uso, evitando fugas de memoria.*

### Añadiendo un gráfico a la diapositiva
**Descripción general:**  
Añadir un gráfico a tu diapositiva puede hacer que la visualización de datos sea más efectiva y atractiva.

#### Paso 1: Importar paquetes necesarios
La clase `Chart` representa una forma de gráfico que puede colocarse en una diapositiva y personalizarse.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Paso 2: Inicializar la presentación y añadir el gráfico
Crea una diapositiva y luego llama a `addChart` con `ChartType.ClusteredColumn` y la posición y tamaño deseados.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Aquí, añadimos un gráfico de columnas agrupadas a la primera diapositiva en las coordenadas y dimensiones especificadas.*

### Gestionando el libro de datos del gráfico
**Descripción general:**  
Gestionar eficientemente el libro de datos de tu gráfico te permite manipular series y categorías sin problemas.

#### Paso 1: Importar paquetes necesarios
`IChartDataWorkbook` brinda acceso al libro de trabajo subyacente similar a Excel que utilizan los gráficos.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Paso 2: Acceder y limpiar el libro de datos
Obtén el libro de datos del gráfico y elimina cualquier dato existente para comenzar de cero.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Limpiar el libro de datos es crucial para iniciar con una hoja limpia al añadir nuevas series y categorías.*

### Añadiendo series y categorías al gráfico
**Descripción general:**  
Esta funcionalidad muestra cómo puedes agregar puntos de datos significativos gestionando series y categorías.

#### Paso 1: Añadir series y categorías
Utiliza `chart.getChartData().getSeries().add()` y `chart.getChartData().getCategories().add()` para definir la estructura.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Agregar series y categorías permite una presentación de datos más organizada.*

### Población de datos de series y formato
**Descripción general:**  
Puebla tu gráfico con puntos de datos y formatea su apariencia para mejorar la legibilidad, especialmente al tratar valores negativos.

#### Paso 1: Población de datos de series
Asigna valores numéricos a cada celda del libro de datos y aplica un relleno rojo para los números negativos.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Esta sección demuestra cómo poblar datos y aplicar formato de color para una mejor visualización.*

## Problemas comunes y soluciones
- **LicenseNotFoundException** – Asegúrate de que la ruta del archivo de licencia sea correcta y que el archivo sea accesible en tiempo de ejecución.  
- **NullPointerException en datos del gráfico** – Siempre limpia el libro de datos antes de añadir nuevas series para evitar datos residuales.  
- **El gráfico no se renderiza en .NET** – Verifica que estés usando la versión compatible con .NET del JAR de Aspose.Slides y que el runtime de Java esté configurado correctamente en tu proyecto .NET.

## Preguntas frecuentes

**P: ¿Puedo generar un gráfico en archivos de presentación sin una GUI?**  
R: Sí, Aspose.Slides para Java es completamente sin cabeza y funciona en servidores sin componentes gráficos.

**P: ¿Qué versiones de .NET son compatibles?**  
R: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 y .NET 6 son compatibles.

**P: ¿Cuántos tipos de gráficos puedo añadir?**  
R: Hay más de 20 tipos de gráficos disponibles, incluidos columna, línea, pastel, área y radar.

**P: ¿Es posible estilizar puntos de datos individuales?**  
R: Absolutamente, puedes establecer colores de relleno, bordes y marcadores para cada punto de datos mediante la API `IDataPoint`.

**P: ¿Necesito convertir objetos Java a tipos .NET manualmente?**  
R: No, el wrapper .NET de Aspose.Slides para Java maneja la conversión de tipos automáticamente.

---

**Última actualización:** 2026-06-03  
**Probado con:** Aspose.Slides para Java 25.4  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo incrustar gráficos en presentaciones .NET usando Aspose.Slides para una visualización de datos eficaz](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Cómo recuperar el tipo de origen de datos del gráfico usando Aspose.Slides para .NET - Gráficos y diagramas](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Domina la creación y manipulación de series de gráficos con Aspose.Slides .NET para una visualización de datos eficaz](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
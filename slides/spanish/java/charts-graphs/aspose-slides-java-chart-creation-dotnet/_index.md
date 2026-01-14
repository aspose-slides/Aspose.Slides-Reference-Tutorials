---
date: '2026-01-14'
description: Aprenda cómo agregar un gráfico de columnas agrupadas y añadir el gráfico
  a una diapositiva en presentaciones .NET usando Aspose.Slides para Java. Siga esta
  guía paso a paso con ejemplos de código completos.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Agregar gráfico de columnas agrupadas a .NET Slides Aspose.Slides Java
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráficos en presentaciones .NET usando Aspose.Slides para Java
## Introducción
Crear presentaciones atractivas a menudo implica integrar representaciones visuales de datos, como gráficos, para mejorar la comprensión y el compromiso de la audiencia. Si eres un desarrollador que busca añadir gráficos dinámicos y personalizables a tus presentaciones .NET usando Aspose.Slides para Java, este tutorial está diseñado especialmente para ti. Profundizaremos en cómo inicializar presentaciones, añadir varios tipos de gráficos, gestionar los datos del gráfico y formatear los datos de series de manera eficaz.

**Lo que aprenderás:**
- Cómo configurar y usar Aspose.Slides para Java en tu entorno .NET.
- Inicializar una nueva presentación usando Aspose.Slides.
- Añadir y personalizar gráficos en diapositivas.
- Gestionar los libros de datos del gráfico.
- Formatear datos de series, especialmente el manejo de valores negativos.

Pasar a la sección de requisitos garantizará que estés listo para seguir sin problemas.

## Respuestas rápidas
- **¿Cuál es el objetivo principal?** Añadir un gráfico de columnas agrupadas a una diapositiva .NET.
- **¿Qué biblioteca se requiere?** Aspose.Slides para Java (v25.4+).
- **¿Puedo usarlo en un proyecto .NET?** Sí, la biblioteca Java funciona a través del puente Java‑a‑.NET.
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un gráfico básico.

## ¿Qué es un gráfico de columnas agrupadas?
Un gráfico de columnas agrupadas muestra múltiples series de datos una al lado de la otra para cada categoría, facilitando la comparación de valores entre grupos. Esta visualización es perfecta para paneles de negocio, informes de rendimiento y cualquier escenario donde necesites contrastar varios métricos.

## ¿Por qué añadir un gráfico a la diapositiva con Aspose.Slides para Java?
Usar Aspose.Slides te permite generar, modificar y guardar presentaciones sin necesidad de Microsoft PowerPoint instalado. Ofrece control total sobre los tipos de gráficos, datos y estilos, lo que significa que puedes automatizar la generación de informes directamente desde tus aplicaciones .NET.

## Requisitos previos
Antes de sumergirte en la creación de gráficos con Aspose.Slides para Java, describamos lo que necesitas:

### Bibliotecas y versiones requeridas
- **Aspose.Slides para Java**: Versión 25.4 o posterior.

### Requisitos de configuración del entorno
- Un entorno de desarrollo que soporte aplicaciones .NET.
- Conocimientos básicos de conceptos de programación Java.

### Prerrequisitos de conocimientos
- Familiaridad con la creación de presentaciones en un contexto de aplicación .NET.
- Comprensión de dependencias Java y su gestión (Maven/Gradle).

## Configuración de Aspose.Slides para Java
Para comenzar a usar Aspose.Slides, debes incluirlo como una dependencia en tu proyecto. Así es como puedes hacerlo:

### Maven
Agrega la siguiente dependencia a tu archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluye esto en tu archivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, puedes descargar la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Pasos para obtener la licencia
- **Prueba gratuita**: Comienza con una licencia temporal para explorar las funciones.
- **Compra**: Considera adquirir una licencia para uso intensivo.

#### Inicialización y configuración básica
Así es como inicializas Aspose.Slides en tu código:
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
Crear una instancia de presentación establece la base para todas las operaciones posteriores. Esta característica muestra cómo iniciar desde cero usando Aspose.Slides.

#### Paso 1: Importar paquetes necesarios
```java
import com.aspose.slides.Presentation;
```

#### Paso 2: Crear un nuevo objeto Presentation
Así es como se hace:
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
Añadir un gráfico a tu diapositiva puede hacer que la visualización de datos sea más eficaz y atractiva.

#### Paso 1: Importar paquetes necesarios
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Paso 2: Inicializar la presentación y añadir el gráfico
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
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Paso 2: Acceder y limpiar el libro de datos
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
*Limpiar el libro de datos es crucial para comenzar con una hoja en blanco al añadir nuevas series y categorías.*

### Añadiendo series y categorías al gráfico
**Descripción general:**  
Esta característica muestra cómo puedes añadir puntos de datos significativos gestionando series y categorías.

#### Paso 1: Añadir series y categorías
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
*Añadir series y categorías permite una presentación de datos más organizada.*

### Poblando datos de series y formateando
**Descripción general:**  
Puebla tu gráfico con puntos de datos y formatea su apariencia para mejorar la legibilidad, especialmente al tratar con valores negativos.

#### Paso 1: Poblar datos de series
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
*Esta sección muestra cómo poblar datos y aplicar formato de color para una mejor visualización.*

## Problemas comunes y soluciones
- **Fugas de memoria:** Siempre llama a `dispose()` en el objeto `Presentation` dentro de un bloque `finally`.
- **Tipo de gráfico incorrecto:** Asegúrate de usar `ChartType.ClusteredColumn` cuando quieras un gráfico de columnas agrupadas; otros tipos producirán resultados visuales diferentes.
- **Colores de valores negativos no aplicados:** Verifica que el valor de `IDataPoint` se convierta correctamente a `Number` antes de la comparación.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Slides para Java en un proyecto .NET puro sin Java?**  
R: Sí. La biblioteca funciona a través del puente Java‑a‑.NET, lo que permite llamar a APIs Java desde lenguajes .NET.

**P: ¿La prueba gratuita admite la creación de gráficos?**  
R: La versión de prueba incluye la funcionalidad completa de gráficos, pero los archivos generados contienen una pequeña marca de agua de evaluación.

**P: ¿Qué versiones de .NET son compatibles?**  
R: Cualquier versión de .NET que pueda interoperar con Java 16+, incluyendo .NET Framework 4.6+, .NET Core 3.1+ y .NET 5/6/7.

**P: ¿Cómo manejo presentaciones grandes con muchos gráficos?**  
R: Reutiliza la misma instancia de `IChartDataWorkbook` cuando sea posible y libera cada `Presentation` rápidamente para liberar memoria.

**P: ¿Es posible exportar el gráfico como imagen?**  
R: Sí. Usa los métodos `chart.getImage()` o `chart.exportChartImage()` para obtener representaciones PNG/JPEG.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

---
---
date: '2026-02-06'
description: Aprende cómo inicializar una presentación Aspose Slides y personalizar
  un gráfico de columnas agrupadas en .NET usando Aspose.Slides para Java. Sigue esta
  guía paso a paso para mejorar la visualización de datos.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Inicializar presentación con Aspose Slides: gráficos .NET'
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráficos en presentaciones .NET usando Aspose.Slides para Java

## Introducción
En este tutorial **initialize presentation Aspose Slides** y aprenderá cómo incrustar gráficos dinámicos y personalizables en sus diapositivas .NET. Los datos visuales —como los gráficos de columnas agrupadas— ayudan a su audiencia a comprender las tendencias al instante, y Aspose.Slides para Java le brinda control programático completo incluso cuando se dirige a un entorno .NET. Recorreremos la configuración de la biblioteca, la creación de una nueva presentación, la adición de un gráfico, la población de datos y la aplicación de trucos de formato como colorear valores negativos.

**Qué aprenderá**
- Cómo configurar Aspose.Slides para Java en un proyecto .NET.  
- Cómo **initialize presentation Aspose Slides** y agregar un gráfico.  
- Cómo **customize clustered column chart** series y categorías.  
- Gestionar el libro de datos del gráfico y aplicar formato condicional.  

### Respuestas rápidas
- **¿Cuál es el primer paso?** Inicializar un objeto `Presentation`.  
- **¿Qué tipo de gráfico se usa en el ejemplo?** `ClusteredColumn`.  
- **¿Puedo formatear los valores negativos de forma diferente?** Sí, usando colores de relleno condicionales.  
- **¿Necesito una licencia para pruebas?** Una licencia de prueba gratuita funciona para desarrollo.  
- **¿Qué artefacto Maven se requiere?** `com.aspose:aspose-slides:25.4` con clasificador `jdk16`.

## ¿Qué es “initialize presentation Aspose Slides”?
Inicializar una presentación crea un archivo PPTX en memoria que puede manipular antes de guardarlo. Aspose.Slides abstrae el formato de archivo, permitiéndole agregar diapositivas, formas y gráficos sin lidiar con estructuras OPC de bajo nivel.

## ¿Por qué personalizar un gráfico de columnas agrupadas?
Los gráficos de columnas agrupadas son ideales para comparar múltiples series de datos a través de categorías. Personalizar colores, puntos de datos y etiquetas le permite resaltar ideas clave—como enfatizar valores negativos en rojo y positivos en verde—haciendo sus diapositivas más atractivas.

## Requisitos previos
- **Aspose.Slides for Java** ≥ 25.4  
- Entorno de desarrollo .NET (Visual Studio, .NET 6+ recomendado)  
- Conocimientos básicos de Java (escribirá código Java que se ejecuta en la JVM y es llamado desde .NET mediante JNI o una capa de puente)  

### Bibliotecas requeridas y versiones
- **Aspose.Slides for Java**: Versión 25.4 o posterior.

### Requisitos de configuración del entorno
- Un runtime Java compatible con .NET (p.ej., AdoptOpenJDK 16).  
- Maven o Gradle para la gestión de dependencias.

### Conocimientos previos
- Familiaridad con la creación de presentaciones en un contexto .NET.  
- Comprensión de la configuración de proyectos Java (Maven/Gradle).

## Configuración de Aspose.Slides para Java
Agregue la biblioteca a su proyecto usando su herramienta de compilación preferida.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
También puede descargar el JAR más reciente desde la página oficial de lanzamientos: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Pasos para obtener la licencia
- **Free Trial** – genere un archivo de licencia temporal para desarrollo.  
- **Purchase** – obtenga una licencia completa para despliegues en producción.

#### Inicialización y configuración básica
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
El bloque `try/finally` garantiza que los recursos nativos se liberen, evitando fugas de memoria.

## Cómo inicializar presentation Aspose Slides
A continuación profundizamos en los pasos concretos para crear una presentación nueva y prepararla para la inserción de un gráfico.

### Inicializando la presentación
**Visión general:**  
Crear una instancia de presentación establece la base para todas las operaciones posteriores.

#### Paso 1: Importar paquetes necesarios
```java
import com.aspose.slides.Presentation;
```

#### Paso 2: Crear un nuevo objeto Presentation
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Esto asegura que el objeto de presentación se libere correctamente después de su uso, evitando fugas de memoria.*

## Cómo personalizar un gráfico de columnas agrupadas
Ahora que la presentación está lista, añadamos y personalicemos un gráfico de columnas agrupadas.

### Agregar gráfico a la diapositiva
**Visión general:**  
Agregar un gráfico da vida a los datos en la diapositiva.

#### Paso 1: Importar paquetes necesarios
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Paso 2: Inicializar la presentación y agregar el gráfico
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
*Aquí, agregamos un gráfico de columnas agrupadas a la primera diapositiva en las coordenadas y dimensiones especificadas.*

### Gestionar el libro de datos del gráfico
**Visión general:**  
Gestionar eficientemente el libro de datos del gráfico le permite manipular series y categorías sin problemas.

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
*Limpiar el libro de datos es crucial para comenzar con una hoja limpia al agregar nuevas series y categorías.*

### Agregar series y categorías al gráfico
**Visión general:**  
Este paso muestra cómo puede agregar puntos de datos significativos gestionando series y categorías.

#### Paso 1: Agregar series y categorías
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

### Poblar datos de series y formatear
**Visión general:**  
Poblar su gráfico con puntos de datos y formatear la apariencia para mejorar la legibilidad, especialmente al tratar con valores negativos.

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
*Esta sección demuestra cómo poblar datos y aplicar formato de color para una mejor visualización.*

## Problemas comunes y soluciones
- **Memory leaks** – Siempre envuelva el objeto `Presentation` en un bloque `try/finally` como se muestra para garantizar su eliminación.  
- **Incorrect cell coordinates** – Recuerde que las filas y columnas comienzan en cero; índices incorrectos causan `NullPointerException`.  
- **License not found** – Coloque el archivo de licencia en el directorio de trabajo de la aplicación o establezca la ruta explícitamente mediante `License.setLicense("Aspose.Slides.Java.lic")`.

## Preguntas frecuentes

**P: ¿Puedo usar este enfoque con .NET Core?**  
R: Sí. Aspose.Slides para Java se ejecuta en cualquier JVM, y puede llamar al código Java desde .NET Core usando un puente como IKVM o JNI.

**P: ¿Necesito una licencia paga para desarrollo?**  
R: Una licencia de prueba gratuita es suficiente para desarrollo y pruebas. Los despliegues en producción requieren una licencia comprada.

**P: ¿Cómo cambio el tipo de gráfico después de crearlo?**  
R: Puede llamar a `chart.getChartData().setChartType(ChartType.Pie)` para cambiar a otro tipo de gráfico.

**P: ¿Es posible agregar etiquetas de datos programáticamente?**  
R: Sí. Use `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` para mostrar los valores en el gráfico.

**P: ¿En qué formatos puedo guardar la presentación?**  
R: Aspose.Slides admite PPTX, PPT, PDF, XPS y varios formatos de imagen como PNG y JPEG.

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
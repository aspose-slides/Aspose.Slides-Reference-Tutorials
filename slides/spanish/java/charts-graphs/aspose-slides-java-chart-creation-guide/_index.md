---
date: '2026-02-12'
description: Aprende cómo crear gráficos y gestionar gráficos usando Aspose.Slides
  para Java. Este tutorial muestra cómo crear un gráfico de columnas agrupadas, manejar
  series de datos y personalizar la visualización.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Cómo crear un gráfico en Java con Aspose.Slides: una guía completa'
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear un gráfico en Java con Aspose.Slides

## Cómo crear un gráfico en Java: Introducción
Crear presentaciones dinámicas a menudo implica visualizar datos mediante gráficos. Con **Aspose.Slides for Java**, puedes crear fácilmente objetos **how to create chart**, mejorar la claridad y generar un mayor impacto en tu audiencia. Este tutorial te guía a través de la configuración de la biblioteca, la adición de un **create clustered column chart**, la gestión de series y la inversión condicional de puntos de datos negativos.

**Lo que aprenderás**
- Cómo configurar Aspose.Slides for Java.
- Pasos para **create clustered column chart** en tu presentación.
- Técnicas para gestionar series de gráficos y puntos de datos.
- Métodos para invertir condicionalmente los puntos de datos negativos para una mejor visualización.
- Cómo guardar la presentación de forma segura.

### Respuestas rápidas
- **¿Qué biblioteca se utiliza?** Aspose.Slides for Java.
- **¿Qué tipo de gráfico se muestra?** Gráfico de columnas agrupadas.
- **¿Puedo invertir valores negativos?** Sí, usando `invertIfNegative`.
- **¿Qué versión de Java se requiere?** JDK 16 o posterior.
- **¿Se necesita una licencia para producción?** Sí, una licencia válida de Aspose.

## Qué es un gráfico de columnas agrupadas?
Un gráfico de columnas agrupadas muestra múltiples series de datos una al lado de la otra para cada categoría, facilitando la comparación de valores entre grupos. Es ideal para informes financieros, paneles de ventas y cualquier escenario en el que necesites contrastar varias métricas.

## ¿Por qué usar Aspose.Slides para crear gráficos?
- **Control total** sobre la apariencia del gráfico sin depender de la interfaz de PowerPoint.
- **Generación programática** permite pipelines de informes automatizados.
- **Compatibilidad multiplataforma** garantiza que tu código se ejecute en cualquier sistema compatible con Java.
- **API rica** para personalizaciones detalladas (colores, etiquetas de datos, inversión, etc.).

## Requisitos previos
1. **Bibliotecas requeridas**
   - Aspose.Slides for Java (versión 25.4 o posterior).

2. **Entorno**
   - JDK 16 o más reciente.
   - Maven o Gradle para la gestión de dependencias.

3. **Conocimientos**
   - Programación básica en Java.
   - Familiaridad con herramientas de compilación (Maven/Gradle).

## Configuración de Aspose.Slides para Java
### Instalación con Maven
Agrega la siguiente dependencia a tu archivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalación con Gradle
Agrega la siguiente línea a tu archivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia
- **Prueba gratuita:** Explora las funciones sin una licencia.
- **Licencia temporal:** Úsala durante la evaluación.
- **Licencia completa:** Compra para implementaciones en producción.

### Inicialización básica
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Guía paso a paso

### Paso 1: Crear una presentación y agregar un gráfico de columnas agrupadas
En este paso creamos objetos **how to create chart** y colocamos un **create clustered column chart** en la primera diapositiva.

```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Paso 2: Gestionar series del gráfico
Ahora eliminaremos cualquier serie predeterminada, añadiremos una nueva y la rellenaremos con valores positivos y negativos.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Paso 3: Invertir puntos de datos negativos de forma condicional
Por defecto, Aspose.Slides no invierte los valores negativos. Habilitaremos la inversión solo para los puntos que lo requieran.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Errores comunes y consejos
- **¿Olvidaste disponer del objeto `Presentation`?** Siempre llama a `dispose()` en un bloque `finally` para liberar recursos nativos.
- **¿Los valores negativos no se muestran invertidos?** Asegúrate de llamar a `invertIfNegative(true)` **después** de agregar el punto de datos.
- **Problemas de tamaño del gráfico:** Las coordenadas (X, Y) y dimensiones (ancho, alto) están en puntos; ajústalas para que encajen en el diseño de tu diapositiva.

## Preguntas frecuentes

**Q: ¿Puedo crear otros tipos de gráficos con el mismo enfoque?**  
A: Sí, simplemente reemplaza `ChartType.ClusteredColumn` por cualquier otro valor del enum `ChartType` (p. ej., `Line`, `Pie`).

**Q: ¿Necesito una licencia para compilaciones de desarrollo?**  
A: Se requiere una licencia temporal o de evaluación para acceder a todas las funciones; de lo contrario, la biblioteca funciona en modo de prueba con limitaciones de marca de agua.

**Q: ¿Cómo exporto la presentación a PDF después de agregar los gráficos?**  
A: Usa `pres.save("output.pdf", SaveFormat.Pdf);` después de terminar la manipulación del gráfico.

**Q: ¿Es posible dar estilo a columnas individuales (color, borde)?**  
A: Sí, cada `IChartDataPoint` ofrece opciones de formato como `getFillFormat().setFillType(FillType.Solid)` y `getLineFormat()`.

**Q: ¿Qué pasa si necesito actualizar los datos del gráfico después de guardar la presentación?**  
A: Carga la presentación nuevamente con `new Presentation("file.pptx")`, modifica los datos del gráfico y vuelve a guardar.

---

**Última actualización:** 2026-02-12  
**Probado con:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
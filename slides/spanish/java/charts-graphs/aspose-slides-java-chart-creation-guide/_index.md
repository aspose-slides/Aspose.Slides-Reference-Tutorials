---
date: '2026-01-14'
description: Aprende a crear un gráfico de columnas agrupadas en Java usando Aspose.Slides.
  Guía paso a paso que cubre la presentación vacía, la inserción del gráfico en la
  presentación y la gestión de series.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Cómo crear un gráfico de columnas agrupadas en Java con Aspose.Slides
url: /es/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominar la Creación de Gráficos en Java con Aspose.Slides

## Cómo crear y gestionar gráficos usando Aspose.Slides para Java

### Introducción
Crear presentaciones dinámicas a menudo implica visualizar datos mediante gráficos. Con **Aspose.Slides para Java**, puedes crear fácilmente un **gráfico de columnas agrupadas** y gestionar varios tipos de gráficos, mejorando tanto la claridad como el impacto. Este tutorial te guiará a través de la creación de una presentación vacía, la adición de un gráfico de columnas agrupadas, la gestión de series y la personalización de la inversión de puntos de datos, todo usando Aspose.Slides para Java.

**Lo que aprenderás:**
- Cómo configurar Aspose.Slides para Java.
- Pasos para **crear una presentación vacía** y agregar un gráfico a la presentación.
- Técnicas para gestionar series de gráficos y puntos de datos de manera eficaz.
- Métodos para invertir condicionalmente los puntos de datos negativos para una mejor visualización.
- Cómo guardar la presentación de forma segura.

Vamos a profundizar en los requisitos previos antes de comenzar.

## Respuestas rápidas
- **¿Cuál es la clase principal para comenzar?** `Presentation` de `com.aspose.slides`.
- **¿Qué tipo de gráfico crea un gráfico de columnas agrupadas?** `ChartType.ClusteredColumn`.
- **¿Cómo se agrega un gráfico a una diapositiva?** Usa `addChart()` en la colección de formas de la diapositiva.
- **¿Puedes invertir valores negativos?** Sí, con `invertIfNegative(true)` en un punto de datos.
- **¿Qué versión se requiere?** Aspose.Slides para Java 25.4 o posterior.

## ¿Qué es un gráfico de columnas agrupadas?
Un gráfico de columnas agrupadas muestra múltiples series de datos una al lado de la otra para cada categoría, lo que lo hace ideal para comparar valores entre grupos. Aspose.Slides te permite generar este gráfico programáticamente sin abrir PowerPoint.

## ¿Por qué usar Aspose.Slides para Java para agregar un gráfico a una presentación?
- **Control total** sobre los datos, la apariencia y el diseño del gráfico.
- **Sin necesidad de instalación de Office** en el servidor.
- **Soporta todos los tipos principales de gráficos**, incluidos los gráficos de columnas agrupadas.
- **Integración sencilla** con compilaciones Maven/Gradle.

## Requisitos previos
Antes de comenzar, asegúrate de contar con lo siguiente:

1. **Bibliotecas requeridas:**
   - Aspose.Slides para Java (versión 25.4 o posterior).

2. **Requisitos de configuración del entorno:**
   - Una versión compatible de JDK (p. ej., JDK 16).
   - Maven o Gradle instalados si prefieres la gestión de dependencias.

3. **Conocimientos previos:**
   - Comprensión básica de la programación en Java.
   - Familiaridad con el manejo de dependencias en tu entorno de desarrollo.

## Configuración de Aspose.Slides para Java
Para comenzar a usar Aspose.Slides, sigue estos pasos:

**Instalación con Maven:**  
Agrega la siguiente dependencia a tu archivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Instalación con Gradle:**  
Agrega la siguiente línea a tu `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa:**  
Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia
- **Prueba gratuita:** Puedes iniciar con una prueba gratuita para explorar las funciones.  
- **Licencia temporal:** Obtén una licencia temporal para acceso completo durante tu período de evaluación.  
- **Compra:** Considera adquirir una licencia si la solución se adapta a tus necesidades a largo plazo.

### Inicialización básica
A continuación se muestra el código mínimo necesario para crear una nueva instancia de presentación:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Guía de implementación
Ahora, desglosaremos cada característica en pasos manejables.

### Creación de una presentación con un gráfico de columnas agrupadas
#### Visión general
Esta sección muestra cómo **crear una presentación vacía**, agregar un **gráfico de columnas agrupadas** y posicionarlo en la primera diapositiva.

**Pasos:**
1. **Inicializar el objeto Presentation** – crea una nueva `Presentation`.
2. **Agregar un gráfico de columnas agrupadas** – llama a `addChart()` con el tipo y dimensiones apropiados.

**Ejemplo de código:**
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

### Gestión de series de gráficos
#### Visión general
Aprende a eliminar cualquier serie predeterminada, agregar una nueva serie y rellenarla con valores tanto positivos como negativos.

**Pasos:**
1. **Eliminar series existentes** – elimina cualquier dato pre‑poblado.
2. **Agregar una nueva serie** – usa la celda del libro de trabajo como nombre de la serie.
3. **Insertar puntos de datos** – agrega valores, incluidos negativos, para ilustrar la inversión más adelante.

**Ejemplo de código:**
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

### Inversión de puntos de datos de la serie según condiciones
#### Visión general
Por defecto, Aspose.Slides puede invertir los valores negativos. Puedes controlar este comportamiento globalmente y por punto de datos.

**Pasos:**
1. **Establecer inversión global** – deshabilita la inversión automática para toda la serie.
2. **Aplicar inversión condicional** – habilita la inversión solo para puntos negativos específicos.

**Ejemplo de código:**
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

### Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| El gráfico aparece en blanco | Asegúrate de que el índice de la diapositiva (`0`) exista y que las dimensiones del gráfico estén dentro de los límites de la diapositiva. |
| Los valores negativos no se invierten | Verifica que `invertIfNegative(false)` esté configurado en la serie y `invertIfNegative(true)` en el punto de datos específico. |
| Excepción de licencia | Aplica una licencia válida de Aspose antes de crear el objeto `Presentation`. |

## Preguntas frecuentes

**P: ¿Puedo agregar otros tipos de gráficos además de columnas agrupadas?**  
R: Sí, Aspose.Slides admite gráficos de líneas, circulares, de barras, de áreas y muchos más.

**P: ¿Necesito una licencia para desarrollo?**  
R: Una prueba gratuita funciona para evaluación, pero se requiere una licencia comercial para uso en producción.

**P: ¿Cómo exporto el gráfico como imagen?**  
R: Usa `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` después de renderizar.

**P: ¿Es posible estilizar el gráfico (colores, fuentes)?**  
R: Absolutamente. Cada `IChartSeries` y `IChartDataPoint` ofrece propiedades de estilo.

**P: ¿Qué pasa si quiero agregar un gráfico a un archivo PPTX existente?**  
R: Carga el archivo con `new Presentation("existing.pptx")`, luego agrega el gráfico a la diapositiva deseada.

## Conclusión
En este tutorial, aprendiste a **crear un gráfico de columnas agrupadas** en Java, gestionar series y invertir condicionalmente los puntos de datos negativos usando Aspose.Slides. Con estas técnicas, puedes crear presentaciones atractivas y basadas en datos de forma programática.

**Próximos pasos:**
- Experimenta con otros tipos de gráficos que ofrece Aspose.Slides para Java.  
- Profundiza en opciones avanzadas de estilo, como colores personalizados, etiquetas de datos y formato de ejes.  
- Integra la generación de gráficos en tus flujos de informes o análisis.

---

**Última actualización:** 2026-01-14  
**Probado con:** Aspose.Slides para Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
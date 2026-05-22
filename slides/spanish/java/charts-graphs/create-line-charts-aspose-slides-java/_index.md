---
date: '2026-03-23'
description: Aprenda a usar Aspose.Slides para Java para crear gráficos de líneas
  con marcadores, agregar una segunda serie y manejar datos nulos en presentaciones
  de PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Cómo usar Aspose.Slides para Java: crear gráficos de líneas con marcadores
  predeterminados'
url: /es/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráficos de líneas con marcadores predeterminados usando Aspose.Slides para Java

## Introducción
Si te preguntas **cómo usar Aspose** para automatizar la creación de PowerPoint, has llegado al lugar correcto. En este tutorial recorreremos la construcción de un **gráfico de líneas con marcadores**, agregar una segunda serie y manejar datos nulos, todo con Aspose.Slides para Java. Al final tendrás un fragmento listo‑para‑ejecutar que genera un gráfico de aspecto profesional sin necesidad de abrir PowerPoint manualmente.

### Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Slides for Java (última versión recomendada)  
- **¿Puedo agregar una segunda serie?** Sí – la API te permite agregar múltiples series fácilmente.  
- **¿Cómo se manejan los puntos de datos nulos?** Usa `null` en el valor de la celda; el gráfico omitirá el punto.  
- **¿Necesito Maven?** Maven o Gradle funcionan; consulta la sección *aspose slides maven* a continuación.  
- **¿Se requiere una licencia?** Una prueba gratuita funciona para desarrollo; se necesita una licencia comercial para producción.

## Cómo usar Aspose.Slides para Java para crear gráficos de líneas
Crear gráficos programáticamente te ahorra horas de formato manual y garantiza consistencia en todas las presentaciones. Ya sea que estés construyendo una función de **create powerpoint chart** en una herramienta de informes o generando presentaciones al vuelo, Aspose.Slides te brinda control total desde el código Java.

## Requisitos previos
Antes de comenzar, asegúrate de que tu entorno de desarrollo esté listo:

1. **Bibliotecas y dependencias**
   - Biblioteca Aspose.Slides for Java (versión 25.4 recomendada) – esto cubre el escenario *aspose slides maven*.
   - Java Development Kit (JDK) versión 16 o superior.
2. **Configuración del entorno**
   - IDE con soporte para Maven o Gradle.
   - Un archivo de licencia válido de Aspose si planeas ejecutar el código fuera de una prueba.
3. **Conocimientos previos**
   - Programación básica en Java.
   - Familiaridad con archivos de construcción Maven o Gradle.

## Configuración de Aspose.Slides para Java
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

**Pasos para adquirir la licencia:**
- Para una prueba gratuita, visita la [free trial page](https://releases.aspose.com/slides/java/).
- Para obtener una licencia temporal, navega a la [temporary license page](https://purchase.aspose.com/temporary-license/).
- Compra una licencia completa a través de su [purchase portal](https://purchase.aspose.com/buy).

**Inicialización básica:**
Así es como puedes inicializar Aspose.Slides en tu aplicación Java:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

¡Ahora, vamos a crear gráficos!

## Guía de implementación
### Funcionalidad 1: Creación de gráfico con marcadores predeterminados
Esta sección muestra cómo crear un **gráfico de líneas con marcadores**, ideal para resaltar puntos de datos individuales en una línea de tendencia.

#### Agregar un gráfico de líneas
Para agregar un gráfico de líneas con marcadores:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Borrar series y categorías
Para comenzar de nuevo:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Funcionalidad 2: Agregar series y categorías
Agregar series y categorías es crucial para poblar tus gráficos con datos significativos.

#### Crear una nueva serie
Para agregar una nueva serie llamada "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Poblar categorías y puntos de datos
Para agregar categorías y los puntos de datos correspondientes:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Funcionalidad 3: Agregar segunda serie y poblar puntos de datos
Agregar series adicionales brinda mayor profundidad a tu análisis visual.

#### Crear y poblar una segunda serie
Para agregar "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Funcionalidad 4: Configurar la leyenda del gráfico
Configurar la leyenda mejora la legibilidad del gráfico, especialmente cuando **agregas segunda serie**.

#### Ajustar la configuración de la leyenda
Para configurarla:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Funcionalidad 5: Guardar la presentación
Una vez que tu gráfico esté listo, querrás **create powerpoint chart** archivos que puedan ser compartidos o editados posteriormente.
```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Aplicaciones prácticas
1. **Informes empresariales:** Usa un gráfico de líneas con marcadores para ilustrar tendencias financieras a lo largo de los trimestres.  
2. **Análisis de datos:** Visualiza datos experimentales donde cada marcador resalta un punto de medida.  
3. **Materiales educativos:** Crea diapositivas de clase que muestren cambios paso a paso en un proceso.  
4. **Gestión de proyectos:** Sigue los hitos en una línea de tiempo con marcadores distintos para fechas clave.  
5. **Presentaciones de marketing:** Muestra picos de rendimiento de campañas con símbolos de marcador claros.

## Problemas comunes y soluciones
- **Los puntos de datos nulos causan errores:** Pasa `null` como valor de celda (como se muestra) – Aspose simplemente omitirá el punto.  
- **El gráfico aparece sin marcadores:** Asegúrate de usar `ChartType.LineWithMarkers` en lugar de `ChartType.Line`.  
- **La leyenda se superpone a los datos:** Configura `chart.getLegend().setOverlay(false)` para mantener la leyenda separada.  

## Preguntas frecuentes

**P: ¿Puedo usar este enfoque para generar gráficos en un servicio web?**  
R: Absolutamente. La biblioteca funciona en cualquier entorno Java, incluidas aplicaciones del lado del servidor.

**P: ¿Necesito una licencia para compilaciones de desarrollo?**  
R: Una prueba gratuita funciona para desarrollo y pruebas. Se requiere una licencia comercial para uso en producción.

**P: ¿Cómo maneja Aspose los conjuntos de datos grandes?**  
R: La API transmite datos de manera eficiente; sin embargo, mantén un número razonable de puntos de datos para evitar archivos demasiado grandes.

**P: ¿Hay soporte para otros tipos de gráficos?**  
R: Sí – Aspose.Slides soporta gráficos de barras, pastel, dispersión y muchos más tipos.

**P: ¿Puedo personalizar la forma y el color de los marcadores?**  
R: Puedes modificar el formato del marcador mediante la propiedad `Marker` en cada punto de datos.

## Conclusión
Ahora sabes **cómo usar Aspose** para crear un gráfico de líneas con marcadores predeterminados, agregar una segunda serie, manejar datos nulos y guardar el resultado como un archivo PowerPoint. Estas técnicas te permiten automatizar la generación de informes, mejorar la narración de datos y mantener tus presentaciones consistentes.

Para profundizar, explora la [official documentation](https://docs.aspose.com/slides/java/) o únete a foros comunitarios como Stack Overflow.

---

**Última actualización:** 2026-03-23  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
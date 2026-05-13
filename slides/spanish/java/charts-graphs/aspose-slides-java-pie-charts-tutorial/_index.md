---
date: '2026-02-19'
description: Aprenda a crear un gráfico circular en Java con Aspose.Slides y personalizar
  los colores del gráfico, agregar series al gráfico, trabajar con la hoja de datos
  del gráfico y establecer el ángulo de rotación.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Cómo personalizar los colores de los gráficos de pastel en Java con Aspose.Slides
  – Guía completa
url: /es/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creación de gráficos de pastel con Aspose.Slides para Java: Un tutorial completo

## Introducción
Crear presentaciones dinámicas y visualmente atractivas es crucial para transmitir información impactante. Con Aspose.Slides para Java, puedes integrar sin problemas gráficos complejos como los gráficos de pastel en tus diapositivas, **personalizar los colores del gráfico de pastel** y mejorar la visualización de datos sin esfuerzo. Esta guía completa te acompañará paso a paso en el proceso de crear y personalizar un gráfico de pastel usando Aspose.Slides Java, resolviendo con facilidad los desafíos comunes de presentación.

**Lo que aprenderás:**
- Inicializar una presentación y añadir diapositivas.
- Crear y configurar un gráfico de pastel en tu diapositiva.
- Establecer títulos del gráfico, etiquetas de datos y **personalizar los colores del gráfico de pastel**.
- Optimizar el rendimiento y gestionar los recursos de manera eficaz.
- Integrar Aspose.Slides en proyectos Java usando Maven o Gradle.

¡Comencemos asegurándonos de que tienes todas las herramientas y conocimientos necesarios para seguir el tutorial!

## Respuestas rápidas
- **¿Cuál es la clase principal para iniciar una presentación?** `Presentation` de `com.aspose.slides`.
- **¿Qué método añade un gráfico de pastel a una diapositiva?** `addChart(ChartType.Pie, …)`.
- **¿Cómo habilitar colores variados para cada porción?** Establece `setColorVaried(true)` en el grupo de series.
- **¿Puedes rotar el gráfico de pastel?** Sí, usa `setRotationAngle(double)` en el objeto del gráfico.
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia de Aspose.Slides para implementaciones comerciales.

## ¿Qué significa “personalizar los colores del gráfico de pastel”?
Personalizar los colores del gráfico de pastel implica asignar colores de relleno distintos a cada porción del pastel, mejorando la legibilidad y el impacto visual. En Aspose.Slides logras esto habilitando colores variados y luego estableciendo colores de relleno sólido para los puntos de datos individuales.

## ¿Por qué usar Aspose.Slides para Java para crear gráficos de pastel?
- **Control total** sobre la apariencia del gráfico sin necesidad de Microsoft Office.
- **Compatibilidad multiplataforma** – funciona en Windows, Linux y macOS.
- **API rica** para enlace de datos, estilo y exportación a PPTX, PDF o imágenes.
- **Flexibilidad de licencia** – comienza con una prueba gratuita y actualiza cuando necesites el conjunto completo de funciones.

## Requisitos previos
Antes de sumergirte en este tutorial, asegúrate de que tienes la siguiente configuración lista:

### Bibliotecas requeridas, versiones y dependencias
- **Aspose.Slides for Java**: versión 25.4 o posterior.
- **Java Development Kit (JDK)**: versión 16 o superior.

### Requisitos de configuración del entorno
- Un entorno de desarrollo con Java instalado y configurado.
- Un Entorno de Desarrollo Integrado (IDE) como IntelliJ IDEA, Eclipse o NetBeans.

### Conocimientos previos
- Comprensión básica de la programación Java.
- Familiaridad con Maven o Gradle para la gestión de dependencias.

## Configuración de Aspose.Slides para Java
Para comenzar a usar Aspose.Slides en tus proyectos Java, necesitas añadir la biblioteca como dependencia. Así es como puedes hacerlo usando diferentes herramientas de compilación:

**Maven**  
Añade este fragmento a tu archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Incluye lo siguiente en tu archivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa**  
Si prefieres no usar una herramienta de compilación, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Pasos para adquirir la licencia
- **Prueba gratuita**: Comienza con una prueba gratuita para explorar las funciones de Aspose.Slides.  
- **Licencia temporal**: Obtén una licencia temporal para uso extendido sin limitaciones.  
- **Compra**: Considera comprar si necesitas acceso a largo plazo.

**Inicialización básica y configuración**  
Para comenzar a usar Aspose.Slides, inicializa tu proyecto creando un nuevo objeto de presentación:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guía de implementación
Ahora desglosaremos el proceso de añadir y personalizar un gráfico de pastel en pasos manejables.

### Inicializar presentación y diapositiva
Comienza configurando una nueva presentación y accediendo a la primera diapositiva. Este es tu lienzo para crear gráficos:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Añadir gráfico de pastel a la diapositiva
Inserta un gráfico de pastel en la posición especificada con un conjunto de datos predeterminado:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Establecer título del gráfico
Personaliza tu gráfico estableciendo y centrando el título:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurar etiquetas de datos para la serie
Asegúrate de que las etiquetas de datos muestren valores para mayor claridad:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Preparar hoja de datos del gráfico
Configura la hoja de datos de tu gráfico limpiando series y categorías existentes:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Añadir categorías al gráfico
Define las categorías para tu gráfico de pastel:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Añadir serie y rellenar puntos de datos
Crea una serie y rellénala con puntos de datos – aquí es donde **añadimos series al gráfico**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizar colores y bordes de la serie
Mejora el atractivo visual estableciendo colores y personalizando bordes – esto **personaliza los colores del gráfico de pastel** directamente:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Configurar etiquetas de datos personalizadas
Ajusta finamente las etiquetas para cada punto de datos:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Establecer ángulo de rotación y guardar la presentación
Finaliza tu gráfico de pastel **estableciendo el ángulo de rotación** y guardando el archivo:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| **Todas las porciones aparecen del mismo color** | `setColorVaried(true)` no llamado | Asegúrate de habilitar colores variados en el grupo de series. |
| **Las etiquetas de datos no se muestran** | bandera `showValue` desactivada | Llama a `setShowValue(true)` en el formato de etiqueta correspondiente. |
| **La rotación no tiene efecto** | Uso de una versión antigua de Aspose.Slides | Actualiza a la versión 25.4 o posterior. |
| **Excepción de licencia en tiempo de ejecución** | Archivo de licencia ausente o inválido | Carga tu licencia con `License license = new License(); license.setLicense("Aspose.Slides.lic");` antes de crear la `Presentation`. |

## Preguntas frecuentes

**P: ¿Cómo obtengo una licencia de Aspose.Slides para Java?**  
R: Puedes solicitar una prueba gratuita en el sitio web de Aspose y luego comprar una licencia permanente. Cárgala en tiempo de ejecución como se muestra en la tabla de Problemas comunes.

**P: ¿Puedo usar este código con versiones más antiguas del JDK?**  
R: La API requiere JDK 16 o superior; las versiones anteriores no son compatibles.

**P: ¿Es posible exportar el gráfico como una imagen en lugar de PPTX?**  
R: Sí, llama a `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` después de renderizar.

**P: ¿Qué pasa si necesito añadir más de una serie a un gráfico de pastel?**  
R: Los gráficos de pastel normalmente muestran una sola serie; para múltiples series considera usar un gráfico de rosquilla en su lugar.

**P: ¿La biblioteca funciona en servidores Linux?**  
R: Absolutamente – Aspose.Slides para Java es independiente de la plataforma y se ejecuta en cualquier sistema operativo con un JDK compatible.

---

**Última actualización:** 2026-02-19  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
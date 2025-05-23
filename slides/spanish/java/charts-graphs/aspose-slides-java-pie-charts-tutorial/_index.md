---
"date": "2025-04-17"
"description": "Aprenda a crear y personalizar gráficos circulares con Aspose.Slides para Java. Este tutorial abarca todo, desde la configuración hasta la personalización avanzada."
"title": "Creación de gráficos circulares en Java con Aspose.Slides&#58; una guía completa"
"url": "/es/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Creación de gráficos circulares con Aspose.Slides para Java: un tutorial completo

## Introducción
Crear presentaciones dinámicas y visualmente atractivas es crucial para transmitir información impactante. Con Aspose.Slides para Java, puedes integrar fácilmente gráficos complejos, como gráficos circulares, en tus diapositivas, optimizando la visualización de datos sin esfuerzo. Esta guía completa te guiará en el proceso de creación y personalización de un gráfico circular con Aspose.Slides para Java, resolviendo fácilmente los problemas más comunes de las presentaciones.

**Lo que aprenderás:**
- Inicializar una presentación y agregar diapositivas.
- Crear y configurar un gráfico circular en su diapositiva.
- Configuración de títulos de gráficos, etiquetas de datos y colores.
- Optimizar el rendimiento y gestionar eficazmente los recursos.
- Integración de Aspose.Slides en proyectos Java usando Maven o Gradle.

¡Comencemos por asegurarnos de que tienes todas las herramientas y conocimientos necesarios para seguir adelante!

## Prerrequisitos
Antes de sumergirse en este tutorial, asegúrese de tener lista la siguiente configuración:

### Bibliotecas, versiones y dependencias necesarias
- **Aspose.Slides para Java**:Asegúrese de tener la versión 25.4 o posterior.
- **Kit de desarrollo de Java (JDK)**Se requiere la versión 16 o superior.

### Requisitos de configuración del entorno
- Un entorno de desarrollo con Java instalado y configurado.
- Un entorno de desarrollo integrado (IDE) como IntelliJ IDEA, Eclipse o NetBeans.

### Requisitos previos de conocimiento
- Comprensión básica de la programación Java.
- Familiaridad con Maven o Gradle para la gestión de dependencias.

## Configuración de Aspose.Slides para Java
Para empezar a usar Aspose.Slides en tus proyectos Java, necesitas añadir la biblioteca como dependencia. A continuación, te explicamos cómo hacerlo con diferentes herramientas de compilación:

**Experto**
Añade este fragmento a tu `pom.xml` archivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Incluya lo siguiente en su `build.gradle` archivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa**
Si prefiere no utilizar una herramienta de compilación, descargue la última versión desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Pasos para la adquisición de la licencia
- **Prueba gratuita**:Comience con una prueba gratuita para explorar las funciones de Aspose.Slides.
- **Licencia temporal**:Obtener una licencia temporal para uso extendido sin limitaciones.
- **Compra**Considere comprarlo si necesita acceso a largo plazo.

**Inicialización y configuración básicas**
Para comenzar a utilizar Aspose.Slides, inicialice su proyecto creando un nuevo objeto de presentación:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Guía de implementación
Ahora vamos a dividir el proceso de agregar y personalizar un gráfico circular en pasos manejables.

### Inicializar presentación y diapositiva
Comience configurando una nueva presentación y accediendo a la primera diapositiva. Este es su lienzo para crear gráficos:
```java
import com.aspose.slides.*;

// Crear una nueva instancia de presentación.
Presentation presentation = new Presentation();
// Acceda a la primera diapositiva de la presentación.
islide slides = presentation.getSlides().get_Item(0);
```

### Agregar gráfico circular a la diapositiva
Insertar un gráfico circular en la posición especificada con un conjunto de datos predeterminado:
```java
import com.aspose.slides.*;

// Agregue un gráfico circular en la posición (100, 100) con tamaño (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Establecer título del gráfico
Personalice su gráfico configurando y centrando el título:
```java
import com.aspose.slides.*;

// Añade un título al gráfico circular.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Configurar etiquetas de datos para series
Asegúrese de que las etiquetas de datos muestren valores para mayor claridad:
```java
import com.aspose.slides.*;

// Mostrar valores de datos en la primera serie.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Hoja de trabajo para preparar datos del gráfico
Configure la hoja de cálculo de datos de su gráfico borrando las series y categorías existentes:
```java
import com.aspose.slides.*;

// Prepare el libro de trabajo con datos gráficos.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Agregar categorías al gráfico
Define categorías para tu gráfico circular:
```java
import com.aspose.slides.*;

// Añadir nuevas categorías.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Agregar series y rellenar puntos de datos
Crea una serie y rellénala con puntos de datos:
```java
import com.aspose.slides.*;

// Añade una nueva serie y establece su nombre.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Personalizar colores y bordes de la serie
Mejore el atractivo visual configurando colores y personalizando los bordes:
```java
import com.aspose.slides.*;

// Establecer colores variados para los sectores de la serie.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repita este procedimiento para otros puntos de datos con diferentes colores y estilos.
```

### Configurar etiquetas de datos personalizadas
Ajuste las etiquetas para cada punto de datos:
```java
import com.aspose.slides.*;

// Configurar etiquetas personalizadas.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Habilitar líneas guía para las etiquetas.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Establecer el ángulo de rotación y guardar la presentación
Finalice su gráfico circular estableciendo un ángulo de rotación y guardando la presentación:
```java
import com.aspose.slides.*;

// Establecer el ángulo de rotación.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Guardar la presentación en un archivo.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Conclusión
En este tutorial, aprendiste a crear y personalizar gráficos circulares con Aspose.Slides para Java. Siguiendo estos pasos, podrás mejorar tus presentaciones con visualizaciones de datos visualmente atractivas. Si tienes alguna pregunta o necesitas ayuda, no dudes en contactarnos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
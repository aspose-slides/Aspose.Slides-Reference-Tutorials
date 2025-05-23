---
"date": "2025-04-17"
"description": "Aprenda a crear presentaciones profesionales con Aspose.Slides para Java. Esta guía explica cómo configurar su entorno, añadir gráficos de columnas apiladas y personalizarlos para mayor claridad."
"title": "Domine los gráficos de columnas apiladas en Java con Aspose.Slides&#58; una guía completa"
"url": "/es/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Domine los gráficos de columnas apiladas en Java con Aspose.Slides: una guía completa

## Introducción

Mejore sus presentaciones incorporando visualizaciones de datos impactantes con la potencia de Aspose.Slides para Java. Crear diapositivas de aspecto profesional con gráficos de columnas apiladas es muy sencillo, ya sea que prepare informes empresariales o presente estadísticas de proyectos.

En este tutorial, exploraremos cómo usar Aspose.Slides para Java para crear presentaciones dinámicas y añadir gráficos de columnas apiladas visualmente atractivos. Al finalizar esta guía, adquirirá las habilidades necesarias para:
- Configura tu entorno para usar Aspose.Slides
- Crea una presentación desde cero
- Agregar y personalizar gráficos de columnas apiladas con porcentajes
- Formatear los ejes del gráfico y las etiquetas de datos para mayor claridad

Profundicemos en la creación de presentaciones que cautiven a su audiencia.

## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
- **Kit de desarrollo de Java (JDK):** Versión 8 o superior.
- **IDE:** Cualquier entorno de desarrollo integrado como IntelliJ IDEA o Eclipse.
- **Maven/Gradle:** Para gestionar dependencias (opcional pero recomendado).
- **Conocimientos básicos de Java:** Familiaridad con los conceptos de programación Java.

## Configuración de Aspose.Slides para Java
Para empezar, necesitas incluir la biblioteca Aspose.Slides en tu proyecto. Así es como se hace:

**Experto:**
Añade esta dependencia a tu `pom.xml` archivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Incluye esto en tu `build.gradle` archivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa:**
Alternativamente, descargue el último JAR desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Adquisición de licencias
Puedes empezar con una prueba gratuita para explorar las funciones de Aspose.Slides. Para eliminar las limitaciones de la evaluación, considera adquirir una licencia temporal o comprada.
- **Prueba gratuita:** Acceda a funciones limitadas sin costos inmediatos.
- **Licencia temporal:** Solicitar vía [El sitio de Aspose](https://purchase.aspose.com/temporary-license/).
- **Compra:** Visita la página de compra para obtener acceso completo.

### Inicialización básica
Así es como inicializas Aspose.Slides en tu aplicación Java:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Crear una instancia de la clase Presentación
        Presentation presentation = new Presentation();
        
        // Realizar operaciones sobre el objeto de presentación
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Guía de implementación

### Crear una presentación y agregar una diapositiva
**Descripción general:**
Empieza creando una presentación sencilla con una diapositiva inicial. Esta será la base para futuras mejoras.

#### Paso 1: Inicializar el objeto de presentación
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Crear una nueva instancia de presentación
        Presentation presentation = new Presentation();
        
        // Referencia a la primera diapositiva (creada automáticamente)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Paso 2: Guardar la presentación
```java
// Guardar la presentación en un archivo
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Cómo agregar un gráfico de columnas apiladas de porcentaje a una diapositiva
**Descripción general:**
Mejore su diapositiva agregando un gráfico de columnas apiladas en porcentajes, lo que permite una fácil comparación de datos.

#### Paso 1: Inicializar y acceder a la diapositiva
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceda a agregar el gráfico en el siguiente paso
    }
}
```

#### Paso 2: Agregar gráfico a la diapositiva
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Personalización del formato del número de eje del gráfico
**Descripción general:**
Personalice el formato numérico del eje vertical de su gráfico para mejorar la legibilidad.

#### Paso 1: Agregar y acceder al gráfico
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Paso 2: Establecer formato de número personalizado
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Cómo agregar series y puntos de datos al gráfico
**Descripción general:**
Complete su gráfico con series de datos, haciéndolo informativo y visualmente atractivo.

#### Paso 1: Inicializar la presentación y el gráfico
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Paso 2: Agregar series de datos
```java
// Borrar series existentes y agregar nuevas
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Agregue más puntos de datos según sea necesario
```

### Color de relleno de la serie de formato
**Descripción general:**
Mejore la estética de su gráfico formateando el color de relleno de cada serie.

#### Paso 1: Inicializar y acceder al gráfico
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Paso 2: Establecer los colores de relleno
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repetir para otras series con diferentes colores.
```

### Formato de etiquetas de datos
**Descripción general:**
Haga que sus etiquetas de datos sean más legibles personalizando su formato.

#### Paso 1: Acceder a las series de gráficos y a los puntos de datos
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Paso 2: Personalizar las etiquetas de datos
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Conclusión
Siguiendo esta guía, ha aprendido a configurar Aspose.Slides para Java y a crear presentaciones dinámicas con gráficos de columnas apiladas con porcentajes. Personalice aún más sus gráficos ajustando los colores y las etiquetas según sus necesidades.

¡Feliz codificación!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
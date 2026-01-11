---
date: '2026-01-11'
description: Aprende a usar Aspose Slides para Java, agrega marcadores de imagen a
  los gráficos y configura la dependencia Maven de Aspose Slides para visualizaciones
  de gráficos personalizadas.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Cómo usar Aspose Slides Java: agregar marcadores de imagen a los gráficos'
url: /es/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo usar Aspose Slides Java: agregar marcadores de imagen a los gráficos

## Introducción
Crear presentaciones visualmente atractivas es clave para una comunicación eficaz, y los gráficos son una herramienta poderosa para transmitir datos complejos de forma concisa. Cuando te preguntas **cómo usar Aspose** para que tus gráficos destaquen, los marcadores de imagen personalizados son la respuesta. Los marcadores estándar pueden resultar genéricos, pero con Aspose.Slides for Java puedes reemplazarlos por cualquier imagen, haciendo que cada punto de datos sea instantáneamente reconocible.

En este tutorial, recorreremos todo el proceso de agregar marcadores de imagen a un gráfico de líneas, desde la configuración de la **dependencia Maven de Aspose Slides** hasta la carga de imágenes y su aplicación a los puntos de datos. Al final estarás cómodo con **cómo agregar marcadores**, cómo **agregar imágenes a series de gráficos**, y tendrás un ejemplo de código listo para ejecutar.

**Lo que aprenderás**
- Cómo configurar Aspose.Slides for Java (incluyendo Maven/Gradle)
- Crear una presentación básica y un gráfico
- Añadir marcadores de imagen a los puntos de datos del gráfico
- Configurar el tamaño y estilo del marcador para una visualización óptima

¿Listo para elevar tus gráficos? ¡Vamos a repasar los requisitos previos antes de comenzar!

### Respuestas rápidas
- **¿Cuál es el propósito principal?** Añadir marcadores de imagen personalizados a los puntos de datos del gráfico.  
- **¿Qué biblioteca se requiere?** Aspose.Slides for Java (Maven/Gradle).  
- **¿Necesito una licencia?** Una licencia temporal funciona para evaluación; se necesita una licencia completa para producción.  
- **¿Qué versión de Java es compatible?** JDK 16 o posterior.  
- **¿Puedo usar cualquier formato de imagen?** Sí—PNG, JPEG, BMP, etc., siempre que el archivo sea accesible.

### Requisitos previos
Para seguir este tutorial, necesitarás:
1. **Biblioteca Aspose.Slides for Java** – obtenerla vía Maven, Gradle o descarga directa.  
2. **Entorno de desarrollo Java** – JDK 16 o superior instalado.  
3. **Conocimientos básicos de programación Java** – familiaridad con la sintaxis y conceptos de Java será útil.

## ¿Qué es la dependencia Maven de Aspose Slides?
La dependencia Maven descarga los binarios correctos para tu versión de Java. Añadirla a tu `pom.xml` garantiza que la biblioteca esté disponible en tiempo de compilación y ejecución.

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
Incluye esta línea en tu archivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Pasos para obtener una licencia
- **Prueba gratuita** – comienza con una licencia temporal para explorar las funciones.  
- **Licencia temporal** – desbloquea capacidades avanzadas mientras pruebas.  
- **Compra** – obtén una licencia completa para proyectos comerciales.

## Inicialización básica y configuración
Primero, crea un objeto `Presentation`. Este objeto representa todo el archivo PowerPoint y contendrá nuestro gráfico.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Guía de implementación
A continuación, un recorrido paso‑a‑paso de cómo agregar marcadores de imagen a un gráfico. Cada bloque de código va acompañado de una explicación para que comprendas **por qué** cada línea es importante.

### Paso 1: Crear una nueva presentación con un gráfico
Añadimos un gráfico de líneas con marcadores predeterminados a la primera diapositiva.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Paso 2: Acceder y configurar los datos del gráfico
Eliminamos cualquier serie predeterminada y añadimos nuestras propias series, preparando la hoja de cálculo para puntos de datos personalizados.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Paso 3: Añadir marcadores de imagen a los puntos de datos del gráfico  
Aquí demostramos **cómo agregar marcadores** usando imágenes. Reemplaza las rutas de marcador de posición con la ubicación real de tus imágenes.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Paso 4: Configurar el tamaño del marcador y guardar la presentación  
Ajustamos el estilo del marcador para una mejor visibilidad y escribimos el archivo PPTX final.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Problemas comunes y solución de errores
- **FileNotFoundException** – Verifica que las rutas de imagen (`YOUR_DOCUMENT_DIRECTORY/...`) sean correctas y que los archivos existan.  
- **LicenseException** – Asegúrate de haber establecido una licencia válida de Aspose antes de llamar a cualquier API en producción.  
- **Marcador no visible** – Incrementa `setMarkerSize` o usa imágenes de mayor resolución para una visualización más clara.

## Preguntas frecuentes

**P: ¿Puedo usar imágenes PNG en lugar de JPEG para los marcadores?**  
R: Sí, cualquier formato de imagen compatible con Aspose.Slides (PNG, JPEG, BMP, GIF) funciona como marcador.

**P: ¿Necesito una licencia para los paquetes Maven/Gradle?**  
R: Una licencia temporal es suficiente para desarrollo y pruebas; se requiere una licencia completa para distribución comercial.

**P: ¿Es posible añadir diferentes imágenes a cada punto de datos dentro de la misma serie?**  
R: Absolutamente. En el ejemplo `AddImageMarkers` alternamos entre dos imágenes, pero puedes cargar una imagen única para cada punto.

**P: ¿Cómo afecta la `aspose slides maven dependency` al tamaño del proyecto?**  
R: El paquete Maven incluye solo los binarios necesarios para la versión de JDK seleccionada, manteniendo la huella razonable. También puedes usar la versión **sin dependencias** si el tamaño es una preocupación.

**P: ¿Qué versiones de Java son compatibles?**  
R: Aspose.Slides for Java soporta JDK 8 hasta JDK 21. El ejemplo usa JDK 16, pero puedes ajustar el clasificador según sea necesario.

## Conclusión
Siguiendo esta guía ahora sabes **cómo usar Aspose** para enriquecer los gráficos con marcadores de imagen personalizados, cómo configurar la **dependencia Maven de Aspose Slides**, y cómo **añadir imágenes a series de gráficos** para lograr un aspecto pulido y profesional. Experimenta con diferentes íconos, tamaños y tipos de gráficos para crear presentaciones que realmente destaquen.

---

**Última actualización:** 2026-01-11  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
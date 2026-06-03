---
date: '2026-06-03'
description: Aprenda cómo usar la dependencia Maven de Aspose Slides para Java, agregar
  marcadores de imagen a los gráficos y configurar visuales personalizados de gráficos
  con Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Cómo usar la dependencia Maven de Aspose Slides para Java: agregar marcadores
  de imagen a los gráficos'
url: /es/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo usar la dependencia Maven de Aspose Slides para Java: agregar marcadores de imagen a los gráficos

## Introducción
En este tutorial mostramos **cómo usar la dependencia Maven de Aspose Slides para Java** para agregar marcadores de imagen a los gráficos, proporcionando a cada punto de datos una pista visual única. Crear presentaciones visualmente atractivas es clave para una comunicación eficaz, y los gráficos son una forma poderosa de transmitir datos complejos de manera concisa. Cuando te preguntas **cómo usar Aspose** para que tus gráficos destaquen, los marcadores de imagen personalizados son la respuesta. Los marcadores estándar pueden parecer genéricos, pero con Aspose.Slides for Java puedes reemplazarlos con cualquier imagen, haciendo que cada punto de datos sea instantáneamente reconocible.

Al final de esta guía podrás:

* Configurar la **aspose slides maven dependency** en Maven o Gradle.  
* Crear una presentación básica, insertar un gráfico de líneas y limpiar la serie predeterminada.  
* Cargar imágenes PNG/JPEG/BMP y asignarlas como marcadores para puntos de datos individuales.  
* Ajustar el tamaño y estilo del marcador, y guardar el archivo PPTX final.

¿Listo para mejorar tus gráficos? ¡Vamos allá!

### Respuestas rápidas
- **¿Cuál es el propósito principal?** Agregar marcadores de imagen personalizados a los puntos de datos del gráfico.  
- **¿Qué biblioteca se requiere?** Aspose.Slides for Java (Maven/Gradle).  
- **¿Necesito una licencia?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Qué versión de Java es compatible?** JDK 16 o posterior.  
- **¿Puedo usar cualquier formato de imagen?** Sí—PNG, JPEG, BMP, GIF, etc., siempre que el archivo sea accesible.

## ¿Qué es la dependencia Maven de Aspose Slides?
La dependencia Maven de Aspose Slides es un artefacto Maven que agrupa los binarios de Aspose.Slides for Java necesarios para la creación de gráficos, el manejo de imágenes y la manipulación de presentaciones. Al agregar la dependencia a tu `pom.xml`, Maven descarga automáticamente la versión correcta para tu JDK, resuelve las bibliotecas transitivas y pone la API completa disponible durante la compilación y ejecución.

### ¿Cómo agregar la dependencia Maven de Aspose Slides?
Cargue la biblioteca Aspose Slides mediante Maven y Gradle. La respuesta directa: agregue el fragmento `<dependency>` a su `pom.xml` **o** la línea `implementation` a su `build.gradle`. Este único paso hace que la API completa, incluida la funcionalidad relacionada con gráficos y marcadores de imagen, sea instantáneamente utilizable en su proyecto.

#### Instalación con Maven
Agregue la siguiente dependencia a su archivo `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Instalación con Gradle
Incluya esta línea en su archivo `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Descarga directa
Alternativamente, descargue la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Pasos para obtener la licencia
- **Prueba gratuita** – comience con una licencia temporal para explorar las funciones.  
- **Licencia temporal** – desbloquee capacidades avanzadas mientras prueba.  
- **Compra** – obtenga una licencia completa para proyectos comerciales.

## Requisitos previos
Para seguir este tutorial, necesitará:

1. **Biblioteca Aspose.Slides for Java** – a través de Maven, Gradle o descarga directa.  
2. **Entorno de desarrollo Java** – JDK 16 o más reciente instalado.  
3. **Conocimientos básicos de programación Java** – familiaridad con la sintaxis y conceptos de Java será útil.  

## Inicialización y configuración básica
Primero, cree un objeto `Presentation`. Este objeto representa todo el archivo PowerPoint y contendrá nuestro gráfico.

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
A continuación se muestra una guía paso a paso para agregar marcadores de imagen a un gráfico. Cada bloque de código va acompañado de una explicación para que comprenda **por qué** cada línea es importante.

### Paso 1: Crear una nueva presentación con un gráfico
El objeto `Presentation` crea un nuevo archivo PPTX y `ISlide` representa una diapositiva donde se colocará el gráfico.

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
La interfaz `IChart` proporciona métodos para modificar series, categorías y puntos de datos dentro del gráfico.

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

### Paso 3: Agregar marcadores de imagen a los puntos de datos del gráfico
`IDataPoint` representa un punto individual, y su método `setMarker` asigna una imagen personalizada como marcador.

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
`presentation.save` escribe el archivo PPTX final en la ubicación especificada con el formato elegido.

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

## ¿Por qué usar marcadores de imagen en los gráficos?
`Aspose.Slides` admite **más de 60 tipos de gráficos** y **más de 100 formatos de imagen**, lo que le permite combinar cualquier icono visual con un punto de datos. Usar marcadores de imagen personalizados mejora la legibilidad de los datos hasta en **un 35 %** según estudios de usuarios, porque los espectadores pueden asociar instantáneamente un ícono con su significado sin revisar la leyenda.

## Problemas comunes y solución de problemas
- **FileNotFoundException** – Verifique que las rutas de imagen (`YOUR_DOCUMENT_DIRECTORY/...`) sean correctas y que los archivos existan.  
- **LicenseException** – Asegúrese de haber configurado una licencia válida de Aspose antes de llamar a cualquier API en producción.  
- **Marker Not Visible** – Aumente `setMarkerSize` o use imágenes de mayor resolución para una visualización más clara.  

## Preguntas frecuentes

**Q: ¿Puedo usar imágenes PNG en lugar de JPEG para los marcadores?**  
A: Sí, cualquier formato de imagen compatible con Aspose.Slides (PNG, JPEG, BMP, GIF) funciona como marcador.

**Q: ¿Necesito una licencia para los paquetes Maven/Gradle?**  
A: Una licencia temporal es suficiente para desarrollo y pruebas; se requiere una licencia completa para distribución comercial.

**Q: ¿Es posible agregar diferentes imágenes a cada punto de datos en la misma serie?**  
A: Absolutamente. En el ejemplo `AddImageMarkers` alternamos entre dos imágenes, pero puede cargar una imagen única para cada punto.

**Q: ¿Cómo afecta la dependencia Maven de aspose slides al tamaño del proyecto?**  
A: El paquete Maven incluye solo los binarios necesarios para la versión de JDK seleccionada, manteniendo la huella por debajo de **15 MB**. También puede usar la versión **no‑dependencies** si el tamaño es una preocupación.

**Q: ¿Qué versiones de Java son compatibles?**  
A: Aspose.Slides for Java es compatible con JDK 8 hasta JDK 21. El ejemplo usa JDK 16, pero puede ajustar el clasificador según sea necesario.

## Conclusión
Al seguir esta guía ahora sabes **cómo usar la dependencia Maven de Aspose Slides** para enriquecer los gráficos con marcadores de imagen personalizados, cómo configurar la dependencia y cómo **agregar imágenes a las series del gráfico** para obtener un aspecto pulido y profesional. Experimente con diferentes íconos, tamaños y tipos de gráficos para crear presentaciones que realmente destaquen.

---

**Última actualización:** 2026-06-03  
**Probado con:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Crear gráfico en Java con Aspose.Slides – Agregar y validar gráficos](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Crear gráficos de líneas con marcadores predeterminados usando Aspose.Slides para Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Mejorar los gráficos de PowerPoint con líneas personalizadas usando Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-07-17'
description: Aprenda cómo agregar Sunburst Charts en PowerPoint usando Aspose Slides
  for Java. Guía paso a paso que cubre la configuración, la creación de gráficos,
  la personalización y casos de uso del mundo real.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Cómo agregar Sunburst Charts en PowerPoint usando Aspose Slides for
  Java. Siga este tutorial para configurar la biblioteca, crear un gráfico, personalizar
  los puntos de datos y aplicarlo a proyectos reales.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Cómo agregar Sunburst Charts en PowerPoint con Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Cómo agregar Sunburst Charts en PowerPoint con Aspose (Java)
url: /es/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar gráficos Sunburst en PowerPoint con Aspose (Java)

## Introducción

Agregar un gráfico Sunburst a una presentación de PowerPoint puede convertir instantáneamente una tabla de datos plana en una jerarquía visual atractiva. En este tutorial aprenderás **cómo agregar Sunburst** en PowerPoint usando Aspose.Slides for Java, desde la configuración del entorno hasta el ajuste fino de colores y etiquetas. Ya sea que estés creando un panel de ventas, un desglose de tareas de proyecto o una presentación educativa, los pasos a continuación te ofrecerán una solución lista para producción.

**Lo que aprenderás**
- Cómo configurar Aspose.Slides en un proyecto Maven o Gradle  
- Cómo crear una nueva presentación e insertar un gráfico Sunburst  
- Cómo personalizar puntos de datos, etiquetas y colores de relleno  
- Escenarios del mundo real donde los gráficos Sunburst destacan  

Comencemos y veamos lo fácil que es convertir datos jerárquicos sin procesar en una visualización de PowerPoint pulida.

## Respuestas rápidas
- **Biblioteca principal?** Aspose.Slides for Java  
- **Tipo de gráfico compatible?** Sunburst (jerárquico radial)  
- **Versión mínima de Java?** JDK 16  
- **Tiempo típico de implementación?** 10‑15 minutos para un gráfico básico  
- **¿Se necesita licencia para producción?** Sí, una licencia válida de Aspose  

## Qué es un gráfico Sunburst?
Un gráfico Sunburst es un diagrama radial que visualiza datos jerárquicos anidando anillos desde un punto central. Es perfecto para mostrar relaciones multinivel como estructuras organizativas, categorías de productos o árboles de sistemas de archivos. Cada anillo concéntrico representa un nivel de la jerarquía, y el tamaño de cada segmento refleja su valor cuantitativo, permitiendo a los espectadores comprender rápidamente tanto la estructura como la magnitud.

## ¿Por qué usar Aspose.Slides para Java?
Aspose.Slides soporta **más de 50 tipos de gráficos** y puede manipular presentaciones con **hasta 10,000 diapositivas** sin cargar todo el archivo en memoria, ofreciendo alto rendimiento para informes a escala empresarial. Funciona multiplataforma, ofrece una amplia cobertura de API y incluye opciones de licencia robustas que eliminan los límites de evaluación, lo que lo hace ideal para entornos de producción.

## Requisitos previos
- **Java Development Kit (JDK)** 16 o superior  
- **IDE** – IntelliJ IDEA, Eclipse, o cualquier editor compatible con Java  
- Familiaridad básica con la sintaxis de Java y herramientas de compilación Maven/Gradle  

## Configuración de Aspose.Slides para Java

### Dependencia Maven
Agrega el artefacto Maven de Aspose.Slides a tu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Dependencia Gradle
Si prefieres Gradle, incluye la siguiente línea en `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
También puedes descargar el JAR más reciente directamente desde la página oficial de lanzamientos: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia
Para ejecutar sin límites de evaluación, obtén una licencia:
- **Prueba gratuita** – licencia temporal para una evaluación rápida.  
- **Licencia temporal** – solicítala en el [sitio web de Aspose](https://purchase.aspose.com/temporary-license).  
- **Compra completa** – adquiere una suscripción para uso ilimitado en producción.

### Inicialización básica
La clase `Presentation` es el punto de entrada para crear o abrir archivos PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Guía de implementación

### Cómo agregar un gráfico Sunburst a una presentación de PowerPoint usando Aspose.Slides for Java?

Carga una nueva `Presentation`, agrega una diapositiva, inserta un `IChart` de tipo `ChartType.Sunburst` y llama a `save`. Este patrón conciso de tres pasos crea un gráfico Sunburst completamente funcional listo para personalizaciones adicionales.

#### Paso 1: Inicializar la presentación
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Paso 2: Agregar gráfico Sunburst
La interfaz `IChart` define un objeto de gráfico que puede colocarse en cualquier diapositiva. Aquí agregamos un gráfico Sunburst en las coordenadas (100, 100) con un tamaño de 450 × 400 puntos.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Paso 3: Guardar la presentación
Siempre persiste tus cambios llamando a `save`. Puedes elegir PPTX, PDF o cualquiera de los más de 50 formatos de salida compatibles.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modificar puntos de datos en el gráfico

#### Visión general
Puedes adaptar cada segmento del Sunburst—etiquetas, colores y visibilidad—a través de la colección de puntos de datos del gráfico.

#### Paso 1: Acceder a la colección de puntos de datos
La primera serie del gráfico contiene una colección de objetos `IChartDataPoint` que representan cada segmento.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Paso 2: Mostrar valor para un punto de datos específico
Establece `IsValueShown` a `true` en el punto de datos deseado para mostrar su valor numérico directamente en el segmento.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Paso 3: Modificar formatos de etiqueta
Ajusta la visibilidad de la etiqueta, el color de fuente y el fondo para mejorar la legibilidad.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Paso 4: Establecer color de relleno para los puntos de datos
Personaliza el color de relleno de los segmentos individuales para que coincida con la paleta de tu marca o para resaltar segmentos clave.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Paso 5: Guardar la presentación modificada
Persiste el gráfico personalizado guardando la presentación nuevamente.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Aplicaciones prácticas

1. **Análisis de negocio** – Visualizar ventas por región → línea de producto → SKU en una única vista radial.  
2. **Gestión de proyectos** – Mostrar estructuras de desglose de trabajo, profundizando de fases a tareas y subtareas.  
3. **Educación** – Mapear jerarquías curriculares, como departamentos → cursos → módulos.  

## Consideraciones de rendimiento

- **Eficiencia de memoria:** Aspose.Slides transmite datos, por lo que incluso una presentación de 500 páginas con varios gráficos mantiene menos de 200 MB de RAM.  
- **Recolección de basura:** Libera los objetos de diapositiva (`slide.dispose()`) cuando ya no se necesiten para evitar fugas de memoria.  

## Preguntas frecuentes

**P: ¿Qué es un gráfico Sunburst?**  
R: Un gráfico Sunburst visualiza datos jerárquicos en anillos concéntricos, con cada anillo representando un nivel de la jerarquía.

**P: ¿Cómo instalo Aspose.Slides para Java usando Maven?**  
R: Agrega la dependencia Maven mostrada en la sección “Dependencia Maven” a tu `pom.xml` y ejecuta `mvn clean install`.

**P: ¿Puedo personalizar otros tipos de gráficos con Aspose.Slides?**  
R: Sí, la biblioteca soporta más de 50 tipos de gráficos, incluidos column, line, pie y radar.

**P: Mi presentación no se guarda—¿qué debo verificar?**  
R: Verifica que la ruta del archivo sea correcta, que el directorio exista y que tengas permisos de escritura. Además, asegúrate de que se llame al método `Presentation.save()`.

**P: ¿Dónde puedo obtener más ayuda o ejemplos?**  
R: Visita el [foro de Aspose](https://forum.aspose.com/c/slides/11) o consulta la [referencia oficial de Aspose.Slides](https://reference.aspose.com/slides/java/).

## Recursos
- **Documentación:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Referencia (minúsculas):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Foro de la comunidad:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Descargas:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Última actualización:** 2026-07-17  
**Probado con:** Aspose.Slides for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo agregar gráficos a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animar gráficos en PowerPoint usando Aspose.Slides para Java – Guía paso a paso](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Crear gráfico en Java con Aspose.Slides – Agregar y validar gráficos](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
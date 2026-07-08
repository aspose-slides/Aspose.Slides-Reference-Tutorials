---
date: '2026-07-08'
description: Aprenda cómo agregar presentaciones PowerPoint con pie chart usando Aspose.Slides
  for Java. Siga esta guía paso a paso para crear y personalizar pie charts profesionales.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Agregar pie chart PowerPoint usando Aspose.Slides for Java. Este tutorial
  muestra cómo generar y personalizar pie charts programáticamente, perfecto para
  informes automatizados.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Agregar pie chart PowerPoint con Aspose.Slides for Java – Guía rápida
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Cómo agregar un pie chart PowerPoint con Aspose.Slides for Java
url: /es/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Agregar gráfico circular a PowerPoint con Aspose.Slides para Java

## Introducción

Si necesitas **agregar gráfico circular a PowerPoint** diapositivas sin abrir PowerPoint manualmente, estás en el lugar correcto. En esta guía repasaremos cómo configurar Aspose.Slides para Java, crear un gráfico circular y personalizar cada porción, perfecto para informes automatizados, paneles de control o presentaciones personalizadas. Al final tendrás un fragmento de código Java reutilizable que genera un archivo PowerPoint con un gráfico circular pulido en segundos.

### Respuestas rápidas
- **¿Qué biblioteca crea el gráfico?** Aspose.Slides for Java (latest release).  
- **¿Puedo ejecutarlo sin interfaz?** Sí—no se requiere instalación de Office.  
- **¿Qué versión de Java es óptima?** JDK 16+ para el mejor rendimiento y mejoras de GC.  
- **¿Cómo exploto una porción?** Llama a `setExplosion` en el `IDataPoint` y establece un desplazamiento en píxeles.  
- **¿Necesito una licencia para producción?** Una prueba funciona para desarrollo; una licencia permanente elimina todos los límites de evaluación.

## ¿Por qué agregar gráfico circular a PowerPoint usando Aspose.Slides para Java?

Puedes generar informes visuales actualizados directamente desde tus servicios de back‑end, eliminando errores manuales de copiar‑pegar y garantizando un estilo coherente con la marca. Aspose.Slides soporta **70+ chart types** y puede procesar presentaciones con **10,000+ slides** sin cargar todo el archivo en memoria, lo que lo hace ideal para automatización a gran escala.

## Requisitos previos

- **Aspose.Slides for Java** – el tutorial hace referencia a la versión 25.4 (la más reciente al momento de escribir).  
- **Java Development Kit** – se recomienda JDK 16 o superior.  
- **Maven** o **Gradle** para la gestión de dependencias.  

## Configuración de Aspose.Slides para Java

### Maven
Agrega esta dependencia a tu `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluye lo siguiente en tu `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, descarga la versión más reciente directamente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenciamiento
Para usar Aspose.Slides sin limitaciones:

- Comienza con una **prueba gratuita** para evaluar la API.  
- Solicita una **licencia temporal** para pruebas extendidas en la página [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Compra una suscripción completa a través de la [Purchase page](https://purchase.aspose.com/buy).

## Cómo agregar gráfico circular a PowerPoint usando Aspose.Slides para Java

Carga una nueva presentación, inserta un gráfico circular y guarda el archivo—todo en tres pasos concisos. Este patrón funciona para cualquier conjunto de datos y puede envolver en un bucle para generar docenas de diapositivas automáticamente. El enfoque es liviano, requiriendo solo unas pocas líneas de código y sin recursos externos, lo que lo hace adecuado tanto para pequeñas utilidades como para trabajos por lotes grandes.

### Paso 1: Inicializar la presentación
La clase `Presentation` representa un único archivo PowerPoint en memoria. Crear una instancia te brinda una nueva baraja de diapositivas vacía con la que trabajar.
```java
Presentation pres = new Presentation();
```

### Paso 2: Agregar el gráfico circular
Inserta un gráfico circular en la primera diapositiva. Las coordenadas (50, 50) y el tamaño (600 × 400) se ajustan a un diseño estándar 16:9 y dejan espacio para los títulos.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Paso 3: Guardar la presentación
Escribe la presentación en disco. Reemplaza `YOUR_OUTPUT_DIRECTORY` con la carpeta donde deseas guardar el archivo.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Paso 4: Limpiar recursos
Descarta el objeto `Presentation` para liberar recursos nativos y evitar fugas de memoria.
```java
if (pres != null) pres.dispose();
```

## ¿Cómo personalizar la explosión y el color del punto de datos?

Carga el gráfico, localiza el punto de datos objetivo y luego aplica un desplazamiento de explosión y un color de relleno sólido. Esto hace que la porción destaque para enfatizar. Estos ajustes ayudan a captar la atención de la audiencia a valores críticos y mejoran la legibilidad general del gráfico.

### Paso 1: Cargar una presentación existente (o reutilizar la que acabas de crear)
El objeto `Presentation` carga un archivo PowerPoint existente en memoria, permitiéndote modificar su contenido.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Paso 2: Acceder al gráfico y al punto de datos objetivo
La interfaz `IDataPoint` representa un punto de datos individual (porción) dentro de una serie de gráfico.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Paso 3: Aplicar explosión y color
`setExplosion(int)` establece la distancia, en píxeles, que una porción se desplaza del centro del gráfico. Separa visualmente la porción con `setExplosion(20)` y cambia su relleno a azul usando `setFillType(FillType.Solid)` y `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Paso 4: Guardar y descartar
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Aplicaciones prácticas
- **Sales Reports:** Resalta los productos más vendidos con porciones explotadas.  
- **Budget Analysis:** Asigna colores distintos a los departamentos para una comparación visual rápida.  
- **Educational Slides:** Desglosa conceptos complejos en segmentos de gráfico digeribles.  

## Consideraciones de rendimiento
- **Dispose objects** rápidamente para evitar fugas de memoria, especialmente al generar muchas diapositivas en un bucle.  
- **Monitor heap usage** para presentaciones grandes; usa la sobrecarga `Save` que acepta un `OutputStream` para transmitir datos y mantener bajo el consumo de memoria.  
- Mantente en **JDK 16+** para beneficiarte de las últimas mejoras de recolección de basura, lo que puede reducir el tiempo de procesamiento hasta un 30 % para barajas de 1,000 diapositivas.

## Conclusión
Ahora tienes un flujo de trabajo completo y listo para producción para **agregar gráficos circulares a PowerPoint** usando Aspose.Slides para Java. Experimenta con diferentes distancias de explosión, colores y conjuntos de datos para que coincidan con tu marca. Cuando estés listo, explora otros tipos de gráficos—barras, líneas o dispersión—para crear un panel de análisis completo dentro de PowerPoint.

## Preguntas frecuentes

**Q: ¿Cuál es la mayor ventaja de usar Aspose.Slides para Java?**  
A: Le permite crear, editar y renderizar archivos PowerPoint programáticamente sin necesidad de tener Microsoft Office instalado, soportando más de 70 tipos de gráficos y más de 100 formatos de archivo.

**Q: ¿Puedo generar un archivo PowerPoint desde cero?**  
A: Sí, instancia un objeto `Presentation`, agrega diapositivas, gráficos o formas, luego llama a `save`, todo en código Java puro.

**Q: ¿Cómo exploto una porción específica del gráfico circular?**  
A: Obtén el `IDataPoint` de la porción y llama a `setExplosion(pixelOffset)`. El desplazamiento define qué tan lejos se mueve la porción hacia afuera.

**Q: ¿Hay un límite al número de diapositivas que puedo crear?**  
A: Aspose.Slides puede manejar presentaciones con hasta **10,000 slides** en un solo archivo, siempre que transmitas la salida para evitar cargar todo en memoria.

**Q: ¿Dónde puedo encontrar ejemplos más avanzados de personalización de gráficos?**  
A: Consulta la documentación oficial [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) para referencias detalladas de la API y proyectos de ejemplo.

## Recursos
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Última actualización:** 2026-07-08  
**Probado con:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo agregar gráficos a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animar gráficos en PowerPoint usando Aspose.Slides para Java – Guía paso a paso](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Crear y validar diseños de gráficos en PowerPoint usando Aspose.Slides para Java | Guía SEO optimizada](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
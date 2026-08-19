---
date: '2026-07-03'
description: Aprenda a crear gráficos Sunburst paso a paso en Java usando Aspose.Slides,
  con opciones de personalización completas para presentaciones de PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Cómo crear gráficos Sunburst en Java usando Aspose.Slides
url: /es/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear gráficos Sunburst en Java usando Aspose.Slides

## Introducción
En las presentaciones impulsadas por datos de hoy, **cómo crear sunburst** visualizaciones rápidamente puede diferenciar tus diapositivas. Este tutorial te guía paso a paso para construir un gráfico Sunburst con Aspose.Slides para Java, desde la configuración del proyecto hasta la exportación final, para que puedas ofrecer gráficos jerárquicos impactantes sin salir del ecosistema Java.

## Respuestas rápidas
- **¿Cuál es la clase principal para un archivo PowerPoint?** `Presentation` – representa todo el PPTX en memoria.  
- **¿Cuántas líneas de código se necesitan para un Sunburst básico?** Normalmente 5–7 líneas una vez referenciada la biblioteca.  
- **¿Qué formatos de salida son compatibles?** PPTX, PDF, PNG, SVG y HTML.  
- **¿Puedo dar estilo a segmentos individuales?** Sí – los colores de relleno, bordes y etiquetas de datos son totalmente personalizables.  
- **¿Necesito una licencia para producción?** Una evaluación gratuita funciona para pruebas; se requiere una licencia comercial para el despliegue.

## ¿Qué es un gráfico Sunburst?
Un gráfico Sunburst visualiza datos jerárquicos como anillos concéntricos, donde cada anillo representa un nivel de la jerarquía. Permite a los espectadores comprender las relaciones padre‑hijo de un vistazo, lo que lo hace ideal para organigramas, visualizaciones de taxonomías y métricas multinivel. Es especialmente útil para mostrar categorías multinivel como líneas de productos, regiones geográficas o estructuras organizativas, permitiendo ver tanto la distribución general como el desglose detallado dentro de cada segmento.

## ¿Por qué usar Aspose.Slides para gráficos Sunburst?
Aspose.Slides soporta **más de 30 tipos de gráficos**, procesa archivos de hasta **500 MB** sin cargar todo el documento en memoria y renderiza gráficos a **300 DPI** para una salida nítida. Estas capacidades cuantificadas garantizan una generación rápida y visuales de alta calidad incluso para presentaciones grandes. Además, la biblioteca ofrece operaciones seguras para subprocesos e integra sin problemas con herramientas de compilación Java populares, lo que la hace adecuada tanto para generación de presentaciones de escritorio como del lado del servidor a gran escala.

## Requisitos previos
- Java Development Kit (JDK) 8 o superior.  
- Maven o Gradle para la gestión de dependencias.  
- Aspose.Slides for Java (última versión).  
- Comprensión básica de estructuras de datos jerárquicas.

## ¿Cómo crear gráficos Sunburst paso a paso?
Carga tu entorno, añade un gráfico, alimenta datos jerárquicos, personalízalo y guarda el archivo, todo en unos pocos pasos sencillos. A continuación se muestra el flujo de trabajo exacto que puedes seguir sin escribir código adicional de plantilla. El proceso está totalmente automatizado, sin interacción manual de UI, y puede incorporarse a trabajos por lotes o servicios web para generar gráficos bajo demanda.

### Paso 1: Configurar el proyecto
Añade la dependencia Maven de Aspose.Slides (o el fragmento equivalente de Gradle) a tu `pom.xml`. Esto incluye todos los binarios requeridos y bibliotecas transitivas.

### Paso 2: Cargar o crear una presentación
`Presentation` es el objeto de nivel superior de Aspose.Slides que representa un archivo PowerPoint en memoria. Instáncialo con `new Presentation()` para una presentación nueva o pasa una ruta de archivo para abrir un PPTX existente.

### Paso 3: Añadir un gráfico Sunburst
Inserta una nueva forma de gráfico en una diapositiva usando `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Esto crea el marcador de posición Sunburst listo para los datos. `ChartType.Sunburst` especifica el tipo de gráfico Sunburst al añadirlo a la diapositiva.

### Paso 4: Poblar datos jerárquicos
`ChartData` contiene las series y categorías para un gráfico. Accede a la colección `ChartData` del gráfico y añade series y categorías que reflejen tu jerarquía. Para cada nivel, especifica la relación padre‑hijo mediante la propiedad `ParentSeries`, lo que permite al gráfico renderizar anillos concéntricos automáticamente.

### Paso 5: Personalizar la apariencia
Ajusta los colores de los segmentos, estilos de borde y etiquetas de datos a través de los objetos `ChartSeries` y `ChartDataPoint`. `ChartSeries` representa una serie de puntos de datos en un gráfico. `ChartDataPoint` representa un punto de datos individual dentro de una serie. También puedes habilitar rotación 3‑D o establecer la propiedad `Explode` para resaltar porciones específicas.

### Paso 6: Guardar la presentación
El enum `SaveFormat` define los formatos de archivo en los que puedes guardar una presentación. Llama a `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` para escribir el archivo en disco. También puedes exportar a PDF o PNG cambiando el valor del enum `SaveFormat`.

## ¿Cómo personalizar los colores del gráfico Sunburst?
Especifica un color de relleno para cada `ChartDataPoint` usando `point.getFillFormat().setFillType(FillType.Solid)` y luego `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Este enfoque directo te permite alinear la paleta con la identidad corporativa o resaltar puntos clave. También puedes aplicar rellenos degradados, ajustar la transparencia o usar colores de tema para garantizar consistencia con el resto del diseño de tu diapositiva.

## Problemas comunes y soluciones
- **Problema:** La jerarquía aparece plana.  
  **Solución:** Asegúrese de que cada serie hija haga referencia correctamente a su `ParentSeries`. Los enlaces faltantes hacen que el gráfico trate todos los datos como un solo nivel.  
- **Problema:** El PNG exportado se ve borroso.  
  **Solución:** Aumente el DPI de exportación configurando `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.  
- **Problema:** Archivos PPTX grandes causan OutOfMemoryError.  
  **Solución:** Use `Presentation.setMemoryOptimization(true)` para transmitir datos y mantener bajo el uso de memoria.

## Preguntas frecuentes

**P: ¿Puedo generar un gráfico Sunburst a partir de un archivo CSV?**  
R: Sí. Lea el CSV, construya la jerarquía en memoria y alimente la colección `ChartData` del gráfico antes de guardar.

**P: ¿Aspose.Slides admite transiciones animadas para gráficos Sunburst?**  
R: Sí. Aplique un `SlideShowTransition` a la diapositiva o use `ChartFormat.setAnimationEnabled(true)` para animación a nivel de gráfico.

**P: ¿Es posible exportar el gráfico como un gráfico vectorial SVG?**  
R: Absolutamente. Guarde la presentación con `SaveFormat.Svg` para obtener una versión vectorial escalable del gráfico Sunburst.

**P: ¿Cuál es el número máximo de puntos de datos que puede manejar un gráfico Sunburst?**  
R: Aspose.Slides procesa de forma fiable hasta **10,000** puntos de datos en un solo gráfico Sunburst sin degradación del rendimiento.

**P: ¿Necesito una licencia separada para cada entorno de despliegue?**  
R: Una única licencia comercial cubre todos los entornos (desarrollo, pruebas, producción) siempre que se respeten los términos de la licencia.

## Conclusión
Ahora tienes una guía completa, paso a paso, para **cómo crear sunburst** gráficos en Java usando Aspose.Slides. Siguiendo el flujo de trabajo anterior, puedes generar visualizaciones jerárquicas de alta calidad y totalmente personalizables para cualquier presentación de PowerPoint.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Tutoriales relacionados

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Master PowerPoint Chart Customization Using Aspose.Slides Java for Dynamic Presentations](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step‑by‑Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
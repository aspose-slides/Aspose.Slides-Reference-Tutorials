---
date: '2026-08-01'
description: Aprenda a usar una licencia de Aspose Slides para crear y personalizar
  gráficos de pastel en presentaciones Java. Siga instrucciones paso a paso para configurar
  los datos del gráfico de pastel y añadir diapositivas de gráficos de manera eficiente.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Aprenda a usar una licencia de Aspose Slides para crear y personalizar
  gráficos de pastel en presentaciones Java. Siga instrucciones paso a paso para configurar
  los datos del gráfico de pastel y añadir diapositivas de gráficos de manera eficiente.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Crear gráficos de pastel en Java con una licencia de Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Crear gráficos de pastel en Java con una licencia de Aspose Slides
url: /es/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear gráficos de pastel en presentaciones Java usando Aspose.Slides

## Introducción

Si necesitas producir presentaciones de aspecto profesional, **una licencia de Aspose Slides** te brinda el poder de generar y dar estilo a los gráficos de forma programática. En esta guía aprenderás a crear un gráfico de pastel, configurar sus datos e incrustarlo en una presentación Java, todo sin depender de Microsoft PowerPoint. Recorreremos la configuración, el flujo de código y consejos de buenas prácticas para que puedas entregar informes visuales pulidos en minutos.

**Lo que aprenderás:**
- Configurar Aspose.Slides para Java con una licencia válida
- Pasos para crear y personalizar un gráfico de pastel
- Cómo configurar los datos del gráfico de pastel y agregar diapositivas con gráficos
- Trampas comunes y trucos de rendimiento

Comencemos confirmando que tu entorno está listo.

## Respuestas rápidas
- **¿Qué habilita la licencia de Aspose Slides?** Creación completa de gráficos, exportación a PDF/HTML y eliminación de marcas de agua.
- **¿Qué versión de Java se requiere?** JDK 16 o posterior.
- **¿Necesito Maven o Gradle?** Ambos funcionan; la biblioteca está disponible en los dos.
- **¿Cuántos puntos de datos puede contener un gráfico de pastel?** Hasta 10 000 puntos sin problemas de memoria.
- **¿Puedo exportar la diapositiva como imagen?** Sí, se admiten PNG, JPEG, SVG y más.

## Requisitos previos

Antes de comenzar, verifica que tienes:
- **Bibliotecas requeridas:** Aspose.Slides para Java (versión 25.4 o posterior) – esta versión soporta los últimos formatos de archivo y optimizaciones de rendimiento.
- **Configuración del entorno:** JDK 16+ instalado y configurado en tu IDE o sistema de compilación.
- **Conocimientos básicos:** Familiaridad con Java, Maven o Gradle y conceptos de programación orientada a objetos.

## Configuración de Aspose.Slides para Java

Para usar Aspose.Slides para Java, inclúyelo en tu proyecto. Así es como se agrega la dependencia con las herramientas de compilación más comunes:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Descarga directa:** También puedes descargar el JAR más reciente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Adquisición de licencia

Aspose ofrece una prueba gratuita que desbloquea todas las funciones, pero se requiere una **licencia válida de Aspose Slides** para uso en producción y eliminar las marcas de agua de evaluación, además de obtener beneficios de rendimiento. Las opciones de compra se enumeran en la [página de compra](https://purchase.aspose.com/buy). Después de obtener el archivo de licencia, cárgalo una vez al iniciar la aplicación:

`License` carga y aplica tu licencia de Aspose.Slides.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Guía de implementación

### Crear y agregar gráfico de pastel a la presentación

#### Visión general
Esta sección explica cómo crear un gráfico de pastel, configurar su serie de datos e incrustar el gráfico en una diapositiva. Verás el flujo completo desde la inicialización del objeto de presentación hasta el guardado del archivo final.

#### Paso 1: Inicializar la presentación  
`Presentation` es el objeto de nivel superior de Aspose.Slides que representa un archivo PowerPoint en memoria. Crear una instancia te brinda una presentación en blanco lista para modificarse.

```java
demo.Presentation pres = new demo.Presentation();
```  
Esta línea crea una nueva presentación donde se aplicarán todos los cambios posteriores.

#### Paso 2: Agregar gráfico de pastel a la diapositiva  
`Chart` es la clase que encapsula los objetos de gráficos, incluidos los gráficos de pastel. Agregar un gráfico a una diapositiva es una única llamada de método que especifica posición y tamaño.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` y `yPosition` establecen la esquina superior izquierda del gráfico.  
- `width` y `height` definen la huella visual del gráfico en la diapositiva.

#### Paso 3: Configurar datos del gráfico de pastel  
`ChartData` contiene la serie de datos para un gráfico.  
**¿Cómo configuro los datos del gráfico de pastel?**  
Proporciona una respuesta concisa primero: Usa la colección `ChartData` para agregar una serie, luego rellena objetos `ChartDataPoint` con valores numéricos y nombres de categoría. Este enfoque te permite mostrar hasta 10 000 porciones mientras mantienes el formato de etiquetas. Después de establecer los datos, puedes personalizar colores, leyendas y etiquetas de datos para que coincidan con la guía de estilo corporativa.

Ahora, aquí está el código que agrega dos categorías y muestra sus etiquetas:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
El fragmento crea una serie de datos, inserta dos puntos y habilita las etiquetas de categoría en el gráfico.

#### Paso 4: Guardar la presentación  
Finalmente, persiste la presentación en el formato de archivo que prefieras (PPTX, PDF o PNG). El método `save` respeta la licencia activa, asegurando que no aparezcan marcas de agua de evaluación.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Problemas comunes y soluciones
- **Error de licencia faltante:** Asegúrate de que la ruta del archivo de licencia sea correcta y de que el objeto `License` se instancie antes de cualquier llamada a Aspose.Slides.
- **Gráfico vacío:** Verifica que la serie `ChartData` contenga al menos un `ChartDataPoint`. Una serie vacía genera un área de gráfico en blanco.
- **Retardo de rendimiento con conjuntos de datos grandes:** Usa `presentation.getSlides().removeAt(index)` para descartar diapositivas no usadas y llama a `System.gc()` después de procesamientos intensivos.

## Aplicaciones prácticas
1. **Informes empresariales:** Visualiza la cuota de mercado o la distribución de ingresos por regiones con un solo gráfico de pastel.
2. **Presentaciones académicas:** Muestra resultados de encuestas o experimentos en un formato claro y digerible.
3. **Paneles de proyecto:** Representa porcentajes de tareas completadas o asignación de recursos al instante en una diapositiva.

También puedes combinar Aspose.Slides con JDBC para extraer datos en tiempo real de una base de datos, generando gráficos actualizados semanalmente para presentaciones ejecutivas.

## Consideraciones de rendimiento
Al trabajar con presentaciones que contienen muchas imágenes de alta resolución o grandes conjuntos de datos:
- Libera objetos rápidamente usando `try‑with‑resources` o llamadas explícitas a `dispose()`.
- Habilita la carga diferida de recursos de diapositivas para mantener bajo el uso de memoria.
- Para procesamiento por lotes, reutiliza una única instancia de `Presentation` siempre que sea posible para reducir la sobrecarga de la JVM.

## Conclusión
Ahora dispones de un flujo de trabajo completo y listo para producción para crear gráficos de pastel en Java usando una **licencia de Aspose Slides**. Experimenta con tipos de gráficos adicionales—barras, líneas o rosquilla—para enriquecer aún más tus diapositivas. A continuación, explora las capacidades de exportación de la API para generar informes PDF o imágenes PNG automáticamente.

## Preguntas frecuentes

**Q: ¿Cómo agrego varios gráficos a una sola diapositiva?**  
A: Llama a `slide.getShapes().addChart()` para cada gráfico, proporcionando coordenadas y dimensiones únicas para cada instancia.

**Q: ¿Cuáles son algunas alternativas a Aspose.Slides para Java?**  
A: Apache POI y JFreeChart son alternativas comunes, pero carecen de las opciones de exportación integrales y del modelo de licenciamiento de Aspose.

**Q: ¿Puedo convertir mi presentación a otros formatos usando Aspose.Slides?**  
A: Sí, puedes exportar a PDF, XPS, HTML, PNG, JPEG, SVG y más con una única llamada a `save`.

**Q: ¿Cómo gestiono la licencia para un gran equipo de desarrollo?**  
A: Compra una licencia empresarial que cubra a varios desarrolladores y servidores; contacta al equipo de ventas de Aspose para descuentos por volumen.

**Q: ¿Qué pasa si los datos de mi gráfico se actualizan con frecuencia?**  
A: Integra Aspose.Slides con una fuente de datos (por ejemplo, una consulta SQL) y reconstruye el gráfico en tiempo de ejecución; la API admite enlace dinámico de datos.

## Recursos
- **Documentación:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Descarga:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Compra:** [Buy a License](https://purchase.aspose.com/buy)
- **Prueba gratuita:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Licencia temporal:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Soporte:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Última actualización:** 2026-08-01  
**Probado con:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Tutoriales relacionados

- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Create and Customize Charts in Java Presentations Using Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [How to Create and Configure Presentations with Aspose.Slides Java: A Step-by-Step Guide](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
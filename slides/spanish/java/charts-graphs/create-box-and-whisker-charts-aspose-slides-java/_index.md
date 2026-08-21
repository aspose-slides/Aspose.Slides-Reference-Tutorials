---
date: '2026-08-21'
description: Aprenda cómo crear box plot Java usando Aspose.Slides, añadir un gráfico
  a la diapositiva y generar un box‑and‑whisker chart en PowerPoint. Ideal para desarrolladores
  Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Aprenda cómo crear box plot Java usando Aspose.Slides, añadir un gráfico
  a la diapositiva y generar un box‑and‑whisker chart en PowerPoint. Ideal para desarrolladores
  Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Cómo crear box plot Java con Aspose.Slides para PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Cómo crear box plot Java con Aspose.Slides para PowerPoint
url: /es/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un diagrama de caja java con Aspose.Slides para PowerPoint

En esta guía **creará un diagrama de caja java** con Aspose.Slides y luego incrustará el gráfico directamente en una diapositiva de PowerPoint. Generar gráficos de caja y bigotes de forma programática le permite convertir datos estadísticos sin procesar en visualizaciones claras sin salir de su código Java. Si necesita automatizar la generación de informes en PowerPoint, Aspose.Slides para Java ofrece una API fiable y de alto rendimiento.

## Lo que aprenderá

- Configurar su entorno para Aspose.Slides para Java
- Pasos para **agregar un gráfico a la diapositiva** y generar un gráfico de caja y bigotes en PowerPoint usando Java
- Mejores prácticas para optimizar el rendimiento al trabajar con Aspose.Slides
- Aplicaciones reales de los gráficos de caja y bigotes

## Respuestas rápidas
- **¿Qué biblioteca crea un diagrama de caja en Java?** Aspose.Slides para Java.  
- **¿Qué tipo de gráfico se utiliza?** `ChartType.BoxAndWhisker`.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Puedo agregar varias series?** Sí – repita el bloque de creación de series para cada conjunto de datos.  
- **¿Cuál es el formato del archivo final?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## ¿Qué es un diagrama de caja y por qué usarlo en Java?

Un gráfico de caja y bigotes (a menudo llamado *diagrama de caja*) visualiza la distribución de los datos—mediana, cuartiles y valores atípicos—en una forma compacta. En Java, generar este gráfico programáticamente le permite incrustar ideas estadísticas directamente en presentaciones de PowerPoint, eliminando la creación manual de gráficos. Es especialmente útil para comparar distribuciones entre múltiples categorías, como calificaciones de exámenes entre clases o cifras de ventas entre regiones. Al generar el gráfico en Java, puede integrarlo en pipelines de informes automatizados, asegurando que los datos más recientes siempre se reflejen en sus presentaciones.

## ¿Por qué agregar un gráfico a la diapositiva con Aspose.Slides?

Aspose.Slides abstrae los detalles de bajo nivel de OpenXML, ofreciéndole una API fluida para crear, dar estilo y exportar gráficos. Esto le permite automatizar la generación de informes, producir una marca consistente e integrar gráficos en flujos de trabajo Java más amplios. La biblioteca también admite opciones de estilo como colores, fuentes y marcadores, lo que le permite coincidir con la identidad corporativa. Además, gestiona tareas complejas como la vinculación de datos y la actualización del gráfico sin requerir Microsoft Office.

## ¿Cómo agregar un gráfico a una diapositiva con Aspose.Slides en Java?

Cargue o cree una `Presentation`, inserte un `Chart` de tipo `BoxAndWhisker`, proporcione sus datos y guarde el archivo—todo en unas pocas líneas de Java. La API maneja el diseño, el escalado y el renderizado, por lo que no necesita manipular XML manualmente. También puede establecer títulos de gráfico y etiquetas de ejes programáticamente para proporcionar contexto a los espectadores.

## Requisitos previos

- **Java Development Kit (JDK)**: JDK 8 o superior.  
- **Biblioteca Aspose.Slides para Java**: Necesaria para la manipulación de PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse o cualquier editor compatible con Java.

## Configuración de Aspose.Slides para Java

Agregue la biblioteca como dependencia de Maven, Gradle o manualmente.

### Maven

Agregue la siguiente dependencia en su `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

En su `build.gradle`, incluya:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa

Alternativamente, descargue la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Obtención de licencia

- **Prueba gratuita** – explore las funciones sin costo.  
- **Licencia temporal** – úsela para una evaluación a corto plazo.  
- **Compra** – desbloquee la funcionalidad completa para entornos de producción.

Para inicializar Aspose.Slides, asegúrese de que el JAR esté en su classpath y configure cualquier archivo de licencia según lo descrito en la documentación.

## Guía de implementación

A continuación se muestra un recorrido paso a paso. Cada bloque se explica antes del fragmento para que sepa exactamente qué hace.

### ¿Qué es la clase `Presentation`?

La clase `Presentation` es el objeto central en Aspose.Slides que representa un archivo PowerPoint completo en memoria. Proporciona acceso a diapositivas, gráficos, formas y otros elementos de la diapositiva, permitiéndole crear, modificar y guardar presentaciones programáticamente. Con esta clase, puede agregar nuevas diapositivas, insertar imágenes y manipular el orden de las diapositivas con llamadas simples a la API.

### Paso 1: crear o abrir una presentación

Primero, abra un PPTX existente o inicie uno nuevo:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Consejo profesional:** Si el archivo no existe, Aspose.Slides creará automáticamente una nueva presentación en blanco.

### Paso 2: agregar un gráfico de caja y bigotes a la diapositiva

Coloque el gráfico donde lo necesite especificando la posición y el tamaño (en puntos):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Paso 3: borrar datos existentes

Antes de proporcionar nuevos datos, elimine cualquier categoría o serie de marcador de posición:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Paso 4: configurar categorías

Agregue las categorías (etiquetas del eje X) que aparecerán bajo cada caja:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Nota:** Ajuste el texto de la etiqueta para que coincida con el dominio de sus datos (p. ej., “Q1”, “Producto A”).

### Paso 5: crear y personalizar la serie

Ahora cree una serie, establezca opciones visuales y proporcione los puntos de datos numéricos:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Puede reemplazar el arreglo `int[] data` con valores leídos de una base de datos, archivo CSV o cualquier otra fuente.

### Paso 6: guardar la presentación

Persista los cambios en un nuevo archivo PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Paso 7: liberar recursos

Siempre libere el objeto `Presentation` para liberar recursos nativos:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Aplicaciones prácticas

Los gráficos de caja y bigotes son invaluables en análisis estadístico y presentación de datos. Aquí algunos escenarios donde brillan:

1. **Análisis financiero** – visualizar la distribución de ingresos por regiones.  
2. **Control de calidad** – detectar valores atípicos en mediciones de fabricación.  
3. **Investigación académica** – mostrar la variabilidad de resultados experimentales.  
4. **Investigación de mercado** – comparar el rendimiento de productos entre demografías.

Incrustar estos gráficos directamente en presentaciones de PowerPoint permite a los interesados comprender datos complejos de un vistazo.

## Consideraciones de rendimiento

Aspose.Slides puede manejar presentaciones con **más de 500 diapositivas** y gráficos con **más de 100 000 puntos de datos** manteniendo el uso de memoria por debajo de 200 MB en un servidor típico. Para mantenerse dentro de esos límites:

- **Gestión de memoria** – libere los objetos `Presentation` rápidamente.  
- **Manejo de datos** – cargue solo los datos que necesita; evite alimentar conjuntos de datos masivos directamente en el libro de trabajo del gráfico.  
- **Carga diferida** – al generar muchas diapositivas, cree gráficos solo para aquellas que se mostrarán.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **El gráfico aparece vacío** | Las celdas de datos no se rellenaron correctamente | Verifique que las referencias `wb.getCell` apunten a la fila/columna correctas y que el valor no sea `null`. |
| **No se muestran los valores atípicos** | `setShowOutlierPoints` está configurado en `false` | Asegúrese de llamar `series.setShowOutlierPoints(true)`. |
| **Fuga de memoria** | La presentación no se libera | Siempre envuelva el uso en `try/finally` y llame a `dispose()`. |
| **Cuartiles incorrectos** | Uso del método `Inclusive` por defecto | Cambie a `Exclusive` mediante `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Preguntas frecuentes

**P1: ¿Qué es un gráfico de caja y bigotes?**  
Un gráfico de caja y bigotes, también conocido como diagrama de caja, muestra la distribución de los datos basándose en cinco estadísticas resumidas: mínimo, primer cuartil, mediana, tercer cuartil y máximo, además de cualquier valor atípico.

**P2: ¿Puedo personalizar la apariencia del gráfico de caja y bigotes?**  
Sí. Aspose.Slides le permite cambiar colores, estilos de línea, formas de marcadores y agregar etiquetas de datos mediante la API de formato del gráfico.

**P3: ¿Es posible manejar múltiples series en un solo gráfico?**  
Absolutamente. Repita el bloque de creación de series para cada conjunto de datos que desee visualizar.

**P4: ¿Cómo resuelvo problemas con datos que no se muestran correctamente?**  
Asegúrese de que los datos se escriban correctamente en las celdas del libro de trabajo y que propiedades de visibilidad como `setShowMeanLine` estén habilitadas.

**P5: ¿Dónde puedo obtener soporte si encuentro problemas?**  
Visite el [foro de Aspose.Slides](https://forum.aspose.com/c/slides/11) para ayuda de la comunidad, o consulte la documentación oficial.

**P6: ¿Aspose.Slides admite otros tipos de gráficos?**  
Sí, admite más de 50 tipos de gráficos—incluidos línea, barra, pastel, dispersión, radar y embudo—para que pueda elegir la visualización más adecuada para sus datos.

**P7: ¿Puedo generar gráficos en un entorno de servidor sin interfaz gráfica?**  
La biblioteca funciona completamente en escenarios del lado del servidor; no se requiere UI ni instalación de Microsoft Office.

## Recursos

- **Documentación**: Explore referencias detalladas de la API en [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Descarga**: Acceda a la página de versiones de Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Compra**: Adquiera una licencia para desbloquear todas las funciones [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Prueba gratuita y licencia temporal**: Comience con una prueba gratuita o solicite una licencia temporal [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Al seguir esta guía, ahora está preparado para generar programáticamente gráficos de caja y bigotes perspicaces en sus aplicaciones Java e incrustarlos directamente en presentaciones de PowerPoint. ¡Feliz codificación!

---

**Última actualización:** 2026-08-21  
**Probado con:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose

## Tutoriales relacionados

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
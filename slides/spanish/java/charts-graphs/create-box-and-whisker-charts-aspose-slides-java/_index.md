---
date: '2026-03-02'
description: Aprenda cómo crear diagramas de caja en Java, agregar un gráfico a una
  diapositiva y generar un gráfico de caja y bigotes en PowerPoint usando Aspose.Slides
  para Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Crear diagrama de caja en Java usando Aspose.Slides para PowerPoint
url: /es/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear gráficos de caja y bigotes en PowerPoint usando Aspose.Slides para Java

En esta guía **create box plot java** con Aspose.Slides, luego incrustarás el gráfico directamente en una diapositiva de PowerPoint. Crear presentaciones de datos visualmente atractivas es crucial en el mundo actual impulsado por los datos, y los gráficos son herramientas esenciales para este propósito. Si deseas generar gráficos de caja y bigotes dentro de PowerPoint usando Java, la biblioteca Aspose.Slides ofrece una solución robusta. Este tutorial te guiará paso a paso en la creación y configuración de estos gráficos sin problemas con Aspose.Slides para Java.

## Lo que aprenderás

- Configurar tu entorno para Aspose.Slides para Java
- Pasos para **add chart to slide** y generar un gráfico de caja‑whisker en PowerPoint usando Java
- Mejores prácticas para optimizar el rendimiento al trabajar con Aspose.Slides
- Aplicaciones reales de gráficos de caja‑y‑bigotes

## Respuestas rápidas
- **¿Qué biblioteca crea un box plot en Java?** Aspose.Slides for Java.
- **¿Qué tipo de gráfico se usa?** `ChartType.BoxAndWhisker`.
- **¿Necesito una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.
- **¿Puedo agregar múltiples series?** Sí – repite el bloque de creación de series para cada conjunto de datos.
- **¿Cuál es el formato del archivo final?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Requisitos previos

Para seguir este tutorial, asegúrate de tener:

- **Java Development Kit (JDK)**: JDK 8 o superior debe estar instalado.
- **Aspose.Slides for Java Library**: Esencial para manejar presentaciones PowerPoint en Java.
- **IDE**: Un Entorno de Desarrollo Integrado como IntelliJ IDEA o Eclipse para escribir y ejecutar tu código.

## Configuración de Aspose.Slides para Java

Para usar Aspose.Slides, añádelo como una dependencia. Puedes gestionarlo a través de Maven, Gradle o mediante descarga directa.

### Maven

Agrega la siguiente dependencia en tu `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

En tu `build.gradle`, incluye:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa

Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Adquisición de licencia

- **Free Trial**: Comienza con una prueba gratuita para explorar las funciones.  
- **Temporary License**: Obtén una licencia temporal para propósitos de evaluación.  
- **Purchase**: Para funcionalidad completa, considera comprar una licencia.

Para inicializar Aspose.Slides, asegúrate de que la biblioteca esté en tu classpath y configura cualquier requisito de licencia según sea necesario.

## Guía de implementación

Ahora profundicemos en el código paso a paso. Cada bloque se explica antes del fragmento para que sepas exactamente qué hace.

### ¿Qué es un box plot y por qué usarlo en Java?

Un gráfico de caja‑bigotes (a menudo llamado *box plot*) visualiza la distribución de datos—mediana, cuartiles y valores atípicos—en una forma compacta. En Java, generar este gráfico programáticamente te permite incrustar ideas estadísticas directamente en presentaciones PowerPoint, eliminando la creación manual de gráficos.

### ¿Por qué agregar un gráfico a una diapositiva con Aspose.Slides?

Aspose.Slides abstrae los detalles de bajo nivel de OpenXML, ofreciéndote una API fluida para crear, estilizar y exportar gráficos. Esto significa que puedes automatizar la generación de informes, producir una marca consistente e integrar gráficos en flujos de trabajo Java más amplios.

### Paso 1: Crear o abrir una presentación

Primero, abre un PPTX existente o inicia uno nuevo:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Consejo:** Si el archivo no existe, Aspose.Slides creará una nueva presentación en blanco para ti.

### Paso 2: Agregar un gráfico de caja‑y‑bigotes a la diapositiva

Coloca el gráfico donde lo necesites especificando la posición y el tamaño (en puntos):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Paso 3: Borrar datos existentes

Antes de introducir nuevos datos, elimina cualquier categoría o serie de marcador de posición:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Paso 4: Configurar categorías

Agrega las categorías (etiquetas del eje X) que aparecerán bajo cada caja:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Nota:** Ajusta el texto de la etiqueta para que coincida con tu dominio de datos (p.ej., “Q1”, “Product A”).

### Paso 5: Crear y personalizar la serie

Ahora crea una serie, establece opciones visuales y proporciona los puntos de datos numéricos:

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

Puedes reemplazar el arreglo `int[] data` con valores leídos de una base de datos, archivo CSV, o cualquier otra fuente.

### Paso 6: Guardar la presentación

Persistir los cambios en un nuevo archivo PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Paso 7: Liberar recursos

Siempre libera el objeto `Presentation` para liberar recursos nativos:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Aplicaciones prácticas

Los gráficos de caja‑y‑bigotes son invaluables en análisis estadístico y presentación de datos. Aquí tienes algunos escenarios donde brillan:

1. **Financial Analysis** – Visualiza la distribución de ingresos entre regiones.  
2. **Quality Control** – Detecta valores atípicos en mediciones de fabricación.  
3. **Academic Research** – Muestra la variabilidad de resultados experimentales.  
4. **Market Research** – Compara el rendimiento de productos entre diferentes demografías.

Integrar estos gráficos en presentaciones PowerPoint permite a los interesados comprender datos complejos de un vistazo.

## Consideraciones de rendimiento

Al trabajar con Aspose.Slides en Java, ten en cuenta estos consejos:

- **Memory Management** – Libera los objetos `Presentation` rápidamente.  
- **Data Handling** – Carga solo los datos que necesitas; evita introducir conjuntos de datos masivos directamente en el libro de trabajo del gráfico.  
- **Lazy Loading** – Si generas muchas diapositivas, considera crear gráficos solo para las que se mostrarán.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **El gráfico aparece en blanco** | Celdas de datos no pobladas correctamente | Verifica que `wb.getCell` haga referencia a la fila/columna correctas y que el valor no sea `null`. |
| **Los valores atípicos no se muestran** | `setShowOutlierPoints` configurado como `false` | Asegúrate de llamar `series.setShowOutlierPoints(true)`. |
| **Fuga de memoria** | Presentación no liberada | Siempre envuelve el uso en try/finally y llama a `dispose()`. |
| **Cuartiles incorrectos** | Uso del método predeterminado `Inclusive` | Cambia a `Exclusive` mediante `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Preguntas frecuentes

**Q1: ¿Qué es un gráfico de caja‑y‑bigotes?**  
Un gráfico de caja‑y‑bigotes, también conocido como box plot, muestra la distribución de datos basada en cinco estadísticas resumidas: mínimo, primer cuartil, mediana, tercer cuartil y máximo, además de cualquier valor atípico.

**Q2: ¿Puedo personalizar la apariencia del gráfico de caja‑y‑bigotes?**  
Sí. Aspose.Slides te permite cambiar colores, estilos de línea, formas de marcadores e incluso agregar etiquetas de datos mediante la API de formato del gráfico.

**Q3: ¿Es posible manejar múltiples series en un solo gráfico?**  
Absolutamente. Repite el bloque de creación de series para cada conjunto de datos que desees visualizar.

**Q4: ¿Cómo resuelvo problemas con datos que no se muestran correctamente?**  
Asegúrate de que los datos se escriban correctamente en las celdas del libro de trabajo y que propiedades de visibilidad como `setShowMeanLine` estén habilitadas.

**Q5: ¿Dónde puedo obtener soporte si encuentro problemas?**  
Visita el [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) para ayuda de la comunidad, o consulta la documentación oficial.

**Q6: ¿Aspose.Slides admite otros tipos de gráficos?**  
Sí, admite líneas, barras, pastel, dispersión, radar y muchos más tipos de gráficos.

**Q7: ¿Puedo generar gráficos en un entorno de servidor sin interfaz gráfica?**  
La biblioteca funciona completamente en escenarios del lado del servidor; no se requiere UI.

## Recursos

- **Documentation**: Explora referencias detalladas de la API en [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Accede a las versiones de Aspose.Slides [aquí](https://releases.aspose.com/slides/java/)  
- **Purchase**: Compra una licencia para desbloquear todas las funciones en [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: Comienza con una prueba gratuita o solicita una licencia temporal [aquí](https://releases.aspose.com/slides/java/)

Siguiendo esta guía, ahora estás preparado para generar programáticamente gráficos de caja‑y‑bigotes perspicaces en tus aplicaciones Java e incrustarlos directamente en presentaciones PowerPoint. ¡Feliz codificación!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-02  
**Probado con:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose
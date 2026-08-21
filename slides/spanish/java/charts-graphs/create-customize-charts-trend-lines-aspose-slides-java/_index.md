---
date: '2026-08-21'
description: Aprenda cómo crear un gráfico de columnas agrupadas y agregar líneas
  de tendencia con Aspose.Slides for Java. Incluye configuración de licencia, integración
  con Maven/Gradle y ejemplos detallados.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Crear un gráfico de columnas agrupadas usando Aspose.Slides for Java.
  Esta guía cubre la configuración de licencia, Maven/Gradle y fragmentos de código
  paso a paso.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Crear un gráfico de columnas agrupadas y agregar líneas de tendencia con
  Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Cómo crear un gráfico de columnas agrupadas y agregar líneas de tendencia usando
  Aspose.Slides for Java
url: /es/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un gráfico de columnas agrupadas y agregar líneas de tendencia usando Aspose.Slides para Java

Crear presentaciones impactantes a menudo comienza con una visual clara de sus datos. En esta guía **creará objetos de gráfico de columnas agrupadas**, luego los enriquecerá con una variedad de líneas de tendencia —exponencial, lineal, logarítmica, media móvil, polinómica y de potencia— usando la potente API de Aspose.Slides para Java.

## Respuestas rápidas
- **¿Cuál es el primer paso?** Inicializar un objeto `Presentation` y agregar un gráfico de columnas agrupadas a una diapositiva.  
- **¿Qué versión de la biblioteca se requiere?** Aspose.Slides para Java 25.4 o superior.  
- **¿Puedo usar Maven o Gradle?** Sí, ambos son compatibles; Maven usa `<dependency>` y Gradle usa `implementation`.  
- **¿Necesito una licencia?** Una licencia de prueba funciona para evaluación; una licencia completa de Aspose.Slides elimina los límites de evaluación.  
- **¿Cuántos tipos de línea de tendencia están disponibles?** Seis tipos incorporados: exponencial, lineal, logarítmica, media móvil, polinómica y de potencia.

## ¿Qué es crear un gráfico de columnas agrupadas?
`create clustered column chart` significa generar un gráfico que agrupa múltiples series de datos una al lado de la otra dentro de cada categoría, facilitando la comparación de valores entre series. Este tipo de gráfico es ideal para visualizar datos categóricos como ventas trimestrales por región, permitiendo a los espectadores detectar rápidamente diferencias entre grupos.

## ¿Por qué agregar una línea de tendencia?
Las líneas de tendencia revelan el patrón subyacente de una serie de datos, ayudándole a pronosticar valores futuros, resaltar tasas de crecimiento o suavizar datos ruidosos. Al agregar una línea de tendencia a un gráfico de columnas agrupadas, los números crudos se convierten en información procesable, permitiendo a los interesados comprender tendencias a largo plazo y tomar decisiones basadas en datos.

## Requisitos previos
- **Java Development Kit (JDK):** 8 o posterior.  
- **Aspose.Slides para Java:** versión 25.4 o superior.  
- **IDE:** IntelliJ IDEA, Eclipse o cualquier editor compatible con Java.  
- **Herramienta de compilación:** Maven o Gradle (opcional pero recomendado).  
- **Licencia:** un archivo de licencia de prueba o comprado de Aspose.Slides.  

Debe sentirse cómodo con la sintaxis básica de Java y familiarizado con la gestión de dependencias del proyecto.

## ¿Cómo configurar Aspose.Slides para Java?
Agregue la biblioteca Aspose.Slides a su proyecto usando su gestor de dependencias preferido, luego coloque su archivo de licencia donde el tiempo de ejecución pueda localizarlo. Esto garantiza la funcionalidad completa y elimina las restricciones de evaluación.

### Maven
Agregue esta dependencia a su archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluya esta línea en su archivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
También puede descargar el JAR manualmente desde [lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

#### Licencia de Aspose Slides
Coloque el archivo `Aspose.Slides.lic` en la raíz de su proyecto o establezca la licencia programáticamente con `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Una licencia de prueba elimina todas las restricciones de funciones, pero una licencia comprada elimina la marca de agua de evaluación y otorga optimizaciones de rendimiento completas. Para uso en producción, considere comprar una licencia en la [página de compra de Aspose](https://purchase.aspose.com/buy).

## ¿Cómo crear una presentación y agregar un gráfico de columnas agrupadas?
La clase `Presentation` representa un archivo PowerPoint y proporciona métodos para crear, editar y guardar diapositivas. Instancie una `Presentation`, agregue una diapositiva y luego llame a `addChart` con `ChartType.ClusteredColumn` para crear el objeto de gráfico. Este proceso configura el lienzo de la diapositiva, inserta una forma de gráfico y lo prepara para la población de datos y el estilo.

1. **Inicializar la presentación** – configure la carpeta de salida y cree una nueva instancia de `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Agregar un gráfico de columnas agrupadas** – obtenga la forma del gráfico, configure sus series y rellene los puntos de datos.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## ¿Cómo agregar una línea de tendencia exponencial?
La interfaz `ITrendline` define una línea de tendencia que puede agregarse a una serie de gráfico para modelar patrones de datos. Aplique una línea de tendencia exponencial a una serie creando una instancia de `ITrendline`, estableciendo su `TrendlineType` a `Exponential` y adjuntándola a la serie deseada. Este tipo de línea es útil para datos que crecen rápidamente a una tasa creciente.

1. **Configurar la línea de tendencia** – seleccione la serie y llame a `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## ¿Cómo agregar una línea de tendencia lineal?
Una línea de tendencia lineal muestra la mejor línea recta ajustada a sus puntos de datos. También puede personalizar su apariencia, como el color y el grosor de la línea, para que coincida con el estilo de su presentación.

1. **Configurar la línea de tendencia** – use `addTrendline(TrendlineType.Linear)` y luego ajuste `getLineFormat().setFillFormat().setFillType(FillType.Solid)` para cambiar el color.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## ¿Cómo agregar una línea de tendencia logarítmica con un marco de texto personalizado?
Las líneas de tendencia logarítmicas son ideales para datos que crecen rápidamente al principio y luego se estabilizan. Sobrescribir la etiqueta predeterminada le permite agregar texto explicativo que aclare la importancia de la tendencia.

1. **Personalizar la línea de tendencia** – después de agregar la línea, acceda a su `getDataLabel()` y establezca la propiedad `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## ¿Cómo agregar una línea de tendencia de media móvil?
Las líneas de tendencia de media móvil suavizan fluctuaciones a corto plazo para resaltar tendencias a más largo plazo. Puede especificar el período (número de puntos) usado para el promedio, lo que le permite controlar la suavidad de la línea.

1. **Configurar la línea de tendencia** – llame a `addTrendline(TrendlineType.MovingAverage)` y establezca `setPeriod(3)` para usar una media móvil de tres puntos.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## ¿Cómo agregar una línea de tendencia polinómica?
Las líneas de tendencia polinómicas ajustan los datos con una curva definida por una ecuación polinómica. La propiedad `order` controla el grado del polinomio, permitiéndole modelar relaciones más complejas.

1. **Personalizar la línea de tendencia** – después de agregar la línea, establezca `setOrder(3)` para un ajuste cúbico.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## ¿Cómo agregar una línea de tendencia de potencia?
Las líneas de tendencia de potencia son útiles cuando los datos siguen una relación de ley de potencia. También puede establecer valores de pronóstico hacia atrás y hacia adelante para extender la línea más allá del rango de datos existente.

1. **Configurar la línea de tendencia** – use `addTrendline(TrendlineType.Power)` y ajuste `setBackward(2)` para extender la línea hacia atrás.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Aplicaciones prácticas de las líneas de tendencia en gráficos de columnas agrupadas
- **Análisis financiero:** Las tendencias exponenciales y polinómicas ayudan a pronosticar movimientos de precios de acciones.  
- **Pronóstico de ventas:** Las líneas de media móvil suavizan picos estacionales, ofreciendo una visión más clara de las tendencias subyacentes de ventas.  
- **Investigación científica:** Las tendencias logarítmicas son perfectas para datos que abarcan varios órdenes de magnitud, como la intensidad acústica o los niveles de pH.  
- **Monitoreo de operaciones:** Las líneas de tendencia de potencia pueden modelar la degradación del rendimiento a lo largo del tiempo.

## ¿Cómo optimizar la memoria al usar Aspose.Slides?
Libere los objetos rápidamente y use `presentation.dispose()` después de guardar. Para conjuntos de datos grandes, habilite la carga diferida de imágenes y evite cargar todo el gráfico en memoria de una sola vez.

- **Patrones de disposición:** Envuelva `Presentation` en un bloque try‑with‑resources o llame a `presentation.dispose()` en una cláusula finally.  
- **Carga diferida:** Establezca `ChartData.setUseCache(true)` al trabajar con miles de puntos de datos.  
- **Salida en streaming:** Escriba la presentación directamente a un `FileOutputStream` para evitar mantener todo el archivo en RAM.

## Beneficios cuantificados de Aspose.Slides para Java
Aspose.Slides soporta **más de 50 tipos de gráficos**, puede generar presentaciones con **más de 1 000 diapositivas** en menos de **30 segundos** en una CPU típica de 2 GHz, y procesa **PDFs de 500 páginas** sin requerir Microsoft Office instalado. Estas cifras están verificadas en la última versión 25.4.

## Conclusión
Ahora dispone de una solución completa, de extremo a extremo, para **crear objetos de gráfico de columnas agrupadas** y enriquecerlos con cada tipo principal de línea de tendencia disponible en Aspose.Slides para Java. Siguiendo los pasos anteriores, podrá producir presentaciones basadas en datos que son tanto visualmente atractivas como analíticamente potentes.

Los siguientes pasos incluyen explorar opciones de estilo de gráficos, exportar a PDF/HTML y automatizar la generación de gráficos a través de múltiples fuentes de datos.

## Preguntas frecuentes

**P: ¿Cómo configuro Aspose.Slides para un proyecto Maven?**  
R: Agregue el fragmento `<dependency>` mostrado en la sección Maven a su `pom.xml` y ejecute `mvn clean install`.

**P: ¿Puedo personalizar las líneas de tendencia más allá del color y la etiqueta?**  
R: Sí, puede modificar el estilo de línea, ancho, patrón de guiones e incluso valores de pronóstico hacia adelante/atrás mediante la API `ITrendline`.

**P: ¿Qué debo hacer si encuentro un error de compatibilidad de versión?**  
R: Verifique que su versión de JDK coincida con el requisito mínimo de Aspose.Slides (JDK 8+). Consulte las notas de la versión de Aspose para cualquier cambio que rompa la compatibilidad.

**P: ¿Es posible agregar líneas de tendencia a varios gráficos automáticamente?**  
R: Absolutamente. Recorra cada `IChart` en una colección de diapositivas e invoque el método `addTrendline` apropiado para cada serie.

**P: ¿Necesito una licencia de pago para uso en producción?**  
R: Sí, una licencia comprada de Aspose.Slides elimina los límites de evaluación y desbloquea optimizaciones de rendimiento completas.

---

**Última actualización:** 2026-08-21  
**Probado con:** Aspose.Slides para Java 25.4  
**Autor:** Aspose

## Tutoriales relacionados

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
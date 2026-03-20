---
date: '2026-03-20'
description: Aprende a añadir gráficos a presentaciones Java usando Aspose.Slides
  y a generar archivos de gráficos de presentación rápidamente.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Cómo agregar un gráfico a presentaciones Java con Aspose.Slides
url: /es/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar un gráfico a una presentación usando Aspose.Slides para Java

## Introducción

Crear presentaciones dinámicas que transmitan datos de manera eficaz es esencial en el entorno empresarial acelerado de hoy. Ya sea que estés preparando un informe financiero, una presentación de marketing o una actualización de estado de proyecto, **saber cómo agregar un gráfico** a tus diapositivas puede mejorar drásticamente la participación de la audiencia. En este tutorial aprenderás paso a paso cómo agregar un gráfico de columnas apiladas 3D, configurar sus datos y guardar el archivo final, todo con Aspose.Slides para Java.

### Respuestas rápidas
- **¿Cuál es la biblioteca principal?** Aspose.Slides para Java  
- **¿Qué tipo de gráfico se muestra?** Columna apilada 3D  
- **¿Puedo generar archivos de gráficos de presentación programáticamente?** Sí, usando los métodos de la API mostrados a continuación  
- **¿Qué versión de Java se recomienda?** JDK 16 o posterior  
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose.Slides para uso comercial  

## ¿Qué es “cómo agregar un gráfico” en Aspose.Slides?

Aspose.Slides para Java ofrece un conjunto amplio de objetos que te permiten crear, editar y exportar archivos PowerPoint sin Microsoft Office. Agregar un gráfico es tan simple como crear un objeto `Presentation`, insertar una forma de gráfico y alimentarla con datos a través del libro de trabajo incorporado.

## ¿Por qué agregar un gráfico a presentaciones Java?

- **Impacto visual:** Los gráficos convierten números crudos en visuales comprensibles al instante.  
- **Automatización:** Genera informes al vuelo, ideal para resúmenes por correo electrónico programados o paneles de control.  
- **Consistencia:** Usa el mismo estilo y marca en todas las presentaciones generadas.  
- **Portabilidad:** Exporta a PPTX, PDF o imágenes con una sola llamada de método.

## Requisitos previos

- **Bibliotecas y dependencias:** Aspose.Slides para Java debe estar instalado.  
- **Configuración del entorno:** Trabaja en un entorno Java (se recomienda JDK 16 o posterior).  
- **Base de conocimientos:** Familiaridad con conceptos básicos de programación Java será beneficiosa.

## Configuración de Aspose.Slides para Java

### Instalación

Para integrar Aspose.Slides en tu proyecto, sigue una de las opciones a continuación.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa**: Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia
- **Prueba gratuita:** Comienza con una prueba gratuita para explorar las funciones.  
- **Licencia temporal:** Obtén una licencia temporal para pruebas extendidas.  
- **Compra:** Adquiere una licencia completa para uso comercial.

Una vez instalado, puedes instanciar la clase `Presentation`, que sirve como punto de entrada para todas las operaciones relacionadas con gráficos.

## Guía de implementación

### Cómo agregar un gráfico a una presentación con una columna apilada 3D

#### Visión general
Crear una presentación desde cero es sencillo con Aspose.Slides. En esta sección, agregaremos un gráfico de columnas apiladas 3D a la primera diapositiva de nuestra presentación.

**Pasos:**

1. **Inicializar el objeto Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Explicar los parámetros**  
   - `ChartType.StackedColumn3D`: Especifica el tipo de gráfico.  
   - Posición y tamaño `(0, 0, 500, 500)`: Determina dónde aparece el gráfico en la diapositiva.

### Configurar los datos del gráfico

#### Visión general
Para que tu gráfico sea significativo, configura sus series de datos y categorías. Esta sección muestra cómo agregar puntos de datos específicos a tu gráfico.

**Pasos:**

1. **Acceder al libro de datos del gráfico**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Establecer propiedades Rotation3D para el gráfico

#### Visión general
Mejora el atractivo visual de tu gráfico con propiedades de rotación 3D. Esta personalización te permite ajustar la perspectiva y la profundidad.

**Pasos:**

1. **Configurar rotaciones 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Explicar los parámetros**  
   - `setRightAngleAxes(true)`: Garantiza que los ejes sean perpendiculares.  
   - Valores de rotación: Ajustan el ángulo y la profundidad de la vista 3D.

### Poblar datos de series en el gráfico

#### Visión general
Poblar tu gráfico con puntos de datos es crucial para el análisis. Aquí, añadiremos valores específicos a una serie dentro de nuestro gráfico.

**Pasos:**

1. **Agregar puntos de datos**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Ajustar la superposición de series en el gráfico

#### Visión general
Afinar la apariencia de tu gráfico puede mejorar la legibilidad. Esta sección cubre cómo ajustar la propiedad de superposición para una mejor visualización de datos.

**Pasos:**

1. **Establecer superposición de series**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Guardar la presentación

#### Visión general
Una vez que tu presentación está configurada, guárdala en disco en el formato deseado. Este paso asegura que todos los cambios se conserven.

**Pasos:**

1. **Guardar la presentación**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **El gráfico aparece plano** | No se ha establecido la rotación 3D | Llama a `setRotation3D` con valores X/Y apropiados. |
| **Los datos no se muestran** | Celdas del libro de trabajo no vinculadas | Asegúrate de que `fact.getCell` haga referencia a los índices de fila/columna correctos. |
| **El archivo no se guarda** | Ruta incorrecta o permisos insuficientes | Verifica que `outputFilePath` sea escribible y que la carpeta exista. |

## Preguntas frecuentes

**P: ¿Puedo generar archivos de gráficos de presentación en formatos diferentes a PPTX?**  
R: Sí, Aspose.Slides admite PDF, ODP y formatos de imagen mediante el enumerado `SaveFormat`.

**P: ¿Necesito una licencia para ejecutar el código en desarrollo?**  
R: Una licencia temporal o de evaluación funciona para desarrollo, pero se requiere una licencia completa para implementaciones en producción.

**P: ¿Es posible agregar varios gráficos a la misma diapositiva?**  
R: Absolutamente. Llama a `slide.getShapes().addChart` varias veces con diferentes posiciones o tamaños.

**P: ¿Cómo cambio la paleta de colores del gráfico?**  
R: Usa `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` y establece un `SolidFillColor`.

**P: ¿Puedo vincular el gráfico a una fuente de datos externa como una base de datos?**  
R: Sí. Recupera los datos con JDBC y luego rellena las celdas del libro de trabajo programáticamente antes de guardar.

## Conclusión

Ahora has aprendido **cómo agregar un gráfico** a una presentación Java, configurar sus datos, personalizar la rotación 3D, ajustar la superposición de series y guardar el archivo final. Este conocimiento te permite automatizar la generación de informes, crear una marca coherente y ofrecer presentaciones basadas en datos sin esfuerzo manual. Para una personalización más profunda —como estilizar leyendas, ejes o aplicar temas— explora todas las capacidades en la documentación oficial.

Para obtener funciones avanzadas y opciones de personalización, consulta la [documentación de Aspose.Slides para Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-20  
**Probado con:** Aspose.Slides para Java 25.4 (JDK 16)  
**Autor:** Aspose
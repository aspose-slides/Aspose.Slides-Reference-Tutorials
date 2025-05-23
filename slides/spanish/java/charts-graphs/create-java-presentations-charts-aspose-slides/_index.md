---
"date": "2025-04-17"
"description": "Aprenda a crear y configurar presentaciones dinámicas con gráficos en Java usando Aspose.Slides. Domine la adición, personalización y guardado de presentaciones de forma eficaz."
"title": "Cree presentaciones Java con gráficos usando Aspose.Slides para Java"
"url": "/es/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear y configurar una presentación con un gráfico usando Aspose.Slides para Java

## Introducción

Crear presentaciones dinámicas que transmitan datos eficazmente es esencial en el dinámico entorno empresarial actual. Ya sea que esté preparando un informe financiero o mostrando las métricas de un proyecto, agregar gráficos puede mejorar significativamente el impacto de su presentación. Este tutorial le guía en la creación y configuración de una presentación con un gráfico de columnas apiladas en 3D utilizando Aspose.Slides para Java, una potente biblioteca diseñada para gestionar presentaciones programáticamente.

**Lo que aprenderás:**
- Cómo crear una nueva presentación
- Agregar y configurar gráficos en diapositivas
- Personalizar los datos y la apariencia del gráfico
- Guarde su presentación de manera efectiva

¿Listo para dominar la creación de presentaciones visualmente atractivas con Java? ¡Comencemos!

## Prerrequisitos

Antes de sumergirse en el tutorial, asegúrese de haber cubierto estos requisitos previos:

- **Bibliotecas y dependencias**:Se debe instalar Aspose.Slides para Java.
- **Configuración del entorno**:Trabajar en un entorno Java (se recomienda JDK 16 o posterior).
- **Base de conocimientos**Será beneficioso estar familiarizado con los conceptos básicos de programación Java.

## Configuración de Aspose.Slides para Java

### Instalación

Para integrar Aspose.Slides en su proyecto, siga estos pasos:

**Experto**

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

**Descarga directa**:Alternativamente, descargue la última versión desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Adquisición de licencias
- **Prueba gratuita**Comience con una prueba gratuita para explorar las funciones.
- **Licencia temporal**:Obtener una licencia temporal para pruebas extendidas.
- **Compra**:Adquiera una licencia completa para uso comercial.

Una vez instalada, inicialice la biblioteca en su entorno Java creando una instancia de la misma. `Presentation` Clase. Esto sienta las bases para agregar gráficos y otros elementos a su presentación.

## Guía de implementación

### Crear y configurar una presentación con un gráfico

#### Descripción general
Crear una presentación desde cero es muy sencillo con Aspose.Slides. En esta sección, añadiremos un gráfico de columnas apiladas en 3D a la primera diapositiva de nuestra presentación.

**Pasos:**

1. **Inicializar objeto de presentación**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Inicializar un nuevo objeto de presentación
           Presentation presentation = new Presentation();
           
           // Acceda a la primera diapositiva de la presentación
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Agregue un gráfico de columnas apiladas en 3D a la diapositiva en la posición (0,0)
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

2. **Explicar los parámetros**:
   - `ChartType.StackedColumn3D`: Especifica el tipo de gráfico.
   - Posición y tamaño `(0, 0, 500, 500)`:Determina dónde aparece el gráfico en la diapositiva.

### Configurar datos del gráfico

#### Descripción general
Para que su gráfico sea significativo, configure sus series de datos y categorías. Esta sección muestra cómo agregar puntos de datos específicos a su gráfico.

**Pasos:**

1. **Libro de trabajo de datos de Access Chart**

   ```java
   public static void configureChartData(IChart chart) {
       // Establecer el índice de la hoja de cálculo que contiene los datos del gráfico
       int defaultWorksheetIndex = 0;
       
       // Acceda al libro de datos del gráfico
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Añade dos series con nombres
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Añadir tres categorías
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Establecer propiedades de Rotation3D para el gráfico

#### Descripción general
Mejore el aspecto visual de su gráfico con las propiedades de rotación 3D. Esta personalización le permite ajustar la perspectiva y la profundidad.

**Pasos:**

1. **Configurar rotaciones 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Habilite ejes de ángulo recto y configure rotaciones en direcciones X, Y y porcentaje de profundidad
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Explicar los parámetros**:
   - `setRightAngleAxes(true)`:Asegura que los ejes sean perpendiculares.
   - Valores de rotación: ajusta el ángulo y la profundidad de la vista 3D.

### Rellenar datos de series en el gráfico

#### Descripción general
Completar el gráfico con puntos de datos es crucial para el análisis. Aquí, añadiremos valores específicos a una serie dentro del gráfico.

**Pasos:**

1. **Agregar puntos de datos**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Acceda a la segunda serie de gráficos
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Agregar puntos de datos para series de barras con valores específicos
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

#### Descripción general
Ajustar la apariencia de su gráfico puede mejorar la legibilidad. Esta sección explica cómo ajustar la propiedad de superposición para una mejor visualización de los datos.

**Pasos:**

1. **Superposición de series de conjuntos**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Obtenga la segunda serie del gráfico y establezca su superposición en 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Guardar presentación

#### Descripción general
Una vez configurada la presentación, guárdela en el disco en el formato deseado. Este paso garantiza que se conserven todos los cambios.

**Pasos:**

1. **Guardar la presentación**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Guardar la presentación modificada en un archivo
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Conclusión

Ya aprendió a crear y configurar presentaciones con gráficos usando Aspose.Slides para Java. Esta guía abarcó la inicialización de una presentación, la adición de un gráfico de columnas apiladas en 3D, la configuración de series y categorías de datos, la configuración de propiedades de rotación, el llenado de datos de series, el ajuste de la superposición de series y el guardado de la presentación final.

Para obtener funciones más avanzadas y opciones de personalización, consulte la [Documentación de Aspose.Slides para Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
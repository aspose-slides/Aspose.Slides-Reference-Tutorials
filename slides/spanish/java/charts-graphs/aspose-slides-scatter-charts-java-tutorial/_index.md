---
"date": "2025-04-17"
"description": "Aprenda a crear gráficos de dispersión dinámicos con Aspose.Slides para Java. Mejore sus presentaciones con funciones de gráficos personalizables."
"title": "Cree y personalice gráficos de dispersión en Java con Aspose.Slides"
"url": "/es/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cree y personalice gráficos de dispersión en Java con Aspose.Slides

Mejore sus presentaciones añadiendo gráficos de dispersión dinámicos con Java y Aspose.Slides. Este completo tutorial le guiará en la configuración de directorios, la inicialización de presentaciones, la creación de gráficos de dispersión, la gestión de datos de gráficos, la personalización de tipos de series y marcadores, y el guardado de su trabajo, todo ello fácilmente.

**Lo que aprenderás:**
- Configuración de un directorio para almacenar archivos de presentación
- Inicialización y manipulación de presentaciones con Aspose.Slides
- Creación de gráficos de dispersión en diapositivas
- Administrar y agregar datos a series de gráficos
- Personalización de tipos de series de gráficos y marcadores
- Guardar su presentación con modificaciones

Comencemos por asegurarnos de que tienes los requisitos previos necesarios.

## Prerrequisitos

Para seguir este tutorial, asegúrese de tener:
- **Aspose.Slides para Java**Se requiere la versión 25.4 o posterior.
- **Kit de desarrollo de Java (JDK)**Se necesita JDK 8 o superior.
- Conocimientos básicos de programación Java y familiaridad con las herramientas de compilación Maven o Gradle.

## Configuración de Aspose.Slides para Java

Antes de comenzar a codificar, integre Aspose.Slides en su proyecto utilizando uno de los siguientes métodos:

### Experto
Incluya esta dependencia en su `pom.xml` archivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Añade esta línea a tu `build.gradle` archivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, descargue la última versión de Aspose.Slides para Java desde [Lanzamientos de Aspose](https://releases.aspose.com/slides/java/).

#### Adquisición de licencias
- **Prueba gratuita**Comience con una prueba gratuita de 30 días para explorar las funciones.
- **Licencia temporal**:Obtener una licencia temporal para pruebas extendidas.
- **Compra**:Compre una licencia para obtener acceso y soporte completo.

Ahora, inicialice Aspose.Slides en su aplicación Java agregando las importaciones necesarias como se muestra a continuación.

## Guía de implementación

### Configuración del directorio
Primero, asegúrese de que nuestro directorio exista para almacenar los archivos de presentación. Esto evita errores al guardar los archivos.

#### Crear el directorio si no existe
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Crear el directorio
    new File(dataDir).mkdirs();
}
```
Este fragmento busca un directorio específico y lo crea si no existe. Utiliza `File.exists()` para verificar la presencia y `File.mkdirs()` para crear directorios.

### Inicialización de la presentación

A continuación, inicialice el objeto de presentación donde agregará el gráfico de dispersión.

#### Inicializar su presentación
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Aquí, `new Presentation()` Crea una presentación en blanco. Accedemos a la primera diapositiva para trabajar con ella directamente.

### Creación de gráficos
El siguiente paso es crear un gráfico de dispersión en nuestra diapositiva inicializada.

#### Agregar gráfico de dispersión a la diapositiva
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Este fragmento de código añade un gráfico de dispersión con líneas suaves a la primera diapositiva. Los parámetros definen la posición y el tamaño del gráfico.

### Gestión de datos de gráficos
Ahora administraremos los datos de nuestro gráfico borrando cualquier serie existente y agregando nuevas.

#### Administrar series de gráficos
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Añadiendo nuevas series al gráfico
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Esta sección borra los datos existentes y agrega dos nuevas series a nuestro gráfico de dispersión.

### Adición de puntos de datos para series de dispersión
Para visualizar nuestros datos, agregamos puntos a cada serie en el gráfico de dispersión.

#### Agregar puntos de datos
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Nosotros usamos `addDataPointForScatterSeries()` Para añadir puntos de datos a nuestra primera serie. Los parámetros definen los valores X e Y.

### Modificación del tipo de serie y del marcador
Personalice la apariencia de su gráfico modificando el tipo y el estilo de los marcadores en cada serie.

#### Serie personalizada
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modificación de la segunda serie
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Estos cambios ajustan el tipo de serie para usar líneas rectas y marcadores. También configuramos el tamaño y el símbolo del marcador para una mejor distinción visual.

### Presentación guardada
Por último, guarde su presentación con todas las modificaciones realizadas.

#### Guarde su presentación
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Usar `SaveFormat.Pptx` Para especificar el formato de PowerPoint para guardar el archivo. Este paso es crucial para conservar todos los cambios.

## Aplicaciones prácticas
A continuación se presentan algunos casos de uso del mundo real:
1. **Análisis financiero**: Utilice gráficos de dispersión para mostrar las tendencias de las acciones a lo largo del tiempo.
2. **Investigación científica**:Representa puntos de datos experimentales para el análisis.
3. **Gestión de proyectos**:Visualice la asignación de recursos y las métricas de progreso.

La integración de Aspose.Slides en su sistema le permite automatizar la generación de informes, mejorando la productividad y la precisión.

## Consideraciones de rendimiento
Para un rendimiento óptimo:
- Administre el uso de la memoria eliminando presentaciones después de guardarlas.
- Utilice estructuras de datos eficientes para conjuntos de datos grandes.
- Minimizar las operaciones que consumen muchos recursos dentro de los bucles.

Las mejores prácticas garantizan una ejecución fluida incluso con manipulaciones de gráficos complejas.

## Conclusión
En este tutorial, aprendiste a configurar directorios, inicializar presentaciones de Aspose.Slides, crear y personalizar gráficos de dispersión, administrar datos de series, modificar marcadores y guardar tu trabajo. Para explorar más a fondo las funciones de Aspose.Slides, considera profundizar en funciones más avanzadas como la animación y las transiciones de diapositivas.

**Próximos pasos**:Experimente con diferentes tipos de gráficos o integre estas técnicas en un proyecto Java más grande.

## Preguntas frecuentes

### ¿Cómo cambio el color de los marcadores?
Para cambiar el color del marcador, utilice `series.getMarker().getFillFormat().setFillColor(ColorObject)`, dónde `ColorObject` Es tu color deseado.

### ¿Puedo agregar más de dos series a un gráfico de dispersión?
Sí, puede agregar tantas series como necesite repitiendo el proceso de agregar nuevas series y puntos de datos.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
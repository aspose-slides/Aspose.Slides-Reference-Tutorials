---
"date": "2025-04-17"
"description": "Aprenda a crear gráficos de líneas con marcadores en Java usando Aspose.Slides. Este tutorial explica cómo crear gráficos, añadir series y guardar presentaciones eficazmente."
"title": "Cree gráficos de líneas con marcadores predeterminados usando Aspose.Slides para Java"
"url": "/es/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cree gráficos de líneas con marcadores predeterminados usando Aspose.Slides para Java
## Introducción
Crear gráficos visualmente atractivos e informativos es esencial para presentaciones, informes y paneles. Automatizar este proceso en el desarrollo de software ahorra tiempo y garantiza la coherencia entre los documentos. Este tutorial muestra cómo crear gráficos de líneas con marcadores usando Aspose.Slides para Java.
**Aspose.Slides para Java** Es una potente biblioteca que permite a los desarrolladores manipular presentaciones de PowerPoint mediante programación sin necesidad de tener instalado Microsoft Office. Simplifica tareas como la creación, edición y exportación de diapositivas, lo que la convierte en una herramienta esencial para la generación automatizada de documentos.
**Lo que aprenderás:**
- Cómo inicializar Aspose.Slides para Java
- Pasos para crear un gráfico de líneas con marcadores
- Agregar series y categorías a los gráficos
- Configuración de leyendas de gráficos
- Guardando la presentación
¿Listo para empezar? ¡Asegúrate de tener todo listo!
## Prerrequisitos
Antes de comenzar, asegúrese de que su entorno de desarrollo esté listo:
1. **Bibliotecas y dependencias:**
   - Biblioteca Aspose.Slides para Java (versión 25.4 recomendada)
   - Java Development Kit (JDK) versión 16 o superior
2. **Configuración del entorno:**
   - Su IDE debe ser compatible con las herramientas de compilación Maven o Gradle.
   - Asegúrese de tener un archivo de licencia válido si es necesario.
3. **Requisitos de conocimiento:**
   - Comprensión básica de la programación Java
   - Familiaridad con la creación de proyectos utilizando Maven o Gradle
¡Con esto en su lugar, configuremos Aspose.Slides para su proyecto!
## Configuración de Aspose.Slides para Java
Para usar Aspose.Slides para Java, debes incluirlo como dependencia en tu proyecto. La configuración variará ligeramente según uses Maven o Gradle.
### Experto
Agregue la siguiente dependencia a su `pom.xml` archivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Incluye esto en tu `build.gradle` archivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Descarga directa
Alternativamente, puede descargar la última versión desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).
**Pasos para la adquisición de la licencia:**
- Para una prueba gratuita, visite el [página de prueba gratuita](https://releases.aspose.com/slides/java/).
- Para obtener una licencia temporal, navegue hasta la [página de licencia temporal](https://purchase.aspose.com/temporary-license/).
- Compre una licencia completa a través de su [portal de compras](https://purchase.aspose.com/buy).
**Inicialización básica:**
A continuación se explica cómo puede inicializar Aspose.Slides en su aplicación Java:
```java
import com.aspose.slides.Presentation;
// Inicializar un nuevo objeto de presentación
Presentation pres = new Presentation();
```
¡Ahora, pasemos a crear gráficos!
## Guía de implementación
### Característica 1: Creación de gráficos con marcadores predeterminados
Esta sección muestra cómo crear un gráfico de líneas con marcadores. Esta función es esencial para visualizar las tendencias de los datos eficazmente.
#### Agregar un gráfico de líneas
Para agregar un gráfico de líneas con marcadores:
```java
import com.aspose.slides.*;
// Acceda a la primera diapositiva
ISlide slide = pres.getSlides().get_Item(0);
// Agregue un gráfico de líneas con marcadores a la diapositiva en la posición (10, 10) con tamaño (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### Series y categorías de compensación
Para empezar de nuevo:
```java
// Limpiar las series y categorías existentes para asegurar una pizarra en blanco
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtenga el libro de trabajo de datos del gráfico para una mayor manipulación
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### Función 2: Agregar series y categorías
Agregar series y categorías es crucial para completar sus gráficos con datos significativos.
#### Creando una nueva serie
Para agregar una nueva serie llamada "Serie 1":
```java
// Añadir una nueva serie al gráfico
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Acceda a la primera serie para la población de datos
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### Población de categorías y puntos de datos
Para agregar categorías y puntos de datos correspondientes:
```java
// Agregar nombres de categorías y sus respectivos puntos de datos
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Manejo elegante de puntos de datos nulos
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### Característica 3: Agregar una segunda serie y completar puntos de datos
Agregar series adicionales proporciona más profundidad a sus gráficos.
#### Creación y llenado de una segunda serie
Para agregar "Serie 2":
```java
// Añade otra serie llamada 'Serie 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Acceda a la segunda serie para la población de datos
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Agregar puntos de datos para la 'Serie 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### Característica 4: Configuración de la leyenda del gráfico
La configuración de la leyenda mejora la legibilidad del gráfico.
#### Ajuste de la configuración de la leyenda
Para configurar:
```java
// Habilite la leyenda y configúrela para que no se superponga a los puntos de datos
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### Función 5: Guardar la presentación
Una vez que su gráfico esté listo, guarde la presentación en un archivo.
```java
try {
    // Guardar la presentación modificada en un directorio específico
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## Aplicaciones prácticas
1. **Informes comerciales:**
   - Utilice gráficos en los informes financieros para representar tendencias a lo largo del tiempo.
2. **Análisis de datos:**
   - Visualice patrones de datos y correlaciones durante las fases de análisis.
3. **Materiales educativos:**
   - Cree diapositivas informativas para conferencias o presentaciones académicas.
4. **Gestión de proyectos:**
   - Mejore los cronogramas del proyecto con elementos de gráficos visuales.
5. **Presentaciones de marketing:**
   - Muestre las tendencias de ventas y los resultados de campañas de manera eficaz utilizando gráficos.
## Conclusión
Has aprendido a crear gráficos de líneas con marcadores en Java usando Aspose.Slides, a añadir series y categorías, a configurar leyendas y a guardar presentaciones. Estas habilidades son valiosas para crear contenido visual dinámico en diversas aplicaciones profesionales.
Para explorar más sobre las características de Aspose.Slides o buscar apoyo de la comunidad, visite su [documentación oficial](https://docs.aspose.com/slides/java/) o únete a foros como Stack Overflow.
¡Feliz codificación!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
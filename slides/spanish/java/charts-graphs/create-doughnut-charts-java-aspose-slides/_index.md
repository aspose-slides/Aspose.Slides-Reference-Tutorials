---
"date": "2025-04-17"
"description": "Aprenda a crear gráficos de anillos impactantes en Java con Aspose.Slides. Esta guía completa abarca la inicialización, la configuración de datos y el guardado de presentaciones."
"title": "Cree gráficos de anillos en Java con Aspose.Slides&#58; una guía completa"
"url": "/es/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráficos de anillos en Java con Aspose.Slides: guía paso a paso

## Introducción

En el entorno actual, basado en datos, visualizar la información eficazmente es clave para mejorar la comprensión y la participación. Si bien crear gráficos profesionales mediante programación puede parecer un desafío, especialmente con Java, esta guía le guiará en el uso de Aspose.Slides para Java para crear gráficos de anillos sin esfuerzo.

Al seguir estos pasos, los desarrolladores adquirirán experiencia práctica en la manipulación de diapositivas de presentaciones y la integración perfecta de la visualización de datos.

**Conclusiones clave:**
- Inicializar un objeto de presentación usando Aspose.Slides Java.
- Configurar datos de gráficos y administrar series o categorías existentes.
- Agregue y personalice series y categorías para sus gráficos.
- Formatear y mostrar puntos de datos de manera eficaz.
- Guarde su presentación en varios formatos con facilidad.

Antes de sumergirse en la implementación, asegúrese de tener todo lo necesario para comenzar.

## Prerrequisitos

Para seguir este tutorial, asegúrate de tener:

- **Bibliotecas requeridas:**
  - Aspose.Slides para Java versión 25.4 o posterior.
  
- **Configuración del entorno:**
  - JDK 16 o superior instalado en su sistema.
  - Un IDE como IntelliJ IDEA, Eclipse o NetBeans.

- **Requisitos de conocimiento:**
  - Comprensión básica de los conceptos de programación Java.
  - Familiaridad con la gestión de dependencias en proyectos Maven o Gradle.

## Configuración de Aspose.Slides para Java

Para integrar Aspose.Slides en su proyecto, siga estos pasos según su herramienta de compilación:

**Configuración de Maven:**
Agregue la siguiente dependencia a su `pom.xml` archivo:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Configuración de Gradle:**
Incluya lo siguiente en su `build.gradle` archivo:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa:**
Alternativamente, descargue la última versión directamente desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Adquisición de una licencia

Para utilizar Aspose.Slides sin limitaciones de evaluación:
- **Prueba gratuita:** Comience con una licencia temporal para explorar todas las funciones.
- **Licencia temporal:** Obtenga uno a través de [Sitio web de Aspose](https://purchase.aspose.com/temporary-license/).
- **Compra:** Considere comprar para uso continuo.

Aplique su licencia en su aplicación Java usando:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Guía de implementación

### Inicializando la presentación y el gráfico

#### Descripción general
Comience inicializando un objeto de presentación y agregando un gráfico de anillos a la primera diapositiva.

**Paso 1: Inicializar la presentación**
Cargue un archivo PPTX existente o cree uno nuevo:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Paso 2: Agregar gráfico de anillos**
Cree un gráfico en la primera diapositiva en las coordenadas especificadas:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Configuración del libro de datos del gráfico y borrado de series/categorías existentes

#### Descripción general
Configure el libro de trabajo de datos del gráfico y elimine cualquier serie o categoría preexistente.

**Paso 1: Acceder al libro de trabajo de datos del gráfico**
Recupere el libro de trabajo vinculado con su gráfico:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Paso 2: Borrar series y categorías existentes**
Asegúrese de que no haya puntos de datos residuales:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Agregar series al gráfico

#### Descripción general
Llene su gráfico con múltiples series, cada una personalizada en apariencia y comportamiento.

**Paso 1: Agregar series iterativamente**
Recorrer los índices para agregar series:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Personaliza la serie
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Agregar categorías y puntos de datos al gráfico

#### Descripción general
Configure categorías y agregue puntos de datos con formato específico para las etiquetas.

**Paso 1: Agregar categorías**
Recorrer los índices de cada categoría:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Paso 2: Agregar puntos de datos a cada serie**
Iterar a través de cada serie para la categoría actual:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Configuración del formato de los puntos de datos
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Formato de etiqueta para la última serie
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Ajustar las opciones de visualización
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Ajustar la posición de la etiqueta
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Guardar la presentación

#### Descripción general
Una vez que haya configurado su gráfico, guarde la presentación en un directorio específico.

**Paso 1: Guardar la presentación**
Utilice el `save` método para escribir cambios:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Conclusión

Ya aprendiste a crear y personalizar gráficos de anillos en Java con Aspose.Slides. Estos pasos te brindan la base para integrar visualizaciones de datos sofisticadas en tus presentaciones.

**Próximos pasos:**
- Experimente con los diferentes tipos de gráficos disponibles en Aspose.Slides.
- Explore opciones de personalización adicionales como colores, fuentes y estilos para satisfacer sus necesidades de marca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-01-19'
description: Aprende cómo agregar una leyenda a un gráfico de PowerPoint y crear gráficos
  de rosquilla dinámicos en PowerPoint usando Aspose.Slides para Java. Guía paso a
  paso con ejemplos de código.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Agregar leyenda al gráfico de PowerPoint – Crear gráficos de rosquilla dinámicos
  con Aspose.Slides para Java
url: /es/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráficos de dona dinámicos en PowerPoint usando Aspose.Slides para Java

## Introducción
Añadir una leyenda a un gráfico de PowerPoint puede convertir una visualización sencilla en una obra maestra narrativa. En este tutorial aprenderás **cómo añadir elementos de leyenda a un gráfico de PowerPoint** mientras construyes un gráfico de dona dinámico con Aspose.Slides para final funcional datos pulidas.

**Lo que aprenderás:**
- Cómo inicializar una presentación usando Aspose.Slides para Java  
- Una guía paso a paso para añadir un gráfico de dona a tus diapositivas  
 de datos, **add data labels chart**, y personalización de propiedades de la leyenda  
- Guardar la presentación modificada con alta fidelidad  

Exploremos cómo puedes aprovechar estas funciones para mejorar tus presentaciones. Antes de comenzar, asegúrate de estar cómodo con la sintaxis básica de Java.

## Respuestas rápidas
- **¿Cuál es la biblioteca principal?** Aspose.Slides para Java  
- **¿Puedo añadir una leyenda a un gráfico de dona?** Sí – usa la leyenda del gráfico y la configuración de series  
- **¿Necesito una licencia?** Una versión de prueba funciona para desarrollo; se requiere una licencia comercial para producción  
- **¿Qué versión de Java es compatible?** El ejemplo usa JDK 16 (clasificador jdk16)  
- **¿Cuántas series de datos puedo crear?** El ejemplo recorre hasta 15 series, pero puedes ajustarlo según necesites  

## ¿Qué es un gráfico de dona y por qué añadir una leyenda?
Un gráfico de dona es una variante del gráfico de pastel con un centro hueco, ideal para mostrar relaciones parte‑todo mientras deja espacio para información adicional. Añadir una leyenda ayuda a los espectadores a mapear rápidamente los colores a las categorías, mejorando la legibilidad—especialmente cuando tienes muchas series.

## Requisitos previos
- Conocimientos básicos de programación en Java.  
- Un IDE como IntelliJ IDEA o Eclipse.  
- Maven o Gradle para la gestión de dependencias.  
- Una licencia válida deides para Java (prElija el formato de dependencia que coincida con su herramienta de compilación.

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

Si prefieres descargar el JAR directamente, visita la página de [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Adquisición de licencia
Puedes comenzar con una prueba gratuita para explorar las funciones de Aspose.Slides. Para uso prolongado, compra una licencia o solicita una temporal en el [sitio web de Aspose](https://purchase.aspose.com/temporary-license/). Sigue las instrucciones proporcionadas para configurar tu entorno e inicializar Aspose.Slides en tu aplicación.

## Guía de implementación
A continuación tienes un recorrido completo. Cada bloque de código se explica antes de aparecer, para que sepas exactamente qué está ocurriendo.

### Inicializar presentación
Primero, carga un PPTX existente o crea uno nuevo. Este paso configura el objeto de presentación que contendrá el gráfico.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Añadir gráfico de dona
Ahora añadimos un gráfico de dona a la diapositiva. `ChartType.Doughnut` crea la visualización adecuada, y también desactivamos la leyenda predeterminada porque la personalizaremos más adelante.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Configurar puntos de datos y etiquetas
A continuación poblamos las categorías, añadimos puntos de datos para cada serie y **add data labels chart**. La personalización de etiquetas también muestra cómo posicionar una descripción tipo leyenda junto a la última serie en cada categoría.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Guardar la presentación
Finalmente, persiste los cambios en un nuevo archivo PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## ¿Por qué añadir una leyenda al gráfico de PowerPoint en un gráfico de dona?
- **Claridad:** Las leyendas asignan colores a categorías sin saturar el área del gráfico.  
- **Escalabilidad:** Cuando tienes muchas series (como en el bucle anterior), una leyenda mantiene la diapositiva legible.  
- **Aspecto profesional:** Una leyenda pulida combinada con etiquetas de datos personalizadas brinda una presentación de nivel corporativo.

## Aplicaciones prácticas
Los gráficos de dona con leyendas son perfectos para:
- **Informes financieros:** Mostrar la desagregación de gastos junto a una leyenda para cada departamento.  
- **Análisis de mercado:** Visualizar la cuota de mercado mientras la leyenda identifica a cada competidor.  
- **Resultados de encuestas:** Presentar respuestas de opción múlt de series serie datos grandes.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| La leyenda no es visible | `chart.setLegend(false)` la desactiva. | Establece `chart.setLegend(true)` y personaliza la posición. |
| Las etiquetas se superponen | La ubicación predeterminada de las etiquetas puede chocar con el agujero de la dona. | Ajusta `lbl.setX()` / `lbl.setY()` o incrementa `DoughnutHoleSize`. |
| El color no se aplica | El tipo de relleno no está configurado a `Solid`. | Asegúrate de que `dataPoint.getFormat().getFill().setFillType(FillType.Solid)`. |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Slides para Java en aplicaciones comerciales?**  
A: Sí, pero necesitas una licencia comercial válida. Hay una prueba gratuita disponible para evaluación.

**Q: ¿Cómo habilito la leyenda después de haberla desactivado?**  
A: Llama a `chart.setLegend(true);` y opcionalmente establece su posición con `chart.getLegend().setPosition(LegendPosition.Right);`.

**Q `chart.getLegend workbook dentro gráfico además de la dona?**  
A: Soporta una gama completa de tipos de gráficos—pie, bar, line, scatter y más. Simplemente reemplaza `ChartType.Doughnut` por el enum deseado.

---

**Última actualización:** 2026-01-19  
**Probado con:** Aspose.Slides 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
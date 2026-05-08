---
date: '2026-02-17'
description: Aprende a crear un gráfico de rosquilla en PowerPoint usando Aspose.Slides
  para Java y a agregar puntos de datos al gráfico de forma programática. Sigue pasos
  sencillos y ejemplos de código.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Crear gráfico de rosquilla en PowerPoint con Aspose.Slides para Java
url: /es/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear gráfico de rosquilla en PowerPoint con Aspose.Slides for Java

## Introducción
Crear presentaciones atractivas a menudo requiere más que solo texto e imágenes; los gráficos pueden mejorar significativamente la narrativa al visualizar los datos de manera efectiva. Sin embargo, muchos desarrolladores tienen dificultades para integrar funciones de gráficos dinámicos en archivos PowerPoint de forma programática. Este tutorial muestra cómo **crear un gráfico de rosquilla en PowerPoint** usando Aspose.Slides for Java, una herramienta poderosa que combina flexibilidad y facilidad de uso.

**Lo que aprenderás:**
- Cómo inicializar una presentación usando Aspose.Slides for Java
- Una guía paso a paso para agregar un gráfico de rosquilla a tus diapositivas
- Configurar puntos de datos y personalizar las propiedades de las etiquetas
- Guardar la presentación modificada con alta fidelidad

Exploremos cómo puedes aprovechar estas funciones para mejorar tus presentaciones. Antes de comenzar, asegúrate de estar familiarizado con los conceptos básicos de programación en Java.

## Respuestas rápidas
- **¿Qué biblioteca crea gráficos de rosquilla en PowerPoint?** Aspose.Slides for Java
- **¿Puedo agregar puntos de datos al gráfico programáticamente?** Sí, usando la API de gráficos
- **¿Necesito una licencia para producción?** Se requiere una licencia válida de Aspose.Slides
- **¿Qué versiones de Java son compatibles?** Java 8 y posteriores (se muestra el clasificador JDK 16)
- **¿Cuántas series puedo agregar?** El ejemplo agrega hasta 15 series, pero puedes ajustarlo según sea necesario

## ¿Qué es un gráfico de rosquilla en PowerPoint?
Un gráfico de rosquilla es una variante del gráfico circular con un centro hueco, lo que permite mostrar múltiples series de datos de forma compacta y visualmente atractiva. Es ideal para mostrar relaciones parte‑todo manteniendo un diseño limpio.

## ¿Por qué usar Aspose.Slides for Java para crear gráficos de rosquilla?
- **Control total** sobre la apariencia del gráfico, los datos y el diseño sin abrir PowerPoint
- **Sin interoperabilidad COM** – funciona en cualquier plataforma que soporte Java
- **Alto rendimiento** para generar presentaciones extensas o integrarse con servicios web
- **Personalización avanzada** como explosión, tamaño del agujero, ángulos de porción y formato de etiquetas

## Requisitos previos
- Conocimientos básicos de programación en Java.
- Un IDE como IntelliJ IDEA o Eclipse.
- Maven o Gradle para la gestión de dependencias.
- Una licencia válida de Aspose.Slides for Java (prueba gratuita disponible).

## Configuración de Aspose.Slides for Java
Elige el gestor de dependencias que se ajuste a tu proyecto.

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

Si prefieres descargar directamente, visita la página de [lanzamientos de Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Obtención de la licencia
Puedes comenzar con una prueba gratuita para explorar las funciones de Aspose.Slides. Para uso prolongado, compra una licencia o solicita una temporal en el [sitio web de Aspose](https://purchase.aspose.com/temporary-license/). Sigue las instrucciones proporcionadas para configurar tu entorno e inicializar Aspose.Slides en tu aplicación.

## Cómo crear un gráfico de rosquilla en PowerPoint usando Aspose.Slides for Java
A continuación se muestra una guía completa paso a paso. Cada bloque de código se explica justo antes, para que sepas exactamente lo que está sucediendo.

### Paso 1: Inicializar la presentación
Primero, carga un PPTX existente o crea uno nuevo. Esto prepara la colección de diapositivas para modificaciones posteriores.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Paso 2: Agregar un gráfico de rosquilla a la diapositiva
Agregamos la forma del gráfico, eliminamos cualquier serie/categoría predeterminada y establecemos propiedades visuales básicas.

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

### Paso 3: Agregar puntos de datos al gráfico y personalizar etiquetas
Aquí poblamos las categorías, agregamos puntos de datos para cada serie y afinamos la apariencia de las etiquetas. Aquí es donde entra en juego la palabra clave **add chart data points**.

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

### Paso 4: Guardar la presentación actualizada
Finalmente, persiste los cambios en un nuevo archivo PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Aplicaciones prácticas
- **Informes financieros:** Visualizar asignaciones presupuestarias o desglose de gastos.
- **Análisis de mercado:** Mostrar la distribución de la cuota de mercado entre competidores.
- **Resultados de encuestas:** Presentar datos de encuestas categóricos de forma compacta.
- **Generación de paneles:** Combinar con consultas a bases de datos para generar diapositivas que se actualizan en tiempo real.

## Consideraciones de rendimiento
- **Liberar recursos**: Llama a `pres.dispose()` cuando termines para liberar la memoria nativa.
- **Limitar la cantidad de gráficos**: Añadir cientos de gráficos puede aumentar el uso de memoria; procesa por lotes si es necesario.
- **Usar streaming**: Para conjuntos de datos masivos, llena el libro de trabajo directamente desde flujos en lugar de matrices en memoria.

## Problemas comunes y soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **El gráfico aparece en blanco** | Celdas de datos no pobladas correctamente | Verifica que `workBook.getCell(...)` haga referencia a los índices de fila/columna correctos. |
| **Las etiquetas se superponen** | Demasiadas categorías en un espacio limitado | Incrementa `DoughnutHoleSize` o ajusta `FirstSliceAngle`. |
| **OutOfMemoryError** | Presentaciones grandes sin liberar recursos | Llama a `pres.dispose()` después de guardar y considera aumentar el tamaño del heap de la JVM. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Slides for Java en aplicaciones comerciales?**  
R: Sí, pero necesitas una licencia comercial válida. Hay una prueba gratuita disponible para evaluación.

**P: ¿Cómo agrego más de 15 series?**  
R: Incrementa el límite del bucle en el paso “Add Doughnut Chart” y asegura que tu libro de datos tenga suficientes filas.

**P: ¿Es posible cambiar el tamaño del agujero de la rosquilla después de crearla?**  
R: Sí, llama a `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` en cualquier momento antes de guardar.

**P: ¿Puedo exportar el gráfico como una imagen en lugar de un PPTX?**  
R: Por supuesto. Usa `chart.getImage()` y guarda el `java.awt.image.BufferedImage` devuelto en el formato que prefieras.

**P: ¿Aspose.Slides admite gráficos animados?**  
R: La animación se puede agregar mediante la API `ISlide.getTimeline()`, aunque está fuera del alcance de este tutorial.

## Conclusión
Ahora tienes un método completo y listo para producción para **crear archivos de PowerPoint con gráficos de rosquilla** con Aspose.Slides for Java, incluyendo cómo **agregar puntos de datos al gráfico**, personalizar etiquetas y manejar consideraciones de rendimiento. Experimenta con diferentes colores, fuentes de datos y tipos de gráficos para que tus presentaciones realmente destaquen.

---

**Última actualización:** 2026-02-17  
**Probado con:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
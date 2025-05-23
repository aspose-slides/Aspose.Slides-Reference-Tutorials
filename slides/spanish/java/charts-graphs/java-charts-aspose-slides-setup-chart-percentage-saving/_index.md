---
"date": "2025-04-17"
"description": "Aprenda a crear, personalizar y guardar gráficos con etiquetas de porcentaje en presentaciones Java con Aspose.Slides. ¡Mejore sus habilidades de presentación hoy mismo!"
"title": "Cree y personalice gráficos en presentaciones Java con Aspose.Slides"
"url": "/es/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cree y personalice gráficos en presentaciones Java con Aspose.Slides

## Introducción
Crear presentaciones atractivas a menudo implica más que solo texto; requiere gráficos dinámicos que transmitan la información eficazmente. Si busca mejorar sus presentaciones basadas en Java con funciones de gráficos sofisticadas usando Aspose.Slides, este tutorial es para usted. Le guiaremos en la creación de una presentación, la adición y configuración de gráficos, el cálculo de totales, la visualización de etiquetas de porcentaje y el guardado de su trabajo, todo en tan solo unos sencillos pasos.

**Lo que aprenderás:**
- Cómo crear y personalizar presentaciones con gráficos usando Aspose.Slides para Java
- Cálculo de totales de categorías en gráficos
- Visualización de datos como etiquetas de porcentaje en gráficos
- Guardar presentaciones con funciones de gráficos mejoradas

Analicemos en profundidad los requisitos previos que necesitas antes de comenzar.

## Prerrequisitos
Para seguir este tutorial, asegúrese de tener lo siguiente:

- **Kit de desarrollo de Java (JDK)**:Versión 8 o superior.
- **IDE**:Como IntelliJ IDEA, Eclipse o cualquier IDE compatible con Java.
- **Biblioteca Aspose.Slides para Java**:Esto es crucial para gestionar las funciones de presentación.

### Bibliotecas y versiones requeridas
Necesitarás Aspose.Slides para Java. Aquí te explicamos cómo incluirlo en tu proyecto:

**Experto:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, puede descargar directamente la última versión desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Configuración del entorno
Asegúrese de que su entorno de desarrollo esté configurado para usar JDK 8 o posterior y que su IDE esté configurado para administrar dependencias usando Maven o Gradle.

**Adquisición de licencia:**
- **Prueba gratuita**:Acceda a funciones básicas para fines de prueba.
- **Licencia temporal**:Pruebe funciones avanzadas sin limitaciones de evaluación.
- **Compra**Para uso comercial a largo plazo, considere comprar una licencia.

## Configuración de Aspose.Slides para Java
Comience configurando la biblioteca Aspose.Slides en su proyecto Java. A continuación, le mostramos cómo inicializarla y configurarla:

1. Agregue la dependencia a través de Maven o Gradle como se muestra arriba.
2. Importe los paquetes Aspose.Slides necesarios:
   ```java
   import com.aspose.slides.*;
   ```

3. Inicializar un nuevo `Presentation` instancia:
   ```java
   Presentation presentation = new Presentation();
   ```

Esta configuración le permitirá comenzar a crear presentaciones mediante programación.

## Guía de implementación

### Cree y personalice gráficos en su presentación

#### Descripción general
Crear un gráfico implica inicializar la presentación, acceder a las diapositivas y agregar un gráfico con atributos específicos como tipo, posición y tamaño.

**Pasos:**
1. **Crear una instancia de presentación**:Comience creando una instancia del `Presentation` clase.
2. **Diapositiva de acceso**:Recuperar la primera diapositiva usando `get_Item(0)`.
3. **Agregar gráfico**: Usar `addChart()` para agregar un gráfico de columnas apiladas en coordenadas específicas con dimensiones definidas.

```java
// Función: Crear una presentación con gráfico
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Calcular totales por categorías

#### Descripción general
Para calcular los totales de categorías es necesario iterar sobre cada serie del gráfico para sumar los valores por categoría.

**Pasos:**
1. **Inicializar matriz**:Crea una matriz para almacenar valores totales.
2. **Iterar a través de categorías y series**:Utilice bucles anidados para acumular totales de cada categoría de todas las series.

```java
// Función: Calcular totales para categorías en un gráfico
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Mostrar datos como etiquetas de porcentaje en un gráfico

#### Descripción general
Esta función se centra en configurar las etiquetas de datos para mostrar valores como porcentajes, proporcionando claridad en la visualización.

**Pasos:**
1. **Configurar etiquetas de series**:Configure las propiedades de la etiqueta, como el tamaño de fuente y la visibilidad de las claves de leyenda.
2. **Calcular porcentajes**:Calcular el porcentaje de cada punto de datos en función del valor total de la categoría.
3. **Establecer texto de etiqueta**:Formatee etiquetas para mostrar porcentajes con dos puntos decimales.

```java
// Característica: Mostrar datos como etiquetas de porcentaje en un gráfico
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Guardar presentación con gráfico

#### Descripción general
Por último, guarde su presentación en una ruta específica en formato PPTX.

**Pasos:**
1. **Método de guardado**:Utilice el `save()` método en el `Presentation` instancia.
2. **Disponer de recursos**:Asegúrese de que los recursos se liberen después de guardar.

```java
// Función: Guardar presentación con gráfico
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Aplicaciones prácticas

1. **Informes financieros**: Utilice gráficos para mostrar los porcentajes de crecimiento de los ingresos en todos los departamentos.
2. **Análisis de datos de ventas**:Visualice los datos de ventas por región con etiquetas de porcentaje para obtener información más clara.
3. **Presentaciones educativas**:Mejore las presentaciones académicas con estadísticas visuales.
4. **Campañas de marketing**:Muestre las métricas de rendimiento de la campaña como elementos visuales atractivos.
5. **Reuniones de estrategia empresarial**:Utilice gráficos para transmitir datos complejos en discusiones de planificación estratégica.

## Consideraciones de rendimiento
- **Gestión de la memoria**:Desechar `Presentation` objetos rápidamente para liberar recursos.
- **Optimizar la carga de gráficos**:Solo cargue los elementos esenciales del gráfico en la memoria, si es posible.
- **Procesamiento por lotes**:Al procesar varias presentaciones, considere manejarlas en lotes para administrar el consumo de recursos de manera eficaz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
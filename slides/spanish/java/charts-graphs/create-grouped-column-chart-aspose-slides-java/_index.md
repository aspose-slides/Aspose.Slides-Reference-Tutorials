---
date: '2026-03-20'
description: Aprenda cómo agregar un gráfico de columnas agrupadas a una presentación
  de PowerPoint, personalizar el gráfico de PowerPoint e insertar un gráfico de series
  de datos usando Aspose.Slides para Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Cómo agregar un gráfico de columnas agrupadas en PowerPoint usando Aspose.Slides
  para Java
url: /es/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar un gráfico de columnas agrupadas en PowerPoint usando Aspose.Slides para Java

## Introducción

Cuando necesitas **agregar un gráfico de columnas agrupadas** a una presentación de PowerPoint, un visual claro puede convertir números crudos en una historia comprensible al instante. Hacer esto manualmente en PowerPoint puede consumir mucho tiempo, sobre todo cuando debes generar muchas diapositivas de forma programática. **Aspose.Slides para Java** elimina la fricción: te permite crear, personalizar gráficos de PowerPoint e insertar series de datos con solo unas pocas líneas de código.

En este tutorial aprenderás a:
- Inicializar una nueva presentación de PowerPoint con Aspose.Slides para Java.
- **Agregar un gráfico a la diapositiva** y configurarlo como un gráfico de columnas agrupadas.
- **Crear un gráfico de columnas agrupadas** definiendo niveles de agrupación para las categorías.
- **Insertar series de datos** para que tu información se muestre correctamente.
- Guardar la presentación final como un archivo PPTX.

Asegurémonos de que tienes todo lo necesario antes de sumergirnos en el código.

## Respuestas rápidas
- **¿Cuál es la clase principal?** `Presentation` de `com.aspose.slides`.
- **¿Qué tipo de gráfico se utiliza?** `ChartType.ClusteredColumn`.
- **¿Necesito una licencia para probar?** Una prueba gratuita funciona, pero una licencia elimina los límites de evaluación.
- **¿Qué versión de Java es compatible?** JDK 16 o posterior (el ejemplo usa JDK 16).
- **¿Cómo ejecutar el ejemplo?** Añade la dependencia Maven/Gradle, compila y ejecuta el método `main`.

## ¿Qué es “agregar un gráfico de columnas agrupadas”?

Un *gráfico de columnas agrupadas* (también llamado gráfico de columnas agrupadas) muestra múltiples series de datos una al lado de la otra para cada categoría, facilitando la comparación de valores entre grupos. En PowerPoint este tipo de gráfico es ideal para ventas trimestrales, resultados de encuestas o cualquier escenario donde necesites contrastar varios conjuntos de datos dentro de la misma categoría.

## ¿Por qué usar Aspose.Slides para agregar un gráfico de columnas agrupadas?

- **Automatización total** – genera docenas de diapositivas sin esfuerzo manual.
- **Personalización granular** – controla colores, etiquetas, niveles de agrupación y más.
- **Multiplataforma** – funciona en cualquier SO que soporte Java.
- **Sin necesidad de instalar Office** – genera archivos PPTX en servidores o pipelines CI.

## Requisitos previos

- Biblioteca **Aspose.Slides para Java** (se recomienda la última versión).  
- JDK 16 o posterior.  
- Herramienta de compilación Maven o Gradle (o puedes añadir el JAR manualmente).  
- Un IDE o editor de texto para ejecutar código Java.

## Configuración de Aspose.Slides para Java

Añade la biblioteca a tu proyecto usando uno de los siguientes scripts de compilación.

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

Alternativamente, puedes descargar directamente la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia

Antes de desplegar en producción, obtén una licencia:
- **Prueba gratuita** – explora todas las funciones sin compra.
- **Licencia temporal** – evalúa capacidades ampliadas por un corto período.
- **Licencia completa** – desbloquea uso ilimitado. Consíguela en la [página de compra de Aspose](https://purchase.aspose.com/buy).

## Guía de implementación

Recorreremos cada paso, explicando **cómo agregar el gráfico** y **personalizar el gráfico de PowerPoint** a lo largo del proceso.

### Inicializar la presentación

Primero, crea un nuevo objeto `Presentation` y obtén la diapositiva predeterminada.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Agregar gráfico a la diapositiva

Ahora **agregamos el gráfico a la diapositiva** usando el tipo `ClusteredColumn` y eliminamos cualquier dato predeterminado.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Preparar el libro de datos del gráfico

El gráfico almacena sus datos en un libro interno. Lo limpiamos para comenzar desde cero.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Añadir categorías con niveles de agrupación

Agrupar categorías crea el efecto de **gráfico de columnas agrupadas**. Cada categoría puede pertenecer a un grupo lógico.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Añadir series de datos al gráfico

Aquí **insertamos series de datos** que se visualizarán como columnas separadas.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Guardar la presentación con el gráfico

Finalmente, escribe el archivo PPTX en disco.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Aplicaciones prácticas

- **Informes empresariales** – comparar ingresos trimestrales por región.  
- **Investigación académica** – mostrar resultados experimentales agrupados por condiciones de prueba.  
- **Gestión de proyectos** – visualizar tasas de finalización de tareas para varios equipos en una sola diapositiva.

## Consideraciones de rendimiento

- **Gestión de memoria** – libera libros de trabajo grandes después de usarlos.  
- **Operaciones por lotes** – evita actualizar el gráfico dentro de bucles intensos; recopila los datos primero y luego aplícalos.  
- **Optimización incorporada** – Aspose.Slides ofrece métodos como `Presentation.optimize()` para archivos de gran tamaño.

## Errores comunes y consejos

- **Error:** Olvidar limpiar series/categorías existentes puede generar datos duplicados.  
  **Consejo:** Siempre llama a `clear()` antes de poblar nuevos datos.  
- **Error:** Usar la dirección de celda incorrecta (p. ej., `"c2"` en lugar de `"C2"`).  
  **Consejo:** Las referencias de celda no distinguen mayúsculas, pero mantenlas consistentes para mayor legibilidad.  
- **Consejo:** Usa `setGroupingItem` para crear etiquetas de grupo significativas; aparecen automáticamente en la leyenda del gráfico.

## Preguntas frecuentes

**P1: ¿Cómo puedo agregar varias series a mi gráfico?**  
R1: Llama a `ch.getChartData().getSeries().add()` repetidamente, proporcionando un nombre único y los puntos de datos para cada serie.

**P2: ¿Cuáles son algunos problemas comunes con los gráficos de Aspose.Slides?**  
R2: Los problemas suelen originarse en rangos de datos incompatibles o celdas de libro faltantes. Verifica que cada categoría y punto de datos tenga una celda correspondiente.

**P3: ¿Puedo usar Aspose.Slides con otros lenguajes de programación?**  
R3: Sí, Aspose ofrece bibliotecas equivalentes para .NET, C++, Python y más.

**P4: ¿Cómo actualizo un gráfico existente en una presentación?**  
R4: Carga la presentación, localiza el gráfico mediante `slide.getShapes().get_Item(index)`, luego modifica sus series o formato según sea necesario.

**P5: ¿Existen limitaciones en los tipos de gráfico con Aspose.Slides?**  
R5: La biblioteca soporta una amplia gama de tipos de gráfico, pero siempre revisa la documentación más reciente para conocer tipos añadidos o obsoletos.

## Recursos

- **Documentación:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Descarga:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Compra:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Prueba gratuita:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Licencia temporal:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Foro de soporte:** [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2026-03-20  
**Probado con:** Aspose.Slides para Java 25.4 (JDK 16)  
**Autor:** Aspose
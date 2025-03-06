---
title: Editar datos de gráficos en un libro de trabajo externo en diapositivas de Java
linktitle: Editar datos de gráficos en un libro de trabajo externo en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a editar datos de gráficos en un libro de trabajo externo usando Aspose.Slides para Java. Guía paso a paso con código fuente.
weight: 17
url: /es/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción a la edición de datos de gráficos en un libro de trabajo externo en diapositivas de Java

En esta guía, demostraremos cómo editar datos de gráficos en un libro de trabajo externo usando Aspose.Slides para Java. Aprenderá cómo modificar datos de gráficos dentro de una presentación de PowerPoint mediante programación. Asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto.

## Requisitos previos

- Aspose.Slides para Java
- entorno de desarrollo java

## Paso 1: Cargue la presentación

 Primero, necesitamos cargar la presentación de PowerPoint que contiene el gráfico cuyos datos queremos editar. Reemplazar`"Your Document Directory"` con la ruta real a su archivo de presentación.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Paso 2: acceda al gráfico

Una vez cargada la presentación, debemos acceder al gráfico dentro de la presentación. En este ejemplo, asumimos que el gráfico está en la primera diapositiva y es la primera forma de esa diapositiva.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Paso 3: modificar los datos del gráfico

Ahora, modifiquemos los datos del gráfico. Nos centraremos en cambiar un punto de datos específico en el gráfico. En este ejemplo, establecemos el valor del primer punto de datos de la primera serie en 100. Puede ajustar este valor según sea necesario.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Paso 4: guarde la presentación

Después de realizar los cambios necesarios en los datos del gráfico, guarde la presentación modificada en un archivo nuevo. Puede especificar la ruta y el formato del archivo de salida según sus requisitos.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Paso 5: limpieza

No olvide deshacerse del objeto de presentación para liberar recursos.

```java
if (pres != null) pres.dispose();
```

Ahora ha editado con éxito los datos del gráfico en un libro de trabajo externo dentro de su presentación de PowerPoint usando Aspose.Slides para Java. Puede personalizar este código para adaptarlo a sus necesidades específicas e integrarlo en sus aplicaciones Java.

## Código fuente completo

```java
        // Preste atención, la ruta al libro externo apenas se guarda en la presentación.
        // así que copie el archivo externalWorkbook.xlsx del directorio Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ antes de ejecutar el ejemplo.
        // La ruta al directorio de documentos.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusión

En esta guía completa, hemos explorado cómo editar datos de gráficos en libros de trabajo externos dentro de presentaciones de PowerPoint usando Aspose.Slides para Java. Al seguir las instrucciones paso a paso y los ejemplos de código fuente, habrá adquirido el conocimiento y las habilidades para modificar datos de gráficos mediante programación con facilidad.

## Preguntas frecuentes

### ¿Cómo especifico un gráfico o diapositiva diferente?

 Para acceder a un gráfico o diapositiva diferente, modifique el índice apropiado en el`getSlides().get_Item()` y`getShapes().get_Item()`métodos. Recuerde que la indexación comienza desde 0.

### ¿Puedo editar datos en varios gráficos dentro de la misma presentación?

Sí, puede editar datos en varios gráficos dentro de la misma presentación repitiendo los pasos de modificación de datos del gráfico para cada gráfico.

### ¿Qué sucede si quiero editar datos en un libro externo con un formato diferente?

Puede adaptar el código para manejar diferentes formatos de libros de trabajo externos utilizando las clases y métodos de Aspose.Cells adecuados para leer y escribir datos en ese formato.

### ¿Cómo puedo automatizar este proceso para múltiples presentaciones?

Puede crear un bucle para procesar varias presentaciones, cargar cada una, realizar los cambios deseados y guardar las presentaciones modificadas una por una.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

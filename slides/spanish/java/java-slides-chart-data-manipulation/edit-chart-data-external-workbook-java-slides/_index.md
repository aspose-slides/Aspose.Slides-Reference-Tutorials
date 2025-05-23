---
"description": "Aprenda a editar datos de gráficos en un libro externo con Aspose.Slides para Java. Guía paso a paso con código fuente."
"linktitle": "Editar datos de gráficos en un libro de trabajo externo en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Editar datos de gráficos en un libro de trabajo externo en diapositivas de Java"
"url": "/es/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Editar datos de gráficos en un libro de trabajo externo en diapositivas de Java


## Introducción a la edición de datos de gráficos en un libro de trabajo externo en diapositivas de Java

En esta guía, le mostraremos cómo editar datos de gráficos en un libro externo con Aspose.Slides para Java. Aprenderá a modificar datos de gráficos en una presentación de PowerPoint mediante programación. Asegúrese de tener la biblioteca Aspose.Slides para Java instalada y configurada en su proyecto.

## Prerrequisitos

- Aspose.Slides para Java
- Entorno de desarrollo Java

## Paso 1: Cargar la presentación

Primero, necesitamos cargar la presentación de PowerPoint que contiene el gráfico cuyos datos queremos editar. Reemplazar `"Your Document Directory"` con la ruta real a su archivo de presentación.

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Paso 2: Acceda al gráfico

Una vez cargada la presentación, necesitamos acceder al gráfico dentro de ella. En este ejemplo, suponemos que el gráfico está en la primera diapositiva y es la primera forma de esa diapositiva.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Paso 3: Modificar los datos del gráfico

Ahora, modifiquemos los datos del gráfico. Nos centraremos en cambiar un punto de datos específico. En este ejemplo, establecemos el valor del primer punto de datos de la primera serie en 100. Puede ajustar este valor según sea necesario.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Paso 4: Guardar la presentación

Después de realizar los cambios necesarios en los datos del gráfico, guarde la presentación modificada en un nuevo archivo. Puede especificar la ruta y el formato del archivo de salida según sus necesidades.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Paso 5: Limpieza

No olvides desechar el objeto de presentación para liberar recursos.

```java
if (pres != null) pres.dispose();
```

Ya ha editado correctamente los datos del gráfico en un libro externo dentro de su presentación de PowerPoint con Aspose.Slides para Java. Puede personalizar este código para adaptarlo a sus necesidades específicas e integrarlo en sus aplicaciones Java.

## Código fuente completo

```java
        // Preste atención: la ruta al libro de trabajo externo apenas se guarda en la presentación.
        // Por lo tanto, copie el archivo externalWorkbook.xlsx del directorio Datos/Gráficos D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ antes de ejecutar el ejemplo
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

En esta guía completa, hemos explorado cómo editar datos de gráficos en libros externos dentro de presentaciones de PowerPoint usando Aspose.Slides para Java. Siguiendo las instrucciones paso a paso y los ejemplos de código fuente, ha adquirido los conocimientos y las habilidades para modificar datos de gráficos mediante programación con facilidad.

## Preguntas frecuentes

### ¿Cómo puedo especificar un gráfico o diapositiva diferente?

Para acceder a un gráfico o diapositiva diferente, modifique el índice apropiado en el `getSlides().get_Item()` y `getShapes().get_Item()` métodos. Recuerde que la indexación comienza desde 0.

### ¿Puedo editar datos en varios gráficos dentro de la misma presentación?

Sí, puede editar datos en varios gráficos dentro de la misma presentación repitiendo los pasos de modificación de datos del gráfico para cada gráfico.

### ¿Qué pasa si quiero editar datos en un libro externo con un formato diferente?

Puede adaptar el código para manejar diferentes formatos de libros de trabajo externos mediante el uso de las clases y métodos Aspose.Cells adecuados para leer y escribir datos en ese formato.

### ¿Cómo puedo automatizar este proceso para múltiples presentaciones?

Puede crear un bucle para procesar múltiples presentaciones, cargar cada una, realizar los cambios deseados y guardar las presentaciones modificadas una por una.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
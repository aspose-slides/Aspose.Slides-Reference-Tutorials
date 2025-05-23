---
"description": "Aprenda a configurar libros externos y actualizar datos de gráficos en Java Slides con Aspose.Slides para Java. Mejore sus habilidades de automatización de PowerPoint."
"linktitle": "Configurar un libro de trabajo externo con datos de gráficos de actualización en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Configurar un libro de trabajo externo con datos de gráficos de actualización en diapositivas de Java"
"url": "/es/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Configurar un libro de trabajo externo con datos de gráficos de actualización en diapositivas de Java


## Introducción a la creación de un libro de trabajo externo con actualización de datos de gráficos en Java

En esta guía completa, le guiaremos a través del proceso de configuración de un libro de trabajo externo con datos de gráficos actualizados en Java Slides mediante la API Aspose.Slides para Java. Esta potente biblioteca le permite manipular presentaciones de PowerPoint mediante programación, lo que facilita la automatización de tareas como la actualización de datos de gráficos desde una fuente externa. Al finalizar este tutorial, comprenderá claramente cómo realizar esta tarea con instrucciones paso a paso y el código Java correspondiente.

## Prerrequisitos

Antes de sumergirnos en la implementación, asegúrese de tener los siguientes requisitos previos:

1. Aspose.Slides para Java: Debe tener instalada la biblioteca Aspose.Slides para Java. Puede descargarla desde [aquí](https://releases.aspose.com/slides/java/).

2. Entorno de desarrollo de Java: asegúrese de tener un entorno de desarrollo de Java configurado en su sistema.

## Paso 1: Crear una nueva presentación

Para empezar, creemos una nueva presentación de PowerPoint con Aspose.Slides para Java. Aquí está el código Java para hacerlo:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Paso 2: Agregar un gráfico

Ahora, agreguemos un gráfico a nuestra presentación. En este ejemplo, crearemos un gráfico circular:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Paso 3: Configurar el libro de trabajo externo

Aquí es donde configuramos el libro de trabajo externo como fuente de datos para nuestro gráfico. Debe proporcionar la URL del libro de trabajo externo, incluso si no existe por ahora:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://ruta/no/existe", falso);
```

## Paso 4: Guardar la presentación

Por último, guarde la presentación con los datos del gráfico actualizados:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Código fuente completo para crear un libro de trabajo externo con actualización de datos de gráficos en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://ruta/no/existe", falso);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

¡Felicitaciones! Aprendió a configurar un libro de trabajo externo con datos de gráficos actualizados en Java Slides usando Aspose.Slides para Java. Esto puede ser increíblemente útil para actualizar dinámicamente gráficos en sus presentaciones de PowerPoint desde fuentes de datos externas.

## Preguntas frecuentes

### ¿Cómo puedo actualizar los datos del libro de trabajo externo para el gráfico?

Para actualizar los datos del libro externo para el gráfico, simplemente modifique los datos del libro externo en la URL especificada. La próxima vez que abra la presentación, Aspose.Slides para Java obtendrá los datos actualizados del libro externo y actualizará el gráfico según corresponda.

### ¿Puedo utilizar un archivo local como libro de trabajo externo?

Sí, puede usar un archivo local como libro de trabajo externo proporcionando la ruta del archivo en lugar de una URL. Solo asegúrese de que la ruta del archivo sea correcta y accesible desde su aplicación Java.

### ¿Existen limitaciones para usar libros de trabajo externos con Aspose.Slides para Java?

Si bien usar libros de trabajo externos es una función potente, tenga en cuenta que la disponibilidad de los datos de estos depende de su accesibilidad en la URL o ruta de archivo proporcionada. Asegúrese de que la fuente de datos externa esté disponible al abrir la presentación para evitar problemas de recuperación de datos.

### ¿Puedo personalizar la apariencia del gráfico después de configurar el libro de trabajo externo?

Sí, puede personalizar la apariencia del gráfico, incluyendo el título, las etiquetas, los colores y más, incluso después de configurar el libro de trabajo externo. Aspose.Slides para Java ofrece amplias opciones de formato de gráficos para satisfacer sus necesidades.

### ¿Dónde puedo encontrar más documentación y recursos para Aspose.Slides para Java?

Para obtener documentación detallada y recursos adicionales, visite la documentación de Aspose.Slides para Java en [aquí](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
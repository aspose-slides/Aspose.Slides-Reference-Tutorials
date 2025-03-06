---
title: Establecer un libro de trabajo externo con datos de gráfico de actualización en diapositivas de Java
linktitle: Establecer un libro de trabajo externo con datos de gráfico de actualización en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a configurar libros de trabajo externos y actualizar datos de gráficos en Java Slides usando Aspose.Slides para Java. Mejore sus habilidades de automatización de PowerPoint.
weight: 20
url: /es/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introducción a configurar un libro de trabajo externo con datos de gráfico de actualización en diapositivas de Java

En esta guía completa, lo guiaremos a través del proceso de configuración de un libro de trabajo externo con datos de gráficos actualizados en Java Slides utilizando la API Aspose.Slides para Java. Esta poderosa biblioteca le permite manipular presentaciones de PowerPoint mediante programación, lo que facilita la automatización de tareas como la actualización de datos de gráficos desde una fuente externa. Al final de este tutorial, comprenderá claramente cómo realizar esta tarea con instrucciones paso a paso y el código Java que las acompaña.

## Requisitos previos

Antes de profundizar en la implementación, asegúrese de tener implementados los siguientes requisitos previos:

1.  Aspose.Slides para Java: debe tener instalada la biblioteca Aspose.Slides para Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/java/).

2. Entorno de desarrollo Java: asegúrese de tener un entorno de desarrollo Java configurado en su sistema.

## Paso 1: crea una nueva presentación

Para comenzar, creemos una nueva presentación de PowerPoint usando Aspose.Slides para Java. Aquí está el código Java para hacer eso:

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Paso 2: agregar un gráfico

Ahora, agreguemos un gráfico a nuestra presentación. Crearemos un gráfico circular en este ejemplo:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Paso 3: configurar el libro de trabajo externo

Aquí es donde configuramos el libro de trabajo externo como fuente de datos para nuestro gráfico. Debe proporcionar la URL del libro externo, incluso si no existe por ahora:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://ruta/no/existe", falso);
```

## Paso 4: guarde la presentación

Finalmente, guarde la presentación con los datos del gráfico actualizados:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Código fuente completo para establecer un libro de trabajo externo con datos de gráfico de actualización en diapositivas de Java

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

¡Felicidades! Ha aprendido cómo configurar un libro de trabajo externo con datos de gráficos actualizados en Java Slides usando Aspose.Slides para Java. Esto puede resultar increíblemente útil para actualizar dinámicamente gráficos en sus presentaciones de PowerPoint desde fuentes de datos externas.

## Preguntas frecuentes

### ¿Cómo puedo actualizar los datos del libro de trabajo externo para el gráfico?

Para actualizar los datos del libro de trabajo externo para el gráfico, simplemente necesita modificar los datos en el libro de trabajo externo en la URL especificada. La próxima vez que abra la presentación, Aspose.Slides para Java recuperará los datos actualizados del libro de trabajo externo y actualizará el gráfico en consecuencia.

### ¿Puedo utilizar un archivo local como libro de trabajo externo?

Sí, puede utilizar un archivo local como libro de trabajo externo proporcionando la ruta del archivo en lugar de una URL. Solo asegúrese de que la ruta del archivo sea correcta y accesible desde su aplicación Java.

### ¿Existe alguna limitación en el uso de libros de trabajo externos con Aspose.Slides para Java?

Si bien el uso de libros de trabajo externos es una característica poderosa, tenga en cuenta que la disponibilidad de los datos del libro de trabajo externo depende de su accesibilidad en la URL o ruta de archivo proporcionada. Asegúrese de que la fuente de datos externa esté disponible cuando abra la presentación para evitar problemas de recuperación de datos.

### ¿Puedo personalizar la apariencia del gráfico después de configurar el libro externo?

Sí, puede personalizar la apariencia del gráfico, incluido su título, etiquetas, colores y más, incluso después de configurar el libro externo. Aspose.Slides para Java proporciona amplias opciones de formato de gráficos para satisfacer sus necesidades.

### ¿Dónde puedo encontrar más documentación y recursos para Aspose.Slides para Java?

 Para obtener documentación detallada y recursos adicionales, visite la documentación de Aspose.Slides para Java en[aquí](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

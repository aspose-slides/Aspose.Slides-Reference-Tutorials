---
title: Acceda a formatos de diseño en diapositivas Java
linktitle: Acceda a formatos de diseño en diapositivas Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo acceder y manipular formatos de diseño en Java Slides con Aspose.Slides para Java. Personalice estilos de formas y líneas sin esfuerzo en presentaciones de PowerPoint.
weight: 10
url: /es/java/presentation-properties/access-layout-formats-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introducción a los formatos de diseño de acceso en diapositivas de Java

En este tutorial, exploraremos cómo acceder y trabajar con formatos de diseño en Java Slides utilizando la API Aspose.Slides para Java. Los formatos de diseño le permiten controlar la apariencia de formas y líneas dentro de las diapositivas de diseño de una presentación. Cubriremos cómo recuperar formatos de relleno y formatos de línea para formas en diapositivas de diseño.

## Requisitos previos

1. Aspose.Slides para la biblioteca Java.
2. Una presentación de PowerPoint (formato PPTX) con diapositivas de diseño.

## Paso 1: Cargue la presentación

 Primero, necesitamos cargar la presentación de PowerPoint que contiene las diapositivas de diseño. Reemplazar`"Your Document Directory"` con la ruta real a su directorio de documentos.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Paso 2: acceda a los formatos de diseño

Ahora, recorramos las diapositivas de diseño en la presentación y accedamos a los formatos de relleno y de línea de las formas en cada diapositiva de diseño.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Acceder a formatos de relleno de formas.
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Acceder a formatos de línea de formas.
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

En el código anterior:

- Repetimos cada diapositiva de diseño usando un`for` bucle.
- Para cada diapositiva de diseño, creamos matrices para almacenar formatos de relleno y formatos de línea para las formas de esa diapositiva.
-  Usamos anidados`for` bucles para recorrer las formas en la diapositiva de diseño y recuperar sus formatos de relleno y línea.

## Paso 3: trabajar con formatos de diseño

Ahora que hemos accedido a los formatos de relleno y de línea para las formas en las diapositivas de diseño, puede realizar varias operaciones en ellas según sea necesario. Por ejemplo, puedes cambiar el color de relleno, el estilo de línea u otras propiedades de las formas.

## Código fuente completo para formatos de diseño de acceso en diapositivas de Java

```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, exploramos cómo acceder y manipular formatos de diseño en Java Slides utilizando la API Aspose.Slides para Java. Los formatos de diseño son esenciales para controlar la apariencia de formas y líneas dentro de las diapositivas de diseño en presentaciones de PowerPoint.

## Preguntas frecuentes

### ¿Cómo cambio el color de relleno de una forma?

 Para cambiar el color de relleno de una forma, puede utilizar el`IFillFormat`métodos del objeto. He aquí un ejemplo:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Establecer tipo de relleno en color sólido
fillFormat.getSolidFillColor().setColor(Color.RED); // Establecer el color de relleno en rojo
```

### ¿Cómo cambio el estilo de línea de una forma?

 Para cambiar el estilo de línea de una forma, puede utilizar el`ILineFormat`métodos del objeto. He aquí un ejemplo:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Establecer estilo de línea en único
lineFormat.setWidth(2.0); // Establecer el ancho de línea en 2,0 puntos
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Establecer el color de la línea en azul
```

### ¿Cómo aplico estos cambios a una forma en una diapositiva de diseño?

Para aplicar estos cambios a una forma específica en una diapositiva de diseño, puede acceder a la forma usando su índice en la colección de formas de la diapositiva de diseño. Por ejemplo:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Acceda a la primera forma en la diapositiva de diseño
```

 Luego puedes usar el`IFillFormat` y`ILineFormat` métodos como se muestran en las respuestas anteriores para modificar los formatos de relleno y línea de la forma.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

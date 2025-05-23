---
"description": "Aprenda a acceder y manipular formatos de diseño en Java Slides con Aspose.Slides para Java. Personalice fácilmente los estilos de forma y línea en sus presentaciones de PowerPoint."
"linktitle": "Formatos de diseño de acceso en diapositivas de Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Formatos de diseño de acceso en diapositivas de Java"
"url": "/es/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formatos de diseño de acceso en diapositivas de Java


## Introducción a los formatos de diseño de Access en diapositivas de Java

En este tutorial, exploraremos cómo acceder y trabajar con formatos de diseño en Java Slides mediante la API de Aspose.Slides para Java. Los formatos de diseño permiten controlar la apariencia de las formas y líneas en las diapositivas de una presentación. Explicaremos cómo recuperar formatos de relleno y de línea para formas en las diapositivas.

## Prerrequisitos

1. Biblioteca Aspose.Slides para Java.
2. Una presentación de PowerPoint (formato PPTX) con diapositivas de diseño.

## Paso 1: Cargar la presentación

Primero, necesitamos cargar la presentación de PowerPoint que contiene las diapositivas de diseño. Reemplazar `"Your Document Directory"` con la ruta real a su directorio de documentos.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Paso 2: Acceder a los formatos de diseño

Ahora, recorramos las diapositivas de diseño en la presentación y accedamos a los formatos de relleno y formatos de línea de las formas en cada diapositiva de diseño.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Acceder a formatos de relleno de formas
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Formatos de líneas de acceso de formas
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

- Recorrimos cada diapositiva de diseño usando un `for` bucle.
- Para cada diapositiva de diseño, creamos matrices para almacenar formatos de relleno y formatos de línea para las formas en esa diapositiva.
- Usamos anidados `for` bucles para iterar a través de las formas en la diapositiva de diseño y recuperar sus formatos de relleno y línea.

## Paso 3: Trabajar con formatos de diseño

Ahora que hemos accedido a los formatos de relleno y de línea de las formas en las diapositivas de diseño, puede realizar diversas operaciones en ellas según sea necesario. Por ejemplo, puede cambiar el color de relleno, el estilo de línea u otras propiedades de las formas.

## Código fuente completo para formatos de diseño de Access en diapositivas de Java

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

En este tutorial, exploramos cómo acceder y manipular formatos de diseño en Java Slides mediante la API de Aspose.Slides para Java. Los formatos de diseño son esenciales para controlar la apariencia de las formas y líneas en las diapositivas de PowerPoint.

## Preguntas frecuentes

### ¿Cómo cambio el color de relleno de una forma?

Para cambiar el color de relleno de una forma, puede utilizar el `IFillFormat` Métodos del objeto. Aquí hay un ejemplo:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Establecer el tipo de relleno en color sólido
fillFormat.getSolidFillColor().setColor(Color.RED); // Establezca el color de relleno en rojo
```

### ¿Cómo cambio el estilo de línea de una forma?

Para cambiar el estilo de línea de una forma, puede utilizar el `ILineFormat` Métodos del objeto. Aquí hay un ejemplo:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Establecer el estilo de línea en sencillo
lineFormat.setWidth(2.0); // Establezca el ancho de línea en 2,0 puntos
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Establecer el color de la línea en azul
```

### ¿Cómo aplico estos cambios a una forma en una diapositiva de diseño?

Para aplicar estos cambios a una forma específica en una diapositiva de diseño, puede acceder a ella mediante su índice en la colección de formas de la diapositiva. Por ejemplo:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Acceda a la primera forma en la diapositiva de diseño
```

Luego puedes utilizar el `IFillFormat` y `ILineFormat` métodos como los que se muestran en las respuestas anteriores para modificar los formatos de relleno y línea de la forma.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
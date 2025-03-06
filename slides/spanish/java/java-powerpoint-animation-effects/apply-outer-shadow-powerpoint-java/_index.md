---
title: Aplicar sombra exterior en PowerPoint con Java
linktitle: Aplicar sombra exterior en PowerPoint con Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda a aplicar el efecto de sombra exterior en PowerPoint usando Java con Aspose.Slides. Mejore sus presentaciones con profundidad y atractivo visual.
weight: 13
url: /es/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introducción
Crear presentaciones de PowerPoint visualmente atractivas a menudo implica agregar varios efectos a las formas y al texto. Uno de esos efectos es la sombra exterior, que puede hacer que los elementos se destaquen y agreguen profundidad a sus diapositivas. En este tutorial, aprenderá cómo aplicar un efecto de sombra exterior a una forma en PowerPoint usando Java con Aspose.Slides.
## Requisitos previos

Antes de comenzar este tutorial, asegúrese de tener los siguientes requisitos previos:

1. Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su sistema. Puede descargar e instalar la última versión de JDK desde el sitio web de Oracle.

2.  Aspose.Slides para Java: descargue e instale Aspose.Slides para Java desde[pagina de descarga](https://releases.aspose.com/slides/java/).

3. Entorno de desarrollo integrado (IDE): elija su IDE de Java preferido, como Eclipse, IntelliJ IDEA o NetBeans, para codificar y ejecutar aplicaciones Java.

4. Conocimientos básicos de Java: la familiaridad con los fundamentos del lenguaje de programación Java y los conceptos orientados a objetos será beneficiosa para comprender los ejemplos de código.

## Importar paquetes

Primero, importe los paquetes necesarios para trabajar con Aspose.Slides y las funcionalidades relacionadas en su proyecto Java:

```java
import com.aspose.slides.*;
```

Ahora dividamos el código de ejemplo en varios pasos para aplicar el efecto de sombra exterior a una forma en PowerPoint usando Java con Aspose.Slides:

## Paso 1: configure el entorno de su proyecto

Cree un nuevo proyecto Java en su IDE preferido y agregue la biblioteca Aspose.Slides para Java a la ruta de compilación de su proyecto.

## Paso 2: inicializar el objeto de presentación

 Crear una instancia del`Presentation` clase, que representa un archivo de presentación de PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Paso 3: agrega una diapositiva y una forma

Obtenga una referencia a la diapositiva donde desea agregar la forma y luego agregue una autoforma (por ejemplo, un rectángulo) a la diapositiva.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Paso 4: personaliza la forma

Establece el tipo de relleno de la forma en 'Sin relleno' y agrega texto a la forma.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Paso 5: personaliza el texto

Accede a las propiedades de texto de la forma y personaliza el tamaño de fuente.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Paso 6: habilite el efecto Sombra exterior

Habilite el efecto de sombra exterior para la parte del texto.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Paso 7: establecer los parámetros de sombra

Defina los parámetros para el efecto de sombra exterior, como el radio de desenfoque, la dirección, la distancia y el color de la sombra.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Paso 8: guarda la presentación

Guarde la presentación modificada con el efecto de sombra exterior aplicado a la forma.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusión

¡Felicidades! Ha aplicado con éxito un efecto de sombra exterior a una forma en PowerPoint usando Java con Aspose.Slides. Experimente con diferentes parámetros para lograr los efectos visuales deseados en sus presentaciones.

## Preguntas frecuentes

### ¿Puedo aplicar el efecto de sombra exterior a otras formas además de los rectángulos?
Sí, puedes aplicar el efecto de sombra exterior a varias formas admitidas por Aspose.Slides, como círculos, triángulos y formas personalizadas.

### ¿Es posible personalizar el color y la intensidad de la sombra?
¡Absolutamente! Tienes control total sobre los parámetros de la sombra, incluido el color, el radio de desenfoque, la dirección y la distancia.

### ¿Puedo aplicar múltiples efectos a la misma forma?
Sí, puedes combinar múltiples efectos como sombra exterior, sombra interior, brillo y reflejo para mejorar el atractivo visual de las formas y el texto en tus presentaciones.

### ¿Aspose.Slides admite la aplicación de efectos a elementos de texto?
Sí, puedes aplicar efectos no sólo a las formas sino también a partes de texto individuales dentro de las formas, lo que te brinda una gran flexibilidad a la hora de diseñar tus diapositivas.

### ¿Dónde puedo encontrar más recursos y soporte para Aspose.Slides?
 Puedes consultar el[documentación](https://reference.aspose.com/slides/java/) para obtener referencias API detalladas y explorar el[Foro Aspose.Slides](https://forum.aspose.com/c/slides/11) para apoyo y debates de la comunidad.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

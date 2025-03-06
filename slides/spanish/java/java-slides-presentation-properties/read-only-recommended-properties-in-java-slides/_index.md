---
title: Propiedades recomendadas de solo lectura en diapositivas de Java
linktitle: Propiedades recomendadas de solo lectura en diapositivas de Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo habilitar las propiedades recomendadas de solo lectura en presentaciones de PowerPoint de Java usando Aspose.Slides para Java. Siga nuestra guía paso a paso con ejemplos de código fuente para mejorar la seguridad de las presentaciones.
weight: 17
url: /es/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introducción a la habilitación de propiedades recomendadas de solo lectura en diapositivas de Java

En este tutorial, exploraremos cómo habilitar las propiedades recomendadas de solo lectura para presentaciones de PowerPoint usando Aspose.Slides para Java. Las propiedades recomendadas de solo lectura pueden resultar útiles cuando desea animar a los usuarios a ver una presentación sin realizar ningún cambio. Estas propiedades sugieren que la presentación debe abrirse en modo de solo lectura. Le proporcionaremos una guía paso a paso junto con el código fuente de Java para lograrlo.

## Requisitos previos

 Antes de comenzar, asegúrese de tener la biblioteca Aspose.Slides para Java configurada en su proyecto. Puedes descargarlo desde el[Sitio web de Aspose.Slides para Java](https://products.aspose.com/slides/java/).

## Paso 1: crea una nueva presentación de PowerPoint

Comenzaremos creando una nueva presentación de PowerPoint usando Aspose.Slides para Java. Si ya tienes una presentación, puedes omitir este paso.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

En el código anterior, definimos la ruta para el archivo de PowerPoint de salida y creamos un nuevo objeto de presentación.

## Paso 2: habilite la propiedad recomendada de solo lectura

Ahora, habilitemos la propiedad Recomendada de solo lectura para la presentación.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 En este fragmento de código, utilizamos el`getProtectionManager().setReadOnlyRecommended(true)` método para establecer la propiedad Recomendada de solo lectura en`true`. Esto garantiza que cuando alguien abra la presentación, se le pedirá que la abra en modo de solo lectura.

## Paso 3: guarde la presentación

Finalmente guardamos la presentación con la propiedad Recomendada de sólo lectura habilitada.

## Código fuente completo para propiedades recomendadas de solo lectura en diapositivas de Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusión

En este tutorial, aprendió cómo habilitar la propiedad Recomendada de solo lectura para una presentación de PowerPoint usando Aspose.Slides para Java. Esta función puede resultar útil cuando desee restringir la edición y animar a los espectadores a utilizar la presentación en modo de solo lectura. Puede mejorar aún más la seguridad estableciendo una contraseña para la presentación.

## Preguntas frecuentes

### ¿Cómo desactivo la propiedad Recomendada de solo lectura?

Para deshabilitar la propiedad Recomendada de solo lectura, simplemente use el siguiente código:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### ¿Puedo establecer una contraseña para una presentación recomendada de solo lectura?

Sí, puede establecer una contraseña para una presentación recomendada de solo lectura usando Aspose.Slides para Java. Puedes usar el`setPassword` Método para establecer una contraseña para la presentación. Si se establece una contraseña, los usuarios deberán ingresarla para abrir la presentación, incluso en modo de solo lectura.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Recuerde reemplazar`"YourPassword"` con la contraseña deseada.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

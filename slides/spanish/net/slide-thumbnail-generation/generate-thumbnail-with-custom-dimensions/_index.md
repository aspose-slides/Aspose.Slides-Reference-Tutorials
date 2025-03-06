---
title: Generar miniatura en diapositivas con dimensiones personalizadas
linktitle: Generar miniatura con dimensiones personalizadas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a generar imágenes en miniatura personalizadas a partir de presentaciones de PowerPoint utilizando Aspose.Slides para .NET. Mejorar la experiencia y la funcionalidad del usuario.
weight: 13
url: /es/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generar miniatura en diapositivas con dimensiones personalizadas


Crear imágenes en miniatura personalizadas de sus presentaciones de PowerPoint puede ser un activo valioso, ya sea que esté creando una aplicación interactiva, mejorando la experiencia del usuario u optimizando contenido para varias plataformas. En este tutorial, lo guiaremos a través del proceso de generación de imágenes en miniatura personalizadas a partir de presentaciones de PowerPoint utilizando la biblioteca Aspose.Slides para .NET. Esta poderosa biblioteca le permite manipular, convertir y mejorar archivos de PowerPoint mediante programación en aplicaciones .NET.

## Requisitos previos

Antes de sumergirnos en la generación de imágenes en miniatura personalizadas, asegúrese de cumplir con los siguientes requisitos previos:

### 1. Aspose.Slides para .NET

 Debe tener instalada la biblioteca Aspose.Slides para .NET en su proyecto. Si aún no lo has hecho, puedes encontrar la documentación necesaria y los enlaces de descarga.[aquí](https://reference.aspose.com/slides/net/).

### 2. Una presentación de PowerPoint

Asegúrese de tener la presentación de PowerPoint desde la cual desea generar una imagen en miniatura personalizada. Esta presentación debe ser accesible desde el directorio de su proyecto.

### 3. Entorno de desarrollo

Para seguir este tutorial, debe tener conocimientos prácticos de programación .NET usando C# y un entorno de desarrollo configurado, como Visual Studio.

Ahora que hemos cubierto los requisitos previos, analicemos el proceso de generación de miniaturas personalizadas en instrucciones paso a paso.

## Importar espacios de nombres

Primero, debe incluir los espacios de nombres requeridos en su código C#. Estos espacios de nombres le permiten trabajar con Aspose.Slides y manipular presentaciones de PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Paso 1: Cargue la presentación

Para comenzar, cargue la presentación de PowerPoint desde la cual desea generar una imagen en miniatura personalizada. Esto se logra utilizando la biblioteca Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Crear una instancia de una clase de presentación que represente el archivo de presentación
using (Presentation pres = new Presentation(srcFileName))
{
    // Su código para la generación de miniaturas irá aquí
}
```

## Paso 2: accede a la diapositiva

Dentro de la presentación cargada, debes acceder a la diapositiva específica desde la cual deseas generar la imagen en miniatura personalizada. Puedes elegir la diapositiva por su índice.

```csharp
// Accede a la primera diapositiva (puedes cambiar el índice según sea necesario)
ISlide sld = pres.Slides[0];
```

## Paso 3: definir dimensiones de miniatura personalizadas

Especifique las dimensiones deseadas para su imagen en miniatura personalizada. Puede definir el ancho y el alto en píxeles según los requisitos de su aplicación.

```csharp
int desiredX = 1200; // Ancho
int desiredY = 800;  // Altura
```

## Paso 4: Calcular los factores de escala

Para mantener la relación de aspecto de la diapositiva, calcule los factores de escala para las dimensiones X e Y según el tamaño de la diapositiva y las dimensiones deseadas.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Paso 5: genere la imagen en miniatura

Cree una imagen a escala completa de la diapositiva con las dimensiones personalizadas especificadas y guárdela en el disco en formato JPEG.

```csharp
// Crea una imagen a gran escala
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Guarde la imagen en el disco en formato JPEG.
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Ahora que ha seguido estos pasos, debería haber generado con éxito una imagen en miniatura personalizada a partir de su presentación de PowerPoint.

## Conclusión

Generar imágenes en miniatura personalizadas a partir de presentaciones de PowerPoint utilizando Aspose.Slides para .NET es una habilidad valiosa que puede mejorar la experiencia del usuario y la funcionalidad de sus aplicaciones. Si sigue los pasos descritos en este tutorial, podrá crear fácilmente miniaturas personalizadas que cumplan con sus requisitos específicos.

---

## Preguntas frecuentes (Preguntas frecuentes)

### ¿Qué es Aspose.Slides para .NET?
Aspose.Slides para .NET es una poderosa biblioteca que permite a los desarrolladores trabajar con presentaciones de PowerPoint mediante programación en aplicaciones .NET.

### ¿Dónde puedo encontrar la documentación de Aspose.Slides para .NET?
 Puedes encontrar la documentación.[aquí](https://reference.aspose.com/slides/net/).

### ¿Aspose.Slides para .NET es de uso gratuito?
 Aspose.Slides para .NET es una biblioteca comercial. Puede encontrar información sobre precios y licencias.[aquí](https://purchase.aspose.com/buy).

### ¿Necesito conocimientos avanzados de programación para utilizar Aspose.Slides para .NET?
Si bien es beneficioso tener algunos conocimientos de programación .NET, Aspose.Slides para .NET proporciona una API fácil de usar que simplifica el trabajo con presentaciones de PowerPoint.

### ¿Hay soporte técnico disponible para Aspose.Slides para .NET?
 Sí, puedes acceder a soporte técnico y foros comunitarios.[aquí](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Generar miniatura a partir de diapositivas en Notas
linktitle: Generar miniatura a partir de diapositivas en Notas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a generar miniaturas de diapositivas en la sección de notas de su presentación usando Aspose.Slides para .NET. ¡Mejora tu contenido visual!
type: docs
weight: 12
url: /es/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

En el mundo de las presentaciones modernas, el contenido visual es el rey. Crear diapositivas atractivas es esencial para una comunicación eficaz. Una forma de mejorar sus presentaciones es generando miniaturas a partir de diapositivas, especialmente cuando desea enfatizar detalles específicos o compartir una descripción general. Aspose.Slides para .NET es una herramienta poderosa que puede ayudarlo a lograr esto sin problemas. En esta guía paso a paso, lo guiaremos a través del proceso de generar miniaturas de diapositivas en la sección de notas de una presentación usando Aspose.Slides para .NET.

## Requisitos previos

Antes de profundizar en los detalles, debe cumplir con los siguientes requisitos previos:

### 1. Aspose.Slides para .NET

 Asegúrese de tener Aspose.Slides para .NET instalado y configurado. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

### 2. Entorno .NET

Debe tener un entorno de desarrollo .NET listo en su sistema.

### 3. Un archivo de presentación

 Tener un archivo de presentación (por ejemplo,`ThumbnailFromSlideInNotes.pptx`) a partir del cual desea generar miniaturas.

Ahora, dividamos el proceso en pasos:

## Paso 1: importar espacios de nombres

Primero, necesita importar los espacios de nombres necesarios para trabajar con Aspose.Slides. Agregue el siguiente código al comienzo de su script C#:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Paso 2: cargue la presentación

 A continuación, deberás cargar el archivo de presentación que contiene las diapositivas con notas. Utilice el siguiente código para crear una instancia de un`Presentation` clase:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Tu código va aquí
}
```

## Paso 3: acceda a la diapositiva

Puede elegir para qué diapositiva de la presentación desea generar una miniatura. En este ejemplo, accederemos a la primera diapositiva:

```csharp
ISlide sld = pres.Slides[0];
```

## Paso 4: definir las dimensiones deseadas

Especifique las dimensiones (ancho y alto) de la miniatura que desea generar. Por ejemplo:

```csharp
int desiredX = 1200; // Ancho
int desiredY = 800;  // Altura
```

## Paso 5: Calcular los factores de escala

Para asegurarse de que la miniatura se ajuste a las dimensiones deseadas, calcule los factores de escala de la siguiente manera:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Paso 6: crea una miniatura

Ahora, cree una miniatura de imagen a escala completa utilizando los factores de escala calculados:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Paso 7: guarde la miniatura

Finalmente, guarde la miniatura generada como una imagen JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

¡Eso es todo! Ha generado con éxito una miniatura de una diapositiva en la sección de notas de su presentación usando Aspose.Slides para .NET.

## Conclusión

La incorporación de miniaturas en sus presentaciones puede mejorar significativamente su atractivo visual y su efectividad. Aspose.Slides para .NET simplifica este proceso, permitiéndole crear miniaturas personalizadas a partir de sus diapositivas con facilidad.

## Preguntas frecuentes (Preguntas frecuentes)

### ¿En qué formatos puedo guardar las miniaturas generadas?
Puede guardar las miniaturas en varios formatos, incluidos JPEG, PNG y más, según sus requisitos.

### ¿Puedo generar miniaturas para varias diapositivas a la vez?
Sí, puedes recorrer las diapositivas de tu presentación y generar miniaturas para cada una.

### ¿Aspose.Slides para .NET es compatible con diferentes marcos .NET?
Sí, Aspose.Slides para .NET es compatible con varios marcos .NET, incluidos .NET Core y .NET Framework.

### ¿Puedo personalizar la apariencia de las miniaturas generadas?
¡Absolutamente! Aspose.Slides para .NET ofrece opciones para personalizar la apariencia de las miniaturas, como dimensiones, calidad y más.

### ¿Dónde puedo obtener soporte o ayuda adicional con Aspose.Slides para .NET?
 Puede encontrar ayuda e interactuar con la comunidad de Aspose en el[Foro de soporte de Aspose](https://forum.aspose.com/).
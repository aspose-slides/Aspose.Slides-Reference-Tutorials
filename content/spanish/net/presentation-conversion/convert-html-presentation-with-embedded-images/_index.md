---
title: Convertir presentaciones HTML con imágenes incrustadas
linktitle: Convertir presentaciones HTML con imágenes incrustadas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Convierta presentaciones HTML con imágenes incrustadas sin esfuerzo utilizando Aspose.Slides para .NET. Cree, personalice y guarde archivos de PowerPoint sin problemas.
type: docs
weight: 11
url: /es/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---

## 1. Introducción

Aspose.Slides para .NET proporciona una manera conveniente de convertir presentaciones de PowerPoint al formato HTML5 conservando las imágenes incrustadas. Esto puede resultar increíblemente útil para mostrar sus presentaciones en sitios web o aplicaciones web.

## 2. Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio o cualquier entorno de desarrollo C#.
- Aspose.Slides para la biblioteca .NET.
- Una presentación de PowerPoint de muestra con imágenes incrustadas.
- Conocimientos básicos de programación en C#.

## 3. Configurando tu proyecto

Comience creando un nuevo proyecto de C# en su entorno de desarrollo preferido. Asegúrese de tener la biblioteca Aspose.Slides para .NET correctamente referenciada en su proyecto.

## 4. Cargando la presentación fuente

```csharp
string dataDir = "Your Document Directory";
string presentationName = Path.Combine(dataDir, "PresentationDemo.pptx");

using (Presentation pres = new Presentation(presentationName))
{
    // Su código para procesar la presentación va aquí.
}
```

## 5. Configurar las opciones de conversión HTML

 Para configurar las opciones de conversión HTML, puede utilizar el`Html5Options` clase. A continuación se muestra un ejemplo de cómo configurar algunas opciones:

```csharp
Html5Options options = new Html5Options()
{
    EmbedImages = false, // No guarde imágenes en un documento HTML5
    OutputPath = "Your Output Directory" // Establecer la ruta para imágenes externas
};
```

## 6. Creando el directorio de salida

Antes de guardar la presentación en formato HTML5, es una buena práctica crear el directorio de salida si aún no existe:

```csharp
string outFilePath = Path.Combine(outPath, "HTMLConversion");

if (!Directory.Exists(outFilePath))
{
    Directory.CreateDirectory(outFilePath);
}
```

## 7. Guardar la presentación en formato HTML5

Ahora, guardemos la presentación en formato HTML5:

```csharp
pres.Save(Path.Combine(outFilePath, "pres.html"), SaveFormat.Html5, options);
```

## 8. Conclusión

¡Felicidades! Ha convertido con éxito una presentación de PowerPoint con imágenes incrustadas al formato HTML5 utilizando Aspose.Slides para .NET. Esta puede ser una herramienta valiosa para compartir sus presentaciones en línea.

## 9. Preguntas frecuentes

**Q1: Can I customize the appearance of the HTML5 presentation?**
Sí, puedes personalizar la apariencia modificando los archivos HTML y CSS generados por Aspose.Slides.

**Q2: Does Aspose.Slides for .NET support other output formats?**
Sí, admite varios formatos de salida, incluidos PDF, imágenes y más.

**Q3: Are there any limitations to converting presentations with embedded images?**
Si bien Aspose.Slides para .NET es potente, es posible que encuentre algunas limitaciones con presentaciones muy complejas.

**Q4: Is Aspose.Slides for .NET compatible with the latest PowerPoint versions?**
Sí, es compatible con archivos de PowerPoint de diferentes versiones, incluidas las más recientes.

**Q5: Where can I find more documentation and resources for Aspose.Slides for .NET?**
 Para obtener documentación y recursos completos, visite el[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).
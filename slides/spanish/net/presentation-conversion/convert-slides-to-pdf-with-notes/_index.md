---
title: Convertir diapositivas a PDF con notas
linktitle: Convertir diapositivas a PDF con notas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Convierta fácilmente diapositivas de presentación con notas del orador a PDF usando Aspose.Slides para .NET. Preserve el contenido y el contexto sin problemas.
weight: 18
url: /es/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convertir diapositivas a PDF con notas


# Escriba una guía tutorial paso a paso sobre la conversión de diapositivas a PDF con notas usando Aspose.Slides para .NET

¿Está buscando una forma confiable de convertir sus diapositivas de PowerPoint a formato PDF conservando todas las notas importantes? ¡No busque más! En este completo tutorial, lo guiaremos a través del proceso de uso de Aspose.Slides para .NET para realizar esta tarea paso a paso.

## 1. Introducción

Convertir diapositivas de PowerPoint a PDF con notas puede ser una herramienta valiosa para compartir presentaciones y al mismo tiempo garantizar que se conserven el contexto y los comentarios importantes. Aspose.Slides para .NET proporciona una solución poderosa para esta tarea.

## 2. Configurando tu entorno

Antes de sumergirnos en el proceso de codificación, asegúrese de tener configurado el entorno necesario. Necesitarás:

- Visual Studio o su entorno de desarrollo .NET preferido.
- Aspose.Slides para la biblioteca .NET instalada.
- Una presentación de PowerPoint con notas que deseas convertir.

## 3. Cargando la presentación

En su código C#, debe cargar la presentación de PowerPoint que desea convertir. Así es como puedes hacerlo:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Clonación de la diapositiva

Para asegurarse de que su PDF incluya todas las diapositivas necesarias con notas, puede clonarlas de la presentación original. Así es cómo:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Ajustar el tamaño de la diapositiva

Es posible que desees ajustar el tamaño de la diapositiva para que se ajuste a tu PDF. Aspose.Slides para .NET le permite hacer esto con facilidad:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Configurar las opciones de PDF

Para controlar cómo se mostrarán sus notas en el PDF, puede configurar las opciones del PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Guardar como PDF con Notas

Finalmente, puedes guardar tu presentación como PDF con notas:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusión

¡Felicidades! Ha convertido con éxito sus diapositivas de PowerPoint a formato PDF conservando todas las notas importantes. Aspose.Slides para .NET hace que este proceso sea sencillo y eficiente.

## 9. Preguntas frecuentes

### P1: ¿Puedo personalizar el diseño de las notas en el PDF?

 Sí, puedes personalizar el diseño de las notas usando el`INotesCommentsLayoutingOptions` en las opciones de PDF.

### P2: ¿Aspose.Slides para .NET admite otros formatos de salida además de PDF?

Sí, Aspose.Slides para .NET admite varios formatos de salida, incluidos PPTX, DOCX y más.

### P3: ¿Existe una versión de prueba disponible de Aspose.Slides para .NET?

 Sí, puede obtener una prueba gratuita de Aspose.Slides para .NET en[https://releases.aspose.com/](https://releases.aspose.com/).

### P4: ¿Dónde puedo obtener soporte para Aspose.Slides para .NET?

 Puede encontrar apoyo y debates comunitarios en[https://forum.aspose.com/](https://forum.aspose.com/).

### P5: ¿Puedo comprar una licencia temporal de Aspose.Slides para .NET?

 Sí, puede comprar una licencia temporal en[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

En conclusión, al utilizar Aspose.Slides para .NET, puede convertir fácilmente diapositivas de PowerPoint a formato PDF con las notas intactas. Es una herramienta valiosa para los profesionales que necesitan compartir presentaciones con colegas y clientes y al mismo tiempo garantizar que no se pierda el contexto importante.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

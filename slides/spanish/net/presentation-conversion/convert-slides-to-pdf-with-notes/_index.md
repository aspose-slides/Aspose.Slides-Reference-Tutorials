---
"description": "Convierte fácilmente diapositivas de presentaciones con notas del orador a PDF con Aspose.Slides para .NET. Conserva el contenido y el contexto sin problemas."
"linktitle": "Convertir diapositivas a PDF con notas"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Convertir diapositivas a PDF con notas"
"url": "/es/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir diapositivas a PDF con notas


# Escriba una guía tutorial paso a paso sobre cómo convertir diapositivas a PDF con notas usando Aspose.Slides para .NET

¿Buscas una forma fiable de convertir tus diapositivas de PowerPoint a formato PDF y conservar todas las notas importantes? ¡No busques más! En este completo tutorial, te guiaremos paso a paso en el proceso de uso de Aspose.Slides para .NET.

## 1. Introducción

Convertir diapositivas de PowerPoint a PDF con notas puede ser una herramienta valiosa para compartir presentaciones, a la vez que se conserva el contexto y los comentarios importantes. Aspose.Slides para .NET ofrece una solución eficaz para esta tarea.

## 2. Configuración de su entorno

Antes de comenzar el proceso de codificación, asegúrese de tener configurado el entorno necesario. Necesitará:

- Visual Studio o su entorno de desarrollo .NET preferido.
- Biblioteca Aspose.Slides para .NET instalada.
- Una presentación de PowerPoint con notas que desea convertir.

## 3. Carga de la presentación

En tu código C#, necesitas cargar la presentación de PowerPoint que quieres convertir. Así es como puedes hacerlo:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Clonación de la diapositiva

Para asegurarte de que tu PDF incluya todas las diapositivas con notas necesarias, puedes clonarlas de la presentación original. Así es como se hace:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Ajuste del tamaño de la diapositiva

Quizás quieras ajustar el tamaño de la diapositiva para que se ajuste a tu PDF. Aspose.Slides para .NET te permite hacerlo fácilmente:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. Configuración de opciones de PDF

Para controlar cómo se mostrarán sus notas en el PDF, puede configurar las opciones del PDF:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Guardar como PDF con notas

Por último, puedes guardar tu presentación como PDF con notas:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Conclusión

¡Felicitaciones! Ha convertido sus diapositivas de PowerPoint a formato PDF, conservando todas las notas importantes. Aspose.Slides para .NET simplifica y optimiza este proceso.

## 9. Preguntas frecuentes

### P1: ¿Puedo personalizar el diseño de las notas en el PDF?

Sí, puedes personalizar el diseño de las notas usando el `INotesCommentsLayoutingOptions` en las opciones de PDF.

### P2: ¿Aspose.Slides para .NET admite otros formatos de salida además de PDF?

Sí, Aspose.Slides para .NET admite varios formatos de salida, incluidos PPTX, DOCX y más.

### P3: ¿Hay una versión de prueba disponible de Aspose.Slides para .NET?

Sí, puede obtener una prueba gratuita de Aspose.Slides para .NET en [https://releases.aspose.com/](https://releases.aspose.com/).

### P4: ¿Dónde puedo obtener soporte para Aspose.Slides para .NET?

Puede encontrar soporte y debates comunitarios en [https://forum.aspose.com/](https://forum.aspose.com/).

### P5: ¿Puedo comprar una licencia temporal para Aspose.Slides para .NET?

Sí, puedes comprar una licencia temporal en [https://purchase.aspose.com/licencia-temporal/](https://purchase.aspose.com/temporary-license/).

En conclusión, con Aspose.Slides para .NET, puede convertir fácilmente diapositivas de PowerPoint a formato PDF con las notas intactas. Es una herramienta valiosa para profesionales que necesitan compartir presentaciones con colegas y clientes, garantizando que no se pierda el contexto importante.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Aprenda a conservar las fuentes originales al convertir presentaciones a HTML con Aspose.Slides para .NET. Garantice la consistencia de las fuentes y el impacto visual sin esfuerzo."
"linktitle": "Conservación de fuentes originales&#58; convertir presentaciones a HTML"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Conservación de fuentes originales&#58; convertir presentaciones a HTML"
"url": "/es/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conservación de fuentes originales: convertir presentaciones a HTML


En esta guía completa, le guiaremos a través del proceso de conservación de las fuentes originales al convertir una presentación a HTML con Aspose.Slides para .NET. Le proporcionaremos el código fuente de C# necesario y explicaremos cada paso en detalle. Al finalizar este tutorial, podrá garantizar que las fuentes de su documento HTML convertido se mantengan fieles a la presentación original.

## 1. Introducción

Al convertir presentaciones de PowerPoint a HTML, es fundamental conservar las fuentes originales para garantizar la consistencia visual del contenido. Aspose.Slides para .NET ofrece una solución eficaz para lograrlo. En este tutorial, le guiaremos por los pasos necesarios para conservar las fuentes originales durante el proceso de conversión.

## 2. Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Visual Studio instalado en su máquina.
- Se agregó la biblioteca Aspose.Slides para .NET a su proyecto.

## 3. Configuración de su proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue la biblioteca Aspose.Slides para .NET como referencia.

## 4. Carga de la presentación

Utilice el siguiente código para cargar su presentación de PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Tu código aquí
}
```

Reemplazar `"Your Document Directory"` con la ruta a su archivo de presentación.

## 5. Exclusión de fuentes predeterminadas

Para excluir fuentes predeterminadas como Calibri y Arial, utilice el siguiente código:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Puede personalizar esta lista según sea necesario.

## 6. Incorporación de todas las fuentes

A continuación, incrustaremos todas las fuentes en el documento HTML. Esto garantiza que se conserven las fuentes originales. Use el siguiente código:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Guardar como HTML

Ahora, guarde la presentación como un documento HTML con fuentes incrustadas:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Reemplazar `"output.html"` con el nombre de archivo de salida deseado.

## 8. Conclusión

En este tutorial, mostramos cómo conservar las fuentes originales al convertir una presentación de PowerPoint a HTML con Aspose.Slides para .NET. Siguiendo estos pasos, puede garantizar que su documento HTML convertido conserve la integridad visual de la presentación original.

## 9. Preguntas frecuentes

### P1: ¿Puedo personalizar la lista de fuentes excluidas?

Sí, puedes. Modificar el `fontNameExcludeList` matriz para incluir o excluir fuentes específicas según sus requisitos.

### P2: ¿Qué pasa si no quiero incrustar todas las fuentes?

Si solo desea incrustar fuentes específicas, puede modificar el código según corresponda. Consulte la documentación de Aspose.Slides para .NET para obtener más información.

### P3: ¿Existen requisitos de licencia para utilizar Aspose.Slides para .NET?

Sí, es posible que necesite una licencia válida para usar Aspose.Slides para .NET en sus proyectos. Consulte el sitio web de Aspose para obtener información sobre licencias.

### P4: ¿Puedo convertir otros formatos de archivos a HTML usando Aspose.Slides para .NET?

Aspose.Slides para .NET se centra principalmente en presentaciones de PowerPoint. Para convertir otros formatos de archivo a HTML, puede que necesite explorar otros productos Aspose diseñados para esos formatos.

### P5: ¿Dónde puedo acceder a recursos y apoyo adicionales?

Puede encontrar más documentación, tutoriales y soporte en el sitio web de Aspose. Visite [Documentación de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/) para obtener información detallada.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
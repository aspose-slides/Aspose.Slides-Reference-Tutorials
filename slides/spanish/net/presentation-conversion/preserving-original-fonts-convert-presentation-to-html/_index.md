---
title: Preservar las fuentes originales convertir la presentación a HTML
linktitle: Preservar las fuentes originales convertir la presentación a HTML
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda cómo conservar las fuentes originales mientras convierte presentaciones a HTML usando Aspose.Slides para .NET. Garantice la coherencia de las fuentes y el impacto visual sin esfuerzo.
weight: 14
url: /es/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Preservar las fuentes originales convertir la presentación a HTML


En esta guía completa, lo guiaremos a través del proceso de conservación de fuentes originales al convertir una presentación a HTML usando Aspose.Slides para .NET. Le proporcionaremos el código fuente C# necesario y le explicaremos cada paso en detalle. Al final de este tutorial, podrá asegurarse de que las fuentes de su documento HTML convertido permanezcan fieles a la presentación original.

## 1. Introducción

Al convertir presentaciones de PowerPoint a HTML, es fundamental mantener las fuentes originales para garantizar la coherencia visual de su contenido. Aspose.Slides para .NET proporciona una solución poderosa para lograr esto. En este tutorial, lo guiaremos a través de los pasos necesarios para conservar las fuentes originales durante el proceso de conversión.

## 2. Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

- Visual Studio instalado en su máquina.
- Biblioteca Aspose.Slides para .NET agregada a su proyecto.

## 3. Configurando tu proyecto

Para comenzar, cree un nuevo proyecto en Visual Studio y agregue la biblioteca Aspose.Slides para .NET como referencia.

## 4. Cargando la presentación

Utilice el siguiente código para cargar su presentación de PowerPoint:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Tu código aquí
}
```

 Reemplazar`"Your Document Directory"` con la ruta a su archivo de presentación.

## 5. Excluyendo fuentes predeterminadas

Para excluir fuentes predeterminadas como Calibri y Arial, use el siguiente código:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Puede personalizar esta lista según sea necesario.

## 6. Incrustar todas las fuentes

A continuación, incrustaremos todas las fuentes en el documento HTML. Esto garantiza que se conserven las fuentes originales. Utilice el siguiente código:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Guardar como HTML

Ahora, guarda la presentación como un documento HTML con fuentes incrustadas:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Reemplazar`"output.html"` con el nombre del archivo de salida que desee.

## 8. Conclusión

En este tutorial, hemos demostrado cómo conservar las fuentes originales al convertir una presentación de PowerPoint a HTML usando Aspose.Slides para .NET. Si sigue estos pasos, puede asegurarse de que su documento HTML convertido mantenga la integridad visual de la presentación original.

## 9. Preguntas frecuentes

### P1: ¿Puedo personalizar la lista de fuentes excluidas?

 Sí tu puedes. Modificar el`fontNameExcludeList`matriz para incluir o excluir fuentes específicas según sus requisitos.

### P2: ¿Qué pasa si no quiero incrustar todas las fuentes?

Si desea incrustar solo fuentes específicas, puede modificar el código en consecuencia. Consulte la documentación de Aspose.Slides para .NET para obtener más detalles.

### P3: ¿Existe algún requisito de licencia para utilizar Aspose.Slides para .NET?

Sí, es posible que necesite una licencia válida para utilizar Aspose.Slides para .NET en sus proyectos. Consulte el sitio web de Aspose para obtener información sobre la licencia.

### P4: ¿Puedo convertir otros formatos de archivo a HTML usando Aspose.Slides para .NET?

Aspose.Slides para .NET se centra principalmente en presentaciones de PowerPoint. Para convertir otros formatos de archivo a HTML, es posible que necesite explorar otros productos Aspose diseñados para esos formatos.

### P5: ¿Dónde puedo acceder a recursos y soporte adicionales?

 Puede encontrar más documentación, tutoriales y soporte en el sitio web de Aspose. Visita[Documentación de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/) para obtener información detallada.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

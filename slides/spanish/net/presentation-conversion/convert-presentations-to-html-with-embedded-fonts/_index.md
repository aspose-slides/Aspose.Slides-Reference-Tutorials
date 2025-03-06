---
title: Convierta presentaciones a HTML con fuentes integradas
linktitle: Convierta presentaciones a HTML con fuentes integradas
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Convierta presentaciones de PowerPoint a HTML con fuentes incrustadas usando Aspose.Slides para .NET. Mantenga la originalidad sin problemas.
weight: 13
url: /es/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Convierta presentaciones a HTML con fuentes integradas


En la era digital actual, compartir presentaciones y documentos en línea se ha convertido en una práctica común. Sin embargo, un desafío que surge a menudo es garantizar que las fuentes se muestren correctamente al convertir presentaciones a HTML. Este tutorial paso a paso lo guiará a través del proceso de uso de Aspose.Slides para .NET para convertir presentaciones a HTML con fuentes incrustadas, asegurando que sus documentos se vean tal como usted esperaba.

## Introducción a Aspose.Slides para .NET

Antes de sumergirnos en el tutorial, presentemos brevemente Aspose.Slides para .NET. Es una poderosa biblioteca que permite a los desarrolladores trabajar con presentaciones de PowerPoint en aplicaciones .NET. Con Aspose.Slides, puede crear, modificar y convertir archivos de PowerPoint mediante programación.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Slides para .NET: debe tener la biblioteca Aspose.Slides instalada en su proyecto. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

## Paso 1: configura tu proyecto

1. Cree un nuevo proyecto o abra uno existente en su entorno de desarrollo .NET preferido.

2. Agregue una referencia a la biblioteca Aspose.Slides en su proyecto.

3. Importe los espacios de nombres necesarios en su código:

   ```csharp
   using Aspose.Slides;
   ```

## Paso 2: cargue su presentación

 Para comenzar, debes cargar la presentación que deseas convertir a HTML. Reemplazar`"Your Document Directory"` con el directorio real donde se encuentra su archivo de presentación.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Tu código va aquí
}
```

## Paso 3: excluir las fuentes de presentación predeterminadas

En este paso, puede especificar cualquier fuente de presentación predeterminada que desee excluir de la incrustación. Esto puede ayudar a optimizar el tamaño del archivo HTML resultante.

```csharp
string[] fontNameExcludeList = { };
```

## Paso 4: elija un controlador HTML

Ahora tienes dos opciones para incrustar fuentes en HTML:

### Opción 1: incrustar todas las fuentes

 Para incrustar todas las fuentes utilizadas en la presentación, utilice el`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opción 2: vincular todas las fuentes

 Para vincular todas las fuentes utilizadas en la presentación, utilice el`LinkAllFontsHtmlController`. Debe especificar el directorio donde se encuentran las fuentes en su sistema.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Paso 5: definir las opciones HTML

 Crear un`HtmlOptions` objeto y configure el formateador HTML al que seleccionó en el paso anterior.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Utilice embedFontsController para incrustar todas las fuentes
};
```

## Paso 6: guardar como HTML

 Finalmente, guarde la presentación como un archivo HTML. Puedes elegir cualquiera`SaveFormat.Html` o`SaveFormat.Html5` dependiendo de sus requisitos.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Conclusión

¡Felicidades! Ha convertido con éxito su presentación a HTML con fuentes incrustadas usando Aspose.Slides para .NET. Esto garantiza que sus fuentes se mostrarán correctamente al compartir sus presentaciones en línea.

Ahora puede compartir fácilmente sus presentaciones bellamente formateadas con confianza, sabiendo que su audiencia las verá exactamente como usted esperaba.

 Para obtener más información y referencias API detalladas, consulte la[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/).

## Preguntas frecuentes

### 1. ¿Puedo convertir presentaciones de PowerPoint a HTML usando Aspose.Slides para .NET en modo por lotes?

Sí, puede convertir por lotes varias presentaciones a HTML utilizando Aspose.Slides para .NET recorriendo sus archivos de presentación y aplicando el proceso de conversión a cada uno.

### 2. ¿Existe alguna forma de personalizar la apariencia de la salida HTML?

¡Ciertamente! Aspose.Slides para .NET proporciona varias opciones para personalizar la apariencia y el formato de la salida HTML, como ajustar colores, fuentes y diseño.

### 3. ¿Existe alguna limitación para incrustar fuentes en HTML usando Aspose.Slides para .NET?

Si bien Aspose.Slides para .NET ofrece excelentes capacidades de incrustación de fuentes, tenga en cuenta que el tamaño de sus archivos HTML puede aumentar al incrustar fuentes. Asegúrese de optimizar sus opciones de fuente para el uso web.

### 4. ¿Puedo convertir presentaciones de PowerPoint a otros formatos con Aspose.Slides para .NET?

Sí, Aspose.Slides para .NET admite una amplia gama de formatos de salida, incluidos PDF, imágenes y más. Puede convertir fácilmente sus presentaciones al formato que elija.

### 5. ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Slides para .NET?

 Puede acceder a una gran cantidad de recursos, incluida documentación, en el[Aspose.Slides para referencia de API .NET](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

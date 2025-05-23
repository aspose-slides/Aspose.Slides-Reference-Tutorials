---
"description": "Convierte presentaciones de PowerPoint a HTML con fuentes incrustadas usando Aspose.Slides para .NET. Mantén la originalidad sin interrupciones."
"linktitle": "Convertir presentaciones a HTML con fuentes integradas"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Convertir presentaciones a HTML con fuentes integradas"
"url": "/es/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Convertir presentaciones a HTML con fuentes integradas


En la era digital actual, compartir presentaciones y documentos en línea se ha vuelto común. Sin embargo, un desafío frecuente es asegurar que las fuentes se muestren correctamente al convertir presentaciones a HTML. Este tutorial paso a paso le guiará en el proceso de usar Aspose.Slides para .NET para convertir presentaciones a HTML con fuentes incrustadas, garantizando que sus documentos se vean tal como usted desea.

## Introducción a Aspose.Slides para .NET

Antes de profundizar en el tutorial, presentemos brevemente Aspose.Slides para .NET. Es una potente biblioteca que permite a los desarrolladores trabajar con presentaciones de PowerPoint en aplicaciones .NET. Con Aspose.Slides, puede crear, modificar y convertir archivos de PowerPoint mediante programación.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

- Aspose.Slides para .NET: Debe tener la biblioteca Aspose.Slides instalada en su proyecto. Puede descargarla desde [aquí](https://releases.aspose.com/slides/net/).

## Paso 1: Configura tu proyecto

1. Cree un nuevo proyecto o abra uno existente en su entorno de desarrollo .NET preferido.

2. Agregue una referencia a la biblioteca Aspose.Slides en su proyecto.

3. Importa los espacios de nombres necesarios en tu código:

   ```csharp
   using Aspose.Slides;
   ```

## Paso 2: Cargue su presentación

Para comenzar, debes cargar la presentación que quieres convertir a HTML. Reemplazar `"Your Document Directory"` con el directorio real donde se encuentra su archivo de presentación.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Tu código va aquí
}
```

## Paso 3: Excluir fuentes de presentación predeterminadas

En este paso, puede especificar las fuentes de presentación predeterminadas que desea excluir de la incrustación. Esto puede ayudar a optimizar el tamaño del archivo HTML resultante.

```csharp
string[] fontNameExcludeList = { };
```

## Paso 4: Elija un controlador HTML

Ahora, tienes dos opciones para incrustar fuentes en el HTML:

### Opción 1: Incrustar todas las fuentes

Para incrustar todas las fuentes utilizadas en la presentación, utilice el `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Opción 2: Vincular todas las fuentes

Para vincular todas las fuentes utilizadas en la presentación, utilice el `LinkAllFontsHtmlController`Debes especificar el directorio donde se encuentran las fuentes en tu sistema.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Paso 5: Definir opciones HTML

Crear un `HtmlOptions` objeto y configure el formateador HTML en el que seleccionó en el paso anterior.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Utilice embedFontsController para incrustar todas las fuentes
};
```

## Paso 6: Guardar como HTML

Finalmente, guarde la presentación como archivo HTML. Puede elegir entre `SaveFomat.Html` or `SaveFormat.Html5` dependiendo de sus necesidades.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Conclusión

¡Felicitaciones! Has convertido tu presentación a HTML con fuentes incrustadas usando Aspose.Slides para .NET. Esto garantiza que tus fuentes se muestren correctamente al compartir tus presentaciones en línea.

Ahora, puede compartir fácilmente sus presentaciones bellamente formateadas con confianza, sabiendo que su audiencia las verá exactamente como usted lo desea.

Para obtener más información y referencias API detalladas, consulte [Documentación de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).

## Preguntas frecuentes

### 1. ¿Puedo convertir presentaciones de PowerPoint a HTML usando Aspose.Slides para .NET en modo por lotes?

Sí, puedes convertir por lotes varias presentaciones a HTML usando Aspose.Slides para .NET recorriendo tus archivos de presentación y aplicando el proceso de conversión a cada uno.

### 2. ¿Hay alguna forma de personalizar la apariencia de la salida HTML?

¡Por supuesto! Aspose.Slides para .NET ofrece varias opciones para personalizar la apariencia y el formato del HTML, como ajustar colores, fuentes y diseño.

### 3. ¿Existen limitaciones para incrustar fuentes en HTML usando Aspose.Slides para .NET?

Aunque Aspose.Slides para .NET ofrece excelentes funciones de incrustación de fuentes, tenga en cuenta que el tamaño de sus archivos HTML puede aumentar al incrustarlas. Asegúrese de optimizar sus fuentes para el uso web.

### 4. ¿Puedo convertir presentaciones de PowerPoint a otros formatos con Aspose.Slides para .NET?

Sí, Aspose.Slides para .NET admite una amplia gama de formatos de salida, como PDF, imágenes y más. Puedes convertir fácilmente tus presentaciones al formato que prefieras.

### 5. ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Slides para .NET?

Puede acceder a una gran cantidad de recursos, incluida documentación, en [Referencia de la API de Aspose.Slides para .NET](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
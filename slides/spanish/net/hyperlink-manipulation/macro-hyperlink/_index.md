---
title: Cómo configurar un clic en un hipervínculo macro en Aspose.Slides para .NET
linktitle: Gestión de hipervínculos mediante macros
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a configurar hipervínculos macro en sus presentaciones con Aspose.Slides para .NET. Mejore la interactividad y atraiga a su audiencia.
weight: 13
url: /es/net/hyperlink-manipulation/macro-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


En el mundo del desarrollo de software moderno, la creación de presentaciones dinámicas e interactivas es un aspecto clave. Aspose.Slides para .NET es una poderosa biblioteca que le permite trabajar con presentaciones sin problemas. Ya sea que esté creando una presentación comercial o una presentación de diapositivas educativa, la capacidad de configurar clics en hipervínculos macro puede mejorar enormemente la experiencia del usuario. En esta guía paso a paso, lo guiaremos a través del proceso de configuración de un clic en un hipervínculo macro usando Aspose.Slides para .NET. 

## Requisitos previos

Antes de sumergirnos en el tutorial paso a paso, existen algunos requisitos previos que debe cumplir:

1.Visual Studio: asegúrese de tener Visual Studio instalado en su computadora, ya que este será nuestro entorno de desarrollo.

 2.Aspose.Slides para .NET: necesitará tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarlo desde[aquí](https://releases.aspose.com/slides/net/).

3.Conocimientos básicos de C#: La familiaridad con el lenguaje de programación C# es esencial para seguir este tutorial.

## Importar espacios de nombres

En el primer paso, importemos los espacios de nombres necesarios para trabajar con Aspose.Slides:

### Paso 1: importar espacios de nombres

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Hemos importado el`Aspose.Slides` espacio de nombres, que es el espacio de nombres principal para trabajar con presentaciones, y el`Aspose.Slides.Export` espacio de nombres.

## Configuración de clic en hipervínculo macro

Ahora, pasemos a la parte principal de este tutorial: configurar un clic de hipervínculo macro en su presentación.

### Paso 2: Inicializar la presentación

Primero, necesitamos inicializar una nueva presentación.

```csharp
using (Presentation presentation = new Presentation())
{
    // Tu código irá aquí.
}
```

Dentro de esta declaración de uso, crea un nuevo objeto de presentación y realiza todas sus operaciones dentro de él.

### Paso 3: agregue una autoforma

Para establecer un clic en un hipervínculo de macro, necesitará un objeto en el que el usuario pueda hacer clic. En este ejemplo, usaremos una autoforma como elemento en el que se puede hacer clic.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Aquí, creamos una Autoforma con el tipo "BlankButton" en coordenadas específicas (20, 20) y con dimensiones de 80x30. Puede personalizar estos valores para adaptarlos al diseño de su presentación.

### Paso 4: Establecer clic en el hipervínculo macro

Ahora viene la parte donde configuras el clic del hipervínculo macro. Deberá proporcionar un nombre de macro como parámetro.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

En este ejemplo, hemos configurado el clic del hipervínculo de la macro en "TestMacro". Cuando el usuario hace clic en la Autoforma, se activará esta macro.

### Paso 5: recuperar información

También puede recuperar información sobre el hipervínculo que ha establecido.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Estas líneas de código le permiten imprimir la URL externa y el tipo de acción del hipervínculo.

¡Y eso es! Ha configurado con éxito un clic en un hipervínculo macro en su presentación usando Aspose.Slides para .NET.

## Conclusión

En este tutorial, hemos aprendido cómo configurar un clic en un hipervínculo macro en su presentación usando Aspose.Slides para .NET. Esta puede ser una característica valiosa para crear presentaciones interactivas y dinámicas que atraigan a su audiencia. Con Aspose.Slides para .NET, tienes una poderosa herramienta a tu disposición para llevar el desarrollo de tu presentación al siguiente nivel.

 Ahora es el momento de experimentar y crear presentaciones cautivadoras con hipervínculos macro personalizados. Siéntete libre de explorar el[Aspose.Slides para la documentación de .NET](https://reference.aspose.com/slides/net/) para obtener información y posibilidades más detalladas.

## Preguntas frecuentes (Preguntas frecuentes)

### ¿Puedo usar Aspose.Slides para .NET con otros lenguajes de programación?
Aspose.Slides está diseñado principalmente para .NET, pero Aspose ofrece bibliotecas similares para otros lenguajes de programación, como Java.

### ¿Aspose.Slides para .NET es una biblioteca gratuita?
Aspose.Slides para .NET es una biblioteca comercial con una versión de prueba gratuita disponible. Puedes descargarlo desde[aquí](https://releases.aspose.com/).

### ¿Existe alguna limitación en el uso de macros en presentaciones creadas con Aspose.Slides para .NET?
Aspose.Slides para .NET le permite trabajar con macros, pero debe tener en cuenta las consideraciones de seguridad y compatibilidad al utilizar macros en presentaciones.

### ¿Puedo personalizar la apariencia de la autoforma utilizada para el hipervínculo?
Sí, puedes personalizar la apariencia de la autoforma ajustando sus propiedades, como tamaño, color y fuente.

### ¿Dónde puedo obtener ayuda o soporte para Aspose.Slides para .NET?
 Si tiene problemas o preguntas, puede buscar ayuda en el foro de soporte de Aspose[aquí](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

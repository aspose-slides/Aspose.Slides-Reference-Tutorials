---
"date": "2025-04-16"
"description": "Aprenda a configurar atributos de idioma para texto dentro de formas con Aspose.Slides para .NET. Esta guía explica cómo agregar formas automáticas, configurar identificadores de idioma y guardar presentaciones."
"title": "Cómo configurar el idioma en las formas de PowerPoint con Aspose.Slides para .NET"
"url": "/es/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo configurar el idioma en las formas de PowerPoint con Aspose.Slides para .NET

En el mundo de las presentaciones digitales, garantizar que el contenido sea accesible y tenga el formato correcto en diferentes idiomas puede ser un desafío. Con Aspose.Slides para .NET, puede configurar fácilmente los atributos de idioma del texto dentro de las formas de las diapositivas de PowerPoint. Esta función es especialmente útil al preparar documentos multilingües o al garantizar la coherencia en las comunicaciones globales.

**Lo que aprenderás:**
- Agregar formas automáticas e insertar texto en ellas.
- Establecer el ID de idioma para partes de texto usando Aspose.Slides.
- Guardar presentaciones con configuraciones personalizadas.

Veamos ahora cómo puedes implementar esta función sin problemas.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

- **Bibliotecas y dependencias**Necesita tener instalado Aspose.Slides para .NET. Esta biblioteca es esencial para manipular presentaciones de PowerPoint en C#.
  
- **Configuración del entorno**:Se requiere un entorno de desarrollo con .NET Core o .NET Framework.

- **Requisitos previos de conocimiento**Será útil estar familiarizado con los conceptos básicos de programación en C# y comprender los principios de programación orientada a objetos.

## Configuración de Aspose.Slides para .NET

Para empezar, necesitas instalar la biblioteca Aspose.Slides. Puedes hacerlo mediante uno de los siguientes métodos:

**CLI de .NET**
```shell
dotnet add package Aspose.Slides
```

**Administrador de paquetes**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet**
Busque "Aspose.Slides" e instale la última versión.

### Adquisición de licencias

Puede comenzar con una prueba gratuita descargando una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/)Para uso continuo, considere comprar una licencia a través de [este enlace](https://purchase.aspose.com/buy).

Una vez que tenga su configuración lista, inicialice Aspose.Slides en su proyecto:

```csharp
using Aspose.Slides;
```

## Guía de implementación

Ahora que estamos configurados, implementemos la función para configurar el idioma del texto de forma.

### Descripción general de funciones: Configuración del idioma del texto de la forma

Esta función permite especificar el idioma del texto dentro de una forma de PowerPoint. Al configurar el ID de idioma, se garantiza que la corrección ortográfica y otras funciones específicas del idioma se apliquen correctamente.

#### Paso 1: Inicializar la presentación

Comience creando una instancia de la `Presentation` clase.

```csharp
using (Presentation pres = new Presentation())
{
    // Tu código aquí
}
```

Esto inicializa un nuevo objeto de presentación de PowerPoint que manipularemos.

#### Paso 2: Agregar forma automática y marco de texto

Añade una forma rectangular a tu diapositiva e inserta texto en ella:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Aquí, `AddAutoShape` Añade un rectángulo a la primera diapositiva. Los parámetros definen su posición y tamaño.

#### Paso 3: Establecer el ID del idioma

Establezca el idioma para la parte de texto dentro de la forma:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Esto asigna el inglés (Reino Unido) como el idioma para la corrección ortográfica.

#### Paso 4: Guardar la presentación

Por último, guarde su presentación en una ruta específica:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
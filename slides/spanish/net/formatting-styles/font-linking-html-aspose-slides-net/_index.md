---
"date": "2025-04-15"
"description": "Aprenda cómo garantizar una representación de fuentes consistente al convertir presentaciones a HTML usando Aspose.Slides para .NET insertando fuentes directamente."
"title": "Cómo vincular fuentes en HTML con Aspose.Slides para .NET&#58; guía paso a paso"
"url": "/es/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo vincular fuentes en HTML con Aspose.Slides para .NET

## Introducción

Convertir presentaciones a HTML manteniendo una representación de fuentes consistente en todas las plataformas puede ser un desafío. **Aspose.Slides para .NET** ofrece una solución perfecta que le permite vincular todas las fuentes utilizadas en una presentación directamente dentro de la salida HTML a través de archivos de fuentes integrados.

En este tutorial, exploraremos cómo implementar la vinculación de fuentes usando Aspose.Slides para .NET y garantizar la coherencia del diseño en diferentes plataformas. 

**Lo que aprenderás:**
- Configuración de su entorno con Aspose.Slides para .NET
- Vinculación de fuentes en la conversión HTML
- Escritura de controladores personalizados para la incrustación de fuentes
- Aplicaciones prácticas y consideraciones de rendimiento

Vamos a profundizar en los pasos necesarios para lograrlo.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:

### Bibliotecas y dependencias requeridas
- **Aspose.Slides para .NET** biblioteca: el componente principal para nuestra implementación.

### Requisitos de configuración del entorno
- Un entorno de desarrollo con .NET Framework o .NET Core instalado.

### Requisitos previos de conocimiento
- Comprensión básica de programación en C#.
- Familiaridad con HTML y CSS, particularmente el `@font-face` regla.

## Configuración de Aspose.Slides para .NET

Para usar Aspose.Slides en su proyecto .NET, necesita instalar la biblioteca. Aquí tiene varios métodos:

### Uso de la CLI de .NET
```bash
dotnet add package Aspose.Slides
```

### Uso de la consola del administrador de paquetes
```powershell
Install-Package Aspose.Slides
```

### A través de la interfaz de usuario del administrador de paquetes NuGet
- Abra su proyecto en Visual Studio.
- Vaya al "Administrador de paquetes NuGet".
- Busque "Aspose.Slides" e instale la última versión.

### Pasos para la adquisición de la licencia
Puede obtener una licencia de prueba gratuita para probar todas las funciones sin limitaciones siguiendo estos pasos:
1. **Prueba gratuita**: Descargar una licencia temporal [aquí](https://releases.aspose.com/slides/net/).
2. **Licencia temporal**:Solicitar un acceso ampliado [aquí](https://purchase.aspose.com/temporary-license/).
3. **Compra**:Para obtener la funcionalidad completa, compre una licencia [aquí](https://purchase.aspose.com/buy).

### Inicialización y configuración básicas
```csharp
// Crear una instancia de la clase Licencia
easpose.slides.License license = new aspose.slides.License();

// Aplicar la licencia desde la ruta del archivo
license.SetLicense("Aspose.Slides.lic");
```

## Guía de implementación

Ahora, implementemos la vinculación de fuentes en la conversión HTML usando **Aspose.Slides para .NET**.

### Descripción general de funciones: Vinculación de fuentes en la conversión HTML
Esta función garantiza que todas las fuentes utilizadas en una presentación se vinculen directamente en el archivo HTML resultante mediante la incrustación de los archivos de fuente. Este método proporciona una solución robusta para mantener la coherencia del diseño en diferentes navegadores y plataformas.

#### Paso 1: Crear el controlador personalizado
Crear una clase de controlador personalizada `LinkAllFontsHtmlController` que hereda de `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Establezca el directorio donde se almacenarán los archivos de fuentes
    }
}
```
#### Paso 2: Implementar el método de escritura de fuentes
El `WriteFont` El método escribe los datos de la fuente en un archivo y genera el código HTML correspondiente para incrustarlo:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Determine el nombre de la fuente a utilizar, prefiriendo fuentes sustitutas si están disponibles.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Construya una ruta de archivo para el archivo de fuente .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Escribe los datos de la fuente en la ruta de archivo especificada.
    File.WriteAllBytes(path, fontData);

    // Genere un bloque de estilo HTML incorporando la fuente usando la regla @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
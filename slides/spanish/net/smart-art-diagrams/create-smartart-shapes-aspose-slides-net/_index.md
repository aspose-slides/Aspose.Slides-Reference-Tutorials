---
"date": "2025-04-16"
"description": "Aprenda a crear gráficos SmartArt dinámicos en PowerPoint con Aspose.Slides para .NET. Mejore sus presentaciones con esta guía completa."
"title": "Cree formas SmartArt en PowerPoint con Aspose.Slides para .NET&#58; guía paso a paso"
"url": "/es/net/smart-art-diagrams/create-smartart-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear formas SmartArt en PowerPoint con Aspose.Slides para .NET: guía paso a paso

## Introducción

Mejore sus presentaciones de PowerPoint integrando gráficos SmartArt dinámicos con C#. Con Aspose.Slides para .NET, puede crear y administrar fácilmente formas SmartArt en sus diapositivas. Esta guía le guiará en el proceso de configuración e implementación de SmartArt con Aspose.Slides para .NET.

**Lo que aprenderás:**
- Configuración de su entorno con Aspose.Slides para .NET
- Crear una forma SmartArt dentro de una diapositiva de PowerPoint
- Administrar directorios de manera eficaz en su código

## Prerrequisitos (H2)

Para implementar con éxito esta solución, asegúrese de tener:
- **Bibliotecas requeridas**:Aspose.Slides para .NET (versión 21.11 o posterior recomendada)
- **Entorno de desarrollo**:.NET Core o .NET Framework
- **Conocimientos básicos**:Familiaridad con C# y operaciones del sistema de archivos

## Configuración de Aspose.Slides para .NET (H2)

### Instalación

Comience instalando Aspose.Slides utilizando uno de los siguientes métodos:

**CLI de .NET**
```bash
dotnet add package Aspose.Slides
```

**Consola del administrador de paquetes en Visual Studio**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet**
1. Abra el Administrador de paquetes NuGet.
2. Busque "Aspose.Slides" e instale la última versión.

### Adquisición de licencias
- **Prueba gratuita**:Descargar una licencia temporal desde [aquí](https://purchase.aspose.com/temporary-license/) para evaluar todas las capacidades de Aspose.Slides.
- **Compra**:Para uso continuo, compre una licencia a través de [este enlace](https://purchase.aspose.com/buy).

Una vez que tenga su archivo de licencia, inicialícelo en su aplicación de la siguiente manera:
```csharp
License license = new License();
license.SetLicense("Aspose.Slides.lic");
```

## Guía de implementación (H2)

### Función: Crear forma SmartArt (H2)

Esta función le permite agregar gráficos SmartArt visualmente atractivos a sus diapositivas de PowerPoint mediante programación.

#### Descripción general del proceso (H3)
Comenzaremos configurando un directorio, creando un objeto de presentación y luego agregando una forma SmartArt.

#### Tutorial del código (H3)
1. **Gestión de directorios**
   Asegúrese de que su directorio de documentos exista o créelo si es necesario:
   ```csharp
   string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Definir la ruta del directorio del documento de destino
   bool isExists = Directory.Exists(dataDir); // Comprobar si el directorio existe
   if (!isExists) 
       Directory.CreateDirectory(dataDir); // Crea el directorio si no existe
   ```

2. **Crear una nueva presentación**
   Inicializar una nueva presentación y acceder a su primera diapositiva:
   ```csharp
   using (Presentation pres = new Presentation())
   {
       ISlide slide = pres.Slides[0]; // Acceda a la primera diapositiva
   ```
   
3. **Cómo agregar SmartArt a la diapositiva**
   Agregue una forma SmartArt en las coordenadas especificadas con las dimensiones y el tipo de diseño deseados:
   ```csharp
   // Agregar una forma SmartArt usando el diseño BasicBlockList
   ISmartArt smart = slide.Shapes.AddSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);
   ```

4. **Guardar la presentación**
   Por último, guarde su presentación en el directorio deseado:
   ```csharp
   pres.Save(dataDir + "SimpleSmartArt_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
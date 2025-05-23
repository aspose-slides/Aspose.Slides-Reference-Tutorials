---
"date": "2025-04-15"
"description": "Aprenda a agregar gráficos circulares mediante programación a sus presentaciones con Aspose.Slides para .NET, mejorando la visualización de datos sin esfuerzo."
"title": "Cree un gráfico circular en PowerPoint con Aspose.Slides para .NET"
"url": "/es/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear y agregar un gráfico circular a una presentación usando Aspose.Slides para .NET
## Introducción
Crear presentaciones atractivas a menudo implica más que solo texto; elementos visuales como gráficos pueden mejorar significativamente el impacto de la narrativa de datos. Si desea agregar gráficos circulares dinámicos a sus presentaciones de PowerPoint mediante programación, **Aspose.Slides para .NET** Es una herramienta potente que facilita y agiliza esta tarea. Este tutorial le guiará en el proceso de agregar un gráfico circular a una diapositiva de presentación y configurarlo con fuentes de datos externas.

### Lo que aprenderás
- Cómo crear una nueva presentación usando Aspose.Slides para .NET
- Cómo agregar un gráfico circular a su primera diapositiva
- Configurar la URL de un libro de trabajo externo como fuente de datos para su gráfico
- Guardar su presentación en formato PPTX
Veamos cómo puedes lograr esto con facilidad, comenzando con los requisitos previos.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente listo:
- **Aspose.Slides para .NET** Biblioteca instalada. Necesitará una versión compatible con .NET Framework o .NET Core/.NET 5 o superior.
- Conocimientos básicos de programación en C# y familiaridad con Visual Studio IDE.
- Un entorno de desarrollo configurado en su máquina (Windows, macOS o Linux).
## Configuración de Aspose.Slides para .NET
### Instrucciones de instalación
Aspose.Slides para .NET se puede agregar a su proyecto mediante varios métodos:
**CLI de .NET**
```shell
dotnet add package Aspose.Slides
```
**Consola del administrador de paquetes**
```powershell
Install-Package Aspose.Slides
```
**Interfaz de usuario del administrador de paquetes NuGet**
1. Abra el Administrador de paquetes NuGet en Visual Studio.
2. Busca "Aspose.Slides".
3. Instalar la última versión.
### Adquisición de licencias
Para usar Aspose.Slides, puede comenzar con una licencia de prueba gratuita para explorar sus funciones sin limitaciones. Para entornos de producción, considere comprar una licencia comercial o adquirir una temporal para realizar pruebas más extensas. Visite [Página de compra de Aspose](https://purchase.aspose.com/buy) Para más detalles.
### Inicialización básica
Para utilizar Aspose.Slides en su proyecto, debe inicializarlo con su licencia si está disponible:
```csharp
// Inicializar la biblioteca
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Guía de implementación
Ahora que ya está configurado, repasemos cada función paso a paso.
### Crear y agregar un gráfico a una presentación
#### Descripción general
Comenzaremos creando una presentación y agregando un gráfico circular a la primera diapositiva.
#### Pasos:
1. **Inicializar la presentación**
   Comience creando una instancia del `Presentation` clase, que representa su archivo de PowerPoint.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Aquí es donde agregaremos nuestro gráfico.
   }
   ```
2. **Agregar un gráfico circular**
   Utilice el `Shapes.AddChart` Método para insertar un gráfico circular en coordenadas específicas en su diapositiva.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Establecer un libro de trabajo externo para los datos del gráfico
#### Descripción general
Ahora configuremos el gráfico circular para utilizar datos de un libro de trabajo externo.
#### Pasos:
1. **Acceder a los datos del gráfico**
   Recupere la interfaz de datos del gráfico donde especificará la URL de su fuente de datos externa.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Establecer la URL del libro de trabajo externo**
   Establezca la URL para su fuente de datos utilizando `SetExternalWorkbook`Este ejemplo utiliza una URL de marcador de posición, que debe reemplazarse con la ruta de la fuente de datos real.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://ruta/no/existe", falso);
   ```
### Guardar presentación en archivo
#### Descripción general
Por último, guarde la presentación en formato PPTX en la ubicación deseada.
#### Pasos:
1. **Guardar la presentación**
   Utilice el `Save` método de la `Presentation` clase para escribir el archivo en el disco.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Aplicaciones prácticas
- **Informes comerciales**:Genere automáticamente gráficos para evaluaciones de desempeño trimestrales.
- **Paneles de datos**:Integre con fuentes de datos para actualizar informes visuales en tiempo real.
- **Contenido educativo**:Cree presentaciones dinámicas que extraigan los datos más recientes de estudios externos o artículos de investigación.
Al integrar Aspose.Slides, puede automatizar y mejorar su proceso de creación de presentaciones en varios dominios.
## Consideraciones de rendimiento
Al trabajar con grandes conjuntos de datos o numerosos gráficos:
- Optimice el uso de recursos administrando la memoria de manera efectiva dentro de .NET.
- Disponer de `Presentation` objetos adecuadamente para liberar recursos.
- Utilice operaciones asincrónicas siempre que sea posible para mejorar la capacidad de respuesta de la aplicación.
## Conclusión
Siguiendo este tutorial, aprendiste a crear presentaciones con gráficos circulares mediante programación usando Aspose.Slides para .NET. Ahora tienes las herramientas para automatizar la creación de gráficos y administrar fuentes de datos externas de forma eficiente.
### Próximos pasos
Explore más personalizando estilos de gráficos, agregando más tipos de gráficos o integrando otros componentes de Aspose como Aspose.Cells para obtener capacidades mejoradas de manipulación de datos.
## Sección de preguntas frecuentes
1. **¿Qué es Aspose.Slides?**  
   Una biblioteca robusta para manipular presentaciones de PowerPoint mediante programación en .NET.
2. **¿Puedo usar Aspose.Slides sin una licencia?**  
   Sí, pero con limitaciones. Considere obtener una prueba gratuita o comprar una licencia para disfrutar de todas las funciones.
3. **¿Cómo actualizo los datos del gráfico dinámicamente?**  
   Utilice libros de trabajo externos y configure sus URL en el `SetExternalWorkbook` método.
4. **¿Se puede utilizar Aspose.Slides en múltiples plataformas?**  
   Sí, es compatible con .NET Framework y .NET Core/.NET 5+ en Windows, macOS y Linux.
5. **¿Qué otros tipos de gráficos son compatibles?**  
   Además de los gráficos circulares, puede crear gráficos de barras, gráficos de líneas y más con Aspose.Slides.
## Recursos
- [Documentación de Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Descargar la última versión](https://releases.aspose.com/slides/net/)
- [Licencia de compra](https://purchase.aspose.com/buy)
- [Prueba gratuita](https://releases.aspose.com/slides/net/)
- [Licencia temporal](https://purchase.aspose.com/temporary-license/)
- [Foro de soporte](https://forum.aspose.com/c/slides/11)
¡Comience hoy mismo a integrar Aspose.Slides en sus proyectos para mejorar y automatizar sus presentaciones de PowerPoint!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
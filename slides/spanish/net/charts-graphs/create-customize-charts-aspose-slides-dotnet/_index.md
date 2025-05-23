---
"date": "2025-04-15"
"description": "Aprenda a crear y personalizar gráficos con Aspose.Slides para .NET, incluyendo la visualización de porcentajes como etiquetas de datos. Siga esta guía paso a paso."
"title": "Cómo crear y personalizar gráficos con Aspose.Slides .NET y mostrar porcentajes como etiquetas"
"url": "/es/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear y personalizar gráficos con Aspose.Slides .NET: Mostrar porcentajes como etiquetas

## Introducción

Presentar datos eficazmente es crucial en muchos campos, y los gráficos desempeñan un papel fundamental al convertir información compleja en imágenes claras. Crear el gráfico perfecto implica tareas de personalización, como mostrar porcentajes en las etiquetas, una tarea que se simplifica con Aspose.Slides para .NET. Esta biblioteca simplifica el proceso de creación y modificación de gráficos en presentaciones de PowerPoint.

En este tutorial, aprenderá a usar Aspose.Slides para .NET para crear un gráfico de columnas apiladas desde cero y personalizarlo mostrando valores porcentuales como etiquetas de datos. Siguiendo estos pasos, mejorará sus diapositivas con representaciones de datos precisas y visualmente atractivas.

**Lo que aprenderás:**
- Inicializando Aspose.Slides para .NET
- Creación de un gráfico de columnas apiladas
- Calcular y mostrar porcentajes en las etiquetas de datos
- Mejores prácticas para optimizar el rendimiento de los gráficos

Antes de sumergirnos en la implementación, asegurémonos de tener todo listo para comenzar.

## Prerrequisitos

Para seguir este tutorial de manera efectiva, asegúrese de tener:
- **SDK de .NET Core** instalado en su máquina.
- Comprensión básica del desarrollo de aplicaciones C# y .NET.
- Visual Studio o un IDE similar para escribir y ejecutar código C#.

Necesitará Aspose.Slides para .NET para crear gráficos, así que asegúrese de que esté configurado como se describe a continuación.

## Configuración de Aspose.Slides para .NET

Aspose.Slides para .NET es una potente biblioteca que permite trabajar con presentaciones de PowerPoint mediante programación. Aquí te explicamos cómo añadirla a tu proyecto:

### Instalación

**CLI de .NET:**
```bash
dotnet add package Aspose.Slides
```

**Consola del administrador de paquetes:**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet:** 
- Abra el Administrador de paquetes NuGet y busque "Aspose.Slides". Instale la última versión.

### Adquisición de licencias

Para aprovechar al máximo Aspose.Slides, comience con una prueba gratuita. Para un uso prolongado, considere adquirir una licencia temporal o comprar una en [Supongamos](https://purchase.aspose.com/buy)Siga sus pautas para configurar su licencia en el entorno de su proyecto.

### Inicialización básica

Una vez instalado, inicialice el `Presentation` Clase para comenzar a crear diapositivas:
```csharp
using Aspose.Slides;

// Inicializar la instancia de la clase Presentación
tPresentation presentation = new Presentation();
```

Ahora, pasemos a implementar nuestra función de creación y personalización de gráficos utilizando Aspose.Slides para .NET.

## Guía de implementación

### Crear un gráfico de columnas apiladas

Nuestro objetivo es crear un gráfico de columnas apiladas y personalizarlo mostrando porcentajes como etiquetas de datos. Así es como se hace:

#### Inicializar la presentación

Comience creando una instancia de `Presentation`:
```csharp
using Aspose.Slides;

// Inicializar la instancia de la clase Presentación
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Agregar un gráfico a la diapositiva

Agregue un gráfico de columnas apiladas a su primera diapositiva en las coordenadas y dimensiones especificadas:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Esta línea crea una `StackedColumn` Gráfico en la posición (20, 20) con ancho y alto de 400.

#### Calcular valores totales para el cálculo de porcentajes

Para mostrar porcentajes, calcule el valor total de cada categoría en todas las series:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Sumar los valores de todas las series para cada categoría
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Personalizar las etiquetas de datos para mostrar valores porcentuales

A continuación, recorra cada serie y personalice las etiquetas de datos:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Calcular porcentaje
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Texto claro para evitar superposiciones
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Configurar el formato de etiqueta para ocultar las etiquetas de datos predeterminadas
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Esta sección calcula el porcentaje de cada punto de datos y lo establece como una etiqueta personalizada, garantizando que no haya superposición con las etiquetas predeterminadas.

#### Guardar la presentación

Por último, guarde su presentación para ver el resultado:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Aplicaciones prácticas

Mostrar porcentajes en gráficos puede ser especialmente útil en situaciones como:
1. **Informes financieros:** Mostrar distribuciones de cartera o rendimientos de inversión como porcentajes.
2. **Análisis de ventas:** Representar datos de participación de mercado en porcentaje para resaltar el desempeño en todas las regiones.
3. **Resultados de la encuesta:** Muestra las respuestas de la encuesta como porcentajes para una mejor comparación visual.
4. **Gestión de proyectos:** Utilice gráficos circulares con porcentajes para ilustrar la asignación de recursos.
5. **Educación:** Explicar conceptos estadísticos utilizando imágenes claras basadas en porcentajes.

La integración de estos gráficos personalizados en sistemas como CRM o ERP puede mejorar los paneles y los informes, facilitando los procesos de toma de decisiones.

## Consideraciones de rendimiento

Al trabajar con Aspose.Slides para .NET, especialmente con conjuntos de datos grandes:
- **Gestión de la memoria:** Descarte los objetos de presentación correctamente para liberar memoria. Usar `using` declaraciones cuando corresponda.
- **Manejo eficiente de datos:** Realice cálculos fuera de los bucles cuando sea posible para reducir la sobrecarga computacional.
- **Equilibrio de carga:** Para las aplicaciones web, asegúrese de que los recursos del servidor estén adecuadamente provistos para las solicitudes de generación de gráficos simultáneas.

## Conclusión

Este tutorial abordó la creación y personalización de gráficos con Aspose.Slides para .NET, mostrando valores porcentuales como etiquetas. Dominar estas técnicas le permitirá mejorar sus presentaciones con representaciones de datos detalladas y visualmente atractivas.

Como siguiente paso, explore otros tipos de gráficos y opciones de personalización disponibles en Aspose.Slides. Experimente con diferentes conjuntos de datos para transformarlos en potentes elementos visuales que transmitan información con claridad.

## Sección de preguntas frecuentes

**P1: ¿Cómo manejo conjuntos de datos grandes al crear gráficos con Aspose.Slides para .NET?**
A1: Para grandes conjuntos de datos, optimice los cálculos y utilice técnicas eficientes de gestión de memoria. Divida las tareas de procesamiento para evitar la sobrecarga de memoria.

**P2: ¿Puedo usar Aspose.Slides para .NET en una aplicación web?**
A2: Sí, se puede integrar en aplicaciones ASP.NET. Asegúrese de asignar los recursos del servidor correctamente para un rendimiento óptimo.

**P3: ¿Es posible exportar gráficos creados con Aspose.Slides a otros formatos?**
A3: ¡Por supuesto! Puedes exportar presentaciones con tus gráficos personalizados a varios formatos, como PDF y archivos de imagen, utilizando las funciones de la biblioteca.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-15"
"description": "Aprenda a crear gráficos de columnas apiladas porcentuales visualmente atractivos con Aspose.Slides para .NET. Siga esta guía paso a paso para una visualización de datos clara."
"title": "Cómo crear gráficos de columnas apiladas basados en porcentajes en .NET con Aspose.Slides"
"url": "/es/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear un gráfico de columnas apiladas basado en porcentajes con Aspose.Slides para .NET

## Introducción

En el ámbito de la visualización de datos, presentar la información de forma clara y eficaz es crucial para una toma de decisiones eficaz. Para mostrar conjuntos de datos complejos de forma intuitiva, los gráficos de columnas apiladas basados en porcentajes son ideales. Esta guía le guiará en la creación de estos gráficos con Aspose.Slides para .NET, una robusta biblioteca diseñada para manipular archivos de presentación.

Siguiendo este tutorial aprenderás:
- Configuración de datos de gráficos y configuración de formatos numéricos.
- Agregar series y personalizar su apariencia.
- Dar formato a las etiquetas para mejorar la legibilidad.

¿Listo para empezar? ¡Comencemos con los prerrequisitos!

## Prerrequisitos

Antes de crear sus gráficos de columnas apiladas basados en porcentajes, asegúrese de que su entorno esté configurado correctamente. Necesitará:

### Bibliotecas, versiones y dependencias necesarias
- **Aspose.Slides para .NET**:Asegúrese de que esta biblioteca esté instalada.

### Requisitos de configuración del entorno
- Un entorno de desarrollo con el SDK .NET instalado.
- Visual Studio o cualquier IDE compatible para ejecutar código C#.

### Requisitos previos de conocimiento
- Comprensión básica de programación en C#.
- Familiaridad con la configuración de proyectos .NET y la gestión de paquetes.

## Configuración de Aspose.Slides para .NET

Para comenzar a crear gráficos con Aspose.Slides, primero instale la biblioteca usando uno de estos métodos:

**CLI de .NET**
```bash
dotnet add package Aspose.Slides
```

**Administrador de paquetes**
```powershell
Install-Package Aspose.Slides
```

**Interfaz de usuario del administrador de paquetes NuGet**
- Busque "Aspose.Slides" e instale la última versión.

### Pasos para la adquisición de la licencia

Comience con una prueba gratuita descargando una licencia temporal desde [El sitio web de Aspose](https://purchase.aspose.com/temporary-license/)Para un uso continuo, considere comprar una licencia completa. 

Una vez configurado, inicie Aspose.Slides en su proyecto:
```csharp
using Aspose.Slides;
```

## Guía de implementación

Con el entorno listo, dividiremos en pasos la creación de un gráfico de columnas apiladas basado en porcentajes.

### Creación y configuración del gráfico

#### Descripción general
Crear una instancia de la `Presentation` Clase, esencial para trabajar con diapositivas. Luego, agregue y configure un gráfico de columnas apiladas en su diapositiva.

#### Cómo agregar un gráfico de columnas apiladas
```csharp
// Crear una instancia de la clase Presentación
document = new Presentation();

// Obtener referencia a la primera diapositiva
slide = document.Slides[0];

// Agregar gráfico PercentsStackedColumn en la posición (20, 20) con tamaño (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Configuración del formato de número
Asegúrese de que sus datos se muestren como porcentajes:
```csharp
// Configurar el formato de número para el eje vertical
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Establecer el formato de número en porcentaje
```

#### Agregar series de datos y puntos
Borrar los datos de las series existentes y agregar nuevos:
```csharp
// Borrar cualquier dato de serie existente
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Libro de trabajo de datos de gráficos de Access
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Añadir una nueva serie de datos "Rojos"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Establezca el color de relleno para la serie en Rojo
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Configurar las propiedades del formato de etiqueta para la serie "Rojos"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Establecer formato de porcentaje
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Añade otra serie "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Establezca el color de relleno para la serie en Azul
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Establecer formato de porcentaje
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Guardar la presentación
Guarde su presentación en un archivo:
```csharp
// Guardar la presentación en formato PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Consejos para la solución de problemas
- Asegúrese de que todos los espacios de nombres se importen correctamente.
- Compruebe si hay errores tipográficos en los nombres de propiedades y llamadas de métodos.
- Verifique que sus rutas para guardar archivos existan y tengan los permisos correctos.

## Aplicaciones prácticas

A continuación se muestran algunos escenarios en los que los gráficos de columnas apiladas basados en porcentajes pueden ser valiosos:
1. **Análisis de ventas**:Visualice el rendimiento del producto en diferentes regiones como proporción de las ventas totales.
2. **Asignación de presupuesto**:Muestre cómo los departamentos asignan su presupuesto en relación con el gasto general de la empresa.
3. **Investigación de mercado**:Comparar las preferencias de los consumidores por distintas categorías de productos a lo largo del tiempo.
4. **Datos educativos**:Muestra la distribución de las calificaciones de los estudiantes en diferentes materias.
5. **Estadísticas de atención médica**:Representar la demografía de los pacientes en múltiples condiciones de salud.

## Consideraciones de rendimiento

Para un rendimiento óptimo, considere:
- Limitar el número de puntos de datos a lo necesario.
- Precarga de datos para minimizar el procesamiento en tiempo de ejecución.
- Uso de prácticas de gestión de memoria eficientes con Aspose.Slides para .NET.

## Conclusión

¡Felicitaciones! Aprendió a crear un gráfico de columnas apiladas basado en porcentajes con Aspose.Slides para .NET. Esta herramienta mejora las presentaciones al hacer que los datos complejos sean más comprensibles y visualmente atractivos.

¿Próximos pasos? Explora otros tipos de gráficos disponibles en Aspose.Slides o integra esta funcionalidad en aplicaciones más grandes. ¡Que disfrutes programando!

## Sección de preguntas frecuentes

**P1: ¿Puedo utilizar Aspose.Slides gratis?**
A1: Sí, puedes comenzar con una prueba gratuita para probar las funciones de Aspose.Slides.

**P2: ¿Qué tipos de gráficos admite Aspose.Slides para .NET?**
A2: Admite varios gráficos como circulares, de barras, de columnas, de líneas y más.

**P3: ¿Cómo puedo empezar a utilizar Aspose.Slides para .NET?**
A3: Instale la biblioteca mediante NuGet o la CLI de .NET como se describe arriba. Siga nuestra documentación para crear su primer gráfico.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
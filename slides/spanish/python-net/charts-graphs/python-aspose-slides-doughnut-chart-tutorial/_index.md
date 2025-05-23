---
"date": "2025-04-22"
"description": "Aprenda a crear gráficos de anillos con Python y Aspose.Slides. Esta guía paso a paso explica la configuración, la personalización y las mejores prácticas para mejorar sus presentaciones."
"title": "Cómo crear gráficos de anillos en Python con Aspose.Slides&#58; guía paso a paso"
"url": "/es/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear gráficos de anillos en Python con Aspose.Slides: guía paso a paso

En el ámbito de la visualización de datos, presentar la información eficazmente puede influir significativamente en la comprensión y la toma de decisiones. Tanto si creas una presentación empresarial como si analizas conjuntos de datos complejos, los gráficos son herramientas esenciales. Entre los diversos tipos de gráficos, los gráficos de anillos ofrecen una forma atractiva de representar datos proporcionales con un orificio central intuitivo. Esta guía paso a paso te guiará en la creación de un gráfico de anillos en Python con Aspose.Slides, una potente biblioteca para manipular presentaciones.

## Lo que aprenderás
- Cómo configurar y usar Aspose.Slides para Python
- El proceso de agregar un gráfico de anillos a las diapositivas de su presentación
- Personalización de series y categorías dentro del gráfico
- Ajustar elementos visuales como etiquetas, colores y efectos de explosión
- Mejores prácticas para optimizar el rendimiento con Aspose.Slides

## Prerrequisitos
Antes de comenzar, asegúrese de tener:
- **Entorno de Python**:Python 3.x instalado en su máquina.
- **Aspose.Slides para Python**:Instala esta biblioteca usando pip.
- **Comprensión básica de la programación en Python**Será útil estar familiarizado con bucles y programación orientada a objetos.

## Configuración de Aspose.Slides para Python
Para comenzar, instale la biblioteca Aspose.Slides a través de pip:

```bash
pip install aspose.slides
```

### Adquisición de licencias
Aspose ofrece una prueba gratuita para probar funciones sin limitaciones por tiempo limitado. Para obtenerla:
1. Visita el [Prueba gratuita](https://releases.aspose.com/slides/python-net/) página.
2. Siga las instrucciones para descargar y aplicar su licencia temporal.

Para un uso continuo, considere comprar una suscripción en [Página de compra](https://purchase.aspose.com/buy).

### Inicialización básica
Después de configurar Aspose.Slides, inicialícelo de la siguiente manera:

```python
import aspose.slides as slides

# Crea una instancia de la clase Presentación.
with slides.Presentation() as pres:
    # Tu código para manipular presentaciones va aquí.

# Guarde la presentación después de realizar cambios.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Guía de implementación
Con Aspose.Slides configurado, siga estos pasos para agregar un gráfico de anillos a su presentación diapositiva por diapositiva.

### Crear una nueva presentación y agregar una diapositiva
Comience creando una instancia de la `Presentation` clase:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Acceder o crear diapositivas dentro de este contexto.
```

### Cómo agregar un gráfico de anillos a la primera diapositiva
Acceda a la primera diapositiva y utilice el `add_chart` método. Especifique el tipo de gráfico como `DOUGHNUT`, junto con la posición y el tamaño:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Configuración de datos de gráficos
Borre los datos existentes y configure ajustes como ocultar la leyenda:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Agregar series y categorías
Agregue varias series y categorías a un gráfico de anillos. A continuación, se explica cómo crear 15 series con propiedades específicas:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Añade categorías de forma similar:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Agregue puntos de datos para cada serie.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Personalice la apariencia de cada punto de datos.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Configure los ajustes de etiqueta para la última serie.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Guardar la presentación
Por último, guarde su presentación en un directorio específico:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Aplicaciones prácticas
Los gráficos de anillos son versátiles y se pueden utilizar en diversos escenarios, como:
1. **Asignación de presupuesto**:Mostrar cómo los diferentes departamentos utilizan sus fondos asignados.
2. **Análisis de cuota de mercado**:Comparar la cuota de mercado de productos o empresas competidoras.
3. **Resultados de la encuesta**:Visualizar respuestas a preguntas de encuestas sobre preferencias o niveles de satisfacción.

## Consideraciones de rendimiento
Para garantizar un rendimiento óptimo al utilizar Aspose.Slides:
- Minimice el uso de memoria desechando los objetos de forma adecuada después de su uso.
- Cargue presentaciones en la memoria sólo cuando sea necesario y ciérrelas lo antes posible.
- Considere el procesamiento por lotes de diapositivas si está trabajando con una gran cantidad de gráficos.

## Conclusión
Siguiendo esta guía, aprendiste a crear gráficos de anillos dinámicos con Aspose.Slides para Python. Estas visualizaciones pueden mejorar tus presentaciones, haciendo que los datos sean más fáciles de digerir y atractivos. Continúa explorando las funciones de la biblioteca para personalizar y optimizar aún más tus gráficos.

## Sección de preguntas frecuentes
1. **¿Puedo usar Aspose.Slides sin comprar una licencia?**
   - Sí, puedes comenzar con una licencia de prueba gratuita para fines de evaluación.
2. **¿Cómo cambio los colores de los gráficos en Aspose.Slides?**
   - Utilice el `fill_format` propiedad para establecer el color deseado para los elementos del gráfico.
3. **¿Es posible exportar gráficos como imágenes?**
   - Sí, puedes renderizar diapositivas que contengan gráficos en formatos de imagen utilizando las capacidades de renderizado de la biblioteca.
4. **¿Cuáles son algunos problemas comunes al agregar gráficos?**
   - Asegúrese de que todos los puntos de datos y categorías se hayan agregado correctamente antes de intentar guardar o mostrar su gráfico.
5. **¿Puedo integrar Aspose.Slides con otras bibliotecas de Python?**
   - ¡Por supuesto! Puedes usarlo junto con bibliotecas como Pandas para optimizar la manipulación de datos.

## Recursos
- [Documentación de Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Descargar Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Comprar una licencia](https://purchase.aspose.com/buy)
- [Prueba gratuita y licencia temporal](https://releases.aspose.com/slides/python-net/)
- [Foro de la comunidad de Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
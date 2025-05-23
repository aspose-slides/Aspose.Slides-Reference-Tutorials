---
"date": "2025-04-22"
"description": "Aprenda a mostrar fácilmente etiquetas de porcentaje en gráficos de presentaciones de PowerPoint con Aspose.Slides para Python. Ideal para mejorar la visualización de datos."
"title": "Cómo mostrar etiquetas de porcentaje en gráficos con Aspose.Slides para Python&#58; una guía completa"
"url": "/es/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo mostrar etiquetas de porcentaje en gráficos con Aspose.Slides para Python

## Introducción

Visualizar datos eficazmente es crucial en presentaciones e informes, especialmente cuando se desea resaltar proporciones o distribuciones con claridad. Pero ¿qué ocurre si necesita mostrar esos porcentajes directamente en sus gráficos? Esta guía completa le guiará en el uso de... **Aspose.Slides para Python** para mostrar valores porcentuales como etiquetas en un gráfico sin esfuerzo.

### Lo que aprenderás:
- Cómo crear e incrustar gráficos en presentaciones de PowerPoint usando Aspose.Slides para Python.
- Visualización de puntos de datos como etiquetas de porcentaje en sus gráficos.
- Guardar y administrar presentaciones de PowerPoint de manera eficiente.

¿Listo para empezar a añadir imágenes reveladoras a tus datos? ¡Primero veamos qué necesitas antes de empezar a programar!

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:
- **Aspose.Slides para Python**:Esta biblioteca es esencial para crear y manipular presentaciones de PowerPoint mediante programación.
- **Entorno de Python**:Una comprensión básica de la programación Python y la configuración del entorno.
- **Administrador de paquetes PIP**:Se utiliza para instalar Aspose.Slides.

## Configuración de Aspose.Slides para Python

Para comenzar a utilizar Aspose.Slides, primero deberá instalarlo:

```bash
pip install aspose.slides
```

### Pasos para la adquisición de la licencia:
Puedes empezar con una prueba gratuita u obtener una licencia temporal para explorar todas las funciones de Aspose.Slides. Para un uso prolongado, considera adquirir una suscripción.

#### Inicialización y configuración básicas

Una vez instalado, inicializará su entorno de presentación de la siguiente manera:

```python
import aspose.slides as slides

# Inicializar un objeto de presentación
def create_presentation():
    with slides.Presentation() as presentation:
        # Tu código aquí
```

## Guía de implementación

Ahora que estamos configurados, profundicemos en la visualización de porcentajes en gráficos.

### Crear el gráfico y agregar datos

#### Descripción general
Crearemos un gráfico de columnas apiladas con etiquetas de porcentaje para cada punto de datos, lo que permitirá a los espectadores ver las proporciones exactas de un vistazo.

##### Paso 1: Agrega un gráfico a tu diapositiva

```python
# Acceda a la primera diapositiva de su presentación
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Agregar un gráfico de columnas apiladas
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Este fragmento de código agrega un gráfico básico a la primera diapositiva. `add_chart` El método especifica el tipo de gráfico y su posición y tamaño.

##### Paso 2: Calcular los valores totales de las categorías

```python
def calculate_totals(chart):
    total_for_category = []
    # Sumar valores de todas las series para cada categoría
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Este bucle calcula el total de todos los puntos de datos de las series, lo que es crucial para los cálculos de porcentajes.

#### Configuración de etiquetas de porcentaje

##### Paso 3: Configurar los puntos de datos de la serie

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Establecer opciones de etiqueta predeterminadas para ocultar información no esencial
        series.labels.default_data_label_format.show_legend_key = False
        
        # Calcular y establecer etiquetas de porcentaje
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Crea una porción de texto con el valor porcentual
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Borrar las etiquetas existentes y agregar una nueva etiqueta de porcentaje
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Ocultar otros elementos de la etiqueta de datos
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Este segmento procesa cada punto de datos para calcular su porcentaje del total y lo asigna como etiqueta.

### Guardar su presentación

```python
def save_presentation(presentation, output_directory):
    # Guarde su presentación con modificaciones
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
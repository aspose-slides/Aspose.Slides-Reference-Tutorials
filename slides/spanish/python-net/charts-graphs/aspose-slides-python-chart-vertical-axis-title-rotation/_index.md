---
"date": "2025-04-23"
"description": "Aprenda a ajustar el ángulo de rotación de los títulos de los gráficos en presentaciones usando Aspose.Slides para Python, mejorando la legibilidad y la estética."
"title": "Cómo configurar la rotación del título del eje vertical de un gráfico en Aspose.Slides para Python"
"url": "/es/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo configurar la rotación del título del eje vertical de un gráfico en Aspose.Slides para Python

## Introducción

En las presentaciones de datos, mejorar la legibilidad de los gráficos es crucial. Ajustar el ángulo de rotación del título del eje vertical de su gráfico con Aspose.Slides para Python puede hacer que los títulos encajen perfectamente o destaquen en sus diapositivas. Este tutorial le guía para configurar este ángulo de rotación y mejorar tanto la funcionalidad como el atractivo visual.

**Lo que aprenderás:**
- Cómo instalar y configurar Aspose.Slides para Python.
- Pasos para agregar y personalizar gráficos dentro de sus diapositivas.
- Técnicas para establecer el ángulo de rotación de los títulos de gráficos.
- Aplicaciones en el mundo real de estas características en la visualización de datos.

Comencemos cubriendo los requisitos previos antes de sumergirnos en la implementación.

## Prerrequisitos

Antes de comenzar, asegúrese de tener:
- **Entorno de Python**:Instalar Python 3.x desde [python.org](https://www.python.org/).
- **Biblioteca Aspose.Slides**:Instalar mediante pip para manipular presentaciones de manera efectiva.
- **Conocimientos básicos de programación en Python**:La familiaridad con la sintaxis de Python y las operaciones con archivos le ayudará a seguir adelante.

## Configuración de Aspose.Slides para Python

Para usar Aspose.Slides, instálalo con pip. Abre tu terminal o símbolo del sistema y ejecuta:

```bash
pip install aspose.slides
```

### Pasos para la adquisición de la licencia

Aspose ofrece diferentes opciones de licencia:
- **Prueba gratuita**: Descargue una versión de prueba desde [Página de lanzamiento de Aspose](https://releases.aspose.com/slides/python-net/).
- **Licencia temporal**: Obtenga una licencia temporal para funciones extendidas a través de [portal de compras](https://purchase.aspose.com/temporary-license/).
- **Compra**:Considere comprar si considera que la herramienta es indispensable, disponible en [Página de compra de Aspose](https://purchase.aspose.com/buy).

#### Inicialización y configuración básicas

A continuación se explica cómo inicializar Aspose.Slides en su script de Python:

```python
import aspose.slides as slides

# Crear un objeto de presentación
def main():
    with slides.Presentation() as pres:
        # Tu código irá aquí
        pass

if __name__ == "__main__":
    main()
```

## Guía de implementación

### Agregar y personalizar gráficos

#### Descripción general

En esta sección, agregaremos un gráfico de columnas agrupadas a su diapositiva y lo personalizaremos configurando el ángulo de rotación del título de su eje vertical.

#### Pasos:

##### Paso 1: Agregar un gráfico de columnas agrupadas

Comience agregando un gráfico en coordenadas específicas con dimensiones definidas:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Agregar un gráfico de columnas agrupadas a la diapositiva 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Paso 2: Configurar el título del eje vertical

Habilitar y configurar el ángulo de rotación para el título del eje vertical:

```python
def configure_chart(chart):
    # Habilitar el título del eje vertical
    chart.axes.vertical_axis.has_title = True
    
    # Establezca el ángulo de rotación a 90 grados.
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Paso 3: Guarda tu presentación

Por último, guarda tu presentación con los cambios:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Guardar la presentación
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
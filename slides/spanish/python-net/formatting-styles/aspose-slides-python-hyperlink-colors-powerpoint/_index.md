---
"date": "2025-04-23"
"description": "Aprenda a personalizar los colores de los hipervínculos en presentaciones de PowerPoint con Aspose.Slides para Python. Mejore sus diapositivas con estilos de enlace personalizados de forma eficiente."
"title": "Cómo configurar los colores de hipervínculos en PowerPoint con Aspose.Slides para Python"
"url": "/es/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo configurar los colores de hipervínculos en PowerPoint con Aspose.Slides para Python

## Introducción

Mejorar el aspecto visual de sus presentaciones de PowerPoint personalizando los colores de los hipervínculos es sencillo con Aspose.Slides para Python. Esta guía le guiará en la configuración de hipervínculos con colores específicos en sus diapositivas usando Python.

**Lo que aprenderás:**
- Cómo establecer un color de hipervínculo dentro de formas de texto en PowerPoint.
- Pasos necesarios para crear una presentación visualmente atractiva.
- Características clave de Aspose.Slides para Python que facilitan esta personalización.

Analicemos los requisitos previos necesarios antes de comenzar.

## Prerrequisitos

Antes de comenzar, asegúrese de que su entorno esté preparado con lo siguiente:
- **Bibliotecas y versiones:** Instalar `aspose.slides` biblioteca. Asegúrese de que Python esté instalado en su máquina.
- **Requisitos de configuración del entorno:** Este tutorial asume una configuración básica de Python en Windows, Mac o Linux.
- **Requisitos de conocimiento:** Será beneficioso estar familiarizado con la programación en Python.

## Configuración de Aspose.Slides para Python

Para comenzar a usar Aspose.Slides para Python, instale el paquete mediante pip:

```bash
pip install aspose.slides
```

**Pasos para la adquisición de la licencia:**
- **Prueba gratuita:** Descargue una versión de prueba desde [Página de lanzamiento de Aspose](https://releases.aspose.com/slides/python-net/).
- **Licencia temporal:** Solicitar una licencia temporal en el [página de compra](https://purchase.aspose.com/temporary-license/) para acceso extendido.
- **Compra:** Para desbloquear completamente las funciones sin limitaciones, considere comprar una licencia de [Página de compra de Aspose](https://purchase.aspose.com/buy).

**Inicialización básica:**
Una vez instalado y licenciado, importe Aspose.Slides en su script:

```python
import aspose.slides as slides
```

## Guía de implementación

Esta sección lo guiará a través de la configuración de colores de hipervínculos dentro de una presentación de PowerPoint.

### Establecer la función de color del hipervínculo

#### Descripción general

Personalice el color de los hipervínculos incrustados en formas de texto con Aspose.Slides para Python. Esto mejora la legibilidad y el atractivo visual.

##### Paso 1: Crear una nueva presentación

Crear una instancia de una presentación:

```python
with slides.Presentation() as presentation:
    # Tu código aquí
```

##### Paso 2: Agregar una forma con texto

Agregue una forma de rectángulo a la primera diapositiva e inserte texto que incluya un hipervínculo.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Paso 3: Establecer las propiedades del hipervínculo

Asignar el hipervínculo y configurar su color. `hyperlink_click` La propiedad especifica a dónde debe dirigirse el enlace al hacer clic.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Establezca la fuente de color para el hipervínculo al formato de porción y defina el tipo y color de relleno.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Paso 4: Guardar la presentación

Guarde su presentación en un directorio específico:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
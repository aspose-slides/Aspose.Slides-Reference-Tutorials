---
"date": "2025-04-23"
"description": "Aprenda a automatizar la creación de gráficos SmartArt en presentaciones de PowerPoint utilizando Aspose.Slides para Python, incluida la extracción y el guardado de miniaturas de manera eficiente."
"title": "Cómo crear y recuperar miniaturas de SmartArt con Aspose.Slides para Python"
"url": "/es/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear y recuperar miniaturas de SmartArt con Aspose.Slides para Python

## Introducción

Crear presentaciones visualmente atractivas es esencial para captar la atención del público. Una forma eficaz de mejorar las diapositivas es incorporar gráficos dinámicos como SmartArt en las presentaciones de PowerPoint. Si busca un método automatizado para generar estos elementos visuales y extraer miniaturas, esta guía sobre "Aspose.Slides Python" le resultará muy útil.

Con Aspose.Slides para Python, puede crear fácilmente gráficos SmartArt, acceder a nodos específicos dentro del gráfico, recuperar miniaturas de dichos nodos y guardarlas para sus proyectos. Este tutorial le guiará paso a paso en detalle.

**Lo que aprenderás:**
- Cómo instalar y configurar Aspose.Slides para Python.
- Creación de un gráfico SmartArt en una presentación de PowerPoint.
- Acceder a nodos dentro de un gráfico SmartArt.
- Extraer y guardar una miniatura de imagen de un nodo específico.

Profundicemos en los requisitos previos antes de comenzar.

## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente listo:

- **Bibliotecas requeridas:** Necesitará Aspose.Slides para Python. Asegúrese de que su entorno sea compatible con Python 3.x.
- **Requisitos de configuración del entorno:** Una instalación funcional de Python y un IDE o editor de texto adecuado como VSCode o PyCharm.
- **Requisitos de conocimiento:** Comprensión básica de la programación en Python, incluidas definiciones de funciones y operaciones con archivos.

## Configuración de Aspose.Slides para Python

Primero, necesitas instalar la biblioteca Aspose.Slides. Esto se puede hacer fácilmente con pip:

```bash
pip install aspose.slides
```

Una vez instalado, obtenga una licencia si desea explorar todas las funciones sin limitaciones. Puede empezar con una prueba gratuita, solicitar una licencia temporal o comprarla para uso a largo plazo.

Para inicializar Aspose.Slides en su entorno Python, importe la biblioteca al comienzo de su script:

```python
import aspose.slides as slides
```

## Guía de implementación

Dividamos el proceso en pasos claros para crear y recuperar una miniatura SmartArt.

### Paso 1: Crear una nueva instancia de presentación

Empieza creando una instancia de presentación. Este será el contenedor donde agregarás tu gráfico SmartArt.

```python
with slides.Presentation() as pres:
```

Usando `with` garantiza que los recursos se administren correctamente, guardando y cerrando automáticamente el archivo al salir.

### Paso 2: Agregar SmartArt a la primera diapositiva

continuación, agregaremos un gráfico SmartArt a nuestra primera diapositiva. Así es como se hace:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Esto agrega un diseño de ciclo básico para el gráfico SmartArt en la posición (10, 10) con dimensiones de 400 x 300 píxeles.

### Paso 3: Acceder al segundo nodo

Acceda a nodos específicos dentro de su SmartArt. En este ejemplo, accedemos al segundo nodo:

```python
node = smart.nodes[1]
```

Los nodos se indexan a partir de cero; por lo tanto, `nodes[1]` se refiere al segundo nodo de la lista.

### Paso 4: recuperar la miniatura de la imagen

Para obtener una miniatura de la imagen de la forma dentro del nodo seleccionado:

```python
image = node.shapes[0].get_image()
```

Esto recupera la imagen de la primera forma como miniatura del nodo SmartArt especificado.

### Paso 5: Guardar la imagen recuperada

Por último, guarde esta miniatura en la ubicación deseada en formato JPEG:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
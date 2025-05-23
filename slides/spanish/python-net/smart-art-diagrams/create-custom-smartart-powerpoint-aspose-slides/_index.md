---
"date": "2025-04-23"
"description": "Aprenda a crear y personalizar gráficos SmartArt en PowerPoint usando Aspose.Slides para Python, mejorando sus presentaciones con organigramas dinámicos."
"title": "Cómo crear y personalizar SmartArt en PowerPoint con Aspose.Slides para Python"
"url": "/es/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear y personalizar SmartArt en PowerPoint con Aspose.Slides para Python

## Introducción

Las presentaciones son una herramienta esencial para representar visualmente estructuras organizativas o sesiones de lluvia de ideas. Con Aspose.Slides para Python, puedes crear y personalizar gráficos SmartArt fácilmente. Este tutorial te guiará para agregar un gráfico SmartArt de organigrama a tus diapositivas de PowerPoint.

**Lo que aprenderás:**
- Agregar un gráfico SmartArt en PowerPoint usando Aspose.Slides para Python.
- Personalizar el diseño de su nodo SmartArt.
- Guardar y exportar presentaciones de manera eficiente.

¡Comencemos a configurar tu entorno!

## Prerrequisitos

Antes de comenzar a crear gráficos SmartArt, asegúrese de tener los siguientes requisitos previos:

### Bibliotecas requeridas
- **Aspose.Slides para Python**:Instale esta biblioteca usando pip si aún no lo ha hecho.

### Requisitos de configuración del entorno
- Una instalación funcional de Python (se recomienda 3.x).
- Comprensión básica de la programación en Python.
- Estar familiarizado con Microsoft PowerPoint es útil pero no necesario.

## Configuración de Aspose.Slides para Python

Para comenzar, configure la biblioteca Aspose.Slides en su entorno de Python:

**Instalación de Pip:**
```bash
pip install aspose.slides
```

### Pasos para la adquisición de la licencia
Aspose ofrece varias opciones de licencia:
- **Prueba gratuita**: Descargue una licencia temporal para evaluar todas las funciones.
- **Licencia temporal**:Obtenga una licencia temporal gratuita para uso a corto plazo.
- **Compra**:Considere comprar una suscripción para proyectos a largo plazo.

### Inicialización y configuración básicas

Una vez instalado, inicialice su script de Python con Aspose.Slides de esta manera:

```python
import aspose.slides as slides

# Inicialice la clase Presentación con slides.Presentation() como presentación:
    # Tu código para agregar SmartArt irá aquí
```

## Guía de implementación

Ahora analicemos el proceso de agregar y personalizar SmartArt en PowerPoint usando Aspose.Slides para Python.

### Agregar un gráfico SmartArt

#### Descripción general
Cree una nueva diapositiva y agréguele un gráfico SmartArt de tipo organigrama:

```python
import aspose.slides as slides

# Cree una instancia de presentación con slides.Presentation() como presentación:
    # Agregar SmartArt con dimensiones especificadas en la posición (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parámetros y propósito del método
- **x, y**:Posición del gráfico SmartArt en la diapositiva.
- **ancho, alto**:Dimensiones para una adecuada visibilidad.
- **tipo_de_diseño**: Especifica el tipo de diseño de SmartArt, en este caso, un organigrama.

### Personalización del diseño del organigrama

#### Descripción general
Personalice el primer nodo de nuestro gráfico SmartArt configurando su diseño en LEFT_HANGING:

```python
# Establezca el primer nodo en el diseño colgante izquierdo
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Explicación de las opciones de configuración de teclas
- **Tipo de diseño del organigrama**:Determina cómo se muestran los nodos, mejorando la legibilidad y el atractivo estético.

### Guardar la presentación

Por último, guarde su presentación en un directorio específico:

```python
# Guarde la presentación con SmartArt\presentation.save("SU_DIRECTORIO_DE_SALIDA/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
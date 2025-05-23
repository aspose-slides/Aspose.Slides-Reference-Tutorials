---
"date": "2025-04-22"
"description": "Aprende a modificar el texto de los cuadros de texto, los títulos de los botones y las imágenes en PowerPoint usando Aspose.Slides con Python. Mejora tus presentaciones con elementos interactivos."
"title": "Domine Aspose.Slides para Python&#58; modifique fácilmente los controles ActiveX de PowerPoint"
"url": "/es/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominando Aspose.Slides para Python: Modificación de controles ActiveX de PowerPoint

En el dinámico panorama digital actual, personalizar las presentaciones de Microsoft PowerPoint es esencial para crear contenido atractivo. Ya sea que esté desarrollando módulos de capacitación interactivos o mejorando presentaciones empresariales con funciones de entrada de usuario, modificar los controles ActiveX de PowerPoint puede mejorar significativamente la funcionalidad de su presentación. Este tutorial explora el uso de Aspose.Slides para Python para cambiar el texto de los cuadros de texto y los títulos de los botones, sustituir imágenes, reposicionar o eliminar controles ActiveX de las diapositivas.

## Lo que aprenderás
- Cómo modificar el texto de los cuadros de texto y los títulos de los botones en presentaciones de PowerPoint.
- Técnicas para sustituir imágenes dentro de controles ActiveX.
- Métodos para reposicionar o eliminar controles ActiveX de manera efectiva.
- Aplicaciones prácticas de estas características en escenarios del mundo real.

Antes de sumergirnos en Aspose.Slides para Python, repasemos los requisitos previos.

## Prerrequisitos
Para seguir este tutorial, asegúrese de tener:
- **Pitón**:Versión 3.6 o superior instalada en su sistema.
- **Aspose.Slides para Python a través de .NET**:Esto se puede instalar usando pip.
- Un conocimiento básico de la programación en Python y familiaridad con la estructura de PowerPoint.

### Requisitos de configuración del entorno
1. **Instalar Aspose.Slides**:
   Utilice el siguiente comando para instalar Aspose.Slides para Python a través de .NET:

   ```bash
   pip install aspose.slides
   ```

2. **Adquisición de licencias**: 
   Comience por obtener una [licencia de prueba gratuita](https://releases.aspose.com/slides/python-net/) o solicitar una licencia temporal para explorar todas las capacidades sin limitaciones.

3. **Inicialización básica**:
   Importe los módulos necesarios y cargue su documento de PowerPoint como se muestra a continuación:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Tu código irá aquí.
   ```

## Guía de implementación
### Característica: Cambiar el texto del cuadro de texto y sustituir la imagen
#### Descripción general
Esta función le permite actualizar el texto dentro de un control ActiveX TextBox y reemplazar su imagen asociada, lo cual es útil para personalizar presentaciones o actualizar contenido dinámicamente.

##### Guía paso a paso
1. **Cargar la presentación**:
   Comience cargando su presentación de PowerPoint que contiene los controles ActiveX.

   ```python
def cambiar_cuadro_de_texto_e_imagen():
    con slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") como presentación:
        diapositiva = presentación.diapositivas[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **Crear imagen sustituta**:
   Generar una imagen para reemplazar el contenido original durante la activación de ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # Crear una imagen con dimensiones específicas
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Añade líneas de borde para una apariencia pulida.
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Función: Cambiar el título del botón y sustituir la imagen
#### Descripción general
Actualice los títulos de los botones dentro de los controles ActiveX de su presentación, proporcionando posibilidades de interacción dinámica con el usuario.

##### Guía paso a paso
1. **Cargar la presentación**:
   Como antes, comience cargando el archivo de PowerPoint.

   ```python
def cambiar_botón_título_e_imagen():
    con slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") como presentación:
        diapositiva = presentación.diapositivas[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **Crear imagen sustituta**:
   Generar una imagen para reemplazo visual.

   ```python
            # Crea un mapa de bits para las dimensiones del botón
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Añade líneas de borde para mayor estética.
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Función: Mover los controles ActiveX hacia abajo y guardar la presentación
#### Descripción general
Aprenda a reposicionar los controles ActiveX dentro de una diapositiva, mejorando la flexibilidad del diseño.

##### Guía paso a paso
1. **Cargar la presentación**:
   Abra su documento de PowerPoint para editarlo.

   ```python
def mover_activo_x_controles_y_guardar():
    con slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") como presentación:
        diapositiva = presentación.diapositivas[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**Conclusión:**
Siguiendo esta guía, podrá modificar eficazmente los controles ActiveX de PowerPoint con Aspose.Slides para Python. Esto mejora la interactividad y la personalización de sus presentaciones, haciéndolas más atractivas para su audiencia.

## Recomendaciones de palabras clave
- Modificar los controles ActiveX de PowerPoint
- "Aspose.Slides para Python"
- Cambiar el texto del cuadro de texto en PowerPoint
- Sustituir imágenes en controles ActiveX

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
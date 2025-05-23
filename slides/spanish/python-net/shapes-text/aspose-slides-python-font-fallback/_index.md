---
"date": "2025-04-24"
"description": "Aprenda a crear y administrar reglas de reserva de fuentes con Aspose.Slides para Python para garantizar que sus presentaciones sean consistentes en diferentes sistemas."
"title": "Dominar la reserva de fuentes en Aspose.Slides para Python&#58; una guía completa"
"url": "/es/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dominar la recuperación de fuentes en Aspose.Slides para Python: una guía completa

## Introducción

Los problemas de compatibilidad de fuentes pueden ser un desafío al crear presentaciones, especialmente con caracteres Unicode no compatibles con las fuentes principales. **Aspose.Slides para Python** Proporciona una solución sólida a través de reglas de respaldo de fuentes, lo que garantiza el atractivo visual y la legibilidad de su presentación en varios sistemas.

En esta guía, exploraremos cómo crear y administrar reglas de reserva de fuentes con Aspose.Slides para Python. Aprenderá:
- Configurando su entorno con Aspose.Slides
- Creación de una colección de reglas de reserva de fuentes
- Administrar estas reglas agregando o eliminando fuentes según rangos Unicode
- Aplicar las reglas a las presentaciones y renderizar diapositivas como imágenes

Comencemos por preparar tu entorno.

## Prerrequisitos

Asegúrese de que su entorno esté preparado para esta tarea. Necesitará lo siguiente:
1. **Aspose.Slides para Python**:Esta biblioteca administra las reglas de reserva de fuentes.
2. **Entorno de Python**:Asegúrese de que Python (versión 3.6 o posterior) esté instalado.
3. **Conocimientos básicos de Python**:La familiaridad con la sintaxis y los conceptos de Python será útil a medida que profundizamos en fragmentos de código.

## Configuración de Aspose.Slides para Python

### Instalación

Para comenzar, instale la biblioteca Aspose.Slides usando pip:

```bash
pip install aspose.slides
```

### Adquisición de licencias

Aspose ofrece una licencia de prueba gratuita para explorar sus funciones sin limitaciones. Puedes obtenerla así:
- Visita [Página de compra de Aspose](https://purchase.aspose.com/buy) para comprar opciones o acceder a una licencia temporal.
- Alternativamente, descargue una versión de prueba gratuita desde [Sección de descargas](https://releases.aspose.com/slides/python-net/).

### Inicialización básica

Una vez instalado, inicialice Aspose.Slides en su script de Python:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Guía de implementación

### Creación y gestión de reglas de reserva de fuentes

#### Descripción general

Las reglas de reserva de fuentes garantizan que todos los caracteres de su presentación tengan una fuente apropiada, manteniendo la legibilidad para idiomas con conjuntos de caracteres únicos.

#### Pasos de implementación

**1. Crear una colección de reglas de reserva de fuentes**

Comience creando una colección para definir fuentes de respaldo:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Agregar una regla de reserva de fuentes**

Define una regla que especifique el rango Unicode y la fuente de reserva:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Parámetros**: `0x400` es el comienzo de la gama Unicode, `0x4FF` es el final, y `"Times New Roman"` Es la fuente de reserva.

**3. Administrar reglas existentes**

Itere sobre cada regla para modificarlas según sea necesario:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Eliminar una regla**

Si es necesario, elimine la primera regla de su colección:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Aplicación de reglas de reserva de fuentes a una presentación y renderizado de una imagen

#### Descripción general

Una vez configuradas las reglas de reserva de fuentes, aplíquelas a las presentaciones para garantizar que el texto use las fuentes de reserva especificadas cuando sea necesario.

#### Pasos de implementación

**1. Inicialice su entorno**

Preparar directorios para entrada y salida:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Aplicar reglas de respaldo a una presentación**

Cargue su archivo de presentación y aplique las reglas de fuente:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
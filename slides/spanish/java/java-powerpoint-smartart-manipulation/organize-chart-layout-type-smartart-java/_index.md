---
"description": "Domine los tipos de diseño de organigramas en SmartArt usando Java con Aspose.Slides, mejorando las imágenes de las presentaciones sin esfuerzo."
"linktitle": "Organizar el tipo de diseño de gráfico en SmartArt con Java"
"second_title": "API de procesamiento de PowerPoint en Java de Aspose.Slides"
"title": "Organizar el tipo de diseño de gráfico en SmartArt con Java"
"url": "/es/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Organizar el tipo de diseño de gráfico en SmartArt con Java

## Introducción
En este tutorial, explicaremos el proceso de organización de tipos de diseño de gráficos en SmartArt con Java, aprovechando específicamente la biblioteca Aspose.Slides. SmartArt en presentaciones puede mejorar considerablemente el atractivo visual y la claridad de los datos, por lo que es fundamental dominar su manejo.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Java Development Kit (JDK) instalado en su sistema.
2. Biblioteca Aspose.Slides descargada e instalada. Si aún no lo has hecho, descárgala desde [aquí](https://releases.aspose.com/slides/java/).
3. Comprensión básica de la programación Java.

## Importar paquetes
En primer lugar, importe los paquetes necesarios:
```java
import com.aspose.slides.*;
```
Dividamos el ejemplo proporcionado en varios pasos:
## Paso 1: Inicializar el objeto de presentación
```java
Presentation presentation = new Presentation();
```
Crear un nuevo objeto de presentación.
## Paso 2: Agregar SmartArt a la diapositiva
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Agregue SmartArt a la diapositiva deseada con las dimensiones y el tipo de diseño especificados.
## Paso 3: Establecer el diseño del organigrama
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Establezca el tipo de diseño del organigrama. En este ejemplo, usamos el diseño "Abierto a la izquierda".
## Paso 4: Guardar la presentación
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Guarde la presentación con el diseño de gráfico organizado.

## Conclusión
Dominar la organización de los tipos de diseño de gráficos en SmartArt con Java te permite crear presentaciones visualmente atractivas con facilidad. Con Aspose.Slides, el proceso se simplifica y se vuelve eficiente, permitiéndote concentrarte en crear contenido impactante.
## Preguntas frecuentes
### ¿Aspose.Slides es compatible con diferentes entornos de desarrollo Java?
Sí, Aspose.Slides es compatible con varios entornos de desarrollo Java, lo que garantiza flexibilidad para los desarrolladores.
### ¿Puedo personalizar la apariencia de los elementos SmartArt usando Aspose.Slides?
Por supuesto, Aspose.Slides ofrece amplias opciones de personalización para los elementos SmartArt, lo que le permite adaptarlos a sus requisitos específicos.
### ¿Aspose.Slides ofrece documentación completa para desarrolladores?
Sí, los desarrolladores pueden consultar la documentación detallada proporcionada por Aspose.Slides para Java, que ofrece información sobre sus funcionalidades y uso.
### ¿Hay una versión de prueba disponible para Aspose.Slides?
Sí, puedes acceder a una versión de prueba gratuita de Aspose.Slides para explorar sus funciones antes de tomar una decisión de compra.
### ¿Dónde puedo buscar ayuda para consultas relacionadas con Aspose.Slides?
Para cualquier ayuda o consulta sobre Aspose.Slides, puede visitar el foro de soporte [aquí](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
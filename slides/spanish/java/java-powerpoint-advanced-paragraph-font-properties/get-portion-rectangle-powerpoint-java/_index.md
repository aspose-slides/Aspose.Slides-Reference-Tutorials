---
title: Obtener rectángulo de porción en PowerPoint con Java
linktitle: Obtener rectángulo de porción en PowerPoint con Java
second_title: Aspose.Slides API de procesamiento de PowerPoint Java
description: Aprenda cómo obtener la porción del rectángulo en PowerPoint usando Aspose.Slides para Java con este tutorial detallado paso a paso. Perfecto para desarrolladores de Java.
weight: 12
url: /es/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtener rectángulo de porción en PowerPoint con Java

## Introducción
Crear presentaciones dinámicas en Java es muy sencillo con Aspose.Slides para Java. En este tutorial, profundizaremos en el meollo de la cuestión de cómo obtener la porción del rectángulo en PowerPoint usando Aspose.Slides. Cubriremos todo, desde configurar su entorno hasta desglosar el código paso a paso. ¡Entonces empecemos!
## Requisitos previos
Antes de pasar al código, asegurémonos de que tiene todo lo que necesita para seguirlo sin problemas:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK 8 o superior instalado en su máquina.
2.  Aspose.Slides para Java: descargue la última versión desde[aquí](https://releases.aspose.com/slides/java/).
3. Entorno de desarrollo integrado (IDE): Eclipse, IntelliJ IDEA o cualquier otro IDE de Java de su elección.
4. Conocimientos básicos de Java: la comprensión de la programación Java es esencial.
## Importar paquetes
Primero lo primero, importemos los paquetes necesarios. Esto incluirá Aspose.Slides y algunos otros para manejar nuestra tarea de manera eficiente.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Paso 1: configurar la presentación
El primer paso es crear una nueva presentación. Este será nuestro lienzo sobre el que trabajar.
```java
Presentation pres = new Presentation();
```
## Paso 2: crear una tabla
Ahora, agreguemos una tabla a la primera diapositiva de nuestra presentación. Esta tabla contendrá las celdas donde agregaremos nuestro texto.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Paso 3: agregar párrafos a las celdas
A continuación, crearemos párrafos y los agregaremos a una celda específica de la tabla. Esto implica borrar cualquier texto existente y luego agregar nuevos párrafos.
```java
// Crear párrafos
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Agregar texto a la celda de la tabla
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Paso 4: agregar un marco de texto a una autoforma
Para hacer nuestra presentación más dinámica, agregaremos un marco de texto a una Autoforma y estableceremos su alineación.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Paso 5: Calcular coordenadas
Necesitamos obtener las coordenadas de la esquina superior izquierda de la celda de la tabla. Esto nos ayudará a colocar las formas con precisión.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Paso 6: agregar marcos a párrafos y partes
 Utilizando el`IParagraph.getRect()` y`IPortion.getRect()`métodos, podemos agregar marcos a nuestros párrafos y partes. Esto implica recorrer los párrafos y partes, crear formas a su alrededor y personalizar su apariencia.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Paso 7: agregar marcos a los párrafos de autoforma
De manera similar, agregaremos marcos a los párrafos de nuestra Autoforma, mejorando el atractivo visual de la presentación.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Paso 8: guardar la presentación
Finalmente, guardaremos nuestra presentación en una ruta especificada.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Paso 9: Limpiar
Es una buena práctica deshacerse del objeto de presentación para liberar recursos.
```java
if (pres != null) pres.dispose();
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo obtener la porción del rectángulo en PowerPoint usando Aspose.Slides para Java. Esta poderosa biblioteca abre un mundo de posibilidades para crear presentaciones dinámicas y visualmente atractivas mediante programación. Profundice en Aspose.Slides y explore más funciones para mejorar aún más sus presentaciones.
## Preguntas frecuentes
### ¿Qué es Aspose.Slides para Java?
Aspose.Slides para Java es una poderosa biblioteca que permite a los desarrolladores crear, modificar y manipular presentaciones de PowerPoint mediante programación.
### ¿Puedo utilizar Aspose.Slides para Java en proyectos comerciales?
 Sí, Aspose.Slides para Java se puede utilizar en proyectos comerciales. Puede adquirir una licencia en[aquí](https://purchase.aspose.com/buy).
### ¿Hay una prueba gratuita disponible para Aspose.Slides para Java?
 Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar la documentación de Aspose.Slides para Java?
 La documentación está disponible.[aquí](https://reference.aspose.com/slides/java/).
### ¿Cómo puedo obtener soporte para Aspose.Slides para Java?
 Puede obtener soporte en el foro de Aspose.[aquí](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

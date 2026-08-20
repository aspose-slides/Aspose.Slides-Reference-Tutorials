---
date: '2026-08-06'
description: Aprenda cómo cambiar el color de fuente de la leyenda y modificar el
  texto de la leyenda del gráfico usando Aspose.Slides for Java. Siga instrucciones
  paso a paso para personalizar rápidamente las leyendas de los gráficos.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Aprenda cómo cambiar el color de fuente de la leyenda y modificar
  el texto de la leyenda del gráfico con Aspose.Slides for Java. Esta guía le muestra
  los pasos exactos y las mejores prácticas.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Cómo cambiar el color de fuente de la leyenda en Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Cómo cambiar el color de fuente de la leyenda en Aspose.Slides for Java
url: /es/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo cambiar el color de fuente de la leyenda en Aspose.Slides for Java

## Introducción
Si necesita **change legend font color** en un gráfico, Aspose.Slides for Java le brinda control total sobre cada entrada de la leyenda. Este tutorial le guía a través de la personalización de los estilos de texto de la leyenda, la aplicación de fuentes en negrita o cursiva, y la configuración de colores sólidos para que sus gráficos se vean exactamente como desea. Al final de esta guía podrá modificar el texto de la leyenda del gráfico con confianza e integrar los cambios en cualquier presentación existente.

**Lo que aprenderá**
- Cómo **change legend font color** programáticamente.
- Formas de **modify chart legend text** como negrita, cursiva y tamaño.
- Consejos para aplicar los cambios a varios gráficos en una presentación.
- Cómo integrar estos pasos en un flujo de trabajo de automatización más amplio.

## Respuestas rápidas
- **¿Puedo cambiar el color de una sola entrada de la leyenda?** Sí – acceda a la entrada mediante su índice y establezca el formato de relleno a un color sólido.  
- **¿Necesito una licencia para usar estas APIs?** Se requiere una licencia temporal o de pago para producción; una prueba gratuita funciona para evaluación.  
- **¿Qué versión de Java es compatible?** Aspose.Slides for Java 25.4+ funciona con JDK 16 y versiones posteriores.  
- **¿Los cambios afectarán a otros elementos del gráfico?** No, el formato de la leyenda está aislado del estilo de las series de datos.  
- **¿Es posible el procesamiento por lotes?** Absolutamente – recorra diapositivas y gráficos para aplicar la misma configuración de leyenda en todo el conjunto.

## ¿Qué es change legend font color?
`change legend font color` se refiere a la operación programática de establecer el color del texto de las entradas de la leyenda de un gráfico mediante la API de Aspose.Slides. Esta operación actualiza la apariencia visual de la leyenda sin alterar los datos subyacentes.

## ¿Por qué personalizar las leyendas de los gráficos?
Aspose.Slides admite **más de 50 formatos de entrada y salida** y puede manejar presentaciones con **más de 500 diapositivas** manteniendo el uso de memoria por debajo de 200 MB. Personalizar las leyendas mejora la legibilidad, refuerza los colores de la marca y asegura que los puntos de datos clave destaquen, especialmente en presentaciones empresariales o educativas donde la claridad visual impulsa la toma de decisiones.

## Requisitos previos
- Biblioteca **Aspose.Slides for Java** (Versión 25.4 o posterior).  
- Java Development Kit (JDK) 16 o superior.  
- Un IDE como IntelliJ IDEA, Eclipse o NetBeans.  
- Maven o Gradle para la gestión de dependencias.  
- Conocimientos básicos de programación en Java.

## Configuración de Aspose.Slides for Java
Para comenzar a personalizar las leyendas de sus gráficos, agregue la biblioteca a su proyecto usando uno de los métodos a continuación.

### Maven
Agregue la siguiente dependencia a su archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluya esta línea en su archivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
También puede obtener el JAR más reciente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Pasos para la adquisición de licencia
- **Prueba gratuita:** Comience con una prueba gratuita para explorar las funciones de Aspose.Slides.  
- **Licencia temporal:** Solicite una licencia temporal para una evaluación prolongada.  
- **Compra:** Para acceso completo, considere comprar una licencia en [Aspose Purchase](https://purchase.aspose.com/buy).

#### Inicialización y configuración básica
Después de agregar la biblioteca a su proyecto:
1. Inicialice Aspose.Slides en su aplicación Java.  
2. Cargue una presentación existente o cree una nueva.

## ¿Cómo cambiar el color de fuente de la leyenda?
Para cambiar el color de fuente de la leyenda, cargue la presentación, recupere el objeto del gráfico, obtenga su leyenda y luego modifique el formato de texto de cada entrada de la leyenda estableciendo el tipo de relleno a sólido y especificando el color deseado. Esta única operación actualiza el color del texto de la leyenda al instante sin necesidad de volver a dibujar toda la diapositiva. Ejemplo: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Este enfoque funciona para cualquier tipo de gráfico y no requiere volver a renderizar toda la diapositiva.

### Acceso y modificación de propiedades de texto de la leyenda

#### Ancla de definición
La interfaz `IChart` representa un objeto de gráfico en una diapositiva, y su método `getLegend()` devuelve un objeto `ILegend` que contiene una colección de elementos `ILegendEntry`.

#### Añadiendo un gráfico a su presentación
1. **Cargar la presentación:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Agregar un gráfico de columnas agrupadas:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Personalizando propiedades de fuente
3. **Acceder al formato de texto de la entrada de la leyenda:**  
   Aquí, `legendEntry` es un objeto `ILegendEntry` que representa una única entrada en la leyenda del gráfico.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Establecer estilos en negrita e cursiva con una altura específica:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Cambiar el tipo de relleno a color sólido para mejor visibilidad:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Guardando la presentación
6. **Guardar sus cambios:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Errores comunes y solución de problemas
- Verifique que el índice de la entrada de la leyenda coincida con el orden de las series en su gráfico.  
- Asegúrese de estar usando una versión de la biblioteca que soporte `setSolidFillColor` (disponible desde la versión 20.9).  

## Aplicaciones prácticas
Personalizar el texto de la leyenda es útil en muchos escenarios del mundo real:

1. **Presentaciones empresariales:** Alinee los colores de la leyenda con la marca corporativa para un aspecto pulido.  
2. **Materiales educativos:** Resalte series de datos clave usando colores de leyenda contrastantes.  
3. **Presentaciones de marketing:** Enfatice métricas de rendimiento con leyendas en negrita y coloridas para captar la atención de los interesados.  

También puede automatizar la actualización de leyendas extrayendo valores de color de una base de datos o archivo de configuración.

## Consideraciones de rendimiento
Al procesar presentaciones grandes, tenga en cuenta estos consejos:

- **Gestión eficiente de memoria:** Llame a `presentation.dispose()` después de guardar para liberar recursos nativos.  
- **Cargar solo diapositivas necesarias:** Use `Presentation.load(String path, LoadOptions options)` con `LoadOptions.setLoadOnlySlideIds()` si necesita un subconjunto.  
- **Procesamiento por lotes:** Agrupe actualizaciones de leyenda por diapositiva para reducir el número de llamadas a la API y mejorar el rendimiento.

## Conclusión
Ahora sabe cómo **change legend font color** y **modify chart legend text** usando Aspose.Slides for Java. Estas personalizaciones mejoran la claridad visual y le ayudan a transmitir los datos de manera más eficaz. Experimente con diferentes fuentes, tamaños y colores para que coincidan con la guía de estilo de su presentación, y explore otras funciones de estilo de gráficos para crear presentaciones verdaderamente profesionales.

**Próximos pasos**
- Intente aplicar el mismo estilo de leyenda a gráficos de pastel y de líneas.  
- Combine la personalización de la leyenda con el formato de etiquetas de datos para un gráfico totalmente con la marca.  

¿Listo para elevar sus presentaciones? ¡Implemente los pasos anteriores y vea la diferencia al instante!

## Sección de Preguntas Frecuentes
1. **¿Cómo cambio el color del texto de una entrada de la leyenda?**  
   Use `getFillFormat().setFillType(FillType.Solid)` y luego `setSolidFillColor(Color.YOUR_COLOR)` en el formato de texto de la entrada de la leyenda.

2. **¿Puedo aplicar estos cambios a todas las leyendas de una presentación?**  
   Sí – itere a través de cada diapositiva, localice cada gráfico y actualice sus entradas de leyenda dentro de un bucle.

3. **¿Es posible ajustar el tamaño de fuente dinámicamente según la longitud del texto?**  
   Puede calcular el tamaño necesario con `TextFrame.getTextFrameFormat().getFontHeight()` y establecerlo mediante `setFontHeight(double)`.

4. **¿Qué hago si encuentro problemas con el indexado de entradas de la leyenda?**  
   Verifique que el índice que usa coincida con el orden de las series; recuerde que los índices comienzan en cero.

5. **¿Dónde encuentro más ejemplos de Aspose.Slides?**  
   Explore la [Aspose Documentation](https://reference.aspose.com/slides/java/) para guías completas y referencias de API.

**Preguntas y Respuestas Adicionales**

**P: ¿Cambiar el color de fuente de la leyenda afecta a los archivos PDF exportados?**  
R: No, el cambio de color se conserva en todos los formatos de exportación compatibles con Aspose.Slides, incluidos PDF y PPTX.

**P: ¿Puedo usar un degradado en lugar de un color sólido?**  
R: Sí – establezca `FillType.Gradient` y configure las paradas del degradado mediante `getGradientStyle()`.

**P: ¿Cuántas entradas de leyenda puede tener un gráfico?**  
R: Un gráfico puede tener hasta 256 entradas de leyenda, limitado solo por la cantidad de series de datos que añada.

## Recursos
- **Documentación:** Guía completa sobre el uso de las funciones de Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Descarga:** Acceda a la última versión de Aspose.Slides for Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Compra:** Adquiera una licencia para desbloquear todas las capacidades ([Link](https://purchase.aspose.com/buy)).  
- **Prueba gratuita y licencia temporal:** Comience con pruebas gratuitas y solicite licencias temporales ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Soporte:** Obtenga ayuda de la comunidad en el foro de soporte de Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Última actualización:** 2026-08-06  
**Probado con:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Tutoriales relacionados

- [Mejorando los gráficos de PowerPoint: Personalización de fuentes y ejes con Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Guía de marcos de texto dinámicos y personalización de fuentes](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animar gráficos en PowerPoint usando Aspose.Slides for Java – Guía paso a paso](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-09-17'
description: Aprenda cómo crear bubble chart PowerPoint usando Aspose.Slides for Java.
  Esta guía le muestra cómo agregar chart a la diapositiva, configurar bubble size
  y guardar el PPTX de manera eficiente.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Aprenda cómo crear bubble chart PowerPoint usando Aspose.Slides for
  Java. Este tutorial explica cómo agregar chart a la diapositiva, ajustar bubble
  sizes y guardar la presentación de manera eficiente.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Crear bubble chart PowerPoint con Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Crear bubble chart PowerPoint con Aspose.Slides for Java
url: /es/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear gráfico de burbujas en PowerPoint con Aspose.Slides para Java

## Introducción
Si necesita **crear presentaciones de PowerPoint con gráficos de burbujas** de forma programática, Aspose.Slides para Java le ofrece una API limpia del lado del servidor que funciona sin Microsoft Office. En este tutorial aprenderá cómo agregar un gráfico a una diapositiva, controlar el tamaño de las burbujas y guardar el PPTX final mientras gestiona los recursos de manera eficiente. Los pasos están desglosados para que pueda copiar‑pegar el código en cualquier proyecto Java y ver los resultados al instante.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Slides for Java
- **¿Qué versión de Java se requiere?** JDK 16 o superior
- **¿Cómo agrego un gráfico de burbujas?** Llame a `addChart(ChartType.Bubble, …)` en una diapositiva
- **¿Puedo cambiar el tamaño de la burbuja?** Sí, mediante `setBubbleSizeScale()`
- **¿Cómo guardo el archivo?** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## ¿Qué es crear un gráfico de burbujas en PowerPoint?
Crear un gráfico de burbujas en PowerPoint significa generar programáticamente un gráfico donde cada punto de datos está representado por una burbuja cuya posición X, posición Y y tamaño codifican tres dimensiones de datos. Aspose.Slides para Java se encarga del renderizado, por lo que no necesita tener PowerPoint instalado.

## ¿Por qué usar Aspose.Slides para Java?
Aspose.Slides admite **más de 50 tipos de gráficos**, puede procesar presentaciones de hasta **2 GB** sin cargar todo el archivo en memoria, y se ejecuta en cualquier plataforma que soporte Java 16+. Estas capacidades cuantificadas lo convierten en una opción fiable para informes de nivel empresarial.

## Requisitos previos
- **Java Development Kit** 16 o posterior instalado.
- Biblioteca **Aspose.Slides for Java** (agregue mediante Maven, Gradle o descarga directa del JAR).
- Familiaridad básica con la sintaxis de Java y la programación orientada a objetos.

## Configuración de Aspose.Slides para Java
Para comenzar a usar Aspose.Slides, incluya la biblioteca en su sistema de compilación.

### Maven
Agregue la siguiente dependencia a su `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluya esto en su `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Descarga directa
También puede obtener el JAR más reciente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Obtención de licencia
- **Prueba gratuita** – explore todas las funciones sin costo.  
- **Licencia temporal** – evaluación ampliada para proyectos más grandes.  
- **Licencia completa** – requerida para implementaciones en producción.

### Inicialización y configuración básica
La clase `Presentation` es el punto de entrada para crear o cargar archivos PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Guía de implementación
A continuación se muestra una guía paso a paso para crear un gráfico de burbujas y gestionar los recursos.

## Cómo crear un gráfico de burbujas en PowerPoint
En esta sección aprenderá la secuencia exacta de llamadas a la API necesarias para generar un gráfico de burbujas, configurar sus propiedades visuales y guardar el resultado como un archivo PPTX. El enfoque funciona para cualquier proyecto Java que incluya Aspose.Slides y siga las mejores prácticas de gestión de recursos.

Cargue la presentación, agregue un gráfico de burbujas, configure su apariencia y guarde el archivo.

### Respuesta directa
Cree una nueva `Presentation`, llame a `addChart(ChartType.Bubble, …)` en la diapositiva deseada, ajuste la escala del tamaño de la burbuja con `setBubbleSizeScale(150)`, y luego guarde usando `pres.save("Result.pptx", SaveFormat.Pptx)`. Esta secuencia agrega un gráfico de burbujas totalmente funcional en solo unas pocas líneas de Java.

- **`ChartType.Bubble`** representa el tipo de gráfico de burbujas.  
- **`addChart`** inserta un nuevo gráfico del tipo especificado en una diapositiva.  
- **`setBubbleSizeScale`** ajusta el tamaño general de las burbujas en el gráfico.  
- **`SaveFormat.Pptx`** especifica el formato de archivo PPTX para guardar.  

#### Implementación paso a paso
**1. Inicializar la presentación** – instanciar el objeto `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Agregar gráfico de burbujas** – insertar el gráfico en las coordenadas elegidas.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` indica a Aspose.Slides que cree un gráfico de burbujas.  
- Los parámetros numéricos definen la posición X/Y y el ancho/alto en puntos.

**3. Configurar la escala del tamaño de la burbuja** – agrandar las burbujas para un mejor impacto visual.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Establecer la escala al **150 %** hace que cada burbuja sea 1.5 × más grande que el valor predeterminado.

**4. Guardar la presentación** – escribir el PPTX en disco.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Consejos de solución de problemas
- Verifique los permisos de escritura para la carpeta de salida.  
- Confirme que el JAR de Aspose.Slides coincida con la versión del JDK que está utilizando.

## Cómo gestionar los recursos de PowerPoint de manera eficaz
Una gestión eficaz de los recursos previene fugas de memoria y mantiene bajo el consumo de la JVM, especialmente al procesar presentaciones grandes o ejecutar en un entorno de servidor. Siga el patrón a continuación para garantizar que los recursos nativos se liberen incluso si ocurre una excepción.

Una gestión eficiente de recursos previene fugas de memoria, especialmente al procesar presentaciones grandes.

### Respuesta directa
Después de terminar de trabajar con una `Presentation`, siempre llame a `pres.dispose()` dentro de un bloque `try‑finally`; esto libera los recursos nativos y permite que la JVM recupere la memoria rápidamente.

- **`pres.dispose()`** libera los recursos nativos utilizados por la presentación.

**1. Crear y modificar** – trabajar con la presentación según sea necesario.  
```java
Presentation pres = new Presentation();
```

**2. Liberar recursos** – liberar la memoria una vez completado el procesamiento.  
```java
if (pres != null) pres.dispose();
```

## Aplicaciones prácticas
Los gráficos de burbujas sobresalen en escenarios donde se necesitan visualizar simultáneamente tres dimensiones de datos:

1. **Análisis de mercado** – el tamaño de la burbuja representa los ingresos mientras que los ejes X/Y muestran el crecimiento y la cuota de mercado.  
2. **Métricas de rendimiento** – comparar la productividad del empleado (X), la satisfacción (Y) y el impacto (tamaño).  
3. **Datos geográficos** – trazar ciudades con la población codificada en el tamaño de la burbuja.  
4. **Gestión de proyectos** – visualizar la línea de tiempo (X), el costo (Y) y el riesgo (tamaño) en una sola diapositiva.

## Consideraciones de rendimiento
- **Uso de recursos** – libere las presentaciones rápidamente para mantener bajo el uso del heap.  
- **Gestión de memoria en Java** – envuelva el trabajo con la presentación en `try‑finally` para garantizar la liberación incluso en caso de excepciones.  
- **Manténgase actualizado** – actualice a la última versión de Aspose.Slides para beneficiarse de optimizaciones de rendimiento y correcciones de errores.

## Preguntas frecuentes

**Q: ¿Qué es Aspose.Slides for Java?**  
A: Aspose.Slides for Java es una biblioteca independiente que le permite crear, editar y convertir archivos PowerPoint sin necesidad de Microsoft Office.

**Q: ¿Cómo integro Aspose.Slides con mi proyecto Java existente?**  
A: Agregue la dependencia Maven o Gradle mostrada anteriormente, o coloque el JAR en su classpath, luego importe `com.aspose.slides.*`.

**Q: ¿Puedo usar Aspose.Slides para presentaciones grandes?**  
A: Sí, la biblioteca maneja eficientemente presentaciones de hasta **2 GB** y soporta streaming para evitar cargar todo el archivo en memoria.

**Q: ¿Qué tipos de gráficos están disponibles además de los gráficos de burbujas?**  
A: Se admiten más de **50 tipos de gráficos**, incluidos de barras, líneas, pastel, radar y cascada.

**Q: ¿Existe soporte incorporado para estilizar los elementos del gráfico?**  
A: Absolutamente. Puede personalizar colores, fuentes, bordes y etiquetas de datos mediante los objetos `ChartSeries` y `ChartTitle` del gráfico.

## Recursos
- **Documentación**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Descarga**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Compra**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Prueba gratuita**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Licencia temporal**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Soporte**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

## Tutoriales relacionados

- [Cómo agregar un gráfico a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Crear gráfico de PowerPoint en Java usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Crear gráfico de PowerPoint en Java – Guardar presentaciones con gráficos usando Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
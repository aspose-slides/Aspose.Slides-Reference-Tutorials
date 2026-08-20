---
date: '2026-07-27'
description: Aprenda cómo crear doughnut chart java usando Aspose.Slides – una guía
  rápida para set up the library, add a customizable doughnut chart, adjust hole size,
  y guardar la presentación.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Aprenda cómo crear doughnut chart java usando Aspose.Slides – una
  guía rápida para set up the library, add a customizable doughnut chart, adjust hole
  size, y guardar la presentación.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Crear Doughnut Chart Java – Paso a paso con Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Crear Doughnut Chart Java – Paso a paso con Aspose.Slides
url: /es/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo crear gráficos de rosquilla en Java usando Aspose.Slides para presentaciones

## Introducción
Crear presentaciones visualmente atractivas es esencial para transmitir información de manera eficaz. **Create doughnut chart java** es un requisito común cuando necesitas ilustrar datos proporcionales con un aspecto moderno. En este tutorial aprenderás a configurar Aspose.Slides para Java, crear un gráfico de rosquilla, personalizar su tamaño de agujero y colores, y finalmente guardar el archivo de presentación. Al final tendrás un patrón reutilizable que puedes incorporar en cualquier proyecto Java que genere presentaciones PowerPoint automáticamente.

**Lo que aprenderás:**
- Configurar Aspose.Slides para Java
- Crear y configurar gráficos de rosquilla en presentaciones
- Ajustar la estética del gráfico, como el tamaño del agujero
- Guardar la presentación con tu nuevo gráfico

¡Comencemos configurando nuestro entorno!

## Respuestas rápidas
- **¿Qué biblioteca crea doughnut chart java?** Aspose.Slides for Java.  
- **¿Cuántas líneas de código se necesitan para un gráfico de rosquilla básico?** Aproximadamente 8–10 líneas después de instanciar la presentación.  
- **¿Puedo cambiar el tamaño del agujero?** Sí, el método `setHoleSize(double)` acepta valores de 0 % a 100 %.  
- **¿Qué formatos de salida son compatibles?** PPTX, PDF, XPS, PNG, JPEG y varios otros (más de 50 en total).  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para uso ilimitado; una prueba gratuita funciona para evaluación.

## ¿Qué es Aspose.Slides para Java?
**Aspose.Slides for Java** es una API totalmente gestionada que permite a los desarrolladores crear, modificar, convertir y renderizar archivos PowerPoint sin Microsoft Office. Soporta más de 50 formatos de archivo y puede manejar presentaciones con miles de diapositivas manteniendo bajo el uso de memoria.

## ¿Por qué usar gráficos de rosquilla en presentaciones?
Los gráficos de rosquilla muestran relaciones parte‑todo mientras liberan espacio en el centro para etiquetas o imágenes. Aspose.Slides puede renderizar gráficos de rosquilla hasta **500 diapositivas por minuto** en un servidor típico de 2.5 GHz, y procesa **presentaciones de cientos de páginas** sin cargar todo el archivo en memoria, lo que lo hace ideal para soluciones de informes a gran escala.

## Requisitos previos
Antes de comenzar, asegúrate de haber cubierto estos requisitos:

### Bibliotecas y versiones requeridas
Para trabajar con Aspose.Slides para Java, inclúyelo en tu proyecto mediante Maven o Gradle, o descárgalo directamente.

#### Requisitos de configuración del entorno
- Un Java Development Kit (JDK) funcional, preferiblemente versión 8 o superior.
- Un Entorno de Desarrollo Integrado (IDE) como IntelliJ IDEA o Eclipse.

### Conocimientos previos
Familiaridad con Java y conceptos básicos de programación es beneficioso. Conocimientos básicos de Maven o Gradle ayudarán a simplificar el proceso de configuración.

## Configuración de Aspose.Slides para Java
Incorporar Aspose.Slides en tu proyecto se puede hacer de varias maneras:

**Maven:**  
Agrega esta dependencia a tu archivo `pom.xml`:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Incluye esto en tu archivo `build.gradle`:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa:**  
Alternativamente, descarga la última versión desde [lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Obtención de licencia
- **Prueba gratuita:** Comienza descargando una versión de prueba para explorar las características de Aspose.Slides.  
- **Licencia temporal:** Obtén una licencia temporal para funcionalidad extendida sin limitaciones.  
- **Compra:** Para uso continuo, se requiere comprar una licencia.  

Una vez que tengas la biblioteca configurada y tu entorno listo, pasemos a implementar nuestro gráfico de rosquilla.

## ¿Cómo crear un gráfico de rosquilla en Java?
Carga un nuevo objeto `Presentation`, agrega un gráfico de rosquilla a una diapositiva, establece el tamaño del agujero y guarda el archivo, todo en unas pocas llamadas API sencillas. Este enfoque te brinda control total sobre los datos del gráfico, su apariencia y el formato de exportación, y funciona sin necesidad de tener Microsoft PowerPoint instalado en el servidor.

### Inicializar objeto Presentation
La clase `Presentation` es el objeto de nivel superior de Aspose.Slides que representa un archivo PowerPoint en memoria.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Este paso crea una presentación vacía donde puedes agregar diapositivas, formas y gráficos.

### Agregar gráfico de rosquilla a la diapositiva
`ISlide` es la interfaz para una sola diapositiva; puedes obtener la primera diapositiva o agregar una nueva.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
El método `addChart` crea un gráfico de rosquilla; los parámetros definen su posición (X, Y) y tamaño (ancho, alto) en la diapositiva.

### Configurar el tamaño del agujero del rosquilla
`Chart` expone `setHoleSize(double)` para controlar el radio interno como porcentaje del radio del gráfico.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Establecer el tamaño del agujero al 90 % hace que el gráfico aparezca casi como un círculo completo, lo cual es útil cuando deseas enfatizar los segmentos externos.

### Guardar la presentación
`presentation.save(String, SaveFormat)` escribe el archivo en disco en el formato elegido.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
El ejemplo guarda el resultado como `DoughnutHoleSize_out.pptx`, pero también podrías elegir PDF, PNG o cualquiera de los más de 50 formatos compatibles.

### Liberar recursos
Llamar a `presentation.dispose()` libera recursos nativos y previene fugas de memoria, especialmente importante en aplicaciones de servidor de larga duración.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Aplicaciones prácticas
Los gráficos de rosquilla son versátiles. Aquí hay algunos escenarios donde destacan:
1. **Asignación de presupuesto:** Muestra cómo se distribuye un presupuesto entre departamentos.  
2. **Resultados de encuestas:** Visualiza respuestas a preguntas con opciones múltiples.  
3. **Fuentes de tráfico web:** Muestra el porcentaje de tráfico proveniente de diferentes canales (orgánico, pagado, referido, etc.).

## Consideraciones de rendimiento
Al trabajar con Aspose.Slides, considera estos consejos para un rendimiento óptimo:
- Desecha los objetos `Presentation` tan pronto como termines para liberar memoria nativa.  
- Utiliza streams (`FileInputStream`, `ByteArrayOutputStream`) para conjuntos de datos grandes y evitar cargar archivos completos en RAM.  
- Reutiliza objetos de gráfico al generar muchas diapositivas en un bucle para reducir la sobrecarga de creación de objetos.  

## Problemas comunes y soluciones
- **Error al guardar:** Verifica que el directorio de salida exista y que la aplicación tenga permisos de escritura.  
- **Datos del gráfico faltantes:** Asegúrate de rellenar la colección `ChartData` del gráfico antes de llamar a `setHoleSize`.  
- **Picos de memoria:** Para presentaciones con miles de diapositivas, habilita `Presentation.setSlideSize` a un tamaño más pequeño y desecha las diapositivas intermedias rápidamente.  

## Preguntas frecuentes

**Q: ¿Puedo ajustar los colores de los segmentos de mi gráfico de rosquilla?**  
A: Sí. Usa `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` y luego especifica el color RGB deseado.

**Q: ¿Cómo agrego etiquetas de datos a mi gráfico?**  
A: Llama a `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` para mostrar el valor dentro de cada segmento.

**Q: ¿Es posible guardar los gráficos en formatos diferentes a PPTX?**  
A: Por supuesto. Aspose.Slides soporta PDF, XPS, PNG, JPEG, TIFF y muchos otros formatos—más de 50 en total.

**Q: ¿Qué debo hacer si encuentro una excepción al cargar una presentación grande?**  
A: Usa el constructor `Presentation` que acepta un stream y habilita `loadOptions.setLoadFormat(LoadFormat.Pptx)` para transmitir el archivo y reducir el consumo de memoria.

**Q: ¿Puedo automatizar actualizaciones de gráficos con fuentes de datos en vivo?**  
A: Sí. Recupera datos de una base de datos o API REST, actualiza la colección `ChartData` y llama a `chart.refresh()` antes de guardar la presentación.

## Recursos
- **Documentación:** Explora referencias API detalladas en [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Descarga:** Obtén la última versión de la biblioteca desde [lanzamientos de Aspose.Slides](https://releases.aspose.com/slides/java/).  
- **Compra:** Para acceso completo, compra una licencia en [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Prueba gratuita:** Prueba Aspose.Slides con una versión de prueba gratuita disponible en su página de descargas.  
- **Licencia temporal:** Obtén una licencia temporal para pruebas extendidas sin limitaciones.  
- **Soporte:** ¿Tienes preguntas? Visita el [Aspose Forum](https://forum.aspose.com/c/slides/11) para obtener ayuda.

---

**Última actualización:** 2026-07-27  
**Probado con:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo agregar gráficos a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Cómo crear un gráfico en Java con Aspose.Slides: Guía completa](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
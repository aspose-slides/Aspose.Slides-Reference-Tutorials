---
date: '2026-05-29'
description: Aprenda cómo crear un gráfico de pastel Aspose usando Aspose.Slides Maven,
  añadir un gráfico de pastel Java a una diapositiva y personalizar los datos del
  gráfico. Guía paso a paso con la configuración de Maven y ejemplos del mundo real.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Crear gráfico de pastel Aspose – Añadir un gráfico a una presentación con Maven
url: /es/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cómo agregar un gráfico circular a una presentación usando Aspose.Slides Java

## Introducción
En esta guía crearás **create pie chart aspose** con Aspose.Slides Maven y verás cómo incrustarlo en una diapositiva de PowerPoint. Crear presentaciones visualmente atractivas es crucial para transmitir información de manera eficaz, especialmente cuando la visualización de datos desempeña un papel clave. Si deseas automatizar este proceso con **aspose slides maven**, has llegado al lugar correcto. Recorreremos el proceso de agregar un gráfico a una diapositiva — específicamente un gráfico circular — y personalizarlo para escenarios del mundo real.

### Qué aprenderás
- Cómo inicializar un objeto de presentación en Java.  
- Pasos para **add a pie chart java** en la primera diapositiva de una presentación.  
- Acceder a los libros de datos del gráfico y enumerar las hojas de cálculo dentro de ellos.  

¡Sumérgete en cómo puedes aprovechar Aspose.Slides Java para mejorar tus presentaciones con gráficos dinámicos!

## Respuestas rápidas
- **¿Qué biblioteca agrega gráficos a través de Maven?** aspose slides maven  
- **¿Qué tipo de gráfico se muestra?** Pie chart (add chart to slide)  
- **¿Versión mínima de Java requerida?** JDK 16 or later  
- **¿Necesito una licencia para pruebas?** A free trial works; production needs a license  
- **¿Dónde puedo encontrar la dependencia Maven?** In the setup section below  

## ¿Qué es Aspose Slides Maven?
Aspose.Slides for Java es una API potente que permite a los desarrolladores crear, modificar y renderizar archivos PowerPoint de forma programática. El paquete Maven (`aspose-slides`) simplifica la gestión de dependencias, permitiéndote centrarte en construir y personalizar diapositivas—como agregar un gráfico circular—sin lidiar con el manejo de archivos de bajo nivel.

## ¿Por qué usar Aspose.Slides Maven para agregar un gráfico a una diapositiva?
Usar Aspose.Slides Maven te permite generar gráficos directamente desde código Java sin edición manual de PowerPoint. Proporciona control total programático sobre los tipos de gráficos, fuentes de datos y estilos, garantizando una marca coherente y precisión. El artefacto Maven también gestiona todas las dependencias necesarias, simplificando las compilaciones y permitiendo una integración fluida en las canalizaciones CI/CD.

## Requisitos previos
- **Aspose.Slides for Java** versión 25.4 o posterior (Maven/Gradle).  
- JDK 16+ instalado.  
- Un IDE (IntelliJ IDEA, Eclipse, etc.).  
- Conocimientos básicos de Java y familiaridad con Maven o Gradle.

## Configuración de Aspose.Slides para Java
Primero, incluye Aspose.Slides en tu proyecto mediante Maven o Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, puedes [descargar la última versión](https://releases.aspose.com/slides/java/) directamente desde el sitio web de Aspose.

### Adquisición de licencia
Aspose.Slides for Java ofrece una prueba gratuita con una licencia temporal para pruebas. Para uso de producción sin restricciones, adquiere una licencia a través de la [página de compra](https://purchase.aspose.com/buy).

## Guía de implementación
A continuación dividimos la solución en dos funcionalidades: agregar un gráfico circular y acceder a su libro de datos.

### Funcionalidad 1: Crear una presentación y agregar un gráfico
#### Visión general
Esta sección muestra cómo crear una nueva presentación y **add a pie chart** a la primera diapositiva.

#### ¿Cómo crear pie chart aspose?
Carga la clase `Presentation`, agrega un gráfico del tipo `ChartType.Pie` y guarda el archivo. Toda la operación requiere solo tres llamadas a la API y se ejecuta en menos de un segundo para una presentación típica de 10 diapositivas, lo que la hace ideal para la generación automatizada de informes.

#### Paso a paso

**Paso 1: Inicializar un nuevo objeto Presentation**  
La clase `Presentation` es el objeto de nivel superior de Aspose.Slides que representa un archivo PowerPoint en memoria.  
```java
Presentation pres = new Presentation();
```
*Crea la instancia `Presentation` que contendrá todas las diapositivas.*

**Paso 2: Agregar un gráfico circular**  
`ChartType.Pie` indica a Aspose que renderice un gráfico circular.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Coloca un gráfico circular en las coordenadas (50, 50) con un ancho de 400 y una altura de 500.*

**Paso 3: Liberar recursos**  
Llamar a `dispose()` libera los recursos nativos y previene fugas de memoria.  
```java
if (pres != null) pres.dispose();
```
*Libera los recursos nativos; siempre llama a `dispose()` cuando termines.*

### Funcionalidad 2: Acceder al libro de datos del gráfico y a las hojas de cálculo
#### Visión general
Aprende cómo acceder al libro subyacente que almacena los datos del gráfico y recorrer sus hojas de cálculo.

#### ¿Cómo acceder al libro de datos del gráfico?
Obtén el `IChartDataWorkbook` del gráfico y luego recorre su colección `Worksheets`. Este libro imita un archivo Excel, permitiéndote leer, modificar o agregar series de datos programáticamente, lo que el gráfico reflejará instantáneamente al actualizarse durante la ejecución sin reiniciar.

#### Paso a paso

**Paso 1: (Reutilizar) Inicializar un nuevo objeto Presentation**  
*Igual que la Funcionalidad 1, Paso 1.*

**Paso 2: (Reutilizar) Agregar un gráfico circular**  
*Igual que la Funcionalidad 1, Paso 2.*

**Paso 3: Obtener el libro de datos del gráfico**  
`IChartDataWorkbook` es la interfaz que brinda acceso de lectura/escritura al libro interno similar a Excel del gráfico.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Obtiene el `IChartDataWorkbook` vinculado al gráfico.*

**Paso 4: Recorrer las hojas de cálculo**  
Los objetos `Worksheet` representan hojas individuales dentro del libro.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Imprime el nombre de cada hoja de cálculo, permitiéndote verificar la estructura de datos.*

**Paso 5: Liberar recursos**  
*Igual que la Funcionalidad 1, Paso 3.*

## Aplicaciones prácticas
- **Data Reporting:** Auto‑generar presentaciones con métricas actualizadas para inteligencia empresarial.  
- **Academic Presentations:** Visualizar resultados de investigación sin creación manual de gráficos.  
- **Marketing Material:** Mostrar el rendimiento del producto o resultados de encuestas al instante.  

## Consideraciones de rendimiento
- Aspose.Slides puede manejar **más de 50 formatos de entrada y salida** y procesar presentaciones de cientos de páginas sin cargar todo el archivo en memoria.  
- Mantén un número razonable de diapositivas y gráficos; cada gráfico consume memoria nativa.  
- Siempre llama a `dispose()` para liberar los recursos rápidamente.  
- Optimiza el manejo de datos del libro; evita cargar conjuntos de datos masivos en un solo gráfico.  

## Conclusión
Hemos cubierto cómo **aspose slides maven** te permite **add chart to slide** programáticamente y cómo trabajar con el libro de datos del gráfico. Con estos bloques de construcción puedes automatizar cualquier flujo de trabajo de informes que requiera una salida de PowerPoint pulida.

### Próximos pasos
- Explora opciones de estilo de gráficos (colores, leyendas, etiquetas de datos).  
- Conéctate a fuentes de datos externas (CSV, bases de datos) para poblar gráficos dinámicamente.  
- Combina varios tipos de gráficos en una sola presentación para una narrativa más rica.  

## Preguntas frecuentes

**P: ¿Cómo instalo Aspose.Slides para Java?**  
R: Usa la dependencia Maven o Gradle mostrada arriba, o descarga la biblioteca desde la página de lanzamientos.

**P: ¿Cuáles son los requisitos del sistema para Aspose.Slides?**  
R: JDK 16 o posterior; la biblioteca funciona en cualquier plataforma que soporte Java.

**P: ¿Puedo agregar otros tipos de gráficos además de los circulares?**  
R: Sí, Aspose.Slides admite barras, líneas, dispersión, radar y más de 20 tipos de gráficos.

**P: ¿Cómo debo manejar presentaciones grandes de manera eficiente?**  
R: Libera los objetos rápidamente, limita las imágenes de alta resolución y reutiliza plantillas de gráficos para mantener bajo el uso de memoria.

**P: ¿Dónde puedo encontrar más detalles sobre las funciones de Aspose.Slides?**  
R: Visita la [documentación de Aspose](https://reference.aspose.com/slides/java/) para una referencia completa de la API.

**P: ¿Se requiere una licencia para uso comercial?**  
R: Se requiere una licencia válida para producción; una prueba gratuita está disponible para evaluación.

**P: ¿El paquete Maven incluye todas las capacidades de gráficos?**  
R: Sí, el artefacto Maven `aspose-slides` contiene el motor completo de gráficos.

## Recursos
- Documentación: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Descarga: [Latest Releases](https://releases.aspose.com/slides/java/)
- Compra y prueba: [Purchase Page](https://purchase.aspose.com/buy)
- Prueba gratuita: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Licencia temporal: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Foro de soporte: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Última actualización:** 2026-05-29  
**Probado con:** Aspose.Slides 25.4 for Java (jdk16)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo personalizar los colores del gráfico circular en Java con Aspose.Slides – Guía completa](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Crear un gráfico de pastel dentro de otro en Java con Aspose.Slides: Guía completa](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animar gráficos en PowerPoint usando Aspose.Slides para Java – Guía paso a paso](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
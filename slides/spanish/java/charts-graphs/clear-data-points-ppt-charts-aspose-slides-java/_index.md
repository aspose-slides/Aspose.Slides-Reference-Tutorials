---
date: '2026-08-27'
description: Aprenda cómo borrar los puntos de datos de los gráficos en PowerPoint
  usando Aspose.Slides for Java. Este tutorial step‑by‑step muestra cómo borrar programmatically
  los valores del gráfico, best practices y efficient series handling.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Aprenda cómo borrar los puntos de datos de los gráficos en PowerPoint
  usando Aspose.Slides for Java. Siga las instrucciones step‑by‑step para resetear
  programmatically los gráficos de forma eficiente.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Cómo borrar los puntos de datos de los gráficos en PowerPoint con Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Cómo borrar los puntos de datos en los gráficos de PowerPoint usando Aspose.Slides
  for Java: una guía completa'
url: /es/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo borrar puntos de datos en gráficos de PowerPoint usando Aspose.Slides para Java

## Introducción

En muchos flujos de informes necesitas **restablecer un gráfico** sin recrear su diseño. Ya sea que estés actualizando un panel, enviando una plantilla o automatizando informes nocturnos, saber **cómo borrar puntos de datos del gráfico** ahorra tiempo y reduce errores. Este tutorial te muestra cómo usar **Aspose.Slides for Java** para borrar programáticamente puntos específicos o una serie completa, manteniendo intacto el estilo visual.

**Qué aprenderás**
- Cómo Aspose.Slides te permite manipular gráficos de PowerPoint desde Java.  
- Instrucciones paso a paso para borrar puntos de datos del gráfico en una serie.  
- Consejos de mejores prácticas para rendimiento y licenciamiento.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Slides for Java (v25.4+).  
- **¿Qué método realmente borra un punto de datos?** Establecer los valores de celda X y Y a `null`.  
- **¿Necesito una licencia para producción?** Sí – una licencia comercial elimina los límites de prueba.  
- **¿Se admite Java 16?** Absolutamente; la biblioteca funciona con JDK 16 y versiones posteriores.  
- **¿Puedo dirigirme solo a una serie?** Sí – itera la serie específica que deseas borrar.

## ¿Qué es Aspose.Slides para Java?

Aspose.Slides for Java es una API totalmente funcional que permite la creación, edición y conversión de archivos PowerPoint sin Microsoft Office. Soporta más de 70 tipos de gráficos, más de 150 formatos de archivo y puede procesar presentaciones de hasta 500 MB sin cargar todo el archivo en memoria.

## ¿Por qué borrar puntos de datos del gráfico?

Borrar puntos de datos del gráfico te permite mantener el diseño existente del gráfico —como colores, leyendas, configuraciones de ejes y marcadores— mientras reemplazas los valores numéricos subyacentes. Este enfoque es útil cuando necesitas actualizar un gráfico con nuevos datos, proporcionar una plantilla con marcadores de posición vacíos o generar paneles dinámicos que cambian con frecuencia sin reconstruir el diseño visual.

- Actualizar un gráfico con un nuevo conjunto de datos mientras se conservan los colores, leyendas y configuraciones de ejes.  
- Enviar una plantilla que contiene gráficos vacíos listos para la entrada del usuario.  
- Construir paneles dinámicos donde los datos cambian con frecuencia.

## Cómo borrar puntos de datos del gráfico en PowerPoint usando Aspose.Slides para Java

Carga tu presentación, localiza el gráfico y establece las celdas X e Y de cada punto de datos a `null`. Esta operación elimina los valores numéricos pero deja la serie, los marcadores y el formato sin tocar. Todo el proceso normalmente se completa en menos de un segundo para un PPTX estándar de 10 diapositivas.

### Respuesta directa
Para borrar los puntos de datos del gráfico, abre el PPTX con `new Presentation("input.pptx")`, recupera el objeto `IChart` objetivo, recorre la `IChartSeries` deseada y llama a `dataPoint.getXValue().setValue(null)` y `dataPoint.getYValue().setValue(null)` para cada punto. Finalmente, guarda la presentación con `pres.save("output.pptx", SaveFormat.Pptx)`. Este enfoque borra programáticamente los datos mientras preserva el diseño visual del gráfico.

### Anclas de definición
- `Presentation` es el objeto de nivel superior de Aspose.Slides que representa un archivo PowerPoint en memoria.  
- `IChart` es la interfaz que brinda acceso a las series, ejes y formato de una forma de gráfico.  
- `IChartSeries` representa una única serie dentro de un gráfico y contiene una colección de objetos `IDataPoint`.  
- `IDataPoint` almacena los valores individuales X e Y de un punto en el gráfico.

### Implementación paso a paso

1. **Cargar la presentación** – crea una instancia de `Presentation` que apunte a tu archivo de origen.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Acceder a la diapositiva y al gráfico** – recupera la diapositiva (normalmente el índice 0) y convierte la primera forma a `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Iterar a través de la serie objetivo** – selecciona la serie que deseas borrar (p.ej., `chart.getChartData().getSeries().get_Item(0)`) y recorre sus puntos de datos, estableciendo ambos valores de celda X e Y a `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Guardar la presentación modificada** – escribe los cambios en un nuevo archivo o sobrescribe el original.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Configuración de Aspose.Slides para Java

### Instalación con Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Instalación con Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Descarga directa

Alternativamente, descarga la última versión desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Obtención de licencia

Para usar Aspose.Slides más allá de sus limitaciones de prueba:
- Obtén una licencia de **prueba gratuita**.  
- Solicita una licencia **temporal** para evaluación.  
- Compra una licencia **comercial** para uso en producción.

#### Inicialización y configuración básica

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Aplicaciones prácticas

Borrar puntos de datos del gráfico es útil en muchos escenarios del mundo real:

1. **Flujos de actualización de datos** – reemplaza números obsoletos con análisis frescos sin reconstruir el diseño del gráfico.  
2. **Distribución de plantillas** – proporciona plantillas de PowerPoint que contienen gráficos vacíos listos para la entrada del usuario.  
3. **Paneles dinámicos** – genera presentaciones nocturnas que extraen datos de APIs, borrando primero los valores antiguos.  
4. **Trabajos de informes automatizados** – integra la lógica de borrado en pipelines CI/CD para la generación automática de informes.

## Consideraciones de rendimiento

- **Liberar objetos**: Llama a `pres.dispose()` después de guardar para liberar recursos nativos.  
- **Procesamiento por lotes**: Reutiliza una única instancia de `License` en varios archivos para minimizar la sobrecarga.  
- **Ajuste de JVM**: Incrementa el tamaño del heap (`-Xmx2g` o superior) al manejar presentaciones mayores de 200 MB.  
- **Modo de eficiencia de memoria**: Aspose.Slides puede transmitir archivos PPTX grandes, permitiendo procesar hasta 10 000 diapositivas sin cargar todo en memoria.

## Preguntas frecuentes

**P: ¿Necesito una licencia para compilaciones de desarrollo?**  
R: Una licencia de prueba gratuita es suficiente para desarrollo y pruebas. Se requiere una licencia comercial para despliegues en producción.

**P: ¿Aspose.Slides para Java soporta las funciones de PowerPoint 2016/2019?**  
R: Sí, la biblioteca soporta completamente las funciones modernas de PPTX, incluidos tipos de gráficos avanzados y SmartArt.

**P: ¿Puedo borrar puntos de datos en un gráfico que usa un eje secundario?**  
R: Absolutamente – simplemente referencia la serie que pertenece al eje secundario y establece sus puntos de datos a `null` como se describió arriba.

**P: ¿Es posible borrar solo los valores Y manteniendo las etiquetas X?**  
R: Sí. Llama a `dataPoint.getYValue().setValue(null)` y deja la celda X sin tocar.

**P: ¿Cómo puedo automatizar esto para múltiples presentaciones?**  
R: Envuelve el código de borrado en un bucle que itere sobre un directorio de archivos PPTX, aplicando la misma lógica a cada archivo.

## Recursos

- [Documentación de Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Descargar Aspose.Slides para Java](https://releases.aspose.com/slides/java/)
- [Comprar una licencia](https://purchase.aspose.com/buy)
- [Versión de prueba gratuita](https://releases.aspose.com/slides/java/)
- [Solicitud de licencia temporal](https://purchase.aspose.com/temporary-license/)
- [Foro de la comunidad de Aspose](https://forum.aspose.com/c/slides/11)

Con estos recursos estás listo para comenzar a borrar puntos de datos del gráfico en tus aplicaciones Java. ¡Feliz codificación!

---

**Última actualización:** 2026-08-27  
**Probado con:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo editar datos de gráficos de PowerPoint usando Aspose.Slides para Java: Guía completa](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Cómo agregar un gráfico a PowerPoint usando Aspose.Slides para Java: Guía paso a paso](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Borrar datos de puntos de series de gráficos específicos en Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
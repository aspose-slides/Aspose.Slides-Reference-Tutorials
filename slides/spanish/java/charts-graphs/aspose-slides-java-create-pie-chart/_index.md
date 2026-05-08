---
date: '2026-02-17'
description: Aprende cómo agregar gráficos de pastel a presentaciones de PowerPoint
  usando Aspose.Slides para Java. Sigue esta guía paso a paso para crear y personalizar
  gráficos de pastel profesionales.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Cómo agregar un gráfico de pastel en PowerPoint con Aspose.Slides para Java
url: /es/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crear y Personalizar Gráficos de Tarta en PowerPoint Usando Aspose.Slides para Java

## Introducción

¿Tiene dificultades para visualizar datos de manera eficaz en sus presentaciones de PowerPoint? **Agregar una diapositiva de gráfico de tarta PowerPoint** puede convertir instantáneamente números crudos en una historia visual clara. Con Aspose.Slides para Java, puede **agregar archivos de gráfico de tarta PowerPoint** programáticamente, dándole control total sobre el diseño y los datos sin necesidad de abrir PowerPoint manualmente. En este tutorial recorreremos todo el proceso —desde la configuración de la biblioteca hasta la personalización de puntos de datos individuales— para que pueda entregar diapositivas pulidas y basadas en datos en minutos.

### Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Slides para Java (última versión).  
- **¿Puedo crear un gráfico sin PowerPoint instalado?** Sí, la API funciona completamente sin conexión.  
- **¿Qué versión de Java se requiere?** Se recomienda JDK 16 o posterior.  
- **¿Cómo cambio el color de una porción?** Use los métodos `setFillType` y `setSolidFillColor` en el punto de datos.  
- **¿Es obligatoria una licencia?** Una prueba funciona para desarrollo; una licencia permanente elimina los límites de evaluación.

### Lo que aprenderá
- Cómo **agregar un gráfico de tarta PowerPoint** programáticamente con Java.  
- Formas de personalizar la explosión de porciones, colores y otras propiedades visuales.  
- Buenas prácticas para la gestión de recursos y el rendimiento al manejar presentaciones grandes.

## ¿Por qué agregar un gráfico de tarta PowerPoint usando Aspose.Slides para Java?
Incorporar un gráfico de tarta directamente desde código le permite generar informes actualizados, automatizar paneles mensuales o crear presentaciones personalizadas al instante. Elimina errores de copiar‑pegar manuales, garantiza consistencia entre presentaciones e integra sin problemas con los back‑ends Java existentes.

## Requisitos previos

Antes de comenzar, asegúrese de contar con:

- **Biblioteca Aspose.Slides para Java** – el tutorial hace referencia a la versión 25.4 (la última publicación al momento de escribir).  
- Un **Java Development Kit (JDK)** compatible – se prefiere JDK 16+.  
- Familiaridad básica con **Maven** o **Gradle** para la gestión de dependencias.  

## Configuración de Aspose.Slides para Java

Para comenzar, incluya la biblioteca Aspose.Slides en su proyecto.

### Maven
Agregue esta dependencia a su archivo `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Incluya lo siguiente en su archivo `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativamente, descargue la última versión directamente desde [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenciamiento
Para usar Aspose.Slides sin limitaciones:

- Comience con una **prueba gratuita** para evaluar la API.  
- Solicite una **licencia temporal** para pruebas extendidas en la página de [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Adquiera una suscripción completa a través de la [Purchase page](https://purchase.aspose.com/buy).

## Cómo agregar un gráfico de tarta PowerPoint usando Aspose.Slides para Java

A continuación se muestra una guía paso a paso que indica exactamente cómo crear y personalizar un gráfico de tarta.

### Paso 1: Inicializar la presentación
Primero, cree un nuevo objeto `Presentation`. Esto representa un archivo de PowerPoint vacío.
```java
Presentation pres = new Presentation();
```

### Paso 2: Agregar el gráfico de tarta
Inserte un gráfico de tarta en la primera diapositiva. Las coordenadas (50, 50) y el tamaño (600 × 400) funcionan bien para una diapositiva estándar 16:9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Paso 3: Guardar la presentación
Escriba la presentación en disco. Reemplace `YOUR_OUTPUT_DIRECTORY` con la carpeta donde desea guardar el archivo.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Paso 4: Liberar recursos
Deseche el objeto `Presentation` para liberar recursos nativos.
```java
if (pres != null) pres.dispose();
```

## Personalización de la explosión y el color del punto de datos

Personalizar porciones individuales hace que su gráfico sea más fácil de leer, especialmente cuando desea resaltar un valor específico.

### Paso 1: Cargar una presentación existente (o reutilizar la que acaba de crear)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Paso 2: Acceder al gráfico y al punto de datos objetivo
Aquí recuperamos el segundo punto de datos (índice 1) de la primera serie.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Paso 3: Aplicar explosión y color
Separe visualmente la porción y cambie su color de relleno a azul.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Paso 4: Guardar y desechar
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Aplicaciones prácticas
- **Informes de ventas:** Resalte los productos más vendidos con porciones explotadas.  
- **Análisis presupuestario:** Asigne colores distintos a los departamentos para una comparación visual rápida.  
- **Diapositivas educativas:** Desglose conceptos complejos en segmentos de gráfico fáciles de digerir.

## Consideraciones de rendimiento
- **Deseche objetos** rápidamente para evitar fugas de memoria, especialmente al generar muchas diapositivas en un bucle.  
- **Monitoree el uso del heap** para presentaciones grandes; considere transmitir la salida con sobrecargas de `Save` que aceptan `OutputStream`.  
- Manténgase en **JDK 16+** para beneficiarse de las últimas mejoras de recolección de basura.

## Conclusión
Ahora dispone de un flujo de trabajo completo y listo para producción para **agregar archivos de gráfico de tarta PowerPoint** usando Aspose.Slides para Java. Experimente con diferentes distancias de explosión, colores y conjuntos de datos para que coincidan con su identidad corporativa. Cuando esté listo, explore otros tipos de gráficos —barras, líneas o dispersión— para construir un panel de análisis completo dentro de PowerPoint.

## Sección de preguntas frecuentes
1. **¿Cuál es la principal ventaja de usar Aspose.Slides para Java?**  
   - Simplifica la creación y manipulación de archivos PowerPoint programáticamente, ofreciendo una amplia gama de funcionalidades.  
2. **¿Puedo personalizar otros tipos de gráficos con Aspose.Slides?**  
   - ¡Claro! Aspose.Slides admite varios tipos de gráficos como barras, líneas y gráficos de dispersión.  
3. **¿Cómo manejo múltiples diapositivas al crear gráficos?**  
   - Acceda a cada diapositiva por índice usando el método `get_Item()` para aplicar cambios en diferentes diapositivas.  
4. **¿Qué ocurre si mi gráfico de tarta no se muestra correctamente después de la personalización?**  
   - Verifique las coordenadas y dimensiones usadas en `addChart()`, asegurándose de que encajen dentro del diseño de su diapositiva.  
5. **¿Dónde puedo encontrar funciones más avanzadas para Aspose.Slides?**  
   - Explore la [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) para conocer funcionalidades y opciones adicionales.

## Recursos
- **Documentación:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Descargar biblioteca:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Comprar licencia:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Prueba gratuita:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Licencia temporal:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Foro de soporte:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Última actualización:** 2026-02-17  
**Probado con:** Aspose.Slides para Java 25.4 (clasificador JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-17"
"description": "Aprenda a crear y personalizar un gráfico circular con Aspose.Slides para Java. Esta guía abarca la configuración, la implementación y las aplicaciones prácticas."
"title": "Cree un gráfico circular en Java con Aspose.Slides&#58; una guía completa"
"url": "/es/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cree un gráfico circular en Java con Aspose.Slides: una guía completa

## Gráficos y tablas

### Introducción

En la visualización de datos, los gráficos circulares son una forma intuitiva de representar proporciones dentro de un conjunto de datos. Sin embargo, al trabajar con conjuntos de datos complejos donde algunos segmentos son significativamente más pequeños que otros, los gráficos circulares tradicionales pueden resultar confusos y difíciles de interpretar. Los gráficos circulares de sectores solucionan este problema dividiendo pequeñas porciones en un gráfico secundario, lo que mejora la legibilidad.

En este tutorial, aprenderá a crear y manipular un gráfico circular con Aspose.Slides para Java. Aprenderá a configurar su entorno, crear el gráfico, personalizar propiedades como etiquetas de datos y posiciones de división, y guardar su presentación en formato PPTX. Al finalizar, dominará estas funciones con aplicaciones prácticas y consejos de rendimiento.

**Lo que aprenderás:**
- Configuración de Aspose.Slides para Java
- Creación de un gráfico circular
- Personalización de propiedades de gráficos, como etiquetas de datos y configuraciones de división
- Guardar su presentación en el disco

¿Listo para empezar? ¡Primero veamos los prerrequisitos!

## Prerrequisitos

Antes de crear nuestro gráfico circular, asegúrese de tener:

### Bibliotecas, versiones y dependencias necesarias:
- **Aspose.Slides para Java**:Esencial para gestionar presentaciones de PowerPoint mediante programación.

### Requisitos de configuración del entorno:
- Tiene instalado un Kit de Desarrollo de Java (JDK) en su equipo. Recomendamos usar JDK 16 o posterior.
- Un entorno de desarrollo integrado (IDE) como IntelliJ IDEA, Eclipse o NetBeans.

### Requisitos de conocimiento:
- Comprensión básica de la programación Java
- Familiaridad con Maven o Gradle para la gestión de dependencias

## Configuración de Aspose.Slides para Java

### Información de instalación:

**Experto:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Descarga directa**:Puedes descargar la última versión desde [Lanzamientos de Aspose.Slides para Java](https://releases.aspose.com/slides/java/).

### Pasos para la adquisición de la licencia:
- **Prueba gratuita**Comience con una prueba de 30 días para explorar todas las funciones.
- **Licencia temporal**:Solicitar una licencia temporal para evaluación extendida.
- **Compra**Considere comprar una licencia si Aspose.Slides satisface sus necesidades.

### Inicialización y configuración básicas

Una vez que tenga la biblioteca configurada en su proyecto, inicialícela creando una instancia de la `Presentation` clase:

```java
Presentation presentation = new Presentation();
```

Esto prepara el terreno para agregar varios gráficos a las diapositivas. A continuación, implementemos nuestro gráfico circular.

## Guía de implementación

### Creación de un gráfico circular

#### Descripción general
Comenzaremos creando una instancia de un `Presentation` Y agregue un gráfico circular en la primera diapositiva. Este gráfico visualizará eficazmente los datos al separar segmentos más pequeños en un gráfico circular secundario, lo que mejora la legibilidad.

#### Paso 1: Crear una instancia de la clase de presentación
```java
// Crear una nueva presentación
ePresentation presentation = new Presentation();
```
Este código inicializa su presentación donde agregaremos nuestros gráficos.

#### Paso 2: Agregue un gráfico circular en la primera diapositiva
```java
// Agregue un gráfico circular a la primera diapositiva en la posición (50, 50) con tamaño (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Aquí especificamos el tipo de gráfico (`PieOfPie`) y su posición y dimensiones en la diapositiva.

#### Paso 3: Establecer etiquetas de datos para mostrar los valores de la serie
```java
// Configurar etiquetas de datos para mostrar valores
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Este paso garantiza que cada segmento de nuestro gráfico circular muestre su valor correspondiente, lo que facilita la interpretación rápida de los datos.

#### Paso 4: Configurar el tamaño del segundo gráfico circular y dividirlo por porcentaje
```java
// Establecer el tamaño del gráfico circular secundario
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Dividir el pastel por porcentaje
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Establecer la posición de división
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Estas configuraciones le permiten personalizar cómo se divide su gráfico y muestra segmentos más pequeños, mejorando la claridad para los espectadores.

#### Paso 5: Guarde la presentación en el disco en formato PPTX
```java
// Definir directorio de salida
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Guarde la presentación\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
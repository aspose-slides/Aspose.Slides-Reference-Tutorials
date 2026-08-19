---
date: '2026-07-17'
description: Узнайте, как добавить Sunburst Charts в PowerPoint с помощью Aspose Slides
  for Java. Пошаговое руководство охватывает настройку, создание диаграммы, кастомизацию
  и реальные примеры использования.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Как добавить Sunburst Charts в PowerPoint с использованием Aspose
  Slides for Java. Следуйте этому руководству, чтобы настроить библиотеку, создать
  диаграмму, настроить точки данных и применить её в реальных проектах.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Как добавить Sunburst Charts в PowerPoint с Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Как добавить Sunburst Charts в PowerPoint с Aspose (Java)
url: /ru/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как добавить Sunburst‑диаграммы в PowerPoint с Aspose (Java)

## Введение

Добавление Sunburst‑диаграммы в презентацию PowerPoint может мгновенно превратить плоскую таблицу данных в захватывающую визуальную иерархию. В этом руководстве вы узнаете **как добавить Sunburst**‑диаграммы в PowerPoint с помощью Aspose.Slides for Java, от настройки окружения до тонкой настройки цветов и подписей. Независимо от того, создаёте ли вы панель продаж, разбивку проекта по задачам или учебную презентацию, приведённые ниже шаги дадут вам готовое к производству решение.

**Что вы узнаете**
- Как настроить Aspose.Slides в проекте Maven или Gradle  
- Как создать новую презентацию и вставить Sunburst‑диаграмму  
- Как настроить точки данных, подписи и цвета заливки  
- Реальные сценарии, где Sunburst‑диаграммы показывают себя  

Давайте начнём и посмотрим, как легко превратить сырые иерархические данные в полированную визуализацию PowerPoint.

## Быстрые ответы
- **Основная библиотека?** Aspose.Slides for Java  
- **Поддерживаемый тип диаграммы?** Sunburst (радиальная иерархическая)  
- **Минимальная версия Java?** JDK 16  
- **Типичное время реализации?** 10‑15 минут для базовой диаграммы  
- **Лицензия требуется для продакшн?** Да, действующая лицензия Aspose  

## Что такое Sunburst‑диаграмма?
Sunburst‑диаграмма — это радиальная схема, визуализирующая иерархические данные путем вложения колец наружу от центральной точки. Она идеально подходит для отображения многоуровневых отношений, таких как организационные структуры, категории продуктов или деревья файловой системы. Каждый концентрический кольцо представляет уровень иерархии, а размер сегмента отражает его количественное значение, позволяя зрителям быстро понять как структуру, так и масштаб.

## Почему использовать Aspose.Slides for Java?
Aspose.Slides поддерживает **более 50 типов диаграмм** и может манипулировать презентациями с **до 10 000 слайдов** без загрузки всего файла в память, обеспечивая высокую производительность для корпоративных отчётов. Он кроссплатформенный, предоставляет обширное покрытие API и включает надёжные варианты лицензирования, снимающие ограничения оценки, что делает его идеальным для производственных сред.

## Требования
- **Java Development Kit (JDK)** 16 или новее  
- **IDE** – IntelliJ IDEA, Eclipse или любой совместимый с Java редактор  
- Базовое знакомство с синтаксисом Java и инструментами сборки Maven/Gradle  

## Настройка Aspose.Slides for Java

### Зависимость Maven
Add the Aspose.Slides Maven artifact to your `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Зависимость Gradle
If you prefer Gradle, include the following line in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямое скачивание
You can also download the latest JAR directly from the official releases page: [Выпуски Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
To run without evaluation limits, obtain a license:
- **Бесплатная пробная версия** – временная лицензия для быстрой оценки.  
- **Временная лицензия** – запросите её на сайте [Aspose](https://purchase.aspose.com/temporary-license).  
- **Полная покупка** – приобретите подписку для неограниченного использования в продакшн.

### Базовая инициализация
The `Presentation` class is the entry point for creating or opening PowerPoint files.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Руководство по реализации

### Как добавить Sunburst‑диаграмму в презентацию PowerPoint с помощью Aspose.Slides for Java?
Load a new `Presentation`, add a slide, insert an `IChart` of type `ChartType.Sunburst`, and call `save`. This concise three‑step pattern creates a fully functional sunburst chart ready for further customization.

#### Шаг 1: Инициализировать презентацию
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Шаг 2: Добавить Sunburst‑диаграмму
The `IChart` interface defines a chart object that can be placed on any slide. Here we add a sunburst chart at coordinates (100, 100) with a size of 450 × 400 points.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Шаг 3: Сохранить презентацию
Always persist your changes by calling `save`. You can choose PPTX, PDF, or any of the 50+ supported output formats.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Изменить точки данных в диаграмме

#### Обзор
You can tailor every slice of the sunburst—labels, colors, and visibility—through the chart’s data point collection.

#### Шаг 1: Доступ к коллекции точек данных
The first series of the chart holds a collection of `IChartDataPoint` objects that represent each slice.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Шаг 2: Показать значение для конкретной точки данных
Set `IsValueShown` to `true` on the desired data point to display its numeric value directly on the slice.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Шаг 3: Изменить форматы подписей
Adjust label visibility, font color, and background to improve readability.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Шаг 4: Установить цвет заливки для точек данных
Customize the fill color of individual slices to match your brand palette or to highlight key segments.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Шаг 5: Сохранить изменённую презентацию
Persist the customized chart by saving the presentation again.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Практические применения

1. **Бизнес‑аналитика** – визуализировать продажи по регионам → продуктовым линиям → SKU в едином радиальном виде.  
2. **Управление проектами** – показать структуру разбивки работ, переходя от фаз к задачам и подпроектам.  
3. **Образование** – отобразить иерархию учебных программ, например факультеты → курсы → модули.  

## Соображения по производительности

- **Эффективность памяти:** Aspose.Slides потоково обрабатывает данные, поэтому даже 500‑страничная презентация с несколькими диаграммами занимает менее 200 МБ ОЗУ.  
- **Сборка мусора:** освобождайте объекты слайдов (`slide.dispose()`), когда они больше не нужны, чтобы избежать утечек памяти.  

## Часто задаваемые вопросы

**В: Что такое Sunburst‑диаграмма?**  
Ответ: Sunburst‑диаграмма визуализирует иерархические данные в концентрических кольцах, каждое кольцо представляет уровень иерархии.

**В: Как установить Aspose.Slides for Java с помощью Maven?**  
Ответ: Добавьте зависимость Maven, показанную в разделе «Зависимость Maven», в ваш `pom.xml` и выполните `mvn clean install`.

**В: Могу ли я настраивать другие типы диаграмм с помощью Aspose.Slides?**  
Ответ: Да, библиотека поддерживает более 50 типов диаграмм, включая столбчатые, линейные, круговые и радиальные диаграммы.

**В: Презентация не сохраняется — что проверить?**  
Ответ: Убедитесь, что путь к файлу правильный, каталог существует и у вас есть права записи. Также проверьте, что вызывается метод `Presentation.save()`.

**В: Где можно получить дополнительную помощь или примеры?**  
Ответ: Посетите [форум Aspose](https://forum.aspose.com/c/slides/11) или обратитесь к официальной [документации Aspose.Slides](https://reference.aspose.com/slides/java/).

## Ресурсы
- **Документация:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Справка (строчная):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Форум сообщества:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Загрузки:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java/)  

---

**Последнее обновление:** 2026-07-17  
**Тестировано с:** Aspose.Slides for Java 24.12  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как добавить диаграммы в PowerPoint с помощью Aspose.Slides for Java: пошаговое руководство](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Анимация диаграмм в PowerPoint с помощью Aspose.Slides for Java – пошаговое руководство](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Создание диаграммы в Java с Aspose.Slides – добавление и проверка диаграмм](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
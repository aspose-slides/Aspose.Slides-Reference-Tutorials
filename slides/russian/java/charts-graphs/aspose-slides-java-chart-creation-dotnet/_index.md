---
date: '2026-01-14'
description: Узнайте, как добавить сгруппированную столбчатую диаграмму и разместить
  её на слайде в .NET‑презентациях с помощью Aspose.Slides для Java. Следуйте этому
  пошаговому руководству с полными примерами кода.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Добавить сгруппированную столбчатую диаграмму в .NET Slides Aspose.Slides Java
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание диаграмм в презентациях .NET с использованием Aspose.Slides for Java
## Introduction
Создание убедительных презентаций часто подразумевает интеграцию визуальных представлений данных, таких как диаграммы, чтобы улучшить понимание и вовлечённость аудитории. Если вы разработчик, желающий добавить динамические, настраиваемые диаграммы в свои .NET‑презентации с помощью Aspose.Slides for Java, этот учебник создан специально для вас. Мы подробно рассмотрим, как инициализировать презентации, добавлять различные типы диаграмм, управлять данными диаграмм и эффективно форматировать данные рядов.

**Что вы узнаете:**
- Как настроить и использовать Aspose.Slides for Java в вашей среде .NET.
- Инициализацию новой презентации с помощью Aspose.Slides.
- Добавление и настройку диаграмм в слайдах.
- Управление рабочими книгами данных диаграмм.
- Форматирование данных рядов, особенно обработку отрицательных значений.

Переход к разделу требований обеспечит вашу готовность легко следовать инструкциям.

## Quick Answers
- **Какова основная цель?** Добавить сгруппированную столбчатую диаграмму в слайд .NET.
- **Какая библиотека требуется?** Aspose.Slides for Java (v25.4+).
- **Можно ли использовать её в проекте .NET?** Да — Java‑библиотека работает через мост Java‑to‑.NET.
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.
- **Сколько времени занимает реализация?** Около 10‑15 минут для базовой диаграммы.

## What is a clustered column chart?
Сгруппированная столбчатая диаграмма отображает несколько рядов данных рядом друг с другом для каждой категории, что упрощает сравнение значений между группами. Такой визуал идеально подходит для бизнес‑дашбордов, отчётов о производительности и любых сценариев, где необходимо сопоставить несколько метрик.

## Why add chart to slide with Aspose.Slides for Java?
Использование Aspose.Slides позволяет генерировать, изменять и сохранять презентации без установленного Microsoft PowerPoint. Библиотека предоставляет полный контроль над типами диаграмм, данными и стилями, что позволяет автоматизировать создание отчётов непосредственно из ваших .NET‑приложений.

## Prerequisites
Прежде чем приступить к созданию диаграмм с помощью Aspose.Slides for Java, перечислим необходимые компоненты:

### Required Libraries and Versions
- **Aspose.Slides for Java**: версия 25.4 или новее.

### Environment Setup Requirements
- Среда разработки, поддерживающая приложения .NET.
- Базовые знания концепций программирования на Java.

### Knowledge Prerequisites
- Знакомство с созданием презентаций в контексте .NET‑приложений.
- Понимание зависимостей Java и их управления (Maven/Gradle).

## Setting Up Aspose.Slides for Java
Чтобы начать использовать Aspose.Slides, необходимо добавить её в качестве зависимости в ваш проект. Вот как это сделать:

### Maven
Добавьте следующую зависимость в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Добавьте это в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
При необходимости вы можете скачать последнюю версию с сайта [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Бесплатная пробная версия**: Начните с временной лицензии для изучения возможностей.
- **Покупка**: Рассмотрите возможность приобретения лицензии для широкого использования.

#### Basic Initialization and Setup
Вот как инициализировать Aspose.Slides в вашем коде:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Эта настройка гарантирует эффективное управление ресурсами.

## Implementation Guide
Мы пройдёмся по реализации функций шаг за шагом.

### Initializing Presentation
**Обзор:**  
Создание экземпляра презентации закладывает основу для всех последующих операций. Эта часть демонстрирует, как начать с нуля, используя Aspose.Slides.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
Here's how you do it:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Это гарантирует корректное освобождение объекта презентации после использования, предотвращая утечки памяти.*

### Adding Chart to Slide
**Обзор:**  
Добавление диаграммы на слайд делает визуализацию данных более эффективной и привлекательной.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Здесь мы добавляем сгруппированную столбчатую диаграмму на первый слайд с указанными координатами и размерами.*

### Managing Chart Data Workbook
**Обзор:**  
Эффективное управление рабочей книгой данных диаграммы позволяет без проблем манипулировать рядами и категориями.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Очистка рабочей книги важна для начала с чистого листа при добавлении новых рядов и категорий.*

### Adding Series and Categories to Chart
**Обзор:**  
Эта часть показывает, как добавить значимые точки данных, управляя рядами и категориями.

#### Step 1: Add Series and Categories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Добавление рядов и категорий обеспечивает более упорядоченную презентацию данных.*

### Populating Series Data and Formatting
**Обзор:**  
Заполните диаграмму точками данных и отформатируйте её внешний вид для повышения читаемости, особенно при работе с отрицательными значениями.

#### Step 1: Populate Series Data
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*В этом разделе показано, как заполнить данные и применить цветовое форматирование для лучшей визуализации.*

## Common Issues and Solutions
- **Утечки памяти:** Всегда вызывайте `dispose()` у объекта `Presentation` в блоке `finally`.
- **Неправильный тип диаграммы:** Убедитесь, что используете `ChartType.ClusteredColumn`, когда нужна сгруппированная столбчатая диаграмма; другие типы дадут иной визуальный результат.
- **Цвета отрицательных значений не применяются:** Проверьте, что значение `IDataPoint` корректно приведено к `Number` перед сравнением.

## Frequently Asked Questions

**В:** Могу ли я использовать Aspose.Slides for Java в чистом проекте .NET без Java?  
**О:** Да. Библиотека работает через мост Java‑to‑.NET, позволяя вызывать Java‑API из .NET‑языков.

**В:** Поддерживает ли бесплатная пробная версия создание диаграмм?  
**О:** Пробная версия включает полную функциональность диаграмм, однако сгенерированные файлы содержат небольшую водяную метку оценки.

**В:** Какие версии .NET совместимы?  
**О:** Любая версия .NET, способная взаимодействовать с Java 16+, включая .NET Framework 4.6+, .NET Core 3.1+ и .NET 5/6/7.

**В:** Как работать с большими презентациями, содержащими множество диаграмм?  
**О:** По возможности переиспользуйте один экземпляр `IChartDataWorkbook` и своевременно освобождайте каждый `Presentation`, чтобы освободить память.

**В:** Можно ли экспортировать диаграмму как изображение?  
**О:** Да. Используйте методы `chart.getImage()` или `chart.exportChartImage()` для получения PNG/JPEG‑представлений.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose  

---
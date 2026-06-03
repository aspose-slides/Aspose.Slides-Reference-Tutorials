---
date: '2026-06-03'
description: Узнайте, как создавать диаграммы в презентациях .NET и добавлять диаграмму
  на слайд с помощью Aspose.Slides for Java. Следуйте этому пошаговому руководству
  по визуализации данных.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Создание диаграмм в .NET с использованием Aspose.Slides for Java
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание диаграмм в .NET с использованием Aspose.Slides for Java

## Введение
Создание убедительных презентаций часто требует интеграции визуальных представлений данных, таких как диаграммы, чтобы улучшить понимание и вовлечённость аудитории. **Если вы хотите создавать диаграммы в .NET**, Aspose.Slides for Java предоставляет мощный, независимый от языка API, который беспрепятственно работает внутри .NET‑приложений. В этом руководстве вы узнаете, как инициализировать презентацию, добавить различные типы диаграмм, управлять рабочей книгой данных диаграммы и форматировать данные серий — включая обработку отрицательных значений. К концу вы сможете программно генерировать диаграммы в файлах презентаций и добавлять их на слайд всего несколькими строками кода.

## Быстрые ответы
- **Какова основная цель?** Создать диаграммы в .NET‑презентациях с использованием Aspose.Slides for Java.  
- **Какая версия библиотеки требуется?** Aspose.Slides for Java 25.4 или новее.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.  
- **Можно ли использовать Maven или Gradle?** Да — обе системы сборки поддерживаются.  
- **Какие типы диаграмм доступны?** Группированные столбцы, линии, круговые, столбчатые, областные и другие.

## Как создавать диаграммы в .NET‑презентациях с помощью Aspose.Slides for Java?
Класс `Presentation` представляет файл PowerPoint и предоставляет методы для работы со слайдами. Загрузите новый объект `Presentation`, вызовите `slides.addEmptySlide()` для получения слайда, затем используйте `slide.getShapes().addChart()` чтобы вставить нужный тип диаграммы в указанные координаты. После добавления диаграммы заполните её рабочую книгу данными серий и категорий, примените нужное форматирование (например, цвета для отрицательных значений) и, наконец, сохраните презентацию в файл .pptx. Такой процесс позволяет **создавать диаграммы в .NET** с помощью небольшого набора вызовов API.

## Что такое Aspose.Slides for Java?
Aspose.Slides for Java — это кроссплатформенный API, позволяющий разработчикам создавать, изменять и рендерить файлы PowerPoint без Microsoft Office. Он поддерживает **более 50 форматов** ввода и вывода и может обрабатывать презентации с тысячами слайдов, удерживая использование памяти ниже 200 МБ.

## Почему использовать Aspose.Slides for Java в .NET‑проекте?
Aspose.Slides for Java работает на Java Virtual Machine и может вызываться из .NET через нативный обёртку, предоставляя .NET‑разработчикам доступ к зрелому движку диаграмм, высокопроизводительной обработке больших наборов данных и полной совместимости с существующим Java‑кодом без необходимости переписывать логику.

## Предварительные требования
Перед тем как приступить к созданию диаграмм с Aspose.Slides for Java, уточним, что вам понадобится:

### Требуемые библиотеки и версии
- **Aspose.Slides for Java**: версия 25.4 или новее.

### Требования к настройке среды
- Среда разработки, поддерживающая .NET‑приложения.  
- Базовое понимание концепций программирования на Java.

### Требования к знаниям
- Знакомство с созданием презентаций в контексте .NET‑приложения.  
- Понимание зависимостей Java и их управления (Maven/Gradle).

## Настройка Aspose.Slides for Java
Чтобы начать использовать Aspose.Slides, необходимо добавить его в зависимости вашего проекта. Ниже показано, как это сделать:

### Maven
Фрагмент зависимости Maven добавляет Aspose.Slides for Java в ваш проект.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Добавьте эту строку в файл `build.gradle`, чтобы загрузить библиотеку из Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка
Кроме того, вы можете скачать последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Шаги получения лицензии
- **Free Trial**: Начните с временной лицензии для изучения возможностей.  
- **Purchase**: Приобретите лицензию для неограниченного использования в продакшн‑среде.

#### Базовая инициализация и настройка
Инициализация `Slides` требует установки лицензии и создания экземпляра `Presentation`.

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

## Руководство по реализации
Мы пройдёмся по реализации функций шаг за шагом.

### Инициализация презентации
**Обзор:**  
Создание экземпляра презентации закладывает основу для всех последующих операций. Эта функция показывает, как начать с нуля, используя Aspose.Slides.

#### Шаг 1: Импортировать необходимые пакеты
`Presentation` и связанные классы находятся в пространстве имён `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Шаг 2: Создать новый объект Presentation
Создайте объект `Presentation` и оберните его в блок `try‑with‑resources`, чтобы гарантировать освобождение ресурсов.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Это гарантирует, что объект презентации будет правильно освобождён после использования, предотвращая утечки памяти.*

### Добавление диаграммы на слайд
**Обзор:**  
Добавление диаграммы на ваш слайд может сделать визуализацию данных более эффективной и привлекательной.

#### Шаг 1: Импортировать необходимые пакеты
Класс `Chart` представляет форму диаграммы, которую можно разместить на слайде и настроить.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Шаг 2: Инициализировать презентацию и добавить диаграмму
Создайте слайд, затем вызовите `addChart` с `ChartType.ClusteredColumn` и укажите желаемое положение и размер.

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

*Здесь мы добавляем группированную столбчатую диаграмму на первый слайд в указанные координаты и размеры.*

### Управление рабочей книгой данных диаграммы
**Обзор:**  
Эффективное управление рабочей книгой данных диаграммы позволяет без труда манипулировать сериями и категориями.

#### Шаг 1: Импортировать необходимые пакеты
`IChartDataWorkbook` предоставляет доступ к подлежащей Excel‑подобной рабочей книге, используемой диаграммами.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Шаг 2: Доступ и очистка рабочей книги данных
Получите рабочую книгу из диаграммы и очистите любые существующие данные, чтобы начать с чистого листа.

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

*Очистка рабочей книги критична для начала работы с чистым набором данных при добавлении новых серий и категорий.*

### Добавление серий и категорий к диаграмме
**Обзор:**  
Эта функция показывает, как добавить значимые точки данных, управляя сериями и категориями.

#### Шаг 1: Добавить серии и категории
Используйте `chart.getChartData().getSeries().add()` и `chart.getChartData().getCategories().add()`, чтобы определить структуру.

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

*Добавление серий и категорий обеспечивает более упорядоченную презентацию данных.*

### Заполнение данных серии и форматирование
**Обзор:**  
Заполните диаграмму точками данных и отформатируйте её внешний вид для повышения читаемости, особенно при работе с отрицательными значениями.

#### Шаг 1: Заполнить данные серии
Присвойте числовые значения каждой ячейке в рабочей книге и примените красную заливку для отрицательных чисел.

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

*Этот раздел демонстрирует, как заполнять данные и применять цветовое форматирование для лучшей визуализации.*

## Распространённые проблемы и решения
- **LicenseNotFoundException** – Убедитесь, что путь к файлу лицензии указан правильно и файл доступен во время выполнения.  
- **NullPointerException on chart data** – Всегда очищайте рабочую книгу перед добавлением новых серий, чтобы избежать остаточных данных.  
- **Chart not rendering in .NET** – Проверьте, что вы используете .NET‑совместимую версию JAR‑файла Aspose.Slides и что Java‑runtime корректно настроен в вашем .NET‑проекте.

## Часто задаваемые вопросы

**Q:** Могу ли я генерировать диаграмму в файлах презентаций без графического интерфейса?  
**A:** Да, Aspose.Slides for Java полностью безголовый и работает на серверах без каких‑либо графических компонентов.

**Q:** Какие версии .NET поддерживаются?  
**A:** Поддерживаются .NET Framework 4.5+, .NET Core 3.1+, .NET 5 и .NET 6.

**Q:** Сколько типов диаграмм можно добавить?  
**A:** Доступно более 20 типов диаграмм, включая столбчатые, линейные, круговые, областные и радиальные.

**Q:** Можно ли стилизовать отдельные точки данных?  
**A:** Абсолютно — вы можете задавать цвета заливки, границы и маркеры для каждой точки данных через API `IDataPoint`.

**Q:** Нужно ли вручную конвертировать Java‑объекты в типы .NET?  
**A:** Нет, .NET‑обёртка Aspose.Slides for Java автоматически обрабатывает преобразование типов.

---

**Последнее обновление:** 2026-06-03  
**Тестировано с:** Aspose.Slides for Java 25.4  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как встраивать диаграммы в .NET‑презентации с помощью Aspose.Slides для эффективной визуализации данных](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Как получить тип источника данных диаграммы с помощью Aspose.Slides для .NET — Диаграммы и графики](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Мастерство создания и манипулирования сериями диаграмм с Aspose.Slides .NET для эффективной визуализации данных](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
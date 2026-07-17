---
date: '2026-07-17'
description: Узнайте, как add chart в PowerPoint, создавая Pie of Pie chart с помощью
  Aspose.Slides for Java. Включает setup, code, customization и сохранение в PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Add chart в PowerPoint с Aspose.Slides for Java. Это руководство показывает,
  как create, customize и save Pie of Pie chart в формате PPTX за несколько минут.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Add Chart в PowerPoint – Create a Pie of Pie Chart в Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Add Chart в PowerPoint – Create a Pie of Pie Chart в Java с Aspose.Slides
url: /ru/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Добавить диаграмму в PowerPoint – Создать диаграмму Круг в круге в Java с Aspose.Slides

## Диаграммы и графики

### Введение

В современных презентациях, основанных на данных, **добавление диаграммы в PowerPoint** часто является самым быстрым способом превратить сырые цифры в визуальное представление. Обычная круговая диаграмма хорошо работает для небольшого количества категорий, но когда несколько секторов очень малы, они становятся нечитаемыми. Диаграмма *Pie of Pie* решает эту проблему, выделяя небольшие сектора во вторичную круговую диаграмму, сохраняя основную диаграмму чистой, а детали доступными.

В этом руководстве вы узнаете, как **добавить диаграмму в PowerPoint**, создав диаграмму Pie of Pie с помощью Aspose.Slides для Java. Мы пройдем настройку окружения, создание диаграммы, настройку меток, настройку положения разбиения и, наконец, сохранение презентации в файл PPTX. К концу вы будете готовы внедрять сложные диаграммы в любую презентацию.

## Быстрые ответы
В Aspose.Slides класс `Presentation` представляет файл PPTX, `ChartType.PieOfPie` выбирает диаграмму Pie of Pie, `setShowValue(true)` отображает значения на метках, а `save` записывает файл.

- **Какой основной класс для работы с PowerPoint?** `Presentation` – представляет весь файл PPTX в памяти.  
- **Какой тип диаграммы создает вторичный круг для небольших секторов?** `ChartType.PieOfPie`.  
- **Как отобразить значения на каждом секторе?** Установите `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Можно ли сохранить файл напрямую как PPTX?** Да — вызовите `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Нужна ли лицензия для разработки?** Бесплатная 30‑дневная trial-версия подходит для тестирования; постоянная лицензия удаляет водяные знаки оценки.

## Что такое диаграмма Pie of Pie?
Диаграмма **Pie of Pie** — это двухуровневая круговая визуализация, которая изолирует один или несколько небольших секторов в отдельный, связанный круг, делая их более читаемыми. Aspose.Slides поддерживает этот тип диаграммы из коробки, позволяя управлять размером разбиения, позицией и форматированием меток.

## Почему добавлять диаграмму в PowerPoint с Aspose.Slides?
Aspose.Slides может генерировать, редактировать и рендерить файлы PowerPoint без установленного Microsoft Office. Он поддерживает **более 50 форматов ввода и вывода**, обрабатывает презентации с **до 500 слайдами** менее чем за секунду на типичном серверном оборудовании и предоставляет **полный контроль API** над стилем диаграмм, метками данных и макетом — идеально для автоматизированных конвейеров отчетности.

## Требования

Before you start, make sure you have:

- **Java Development Kit (JDK) 16+** установлен.
- IDE, например **IntelliJ IDEA**, **Eclipse** или **NetBeans**.
- Maven или Gradle для управления зависимостями (см. разделы ниже).
- Базовые знания Java и знакомство со сборкой проектов.

## Настройка Aspose.Slides для Java

### Информация об установке

**Maven:**  
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

**Прямое скачивание:** Вы можете скачать последнюю версию по ссылке [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
- **Бесплатная пробная версия:** Начните с 30‑дневной trial-версии, чтобы изучить все функции.  
- **Временная лицензия:** Запросите временный ключ для расширенной оценки.  
- **Покупка:** Приобретите постоянную лицензию для использования в продакшене, чтобы убрать водяные знаки оценки.

### Базовая инициализация и настройка
`Presentation` — основной объект для создания файлов PowerPoint, а `Chart` представляет форму диаграммы на слайде.

```java
Presentation presentation = new Presentation();
```  

Это создает пустую презентацию, готовую для слайдов и диаграмм.

## Руководство по реализации

### Как добавить диаграмму в PowerPoint с помощью Aspose.Slides для Java?

Загрузите новый `Presentation`, добавьте слайд и вставьте `Chart` типа `PieOfPie`. Цепочка вызовов API лаконична: создайте диаграмму, заполните данные серии, настройте видимость меток, сконфигурируйте размер вторичного круга и, наконец, сохраните. Весь процесс обычно укладывается в менее чем 20 строк кода, что делает его идеальным для автоматической генерации отчетов.

### Создание диаграммы 'Pie of Pie'

#### Обзор
Мы построим диаграмму Pie of Pie на первом слайде, выделим самые маленькие сектора и подпишем каждый сегмент его значением.

#### Шаг 1: Создать экземпляр класса Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Это инициализирует контейнер для всех последующих слайдов и диаграмм.

#### Шаг 2: Добавить диаграмму 'Pie of Pie' на первый слайд
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Здесь мы указываем `ChartType.PieOfPie` и задаем позицию диаграммы (X, Y) и размер (ширина, высота) на холсте слайда.

#### Шаг 3: Установить метки данных для отображения значений серии
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Включение `showValue` заставляет каждый сектор отображать свое числовое значение, что важно для быстрой интерпретации данных.

#### Шаг 4: Настроить размер вторичного круга и разбиение по процентам
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Эти параметры позволяют решить, какая часть диаграммы будет отведена вторичному кругу и какие сектора перемещаются на основе порогового процента.

#### Шаг 5: Сохранить презентацию на диск в формате PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Полезный совет:** Используйте абсолютный путь или `Paths.get()` в Java, чтобы избежать разделителей, специфичных для платформы.

## Распространённые проблемы и решения

`License` класс загружает файл лицензии, чтобы убрать ограничения оценки.

- **Отсутствие предупреждения о лицензии:** Если вы видите «Evaluation Only» на диаграмме, убедитесь, что применили действительный файл лицензии через `License license = new License(); license.setLicense("Aspose.Slides.lic");`.
- **Неправильное разбиение секторов:** Проверьте, что свойство `splitBy` установлено в `SplitBy.Percentage`, а `secondPieSize` имеет значение от 0 до 100.
- **Данные не отображаются:** Убедитесь, что серия диаграммы содержит хотя бы одну точку данных; иначе диаграмма будет пустой.

## Часто задаваемые вопросы

`IChart` представляет объект диаграммы, который можно добавить на слайд.

**Q: Могу ли я создать несколько диаграмм в одной презентации?**  
A: Да, создайте новый `IChart` для каждого слайда или места; API позволяет неограниченное количество объектов диаграмм в файле.

`SaveFormat.Pdf` указывает формат вывода PDF при сохранении.

**Q: Поддерживает ли Aspose.Slides сохранение в PDF?**  
A: Конечно — вызовите `presentation.save("output.pdf", SaveFormat.Pdf)`, чтобы экспортировать ту же презентацию в PDF.

`IPortion` представляет отдельный сектор круговой диаграммы.

**Q: Какое максимальное количество точек данных может обрабатывать диаграмма Pie of Pie?**  
A: Библиотека поддерживает до **10 000** точек данных на серию, ограничение только доступной памятью.

**Q: Можно ли настроить цвета отдельных секторов?**  
A: Да, доступ к каждому `IPortion` можно получить через `chart.getChartData().getSeries().get_Item(0).getPortions()` и установить `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Как встроить сгенерированный PPTX в веб‑приложение?**  
A: После сохранения файла передайте его напрямую клиенту, используя `HttpServletResponse` с `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Заключение

Теперь у вас есть полное, готовое к продакшену руководство по **добавлению диаграммы в PowerPoint** путем создания диаграммы Pie of Pie с Aspose.Slides для Java. Экспериментируйте с различными порогами разбиения, форматами меток и цветовыми схемами, чтобы соответствовать рекомендациям вашего бренда. Далее изучайте другие типы диаграмм — такие как сложенные столбцы или радиальная — чтобы еще больше обогатить ваши автоматизированные презентации.

---

**Последнее обновление:** 2026-07-17  
**Тестировано с:** Aspose.Slides for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [Создать динамическую диаграмму Java – Руководства по диаграммам PowerPoint для Aspose.Slides](/slides/java/charts-graphs/)
- [Как добавить круговую диаграмму в PowerPoint с Aspose.Slides для Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Как добавить диаграммы в PowerPoint с помощью Aspose.Slides для Java: пошаговое руководство](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
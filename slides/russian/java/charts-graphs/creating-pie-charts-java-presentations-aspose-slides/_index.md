---
date: '2026-08-01'
description: Узнайте, как использовать лицензию Aspose Slides для создания и настройки
  круговых диаграмм в презентациях Java. Следуйте пошаговым инструкциям по настройке
  данных круговой диаграммы и эффективному добавлению слайдов с диаграммами.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Узнайте, как использовать лицензию Aspose Slides для создания и настройки
  круговых диаграмм в презентациях Java. Следуйте пошаговым инструкциям по настройке
  данных круговой диаграммы и эффективному добавлению слайдов с диаграммами.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Создание круговых диаграмм в Java с лицензией Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Создание круговых диаграмм в Java с лицензией Aspose Slides
url: /ru/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создавать круговые диаграммы в Java‑презентациях с использованием Aspose.Slides

## Введение

Если вам нужно создавать профессионально выглядящие презентации, **лицензия Aspose Slides** дает возможность программно генерировать и оформлять диаграммы. В этом руководстве вы узнаете, как создать круговую диаграмму, настроить её данные и встроить её в набор слайдов Java — без использования Microsoft PowerPoint. Мы пройдём через настройку, поток кода и рекомендации по лучшим практикам, чтобы вы могли за считанные минуты создавать отшлифованные визуальные отчёты.

**Что вы узнаете:**
- Настройка Aspose.Slides для Java с действующей лицензией
- Шаги по созданию и настройке круговой диаграммы
- Как настроить данные круговой диаграммы и добавить слайды с диаграммами
- Распространённые подводные камни и приёмы повышения производительности

Начнём с проверки готовности вашей среды.

## Быстрые ответы
- **Что позволяет лицензия Aspose Slides?** Полнофункциональное создание диаграмм, экспорт в PDF/HTML и удаление водяных знаков.
- **Какая версия Java требуется?** JDK 16 или новее.
- **Нужен ли Maven или Gradle?** Подходит любой; библиотека доступна через оба.
- **Сколько точек данных может содержать круговая диаграмма?** До 10 000 точек без проблем с памятью.
- **Могу ли я экспортировать слайд как изображение?** Да — поддерживаются PNG, JPEG, SVG и другие форматы.

## Требования
- **Требуемые библиотеки:** Aspose.Slides for Java (версия 25.4 или новее) — эта версия поддерживает новейшие форматы файлов и оптимизации производительности.
- **Настройка среды:** установленный JDK 16+ и настроенный в вашей IDE или системе сборки.
- **Базовые знания:** знакомство с Java, Maven или Gradle и концепциями объектно‑ориентированного программирования.

## Настройка Aspose.Slides для Java

Чтобы использовать Aspose.Slides для Java, включите её в свой проект. Ниже показано, как добавить зависимость с помощью самых популярных инструментов сборки:

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

**Прямое скачивание:** Вы можете также скачать последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Получение лицензии

Aspose предлагает бесплатную пробную версию, открывающую все функции, но для использования в продакшене требуется **действительная лицензия Aspose Slides**, чтобы убрать водяные знаки оценки и получить преимущества в производительности. Варианты покупки указаны на [странице покупки](https://purchase.aspose.com/buy). После получения файла лицензии загрузите его один раз при запуске приложения:

```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Руководство по реализации

### Создание и добавление круговой диаграммы в презентацию

#### Обзор
В этом разделе объясняется, как создать круговую диаграмму, настроить её серию данных и встроить диаграмму в слайд. Вы увидите полный процесс от инициализации объекта презентации до сохранения конечного файла.

#### Шаг 1: Инициализация презентации
`Presentation` — это объект верхнего уровня Aspose.Slides, представляющий файл PowerPoint в памяти. Создание экземпляра дает вам пустой набор слайдов, готовый к модификации.

```java
demo.Presentation pres = new demo.Presentation();
```  
Эта строка создаёт новую презентацию, в которой будут применены все последующие изменения.

#### Шаг 2: Добавление круговой диаграммы на слайд
`Chart` — класс, инкапсулирующий объекты диаграмм, включая круговые диаграммы. Добавление диаграммы на слайд осуществляется одним вызовом метода, указывающим позицию и размер.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` и `yPosition` задают левый верхний угол диаграммы.  
- `width` и `height` определяют визуальный размер диаграммы на слайде.

#### Шаг 3: Настройка данных круговой диаграммы
`ChartData` хранит серии данных для диаграммы.  
**Как настроить данные круговой диаграммы?**  
Сначала дайте краткий ответ: используйте коллекцию `ChartData` для добавления серии, затем заполните объекты `ChartDataPoint` числовыми значениями и названиями категорий. Такой подход позволяет отображать до 10 000 секторов, сохраняя форматирование меток. После установки данных вы можете настроить цвета, легенды и подписи данных в соответствии с корпоративным стилевым руководством.

Теперь представляем код, который добавляет две категории и отображает их метки:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Этот фрагмент создаёт серию данных, вставляет две точки и включает метки категорий на диаграмме.

#### Шаг 4: Сохранение презентации
Наконец, сохраните презентацию в выбранный вами формат файла (PPTX, PDF или PNG). Метод `save` учитывает активную лицензию, гарантируя отсутствие пробных водяных знаков.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Распространённые проблемы и решения
- **Ошибка отсутствующей лицензии:** Убедитесь, что путь к файлу лицензии правильный и объект `License` создан до любых вызовов Aspose.Slides.
- **Пустая диаграмма:** Проверьте, что серия `ChartData` содержит хотя бы один `ChartDataPoint`. Пустая серия приводит к пустой области диаграммы.
- **Задержка производительности при больших наборах данных:** Используйте `presentation.getSlides().removeAt(index)`, чтобы удалить неиспользуемые слайды, и вызовите `System.gc()` после интенсивной обработки.

## Практические применения
1. **Бизнес‑отчёты:** Визуализировать долю рынка или распределение доходов по регионам с помощью одной круговой диаграммы.
2. **Академические презентации:** Показать результаты опросов или экспериментов в ясном, легко воспринимаемом формате.
3. **Проектные панели:** Отобразить процент выполнения задач или распределение ресурсов мгновенно на слайде.

Вы также можете комбинировать Aspose.Slides с JDBC для получения живых данных из базы данных, генерируя актуальные диаграммы для еженедельных брифингов руководства.

## Соображения по производительности
При работе с презентациями, содержащими множество изображений высокого разрешения или большие наборы данных:
- • Освобождайте объекты сразу с помощью `try‑with‑resources` или явных вызовов `dispose()`.
- • Включайте отложенную загрузку ресурсов слайдов, чтобы снизить использование памяти.
- • При пакетной обработке по возможности переиспользуйте один экземпляр `Presentation`, чтобы уменьшить нагрузку на JVM.

## Заключение
Теперь у вас есть полный, готовый к продакшену рабочий процесс создания круговых диаграмм в Java с использованием **лицензии Aspose Slides**. Поэкспериментируйте с другими типами диаграмм — столбчатыми, линейными или кольцевыми — чтобы ещё больше обогатить ваши слайды. Далее изучите возможности экспорта API для автоматической генерации PDF‑отчётов или PNG‑изображений.

## Часто задаваемые вопросы

**Q: Как добавить несколько диаграмм на один слайд?**  
A: Вызовите `slide.getShapes().addChart()` для каждой диаграммы, задавая уникальные координаты и размеры для каждого экземпляра.

**Q: Какие существуют альтернативы Aspose.Slides для Java?**  
A: Apache POI и JFreeChart являются распространёнными альтернативами, но им не хватает полного набора опций экспорта и модели лицензирования Aspose.

**Q: Могу ли я конвертировать свою презентацию в другие форматы с помощью Aspose.Slides?**  
A: Да — экспорт в PDF, XPS, HTML, PNG, JPEG, SVG и другие возможен одним вызовом `save`.

**Q: Как управлять лицензированием для большой команды разработчиков?**  
A: Приобретите корпоративную лицензию, покрывающую нескольких разработчиков и серверы; свяжитесь с отделом продаж Aspose для получения скидок при объёмах.

**Q: Что делать, если данные моей диаграммы часто обновляются?**  
A: Интегрируйте Aspose.Slides с источником данных (например, SQL‑запросом) и перестраивайте диаграмму во время выполнения; API поддерживает динамическое привязывание данных.

## Ресурсы
- **Документация:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Скачать:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Покупка:** [Buy a License](https://purchase.aspose.com/buy)
- **Бесплатная пробная версия:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Временная лицензия:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Поддержка:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Последнее обновление:** 2026-08-01  
**Тестировано с:** Aspose.Slides for Java 25.4  
**Автор:** Aspose

## Связанные руководства

- [Как добавить и настроить диаграммы в презентациях с использованием Aspose.Slides для Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Создание и настройка диаграмм в Java‑презентациях с использованием Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Как создавать и настраивать презентации с Aspose.Slides Java: пошаговое руководство](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
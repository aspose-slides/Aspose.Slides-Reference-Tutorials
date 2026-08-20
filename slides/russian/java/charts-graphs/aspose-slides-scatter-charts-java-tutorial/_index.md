---
date: '2026-07-27'
description: Как настроить диаграмму с помощью Aspose.Slides for Java. Узнайте, как
  создать диаграмму PowerPoint, оформить точечные серии и эффективно сохранять презентации.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Как настроить диаграмму с Aspose.Slides for Java. Это руководство
  показывает, как создать диаграмму PowerPoint, оформить точечные точки и экспортировать
  презентации.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Как настроить диаграмму: точечная диаграмма Aspose в Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Как настроить диаграмму: точечная диаграмма Aspose в Java'
url: /ru/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Настройка диаграммы рассеяния Aspose в Java

В этом руководстве вы узнаете **как настраивать диаграмму** — конкретно диаграмму рассеяния — с помощью мощной библиотеки Aspose.Slides for Java. Мы пройдем настройку проекта, создание диаграммы рассеяния, настройку типов рядов и маркеров, а затем сохранение презентации. В конце вы сможете программно генерировать профессионально выглядящие диаграммы рассеяния и подгонять каждый визуальный элемент под ваш бренд или требования к отчетности.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Slides for Java (v25.4+).  
- **Какая версия Java поддерживается?** JDK 8 or higher.  
- **Можно ли изменить формы маркеров?** Yes – use `MarkerStyleType` to pick stars, circles, etc.  
- **Как сохранить файл?** Call `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Требуется ли лицензия?** A free trial works for development; a commercial license is needed for production.

## Как настроить диаграмму в Java с помощью Aspose.Slides?
`Presentation` — это класс Aspose.Slides, представляющий в памяти весь файл PowerPoint. Загрузите новый `Presentation`, добавьте диаграмму рассеяния на первый слайд, настройте типы рядов и стили маркеров, затем вызовите `save`. Этот простой процесс создает полностью оформленную диаграмму всего в несколько строк кода Java, готовую к включению в любую презентацию PowerPoint.

## Что такое «customize scatter chart aspose»?
Настройка диаграммы рассеяния с помощью Aspose означает программное определение данных диаграммы, её внешнего вида и поведения — всего, от координат точек до символов маркеров — без ручного открытия PowerPoint. Такой подход идеален для автоматизированных отчетов, презентаций, основанных на данных, или любой ситуации, когда требуются повторяемые визуализации высокого качества.

## Почему настраивать диаграммы рассеяния с Aspose.Slides?
Aspose.Slides предоставляет разработчикам полный программный контроль над внешним видом диаграмм, позволяя автоматически создавать визуализации высокого качества, бесшовно интегрировать их в конвейеры отчетности и настраивать каждый визуальный элемент без ручного открытия PowerPoint, что экономит время и обеспечивает согласованность презентаций.

- **Full control** – изменяйте типы рядов, стили маркеров, цвета и многое другое с помощью Java‑кода.  
- **Automation** – генерируйте десятки диаграмм «на лету» для панелей мониторинга или пакетных отчетов.  
- **Cross‑platform** – работает на любой ОС, поддерживающей Java, без необходимости установки Office.  
- **Performance** – легковесный API, обрабатывающий **150+ типов диаграмм** и работающий с презентациями в сотни страниц без загрузки всего файла в память.

## Требования

Чтобы следовать инструкциям, убедитесь, что у вас есть:

- **Aspose.Slides for Java** (v25.4 или новее).  
- **Java Development Kit (JDK)** 8 + установлен.  
- Maven или Gradle для управления зависимостями (или можно скачать JAR вручную).  
- Базовые знания Java и знакомство с выбранным инструментом сборки.

## Настройка Aspose.Slides для Java

Интегрируйте библиотеку в ваш проект, используя один из методов ниже.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Или загрузите последнюю версию с [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Приобретение лицензии
- **Free Trial** – 30‑дневная оценка.  
- **Temporary License** – расширенный период тестирования.  
- **Full License** – использование в продакшене с премиум‑поддержкой.

## Пошаговое руководство по настройке диаграммы рассеяния Aspose

### 1️⃣ Подготовьте папку для файлов презентации
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Почему это важно:* Убедившись, что папка вывода существует, вы предотвращаете `FileNotFoundException` при последующем сохранении PPTX.

### 2️⃣ Создайте новую презентацию и получите первый слайд
`Presentation` представляет документ PowerPoint и предоставляет доступ к слайдам и объектам. Класс `Presentation` представляет в памяти весь файл PowerPoint.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Добавьте диаграмму рассеяния со сглаженными линиями
`ChartType.ScatterWithSmoothLines` создает диаграмму рассеяния, где точки соединены сглаженными линиями.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Очистите любые стандартные ряды и добавьте свои
`IChartSeries` представляет серию данных внутри диаграммы.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Заполните первый ряд точками данных
`addDataPointForScatterSeries` добавляет одну точку X‑Y в ряд диаграммы рассеяния.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Настройте тип ряда и внешний вид маркера
`Marker` управляет визуальным символом, используемым для каждой точки данных в ряду диаграммы.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Сохраните презентацию
`save` записывает презентацию в файл в указанном формате.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Общие сценарии использования настроенных диаграмм рассеяния
- **Financial dashboards** – построение графика цены акции против объёма.  
- **Scientific research** – отображение экспериментальных измерений с маркерами ошибок.  
- **Project management** – сравнение запланированных и фактических усилий по задачам.  

## Советы по производительности
- Вызовите `pres.dispose()` после сохранения, чтобы освободить нативную память.  
- Для больших наборов данных сначала заполните рабочую книгу, а затем привяжите ряды, чтобы избежать повторных обновлений UI.  
- Повторно используйте один экземпляр `IChartDataWorkbook` при добавлении множества рядов, чтобы снизить потребление памяти.

## Часто задаваемые вопросы

**Q: Как изменить цвет маркеров?**  
A: Используйте `series.getMarker().getFillFormat().setFillColor(Color)`, где `Color` — это экземпляр `java.awt.Color`, например `Color.RED`.

**Q: Можно ли добавить более двух рядов в диаграмму рассеяния?**  
A: Да. Вызовите `chart.getChartData().getSeries().add(...)` для каждого дополнительного ряда и заполните его точки соответствующим образом.

**Q: Можно ли задать пользовательскую подпись (legend) для каждого ряда?**  
A: Конечно. После создания ряда вызовите `series.getLegend().setText("Your Legend Text")`, чтобы переопределить имя по умолчанию.

**Q: Как экспортировать диаграмму как изображение вместо PPTX?**  
A: Вызовите `chart.getImage().save("chart.png", ImageFormat.Png)` после настройки диаграммы. Это создаст отдельный PNG‑файл.

**Q: Что делать, если нужно анимировать точки рассеяния?**  
A: Aspose.Slides поддерживает анимационные эффекты. Используйте `chart.getTimeline().getMainSequence().addEffect(...)`, чтобы добавить анимацию появления или акцента к диаграмме или отдельным рядам.

---

**Последнее обновление:** 2026-07-27  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создание и настройка диаграмм PowerPoint в Java с использованием Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Как создать пузырьковую диаграмму в PowerPoint с помощью Aspose.Slides for Java (руководство)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Создание и настройка диаграмм с трендовыми линиями в Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
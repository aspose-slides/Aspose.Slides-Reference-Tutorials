---
date: '2026-08-16'
description: Узнайте, как добавить doughnut charts в Java с помощью Aspose.Slides.
  Это пошаговое руководство охватывает настройку зависимости Maven, конфигурацию chart,
  цвета, подписи и сохранение PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Как добавить doughnut charts в Java с использованием Aspose.Slides.
  Следуйте этому руководству, чтобы настроить Maven, настроить цвета, подписи и создать
  файлы PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Как добавить doughnut chart в Java с Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Как добавить doughnut chart в Java с Aspose.Slides
url: /ru/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как добавить кольцевую диаграмму в Java с помощью Aspose.Slides

## Введение

Создание **кольцевой диаграммы** программно может превратить сырые цифры в привлекающий внимание визуальный элемент, который мгновенно рассказывает историю. В Java **Aspose.Slides** упрощает этот процесс, позволяя генерировать готовые к презентации диаграммы без необходимости открывать PowerPoint. В этом руководстве вы узнаете **как добавить кольцевые** диаграммы в файл PPTX шаг за шагом — от настройки зависимости Maven Aspose Slides до настройки рядов, категорий, цветов и подписей, и, наконец, сохранения презентации.

К концу этого руководства вы сможете встраивать динамические кольцевые диаграммы в любой файл PPTX, что идеально подходит для отчетов, панелей мониторинга или автоматических наборов слайдов.

### Быстрые ответы
- **Какая библиотека используется?** Aspose.Slides for Java  
- **Основная задача?** Добавить кольцевую диаграмму в файл PPTX  
- **Как добавить библиотеку?** Использовать Maven‑зависимость Aspose Slides (или Gradle)  
- **Минимальная версия Java?** JDK 16 или выше  
- **Можно ли настроить цвета и подписи?** Да, API предоставляет полный контроль форматирования  

## Что такое кольцевая диаграмма и зачем её использовать?

Кольцевая диаграмма — это вариант круговой диаграммы с пустым центром, позволяющий отображать несколько рядов данных в виде концентрических колец. **Она визуализирует части‑целого по нескольким категориям, оставляя место для дополнительной информации в центре.** Это делает её идеальной для сравнения продаж по регионам за несколько кварталов, распределения бюджета по отделам или любой ситуации, где необходимо показать иерархические пропорциональные данные.

## Почему использовать Aspose.Slides для Java?

Вы можете добавить кольцевую диаграмму без установки Microsoft Office, а библиотека обрабатывает **более 50 + форматов ввода и вывода**, работая с презентациями, превышающими 500 слайдов. Aspose.Slides обеспечивает **до 3× более быструю отрисовку** по сравнению с нативной автоматизацией Office на том же оборудовании и работает на Windows, Linux и macOS. Эти измеримые преимущества позволяют генерировать большие наборы слайдов на безголовых серверах с предсказуемой производительностью.

## Требования

- **Необходимые библиотеки**  
  - Aspose.Slides for Java 25.4 или новее (библиотека, позволяющая добавлять кольцевые диаграммы).  

- **Среда**  
  - Установленный JDK 16 или выше.  
  - IDE, например IntelliJ IDEA, Eclipse или NetBeans.  

- **Знания**  
  - Базовый синтаксис Java и концепции объектно‑ориентированного программирования.  
  - Знакомство с Maven или Gradle для управления зависимостями.  

## Зависимость Maven Aspose Slides

Добавьте следующую зависимость Maven в ваш `pom.xml`. Это **maven aspose slides dependency**, необходимая для подключения библиотеки к проекту.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Если вы предпочитаете Gradle, используйте эквивалентный фрагмент ниже.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Вы также можете скачать JAR‑файл напрямую со страницы официальных релизов:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Получение лицензии

Чтобы убрать водяной знак оценки и разблокировать полный набор функций:

- **Бесплатная пробная версия** – начните с временной лицензии.  
- **Временная лицензия** – запросите её на [веб‑сайте Aspose](https://purchase.aspose.com/temporary-license/).  
- **Коммерческая лицензия** – приобретите для использования в продакшене.

Примените лицензию в вашем коде:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Руководство по реализации

### Инициализация презентации и добавление кольцевой диаграммы

`Presentation` — класс Aspose.Slides, представляющий презентацию PowerPoint.  
Загрузите существующий PPTX или создайте новый объект `Presentation`, затем добавьте кольцевую диаграмму на первый слайд.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Настройка рабочей книги данных диаграммы и очистка существующих данных

Рабочая книга — внутренняя таблица, хранящая данные диаграммы.  
Получите рабочую книгу, связанную с диаграммой, затем очистите любые рядки или категории по умолчанию, чтобы начать с чистого листа.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Добавление рядов к диаграмме

Ряд представляет собой набор точек данных, отображаемых на диаграмме.  
Можно добавить до 15 рядов. Каждый ряд можно настроить — здесь мы задаём взрыв, размер отверстия кольца и угол первого сектора.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Добавление категорий и точек данных

Категории — подписи для каждой точки данных вдоль оси диаграммы.  
Создайте 15 категорий и заполните каждую серию точкой данных. Последний ряд получает особое форматирование подписи.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Настройка цветов и подписей данных

`FillType.Solid` задаёт сплошную заливку цветом для элементов диаграммы.  
Установите сплошную заливку для каждого ряда и включите подписи данных. Для последнего ряда также изменяем цвет шрифта подписи.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Сохранение презентации

`save` записывает презентацию в файл в выбранном формате.  
Запишите обновлённую презентацию на диск в формате PPTX или экспортируйте в PDF при необходимости.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Распространённые проблемы и решения

- **Лицензия не найдена** – проверьте правильность пути к `license.lic` и доступность файла.  
- **Диаграмма отображается пустой** – убедитесь, что вы очистили существующие ряды/категории перед добавлением новых.  
- **Неправильные цвета** – убедитесь, что `FillType.Solid` установлен как для заливки, так и для формата линии.  
- **Производительность при большом количестве рядов** – ограничьте количество рядов/категорий или переиспользуйте ячейки рабочей книги, чтобы контролировать использование памяти.  

## Часто задаваемые вопросы

**В: Можно ли сгенерировать кольцевую диаграмму без предварительно существующего файла PPTX?**  
О: Да, создайте `new Presentation()` для начала с пустой колоды слайдов, затем добавьте диаграмму, как показано выше.

**В: Поддерживает ли Aspose.Slides экспорт в PDF?**  
О: Абсолютно. После создания диаграммы вызовите `pres.save("output.pdf", SaveFormat.Pdf);`, чтобы получить PDF‑версию слайда.

**В: Как изменить размер отверстия кольца?**  
О: Используйте `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, где `value` находится в диапазоне от 0 до 100.

**В: Можно ли добавить подписи данных ко всем рядам, а не только к последнему?**  
О: Да, переместите блок форматирования подписи за пределы условия `if (i == ...)` и примените его к каждому `dataPoint`.

**В: Какие версии Java поддерживаются?**  
О: Aspose.Slides 25.4 поддерживает JDK 16 и новее. Для более ранних JDK требуется соответствующий классификатор в зависимости Maven.

---

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Связанные руководства

- [Как добавить диаграмму в PowerPoint с помощью Aspose.Slides для Java: пошаговое руководство](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Как настроить цвета круговой диаграммы в Java с Aspose.Slides – Полное руководство](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Анимация категорий диаграммы PowerPoint с Aspose.Slides для Java | Пошаговое руководство](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
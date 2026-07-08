---
date: '2026-07-08'
description: Узнайте, как использовать Aspose для создания кольцевой диаграммы в PowerPoint
  с помощью Java. Это пошаговое руководство показывает, как программно добавлять точки
  данных диаграммы, настраивать подписи и сохранять файл PPTX с высоким качеством.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Как использовать Aspose, позволяет создавать кольцевую диаграмму в
  PowerPoint с помощью Java. Следуйте этому руководству, чтобы добавить точки данных,
  настроить подписи и сохранить файл PPTX с высоким качеством.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Как использовать Aspose: создать кольцевую диаграмму в PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Как использовать Aspose для создания кольцевой диаграммы в PowerPoint (Java)
url: /ru/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как использовать Aspose для создания кольцевой диаграммы в PowerPoint (Java)

## Введение
Создание убедительных презентаций часто требует не только текста и изображений; диаграммы могут значительно улучшить повествование, эффективно визуализируя данные. **How to use Aspose** для генерации диаграмм предоставляет программный контроль без необходимости открывать PowerPoint. В этом руководстве мы пошагово создадим кольцевую диаграмму, настроим её точки данных и сохраним PPTX высокого качества. Вам понадобится лишь базовое знание Java и несколько минут на настройку.

`Aspose.Slides for Java` — это библиотека Java, позволяющая создавать, изменять и конвертировать файлы PowerPoint без Microsoft Office.

## Быстрые ответы
- **Какая библиотека создает кольцевую диаграмму в PowerPoint?** Aspose.Slides for Java  
- **Можно ли программно добавлять точки данных в диаграмму?** Да, используя API диаграмм  
- **Нужна ли лицензия для продакшна?** Требуется действующая лицензия Aspose.Slides  
- **Какие версии Java поддерживаются?** Java 8 и новее (показан классификатор JDK 16)  
- **Сколько серий можно добавить?** В примере добавлено до 15 серий, но вы можете изменить это по необходимости  

## Что такое кольцевая диаграмма в PowerPoint?
Кольцевая диаграмма — это круговая диаграмма, похожая на круговую, но с полой серединой, позволяющая одновременно отображать несколько серий. Она подчеркивает отношения часть‑целое, при этом сохраняет компактный и легко читаемый визуальный вид.

## Почему использовать Aspose.Slides for Java для создания кольцевых диаграмм?
Aspose.Slides for Java поддерживает более 50 форматов ввода и вывода и может генерировать презентации размером до 500 МБ без загрузки всего файла в память. Он предоставляет полный программный контроль над внешним видом диаграмм, данными и макетом на любой платформе Java, устраняет необходимость в COM‑взаимодействии и может отрисовать 100 слайдов, насыщенных диаграммами, менее чем за две секунды на типичном сервере.

## Требования
- Базовые знания программирования на Java.  
- IDE, например IntelliJ IDEA или Eclipse.  
- Maven или Gradle для управления зависимостями.  
- Действительная лицензия Aspose.Slides for Java (доступна бесплатная пробная версия).  

## Настройка Aspose.Slides for Java
Выберите менеджер зависимостей, подходящий вашему проекту.

**Maven**  
Добавьте следующую зависимость в ваш `pom.xml` (замените версию на последнюю доступную):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Добавьте эту строку в ваш `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Если вы предпочитаете загрузить напрямую, посетите страницу [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
Вы можете начать с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides. Для длительного использования приобретите лицензию или запросите временную на сайте [Aspose's website](https://purchase.aspose.com/temporary-license/). Следуйте инструкциям по настройке среды и инициализации Aspose.Slides в вашем приложении.

## Как создать кольцевую диаграмму в PowerPoint с помощью Aspose.Slides for Java
Чтобы создать кольцевую диаграмму, начните с загрузки или создания `Presentation`, добавьте форму диаграммы типа `ChartType.Doughnut`, очистите серии по умолчанию, задайте размер отверстия, а затем заполните рабочую книгу диаграммы названиями категорий и числовыми значениями. В конце отрегулируйте форматирование меток и сохраните PPTX.

### Шаг 1: Инициализация презентации
Создайте новую презентацию или откройте существующий файл, чтобы получить коллекцию слайдов.

`Presentation` — основной класс, представляющий файл PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Шаг 2: Добавление кольцевой диаграммы на слайд
Вставьте форму диаграммы, удалите серии/категории по умолчанию и настройте базовые визуальные параметры, такие как размер отверстия кольца.

`Chart` (или форма диаграммы) представляет объект диаграммы, размещённый на слайде.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Шаг 3: Добавление точек данных в диаграмму и настройка меток
Заполните названия категорий, добавьте точки данных для каждой серии и точно настройте форматирование меток (шрифт, цвет, позиция). Этот шаг демонстрирует возможность “добавления точек данных в диаграмму”.

`Workbook` предоставляет доступ к подлежащим данным таблицы диаграммы, где заполняются ячейки.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Шаг 4: Сохранение обновлённой презентации
`save` записывает презентацию в файл выбранного формата.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Практические применения
- **Финансовые отчёты:** Визуализация распределения бюджета или разбивки расходов.  
- **Анализ рынка:** Показ распределения доли рынка среди конкурентов.  
- **Результаты опросов:** Представление категориальных данных опросов в компактной форме.  
- **Создание панелей мониторинга:** Комбинация с запросами к базе данных для создания слайдов с живым обновлением.  

## Соображения по производительности
- **Освобождение ресурсов:** Вызовите `pres.dispose()` после сохранения, чтобы освободить нативную память.  
- **Ограничение количества диаграмм:** Добавление сотен диаграмм может увеличить использование памяти; при необходимости обрабатывайте их пакетно.  
- **Используйте потоковую передачу:** Для огромных наборов данных заполняйте рабочую книгу напрямую из потоков, а не из массивов в памяти.  

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Диаграмма пустая** | Ячейки данных не заполнены корректно | Убедитесь, что `workBook.getCell(...)` ссылается на правильные индексы строк/столбцов. |
| **Метки перекрываются** | Слишком много категорий в ограниченном пространстве | Увеличьте `DoughnutHoleSize` или скорректируйте `FirstSliceAngle`. |
| **OutOfMemoryError** | Большие презентации без освобождения ресурсов | Вызовите `pres.dispose()` после сохранения и рассмотрите возможность увеличения размера кучи JVM. |

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.Slides for Java в коммерческих приложениях?**  
О: Да, но требуется действующая коммерческая лицензия. Доступна бесплатная пробная версия для оценки.

**В: Как добавить более 15 серий?**  
О: Увеличьте предел цикла в шаге “Add Doughnut Chart” и убедитесь, что ваша рабочая книга данных содержит достаточное количество строк.

**В: Можно ли изменить размер отверстия кольца после создания?**  
О: Да, вызовите `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` перед сохранением.

**В: Можно ли экспортировать диаграмму как изображение вместо PPTX?**  
О: Конечно. Используйте `chart.getImage()` и сохраните полученный `java.awt.image.BufferedImage` в нужном вам формате.

**В: Поддерживает ли Aspose.Slides анимированные диаграммы?**  
О: Анимацию можно добавить через API `ISlide.getTimeline()`, хотя это выходит за рамки данного руководства.

## Заключение
Теперь у вас есть полный, готовый к продакшну метод **создания файлов PowerPoint с кольцевой диаграммой** с помощью Aspose.Slides for Java, включая то, как **добавлять точки данных в диаграмму**, настраивать метки и учитывать вопросы производительности. Экспериментируйте с различными цветами, источниками данных и типами диаграмм, чтобы ваши презентации действительно выделялись.

---

**Последнее обновление:** 2026-07-08  
**Тестировано с:** Aspose.Slides for Java 25.4 (классификатор JDK 16)  
**Автор:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Связанные руководства

- [Как добавить диаграммы в PowerPoint с помощью Aspose.Slides for Java: пошаговое руководство](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Как редактировать данные диаграммы PowerPoint с помощью Aspose.Slides for Java: полное руководство](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Анимация диаграмм в PowerPoint с помощью Aspose.Slides for Java – пошаговое руководство](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
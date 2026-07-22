---
date: '2026-07-22'
description: Изучите Aspose Slides Maven Dependency, чтобы создавать stacked column
  chart в Java, добавлять data labels, изменять vertical axis number format и экспортировать
  результат в файл PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency позволяет создавать stacked column
  chart в Java, настраивать data labels, регулировать vertical axis format и сохранять
  в PPTX — всё с лаконичным, production‑ready code.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Столбчатая диаграмма с накоплением в Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Столбчатая диаграмма с накоплением в Java'
url: /ru/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: Столбчатая диаграмма с накоплением в Java

## Введение

Поднимите уровень ваших презентаций, внедрив информативные визуализации данных с помощью **Aspose.Slides for Java**. В этом руководстве вы **создадите столбчатую диаграмму с накоплением**, выглядящую профессионально, будь то бизнес‑отчёты или демонстрация статистики проекта. По завершении этого урока вы сможете:

- Настроить окружение с помощью **Aspose Slides Maven dependency**
- Создать презентацию с нуля
- **Добавить процентную накопленную диаграмму** и настроить её внешний вид
- **Форматировать подписи данных диаграммы** и **изменить формат чисел вертикальной оси**
- **Сохранить презентацию как PPTX** одной строкой кода

## Быстрые ответы
- **Какая библиотека нужна?** Добавьте зависимость Maven/Gradle `aspose-slides` (см. раздел «Aspose Slides Maven Dependency» ниже).  
- **Какой тип диаграммы создаёт накопленный вид?** Используйте `ChartType.PercentsStackedColumn` для процентной накопленной столбчатой диаграммы.  
- **Как изменить формат чисел оси?** Вызовите `IAxis.setNumberFormat()` и установите `setNumberFormatLinkedToSource(false)`.  
- **Можно ли настроить подписи данных?** Да — пройдитесь по каждому `IChartDataPoint` и назначьте пользовательский `ITextFrame`.  
- **Как сохранить файл?** Вызовите `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Что такое столбчатая диаграмма с накоплением?
Столбчатая диаграмма с накоплением визуализирует несколько рядов данных, наложенных вертикально в каждом столбце категории, при этом вариант **процентного накопления** нормализует каждый столбец до 100 % для удобного сравнения пропорций. Такой формат позволяет зрителям быстро оценить вклад каждой составляющей в общую картину по разным категориям, делая тенденции и относительные размеры мгновенно очевидными.

## Почему использовать Aspose.Slides for Java?
Aspose.Slides for Java позволяет генерировать, редактировать и конвертировать файлы PowerPoint **без необходимости Microsoft Office** и поддерживает **более 50 форматов вывода** на Windows, Linux и macOS. Библиотека полностью работает на JRE, что обеспечивает серверную автоматизацию и высокопроизводительную генерацию отчётов. Кроме того, она предоставляет тонкий контроль над объектами диаграмм, макетами слайдов и свойствами документа, что делает её идеальной для корпоративного уровня создания презентаций.

## Требования
- **Java Development Kit (JDK):** 8 или выше  
- **IDE:** IntelliJ IDEA, Eclipse или любой совместимый редактор Java  
- **Система сборки:** Maven или Gradle (необязательно, но рекомендуется)  
- **Базовые знания Java** – вы должны быть уверены в работе с классами и методами  

## Настройка Aspose.Slides for Java
Чтобы начать, добавьте библиотеку Aspose.Slides в ваш проект.

### Зависимость Maven Aspose Slides
Добавьте следующее в ваш `pom.xml` (это **aspose slides maven dependency**, которая вам понадобится):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Альтернатива Gradle
Если вы предпочитаете Gradle, включите эту строку в `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямое скачивание
В качестве альтернативы загрузите последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
Вы можете начать с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides. Чтобы убрать ограничения оценки, рассмотрите возможность получения временной или приобретённой лицензии.

- **Бесплатная пробная версия:** Доступ к ограниченному набору функций без немедленных расходов.  
- **Временная лицензия:** Запросите через [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Покупка:** Посетите страницу покупки для полного доступа.

### Базовая инициализация
`Presentation` — основной класс Aspose.Slides, представляющий файл PowerPoint в памяти. Ниже минимальный фрагмент кода, показывающий, как создать объект `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Руководство по реализации

### Создание презентации и добавление слайда
**Обзор:**  
Сначала мы создадим пустую презентацию и проверим, что слайд существует.

#### Шаг 1: Инициализация объекта Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Шаг 2: Сохранение презентации
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Добавление процентной накопленной столбчатой диаграммы на слайд
**Обзор:**  
Теперь мы разместим **процентную накопленную диаграмму** на первом слайде.

`ChartType.PercentsStackedColumn` указывает тип процентной накопленной столбчатой диаграммы.

#### Шаг 1: Инициализация и доступ к слайду
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Шаг 2: Добавление диаграммы на слайд
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Настройка формата чисел оси диаграммы
**Обзор:**  
Для лучшей читаемости мы **изменим формат вертикальной оси**, чтобы отображать проценты.

`IAxis` — интерфейс, представляющий ось диаграммы, позволяющий настраивать формат и масштабирование.

#### Шаг 1: Добавление и доступ к диаграмме
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Шаг 2: Установка пользовательского формата чисел
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Добавление серий и точек данных в диаграмму
**Обзор:**  
Мы заполним диаграмму примерными рядами данных.

#### Шаг 1: Инициализация презентации и диаграммы
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Шаг 2: Добавление серии данных
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Форматирование цвета заливки серии
**Обзор:**  
Присвойте каждой серии отдельный цвет, чтобы диаграмма была легче читаема.

#### Шаг 1: Инициализация и доступ к диаграмме
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Шаг 2: Установка цветов заливки
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Форматирование меток данных
**Обзор:**  
Теперь мы **форматируем подписи данных диаграммы**, чтобы они отображали пользовательский текст.

`IChartDataPoint` представляет отдельную точку данных в ряду диаграммы, а `ITextFrame` содержит текст подписи.

#### Шаг 1: Доступ к сериям диаграммы и точкам данных
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Шаг 2: Настройка меток данных
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Распространённые проблемы и решения
- **Диаграмма пустая:** Убедитесь, что вы добавили хотя бы один ряд данных и точку данных перед сохранением.  
- **Числа оси не показывают проценты:** Не забудьте установить `verticalAxis.setNumberFormatLinkedToSource(false)`; иначе пользовательский формат будет игнорироваться.  
- **Сообщение об оценочной лицензии:** Примените действительный файл лицензии перед созданием объекта `Presentation`, чтобы скрыть баннер оценки.

## Часто задаваемые вопросы

**В: Можно ли использовать этот код с Java 11 или новее?**  
О: Да. Библиотека поддерживает JDK 8+; просто используйте соответствующий классификатор (например, `jdk16` для JDK 16 и выше).

**В: Как экспортировать диаграмму как изображение вместо PPTX?**  
О: Используйте `chart.getImage().save("chart.png", ImageFormat.Png);` после добавления диаграммы на слайд.

**В: Можно ли добавить легенду к накопленной столбчатой диаграмме?**  
О: Конечно. Вызовите `chart.getChartTitle().addTextFrameForOverriding("My Chart");` и при необходимости настройте `chart.getLegend()`.

**В: Что делать, если нужно обновить данные после генерации презентации?**  
О: Вы можете изменить ячейки `ChartDataWorkbook`, а затем вызвать `chart.refresh();`, чтобы отразить изменения.

**В: Работает ли Aspose.Slides на Linux‑серверах?**  
О: Да. Библиотека полностью написана на Java и работает на любой ОС с совместимым JRE.

## Заключение
Следуя этому руководству, вы научились **создавать столбчатую диаграмму с накоплением** в Java с использованием **Aspose Slides Maven dependency**, от настройки окружения до тонкой визуальной стилизации. Экспериментируйте с различными наборами данных, цветами и форматами подписей, чтобы ваши отчёты действительно выделялись.

---

**Последнее обновление:** 2026-07-22  
**Тестировано с:** Aspose.Slides 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как создать сгруппированную столбчатую диаграмму в Java с Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Как задать форматы чисел в точках данных диаграммы с помощью Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Как добавить и настроить диаграммы в презентациях с помощью Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
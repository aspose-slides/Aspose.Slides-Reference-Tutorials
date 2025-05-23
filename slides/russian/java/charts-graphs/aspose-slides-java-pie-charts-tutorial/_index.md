---
"date": "2025-04-17"
"description": "Узнайте, как создавать и настраивать круговые диаграммы с помощью Aspose.Slides для Java. Этот урок охватывает все&#58; от настройки до расширенной настройки."
"title": "Создание круговых диаграмм в Java с помощью Aspose.Slides&#58; Подробное руководство"
"url": "/ru/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание круговых диаграмм с помощью Aspose.Slides для Java: полное руководство

## Введение
Создание динамичных и визуально привлекательных презентаций имеет решающее значение для предоставления эффективной информации. С Aspose.Slides для Java вы можете легко интегрировать сложные диаграммы, такие как круговые диаграммы, в свои слайды, улучшая визуализацию данных без усилий. Это всеобъемлющее руководство проведет вас через процесс создания и настройки круговой диаграммы с помощью Aspose.Slides Java, с легкостью решая распространенные проблемы с презентациями.

**Что вы узнаете:**
- Инициализация презентации и добавление слайдов.
- Создание и настройка круговой диаграммы на слайде.
- Настройка названий диаграмм, меток данных и цветов.
- Оптимизация производительности и эффективное управление ресурсами.
- Интеграция Aspose.Slides в проекты Java с использованием Maven или Gradle.

Давайте начнем с того, что убедимся, что у вас есть все необходимые инструменты и знания для продолжения обучения!

## Предпосылки
Прежде чем приступить к изучению этого руководства, убедитесь, что у вас готовы следующие настройки:

### Требуемые библиотеки, версии и зависимости
- **Aspose.Slides для Java**: Убедитесь, что у вас установлена версия 25.4 или более поздняя.
- **Комплект разработчика Java (JDK)**: Требуется версия 16 или выше.

### Требования к настройке среды
- Среда разработки с установленной и настроенной Java.
- Интегрированная среда разработки (IDE), например IntelliJ IDEA, Eclipse или NetBeans.

### Необходимые знания
- Базовые знания программирования на Java.
- Знакомство с Maven или Gradle для управления зависимостями.

## Настройка Aspose.Slides для Java
Чтобы начать использовать Aspose.Slides в своих проектах Java, вам нужно добавить библиотеку как зависимость. Вот как это можно сделать с помощью различных инструментов сборки:

**Знаток**
Добавьте этот фрагмент в свой `pom.xml` файл:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Градл**
Включите в свой план следующее: `build.gradle` файл:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямая загрузка**
Если вы предпочитаете не использовать инструмент сборки, загрузите последнюю версию с сайта [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

### Этапы получения лицензии
- **Бесплатная пробная версия**: Начните с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides.
- **Временная лицензия**: Получите временную лицензию для длительного использования без ограничений.
- **Покупка**: Рассмотрите возможность покупки, если вам нужен долгосрочный доступ.

**Базовая инициализация и настройка**
Чтобы начать использовать Aspose.Slides, инициализируйте свой проект, создав новый объект презентации:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Руководство по внедрению
Теперь давайте разобьем процесс добавления и настройки круговой диаграммы на удобные для выполнения шаги.

### Инициализировать презентацию и слайд
Начните с настройки новой презентации и доступа к первому слайду. Это ваш холст для создания диаграмм:
```java
import com.aspose.slides.*;

// Создайте новый экземпляр презентации.
Presentation presentation = new Presentation();
// Откройте первый слайд презентации.
islide slides = presentation.getSlides().get_Item(0);
```

### Добавить круговую диаграмму на слайд
Вставьте круговую диаграмму в указанную позицию с набором данных по умолчанию:
```java
import com.aspose.slides.*;

// Добавьте круговую диаграмму в позицию (100, 100) размером (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Установить заголовок диаграммы
Настройте диаграмму, задав и отцентрировав заголовок:
```java
import com.aspose.slides.*;

// Добавьте заголовок к круговой диаграмме.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Настройка меток данных для серий
Для ясности убедитесь, что метки данных отображают значения:
```java
import com.aspose.slides.*;

// Показать значения данных по первой серии.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Подготовить рабочий лист данных диаграммы
Настройте рабочий лист данных диаграммы, очистив существующие серии и категории:
```java
import com.aspose.slides.*;

// Подготовьте рабочую тетрадь с данными диаграммы.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Добавить категории в диаграмму
Определите категории для вашей круговой диаграммы:
```java
import com.aspose.slides.*;

// Добавить новые категории.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Добавить ряды и заполнить точки данных
Создайте ряд и заполните его точками данных:
```java
import com.aspose.slides.*;

// Добавьте новую серию и задайте ее название.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Настройте цвета и границы серии
Повысьте визуальную привлекательность, задав цвета и настроив границы:
```java
import com.aspose.slides.*;

// Установите различные цвета для секторов серии.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Повторите эти действия для других точек данных, используя другие цвета и стили.
```

### Настройка пользовательских меток данных
Настройте метки для каждой точки данных:
```java
import com.aspose.slides.*;

// Настройте пользовательские метки.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Включить линии выноски для этикеток.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Установить угол поворота и сохранить презентацию
Завершите создание круговой диаграммы, установив угол поворота и сохранив презентацию:
```java
import com.aspose.slides.*;

// Установить угол поворота.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Сохраните презентацию в файл.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Заключение
В этом уроке вы узнали, как создавать и настраивать круговые диаграммы с помощью Aspose.Slides для Java. Выполнив эти шаги, вы сможете улучшить свои презентации с помощью визуально привлекательных визуализаций данных. Если у вас есть какие-либо вопросы или вам нужна дополнительная помощь, не стесняйтесь обращаться.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
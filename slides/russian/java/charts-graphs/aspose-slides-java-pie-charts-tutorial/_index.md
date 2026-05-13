---
date: '2026-02-19'
description: Узнайте, как создать круговую диаграмму в Java с помощью Aspose.Slides,
  настроить её цвета, добавить серии диаграммы, работать с листом данных диаграммы
  и задать угол вращения.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Как настроить цвета круговой диаграммы в Java с Aspose.Slides – Полное руководство
url: /ru/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание круговых диаграмм с помощью Aspose.Slides for Java: Полное руководство

## Введение
Создание динамичных и визуально привлекательных презентаций имеет решающее значение для передачи информации. С Aspose.Slides for Java вы можете без труда интегрировать сложные диаграммы, такие как круговые, в свои слайды, **настраивать цвета круговой диаграммы** и улучшать визуализацию данных. Это всестороннее руководство проведёт вас через процесс создания и настройки круговой диаграммы с помощью Aspose.Slides Java, решая типичные задачи презентаций с лёгкостью.

**Что вы узнаете:**
- Инициализацию презентации и добавление слайдов.
- Создание и настройку круговой диаграммы на слайде.
- Установку заголовков диаграмм, подписей данных и **настройку цветов круговой диаграммы**.
- Оптимизацию производительности и эффективное управление ресурсами.
- Интеграцию Aspose.Slides в Java‑проекты с использованием Maven или Gradle.

Начнём с того, что убедимся, что у вас есть все необходимые инструменты и знания для выполнения инструкций!

## Быстрые ответы
- **Какой основной класс для начала работы с презентацией?** `Presentation` из `com.aspose.slides`.
- **Какой метод добавляет круговую диаграмму на слайд?** `addChart(ChartType.Pie, …)`.
- **Как включить разные цвета для каждого сектора?** Установите `setColorVaried(true)` у группы серий.
- **Можно ли вращать круговую диаграмму?** Да, используйте `setRotationAngle(double)` у объекта диаграммы.
- **Нужна ли лицензия для использования в продакшене?** Для коммерческих развертываний требуется лицензия Aspose.Slides.

## Что означает «настроить цвета круговой диаграммы»?
Настройка цветов круговой диаграммы подразумевает назначение различных цветов заливки каждому сектору, улучшая читаемость и визуальное восприятие. В Aspose.Slides это достигается включением разнообразных цветов и последующей установкой сплошных цветов заливки для отдельных точек данных.

## Почему стоит использовать Aspose.Slides for Java для создания круговых диаграмм?
- **Полный контроль** над внешним видом диаграммы без необходимости в Microsoft Office.
- **Кросс‑платформенная** совместимость — работает на Windows, Linux и macOS.
- **Богатый API** для привязки данных, стилизации и экспорта в PPTX, PDF или изображения.
- **Гибкость лицензирования** — начните с бесплатной пробной версии и перейдите на полную при необходимости.

## Предварительные требования
Прежде чем приступить к этому руководству, убедитесь, что у вас готова следующая среда:

### Необходимые библиотеки, версии и зависимости
- **Aspose.Slides for Java**: версия 25.4 или новее.
- **Java Development Kit (JDK)**: версия 16 или выше.

### Требования к настройке окружения
- Среда разработки с установленным и настроенным Java.
- Интегрированная среда разработки (IDE) — IntelliJ IDEA, Eclipse или NetBeans.

### Требования к знаниям
- Базовое понимание программирования на Java.
- Знакомство с Maven или Gradle для управления зависимостями.

## Настройка Aspose.Slides for Java
Чтобы начать использовать Aspose.Slides в ваших Java‑проектах, необходимо добавить библиотеку как зависимость. Вот как это сделать с разными инструментами сборки:

**Maven**  
Добавьте следующий фрагмент в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Включите следующее в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямая загрузка**  
Если вы не используете систему сборки, скачайте последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
- **Бесплатная пробная версия**: начните с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides.  
- **Временная лицензия**: получите временную лицензию для расширенного использования без ограничений.  
- **Покупка**: рассмотрите покупку, если вам нужен долгосрочный доступ.

**Базовая инициализация и настройка**  
Чтобы начать работу с Aspose.Slides, инициализируйте проект, создав новый объект презентации:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Руководство по реализации
Теперь разберём процесс добавления и настройки круговой диаграммы на отдельные шаги.

### Инициализация презентации и слайда
Создайте новую презентацию и получите доступ к первому слайду. Это будет ваш холст для создания диаграмм:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Добавление круговой диаграммы на слайд
Вставьте круговую диаграмму в указанную позицию с набором данных по умолчанию:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Установка заголовка диаграммы
Настройте заголовок диаграммы, установив его и выровняв по центру:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Настройка подписей данных для серии
Убедитесь, что подписи данных отображают значения для лучшей наглядности:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Подготовка листа данных диаграммы
Очистите существующие серии и категории в листе данных диаграммы:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Добавление категорий в диаграмму
Определите категории для вашей круговой диаграммы:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Добавление серии и заполнение точек данных
Создайте серию и заполните её точками данных — здесь мы **добавляем серию диаграммы**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Настройка цветов серии и границ
Повышаем визуальную привлекательность, задавая цвета и настраивая границы — это непосредственно **настраивает цвета круговой диаграммы**:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Настройка пользовательских подписей данных
Точно настройте подписи для каждой точки данных:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Установка угла вращения и сохранение презентации
Завершите работу над круговой диаграммой, **установив угол вращения** и сохранив файл:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Все сектора одного цвета** | `setColorVaried(true)` не вызван | Убедитесь, что включили разнообразные цвета у группы серий. |
| **Подписи данных не отображаются** | Флаг `showValue` отключён | Вызовите `setShowValue(true)` у соответствующего формата подписи. |
| **Вращение не оказывает эффекта** | Используется более старая версия Aspose.Slides | Обновитесь до версии 25.4 или новее. |
| **Исключение лицензии во время выполнения** | Отсутствует или неверный файл лицензии | Загрузите лицензию с помощью `License license = new License(); license.setLicense("Aspose.Slides.lic");` перед созданием `Presentation`. |

## Часто задаваемые вопросы

**В: Как получить лицензию Aspose.Slides для Java?**  
О: Вы можете запросить бесплатную пробную версию на сайте Aspose, а затем приобрести постоянную лицензию. Загрузите её во время выполнения, как показано в таблице «Распространённые проблемы и решения».

**В: Можно ли использовать этот код со старыми версиями JDK?**  
О: API требует JDK 16 или выше; более старые версии не поддерживаются.

**В: Можно ли экспортировать диаграмму как изображение вместо PPTX?**  
О: Да, вызовите `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` после рендеринга.

**В: Что делать, если нужно добавить более одной серии в круговую диаграмму?**  
О: Круговые диаграммы обычно отображают одну серию; для нескольких серий используйте кольцевую (doughnut) диаграмму.

**В: Работает ли библиотека на Linux‑серверах?**  
О: Да — Aspose.Slides for Java независим от платформы и работает на любой ОС с совместимым JDK.

---

**Последнее обновление:** 2026-02-19  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
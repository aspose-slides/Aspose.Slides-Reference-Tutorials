---
date: '2026-01-22'
description: Узнайте, как настроить цвета круговой диаграммы и добавить заголовок
  диаграммы с помощью Aspose.Slides для Java. Включает настройку Maven Aspose Slides
  и способы сохранения презентации в формате pptx.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'Как настроить цвета круговой диаграммы в Java с помощью Aspose.Slides: Полное
  руководство'
url: /ru/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание круговых диаграмм с Aspose.Slides для Java: Как **customize pie chart colors** – Полный учебник

## Введение
Представление историй, основанных на данных, в презентациях становится проще, когда вы можете **customize pie chart colors** чтобы они соответствовали вашему бренду или выделяли ключевые значения. В этом учебнике вы точно увидите, как создать круговую диаграмму, добавить заголовок диаграммы, работать с точками данных круговой диаграммы и точно настроить цвета каждого сектора с помощью Aspose.Slides для Java. К концу вы также узнаете, как **save presentation pptx** и интегрировать библиотеку с Maven Aspose Slides.

**Что вы узнаете**
- Как создавать круговые диаграммы (how to create pie) и настроить проект Java.
- Шаги по добавлению заголовка диаграммы и управлению точками данных круговой диаграммы.
- Методы **customize pie chart colors** для максимального визуального воздействия.
- Конфигурация зависимости Maven Aspose Slides.
- Сохранение конечного файла как PPTX‑презентации.

Начнём!

## Быстрые ответы
- **Как добавить заголовок диаграммы?** Используйте `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **Какой инструмент сборки лучше всего подходит?** Поддерживаются как Maven, так и Gradle;ённым.
- **Можно ли изменить цвета секторов?** Да — установите `setColorVaried(true)` и настройте.pptx", SaveFormat.Pptx)`.
- **Н IDE, NetBeans.
- Базовые знания Java и знакомство с Maven или Gradle.

## Настройка Aspose.Slides для Java
Чтобы начать использовать Aspose.Slides, добавьте библиотеку в ваш проект.

**Maven** (maven aspose slides)  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямое скачивание**  
Если вы предпочитаете не использовать инструмент сборки, скачайте последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
- **Free Trial** – начните экспериментировать без лицензии.
- **Temporary License** – продлить период пробной версии.
- **Purchase** – получить полную лицензию для продакшн‑развертываний.

### Базовая инициализация
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Руководство по реализации
Ниже пошаговое руководство, сохраняющее код точно таким, как ожидает оригинальная библиотека.

### Шаг 1: Инициализация Presentation и Slide
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Шаг 2: Добавление круговой диаграммы на слайд
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Шаг 3: Добавление заголовка диаграммы
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Шаг 4: Показ меток данных для первой серии
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Шаг 5: Подготовка листа данных диаграммы
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Шаг 6: Добавление категорий (точек данных круговой диаграммы)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Шаг 7: Добавление серии и заполнение точек данных
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Шаг 8: **Customize Pie Chart Colors** – Основная часть этого учебника
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Шаг 9: Настройка пользовательских меток данных
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Шаг 10: Установка угла вращения и **Save Presentation PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Распространённые проблемы и устранение неполадок
- **Missing colors after export** – Убедитесь, что `setColorVaried(true)` вызывается до изменения отдельных точек данных.
- **Data points not showing** – Проверьте, что категории и серии очищены перед добавлением новых (см. Шаг 5).
- **License not applied** – Загрузите файл лицензии перед созданием объекта `Presentation`, чтобы избежать водяных знаков пробной версии.

## Часто задаваемые вопросы

**Q: Можно ли использовать этот код со старыми версиями JDK?**  
A: Библиотека требует JDK 16 или выше; старые версии не поддерживаются.

**Q: Как изменить заголовок диаграммы после создания?**  
A: Вызовите `chart.getChartTitle().addTextFrameForOverriding("New Title")` и при необходимости отрегулируйте формат текста.

**Q: Можно ли экспортировать в форматы, отличные от PPTX?**  
A: Да — Aspose.Slides поддерживает PDF, ODP и несколько форматов изображений через перечисление `SaveFormat`.

**Q: Что если я хочу анимировать сектора круговой диаграммы?**  
A: Используйте API `SlideShow` для добавления переходов слайдов или анимаций фигур после создания диаграммы.

**Q: Включает ли зависимость Maven все транзитивные библиотеки?**  
A: Артефакт Maven Aspose Slides автоматически подтягивает необходимые зависимости; дополнительные шаги не требуются.

## Заключение
Теперь у вас есть полноценный, готовый к продакшну пример, который демонстрирует **how to customize pie chart colors**, добавляет заголовок диаграммы, работает с точками данных круговой диаграммы и **save presentation pptx** с использованием Aspose.Slides для Java. Не стесняйтесь экспериментировать с различными цветовыми палитрами, наборами данных и углами вращения, чтобы соответствовать стилю вашего бренда.

---

**Последнее обновление:** 2026-01-22  
**Тестировано с:** Aspose.Slides 25.4 (JDK 16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Диаграмма с несколькими категориями в слайдах Java
linktitle: Диаграмма с несколькими категориями в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Создавайте диаграммы с несколькими категориями в слайдах Java, используя Aspose.Slides для Java. Пошаговое руководство с исходным кодом для впечатляющей визуализации данных в презентациях.
weight: 20
url: /ru/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Диаграмма с несколькими категориями в слайдах Java


## Введение в многокатегорийную диаграмму в слайдах Java с помощью Aspose.Slides

В этом уроке мы узнаем, как создать диаграмму с несколькими категориями в слайдах Java с помощью API Aspose.Slides для Java. В этом руководстве представлены пошаговые инструкции вместе с исходным кодом, которые помогут вам создать кластеризованную столбчатую диаграмму с несколькими категориями и сериями.

## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашей среде разработки Java.

## Шаг 1: Настройка среды
Сначала импортируйте необходимые классы и создайте новый объект Presentation для работы со слайдами.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2. Добавление слайда и диаграммы
Затем создайте слайд и добавьте к нему гистограмму с кластеризацией.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Шаг 3: Очистка существующих данных
Удалите все существующие данные из диаграммы.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Шаг 4. Настройка категорий данных
Теперь давайте настроим категории данных для диаграммы. Мы создадим несколько категорий и сгруппируем их.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Добавляйте категории и группируйте их
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Шаг 5: Добавление серии
Теперь давайте добавим на диаграмму серию вместе с точками данных.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Шаг 6: Сохранение презентации
Наконец, сохраните презентацию с диаграммой.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали диаграмму с несколькими категориями на слайде Java с помощью Aspose.Slides. Вы можете дополнительно настроить эту диаграмму в соответствии с вашими конкретными требованиями.

## Полный исходный код для диаграммы с несколькими категориями в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Добавление серии
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Сохранить презентацию с диаграммой
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы узнали, как создать диаграмму с несколькими категориями в слайдах Java с помощью API Aspose.Slides для Java. Мы прошли пошаговое руководство с исходным кодом для создания кластеризованной столбчатой диаграммы с несколькими категориями и сериями.

## Часто задаваемые вопросы

### Как настроить внешний вид диаграммы?

Вы можете настроить внешний вид диаграммы, изменив такие свойства, как цвета, шрифты и стили. Подробные параметры настройки см. в документации Aspose.Slides.

### Могу ли я добавить в диаграмму больше серий?

Да, вы можете добавить дополнительные серии в диаграмму, выполнив процесс, аналогичный показанному в шаге 5.

### Как изменить тип диаграммы?

 Чтобы изменить тип диаграммы, замените`ChartType.ClusteredColumn` с нужным типом диаграммы при добавлении диаграммы на шаге 2.

### Как добавить заголовок к диаграмме?

 Вы можете добавить заголовок к диаграмме, используя`ch.getChartTitle().getTextFrame().setText("Chart Title");` метод.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

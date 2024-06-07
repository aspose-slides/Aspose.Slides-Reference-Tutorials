---
title: Обычные диаграммы в слайдах Java
linktitle: Обычные диаграммы в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Создавайте обычные диаграммы в слайдах Java с помощью Aspose.Slides для Java. Пошаговое руководство и исходный код для создания, настройки и сохранения диаграмм в презентациях PowerPoint.
type: docs
weight: 21
url: /ru/java/chart-data-manipulation/normal-charts-java-slides/
---

## Введение в обычные диаграммы в слайдах Java

В этом уроке мы рассмотрим процесс создания обычных диаграмм в Java Slides с использованием API Aspose.Slides для Java. Мы будем использовать пошаговые инструкции вместе с исходным кодом, чтобы продемонстрировать, как создать гистограмму с кластерами в презентации PowerPoint.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Установлен Aspose.Slides для Java API.
2. Настроена среда разработки Java.
3. Базовые знания Java-программирования.

## Шаг 1: Настройка проекта

Убедитесь, что у вас есть каталог для вашего проекта. Назовем его «Каталог ваших документов», как указано в коде. Вы можете заменить это фактическим путем к каталогу вашего проекта.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если он еще не существует.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Шаг 2: Создание презентации

Теперь давайте создадим презентацию PowerPoint и получим доступ к ее первому слайду.

```java
// Создать класс презентации, представляющий файл PPTX.
Presentation pres = new Presentation();
// Доступ к первому слайду
ISlide sld = pres.getSlides().get_Item(0);
```

## Шаг 3. Добавление диаграммы

Мы добавим на слайд кластеризованную столбчатую диаграмму и зададим ее заголовок.

```java
// Добавить диаграмму с данными по умолчанию
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Название диаграммы настроек
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Шаг 4: Настройка данных диаграммы

Далее мы установим данные диаграммы, определив серии и категории.

```java
// Установите для первой серии значение «Показать значения».
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;

// Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Добавляем новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Шаг 5. Заполнение данных серии

Теперь давайте заполним точки данных ряда для диаграммы.

```java
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Заполнение данных серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

//Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);

// Заполнение данных серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

//Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Шаг 6. Настройка ярлыков

Давайте настроим метки данных для серии диаграмм.

```java
// На первом ярлыке будет указано название категории.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Показать значение третьей метки с названием серии и разделителем.
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Шаг 7: Сохранение презентации

Наконец, сохраните презентацию с диаграммой в каталоге вашего проекта.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали кластеризованную столбчатую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете настроить эту диаграмму в соответствии с вашими требованиями.

## Полный исходный код для обычных диаграмм в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если он еще не существует.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Создать класс презентации, представляющий файл PPTX.
Presentation pres = new Presentation();
// Доступ к первому слайду
ISlide sld = pres.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Название диаграммы настроек
// Chart.getChartTitle().getTextFrameForOverriding().setText("Пример заголовка");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Установите для первой серии значение «Показать значения».
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;
// Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Добавляем новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Теперь заполняем данные серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
//Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
//Теперь заполняем данные серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
//Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// На первом ярлыке будет показано название категории.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Показать значение для третьего ярлыка
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Сохранить презентацию с диаграммой
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Заключение

В этом уроке мы узнали, как создавать обычные диаграммы в Java Slides с использованием API Aspose.Slides для Java. Мы рассмотрели пошаговое руководство с исходным кодом для создания гистограммы с кластерами в презентации PowerPoint.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

 Чтобы изменить тип диаграммы, измените`ChartType` параметр при добавлении диаграммы с помощью`sld.getShapes().addChart()`. Вы можете выбирать из различных типов диаграмм, доступных в Aspose.Slides.

### Могу ли я изменить цвета серии диаграмм?

 Да, вы можете изменить цвета серий диаграмм, задав цвет заливки для каждой серии с помощью`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Как добавить на диаграмму дополнительные категории или серии?

 Вы можете добавить на диаграмму дополнительные категории или серии, добавив новые точки данных и метки с помощью кнопки`chart.getChartData().getCategories().add()` и`chart.getChartData().getSeries().add()` методы.

### Как я могу настроить заголовок диаграммы дальше?

 Вы можете дополнительно настроить заголовок диаграммы, изменив свойства`chart.getChartTitle()` такие как выравнивание текста, размер шрифта и цвет.

### Как сохранить диаграмму в другом формате файла?

 Чтобы сохранить диаграмму в другом формате файла, измените`SaveFormat` параметр в`pres.save()`метод в нужный формат (например, PDF, PNG, JPEG).
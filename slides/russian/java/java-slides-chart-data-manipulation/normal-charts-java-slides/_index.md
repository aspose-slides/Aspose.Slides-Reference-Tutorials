---
"description": "Создавайте обычные диаграммы в слайдах Java с помощью Aspose.Slides для Java. Пошаговое руководство и исходный код для создания, настройки и сохранения диаграмм в презентациях PowerPoint."
"linktitle": "Обычные диаграммы в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Обычные диаграммы в Java Slides"
"url": "/ru/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Обычные диаграммы в Java Slides


## Введение в обычные диаграммы в Java Slides

В этом уроке мы рассмотрим процесс создания обычных диаграмм в Java Slides с использованием API Aspose.Slides for Java. Мы будем использовать пошаговые инструкции вместе с исходным кодом, чтобы продемонстрировать, как создать кластеризованную столбчатую диаграмму в презентации PowerPoint.

## Предпосылки

Прежде чем начать, убедитесь, что выполнены следующие предварительные условия:

1. Установлен API Aspose.Slides для Java.
2. Настроена среда разработки Java.
3. Базовые знания программирования на Java.

## Шаг 1: Настройка проекта

Убедитесь, что у вас есть каталог для вашего проекта. Давайте назовем его «Ваш каталог документов», как указано в коде. Вы можете заменить его фактическим путем к каталогу вашего проекта.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если его еще нет.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Шаг 2: Создание презентации

Теперь давайте создадим презентацию PowerPoint и откроем ее первый слайд.

```java
// Создать экземпляр класса Presentation, представляющего файл PPTX
Presentation pres = new Presentation();
// Доступ к первому слайду
ISlide sld = pres.getSlides().get_Item(0);
```

## Шаг 3: Добавление диаграммы

Мы добавим на слайд кластеризованную столбчатую диаграмму и зададим ее заголовок.

```java
// Добавить диаграмму с данными по умолчанию
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Настройка диаграммы Название
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Шаг 4: Настройка данных диаграммы

Далее мы настроим данные диаграммы, определив серии и категории.

```java
// Установить первую серию для показа значений
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;

// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Добавление новых серий
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Шаг 5: Заполнение рядов данных

Теперь давайте заполним ряд точек данных для диаграммы.

```java
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Заполнение рядов данных
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);

// Заполнение рядов данных
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Шаг 6: Настройка этикеток

Давайте настроим метки данных для серии диаграмм.

```java
// Первая метка будет отображать название категории.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Показать значение для третьей метки с названием серии и разделителем
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

Вот и все! Вы успешно создали кластеризованную столбчатую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете настроить эту диаграмму в дальнейшем в соответствии с вашими требованиями.

## Полный исходный код для обычных диаграмм в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если его еще нет.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Создать экземпляр класса Presentation, представляющего файл PPTX
Presentation pres = new Presentation();
// Доступ к первому слайду
ISlide sld = pres.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Настройка диаграммы Название
// Chart.getChartTitle().getTextFrameForOverriding().setText("Заголовок образца");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Установить первую серию для показа значений
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;
// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Добавление новых серий
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Сейчас заполняем данные серий
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Сейчас заполняем данные серий
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Установка цвета заливки для серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Первая метка будет отображать название категории.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Показать значение для третьей метки
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Сохранить презентацию с диаграммой
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Заключение

В этом уроке мы узнали, как создавать обычные диаграммы в Java Slides с помощью API Aspose.Slides for Java. Мы прошли пошаговое руководство с исходным кодом для создания кластеризованной столбчатой диаграммы в презентации PowerPoint.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

Чтобы изменить тип диаграммы, измените `ChartType` параметр при добавлении диаграммы с использованием `sld.getShapes().addChart()`. Вы можете выбрать один из различных типов диаграмм, доступных в Aspose.Slides.

### Могу ли я изменить цвета серии диаграмм?

Да, вы можете изменить цвета серий диаграмм, установив цвет заливки для каждой серии с помощью `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Как добавить больше категорий или серий в диаграмму?

Вы можете добавить больше категорий или рядов в диаграмму, добавив новые точки данных и метки с помощью `chart.getChartData().getCategories().add()` и `chart.getChartData().getSeries().add()` методы.

### Как можно дополнительно настроить заголовок диаграммы?

Вы можете дополнительно настроить заголовок диаграммы, изменив свойства `chart.getChartTitle()` такие как выравнивание текста, размер шрифта и цвет.

### Как сохранить диаграмму в другом формате файла?

Чтобы сохранить диаграмму в другом формате файла, измените `SaveFormat` параметр в `pres.save()` метод в нужный формат (например, PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
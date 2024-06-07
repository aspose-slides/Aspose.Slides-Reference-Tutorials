---
title: Установите знак процента для меток данных в слайдах Java
linktitle: Установите знак процента для меток данных в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как устанавливать метки данных со знаками процента в презентациях PowerPoint с помощью Aspose.Slides для Java. Создавайте интересные диаграммы с помощью пошаговых инструкций и исходного кода.
type: docs
weight: 17
url: /ru/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Введение в установку меток данных в процентах в Aspose.Slides для Java

В этом руководстве мы покажем вам процесс установки меток данных со знаком процента с помощью Aspose.Slides для Java. Мы создадим презентацию PowerPoint с многоуровневой гистограммой и настроим метки данных для отображения процентов.

## Предварительные условия

 Прежде чем начать, убедитесь, что в ваш проект добавлена библиотека Aspose.Slides for Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).

## Шаг 1. Создайте новую презентацию

Сначала мы создаем новую презентацию PowerPoint с помощью Aspose.Slides.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 2. Добавьте слайд и диаграмму

Затем мы добавляем в презентацию слайд и гистограмму с накоплением.

```java
// Получить ссылку на слайд
ISlide slide = presentation.getSlides().get_Item(0);

// Добавление диаграммы PercentsStackedColumn на слайд
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Шаг 3. Настройка формата номера оси

Чтобы отображать проценты, нам необходимо настроить числовой формат для вертикальной оси диаграммы.

```java
//Установите для NumberFormatLinkedToSource значение false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Шаг 4. Добавьте данные диаграммы

Мы добавляем данные на диаграмму, создавая ряды и точки данных. В этом примере мы добавляем две серии с соответствующими точками данных.

```java
// Получение листа данных диаграммы
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Добавить новую серию
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Добавить новую серию
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Шаг 5. Настройте метки данных

Теперь давайте настроим внешний вид меток данных.

```java
// Установка свойств LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Шаг 6. Сохраните презентацию

Наконец, мы сохраняем презентацию в файл PowerPoint.

```java
// Записать презентацию на диск
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали презентацию PowerPoint с многоуровневой гистограммой и настроили метки данных для отображения процентов с помощью Aspose.Slides для Java.

## Полный исходный код для набора меток данных. Знак процента в слайдах Java.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
// Получить ссылку на слайд
ISlide slide = presentation.getSlides().get_Item(0);
// Добавление диаграммы PercentsStackedColumn на слайд
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
//Установите для NumberFormatLinkedToSource значение false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Получение листа данных диаграммы
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Добавить новую серию
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Установка цвета заливки серии
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Установка свойств LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Добавить новую серию
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Настройка типа и цвета заливки
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Записать презентацию на диск
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Заключение

Следуя этому руководству, вы научились создавать привлекательные презентации с метками данных в процентах, что может быть особенно полезно для эффективной передачи информации в бизнес-отчетах, учебных материалах и т. д.

## Часто задаваемые вопросы

### Как изменить цвета серии диаграмм?

 Вы можете изменить цвет заливки серии диаграмм, используя`setFill` метод, как показано в примере.

### Могу ли я настроить размер шрифта меток данных?

 Да, вы можете настроить размер шрифта меток данных, установив`setFontHeight` свойство, как показано в коде.

### Как добавить на диаграмму больше серий?

 Вы можете добавить дополнительные серии на диаграмму, используя`add` метод на`IChartSeriesCollection` объект.

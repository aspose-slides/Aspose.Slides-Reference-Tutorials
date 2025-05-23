---
"description": "Узнайте, как устанавливать метки данных с процентными знаками в презентациях PowerPoint с помощью Aspose.Slides для Java. Создавайте привлекательные диаграммы с пошаговыми инструкциями и исходным кодом."
"linktitle": "Установить метки данных Процентный знак в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Установить метки данных Процентный знак в слайдах Java"
"url": "/ru/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Установить метки данных Процентный знак в слайдах Java


## Введение в установку меток данных процентного знака в Aspose.Slides для Java

В этом руководстве мы проведем вас через процесс настройки меток данных со знаком процента с помощью Aspose.Slides для Java. Мы создадим презентацию PowerPoint с диаграммой с накоплением столбцов и настроим метки данных для отображения процентов.

## Предпосылки

Прежде чем начать, убедитесь, что в ваш проект добавлена библиотека Aspose.Slides for Java. Вы можете загрузить ее с [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Создайте новую презентацию

Сначала мы создаем новую презентацию PowerPoint с помощью Aspose.Slides.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 2: Добавьте слайд и диаграмму

Далее мы добавляем в презентацию слайд и столбчатую диаграмму с накоплением.

```java
// Получить ссылку на слайд
ISlide slide = presentation.getSlides().get_Item(0);

// Добавить диаграмму PercentsStackedColumn на слайд
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Шаг 3: Настройте формат номера оси

Для отображения процентов нам необходимо настроить числовой формат для вертикальной оси диаграммы.

```java
// Установите NumberFormatLinkedToSource на false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Шаг 4: Добавьте данные диаграммы

Мы добавляем данные в диаграмму, создавая ряды и точки данных. В этом примере мы добавляем два ряда с соответствующими им точками данных.

```java
// Получение рабочего листа данных диаграммы
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

## Шаг 5: Настройте метки данных

Теперь давайте настроим внешний вид меток данных.

```java
// Настройка свойств LabelFormat
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

## Шаг 6: Сохраните презентацию

Наконец, мы сохраняем презентацию в файл PowerPoint.

```java
// Записать презентацию на диск
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали презентацию PowerPoint с составной столбчатой диаграммой и настроили подписи данных для отображения процентов с помощью Aspose.Slides для Java.

## Полный исходный код для установки меток данных Процентный знак в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
// Получить ссылку на слайд
ISlide slide = presentation.getSlides().get_Item(0);
// Добавить диаграмму PercentsStackedColumn на слайд
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Установите NumberFormatLinkedToSource на false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Получение рабочего листа данных диаграммы
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
// Настройка свойств LabelFormat
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

Следуя этому руководству, вы узнали, как создавать увлекательные презентации с метками данных на основе процентов, которые могут быть особенно полезны для эффективной передачи информации в деловых отчетах, образовательных материалах и т. д.

## Часто задаваемые вопросы

### Как изменить цвета серии диаграмм?

Вы можете изменить цвет заливки ряда диаграмм с помощью `setFill` метод, как показано в примере.

### Могу ли я настроить размер шрифта меток данных?

Да, вы можете настроить размер шрифта меток данных, установив `setFontHeight` свойство, как показано в коде.

### Как добавить больше серий в диаграмму?

Вы можете добавить дополнительные ряды в диаграмму, используя `add` метод на `IChartSeriesCollection` объект.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
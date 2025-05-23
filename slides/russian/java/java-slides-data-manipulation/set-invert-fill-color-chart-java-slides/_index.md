---
"description": "Узнайте, как установить инвертированные цвета заливки для диаграмм Java Slides с помощью Aspose.Slides. Улучшите визуализацию диаграмм с помощью этого пошагового руководства и исходного кода."
"linktitle": "Установить инвертировать цвет заливки диаграммы в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Установить инвертировать цвет заливки диаграммы в Java Slides"
"url": "/ru/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Установить инвертировать цвет заливки диаграммы в Java Slides


## Введение в установку инвертированной цветовой заливки диаграммы в Java Slides

В этом уроке мы покажем, как установить инвертированный цвет заливки для диаграммы в Java Slides с помощью Aspose.Slides для Java. Инвертирование цвета заливки — полезная функция, когда вы хотите выделить отрицательные значения в диаграмме определенным цветом. Мы предоставим пошаговые инструкции и исходный код для достижения этой цели.

## Предпосылки

Прежде чем начать, убедитесь, что выполнены следующие предварительные условия:

1. Установлена библиотека Aspose.Slides для Java.
2. Настроена среда разработки Java.

## Шаг 1: Создайте презентацию

Сначала нам нужно создать презентацию, в которую мы добавим нашу диаграмму. Вы можете использовать следующий код для создания презентации:

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2: Добавьте диаграмму

Далее мы добавим в презентацию кластеризованную столбчатую диаграмму. Вот как это можно сделать:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Шаг 3: Настройка данных диаграммы

Теперь давайте настроим данные диаграммы, включая серии и категории:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Добавление новых серий и категорий
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Шаг 4: Заполнение рядов данных

Теперь давайте заполним ряд данных для диаграммы:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Шаг 5: Установите инвертированный цвет заливки

Чтобы установить инвертированный цвет заливки для ряда диаграмм, можно использовать следующий код:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

В приведенном выше коде мы задаем серию для инвертирования цвета заливки для отрицательных значений и указываем цвет для инвертированной заливки.

## Шаг 6: Сохраните презентацию

Наконец, сохраните презентацию с диаграммой:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для установки инвертированной цветовой диаграммы заливки в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Добавление новых серий и категорий
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Возьмем первую серию диаграмм и заполним ряд данными.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы показали вам, как установить инвертированный цвет заливки для диаграммы в Java Slides с помощью Aspose.Slides для Java. Эта функция позволяет вам выделять отрицательные значения в ваших диаграммах определенным цветом, делая ваши данные визуально более информативными.

## Часто задаваемые вопросы

В этом разделе мы рассмотрим некоторые распространенные вопросы, связанные с настройкой инвертированного цвета заливки для диаграммы в Java Slides с помощью Aspose.Slides для Java.

### Как установить Aspose.Slides для Java?

Вы можете установить Aspose.Slides для Java, включив файлы JAR Aspose.Slides в свой проект Java. Вы можете загрузить библиотеку с [Страница загрузки Aspose.Slides для Java](https://releases.aspose.com/slides/java/). Следуйте инструкциям по установке, приведенным в документации для вашей конкретной среды разработки.

### Могу ли я настроить цвет инвертированной заливки в серии диаграмм?

Да, вы можете настроить цвет инвертированной заливки в серии диаграмм. В приведенном примере кода `series.getInvertedSolidFillColor().setColor(Color.RED)` line задает красный цвет для инвертированной заливки. Вы можете заменить `Color.RED` с любым другим цветом по вашему выбору.

### Как изменить тип диаграммы в Aspose.Slides для Java?

Вы можете изменить тип диаграммы, изменив `ChartType` параметр при добавлении диаграммы в презентацию. В примере кода мы использовали `ChartType.ClusteredColumn`. Вы можете изучить другие типы диаграмм, такие как линейные диаграммы, столбчатые диаграммы, круговые диаграммы и т. д., указав соответствующий `ChartType` значение перечисления.

### Как добавить несколько рядов данных на диаграмму?

Чтобы добавить несколько рядов данных на диаграмму, вы можете использовать `chart.getChartData().getSeries().add(...)` метод для каждой серии, которую вы хотите добавить. Обязательно укажите соответствующие точки данных и метки для каждой серии, чтобы заполнить вашу диаграмму несколькими сериями.

### Есть ли способ настроить другие аспекты внешнего вида диаграммы?

Да, вы можете настроить различные аспекты внешнего вида диаграммы, включая метки осей, заголовки, легенды и многое другое, используя Aspose.Slides для Java. Подробное руководство по настройке элементов и внешнего вида диаграммы см. в документации.

### Могу ли я сохранить диаграмму в разных форматах?

Да, вы можете сохранить диаграмму в разных форматах с помощью Aspose.Slides for Java. В приведенном примере кода мы сохранили презентацию как файл PPTX. Вы можете использовать разные `SaveFormat` возможность сохранения в других форматах, таких как PDF, PNG или SVG, в зависимости от ваших требований.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
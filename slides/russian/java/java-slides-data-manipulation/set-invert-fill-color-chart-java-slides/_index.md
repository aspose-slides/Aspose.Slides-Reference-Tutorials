---
title: Установить инвертированную диаграмму цветов заливки в слайдах Java
linktitle: Установить инвертированную диаграмму цветов заливки в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как установить инвертированные цвета заливки для диаграмм Java Slides с помощью Aspose.Slides. Улучшите визуализацию диаграмм с помощью этого пошагового руководства и исходного кода.
weight: 22
url: /ru/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Установить инвертированную диаграмму цветов заливки в слайдах Java


## Введение в настройку инвертированной цветовой диаграммы заливки в слайдах Java

В этом уроке мы покажем, как установить инвертированный цвет заливки для диаграммы в Java Slides с помощью Aspose.Slides для Java. Инвертирование цвета заливки — полезная функция, если вы хотите выделить отрицательные значения на диаграмме определенным цветом. Мы предоставим пошаговые инструкции и исходный код для достижения этой цели.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Установлена библиотека Aspose.Slides для Java.
2. Настроена среда разработки Java.

## Шаг 1. Создайте презентацию

Сначала нам нужно создать презентацию, в которую можно добавить нашу диаграмму. Для создания презентации вы можете использовать следующий код:

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2. Добавьте диаграмму

Далее мы добавим в презентацию кластеризованную столбчатую диаграмму. Вот как вы можете это сделать:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Шаг 3. Настройка данных диаграммы

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

## Шаг 4. Заполнение данных серии

Теперь давайте заполним данные серии для диаграммы:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Шаг 5. Установите инвертированный цвет заливки

Чтобы установить инвертированный цвет заливки для серии диаграмм, вы можете использовать следующий код:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

В приведенном выше коде мы устанавливаем для серии инвертирование цвета заливки для отрицательных значений и указываем цвет инвертированной заливки.

## Шаг 6. Сохраните презентацию

Наконец, сохраните презентацию с диаграммой:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для установки диаграммы цветов инвертированной заливки в слайдах Java

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
// Возьмите первую серию диаграмм и заполните данные серии.
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

В этом уроке мы показали вам, как установить инвертированный цвет заливки для диаграммы в Java Slides с помощью Aspose.Slides для Java. Эта функция позволяет выделять отрицательные значения на диаграммах определенным цветом, делая ваши данные более визуально информативными.

## Часто задаваемые вопросы

В этом разделе мы рассмотрим некоторые распространенные вопросы, связанные с настройкой инвертированного цвета заливки для диаграммы в Java Slides с использованием Aspose.Slides для Java.

### Как установить Aspose.Slides для Java?

 Вы можете установить Aspose.Slides для Java, включив файлы JAR Aspose.Slides в свой проект Java. Вы можете скачать библиотеку с сайта[Страница загрузки Aspose.Slides для Java](https://releases.aspose.com/slides/java/). Следуйте инструкциям по установке, приведенным в документации для вашей конкретной среды разработки.

### Могу ли я настроить цвет инвертированной заливки в серии диаграмм?

Да, вы можете настроить цвет инвертированной заливки в серии диаграмм. В приведенном примере кода`series.getInvertedSolidFillColor().setColor(Color.RED)` line устанавливает красный цвет для инвертированной заливки. Вы можете заменить`Color.RED` с любым другим цветом по вашему выбору.

### Как изменить тип диаграммы в Aspose.Slides для Java?

 Вы можете изменить тип диаграммы, изменив`ChartType` параметр при добавлении диаграммы в презентацию. В примере кода мы использовали`ChartType.ClusteredColumn` . Вы можете изучить другие типы диаграмм, такие как линейные диаграммы, гистограммы, круговые диаграммы и т. д., указав соответствующие`ChartType` значение перечисления.

### Как добавить на диаграмму несколько рядов данных?

 Чтобы добавить несколько рядов данных на диаграмму, вы можете использовать`chart.getChartData().getSeries().add(...)` метод для каждой серии, которую вы хотите добавить. Обязательно укажите соответствующие точки данных и метки для каждой серии, чтобы заполнить диаграмму несколькими сериями.

### Есть ли способ настроить другие аспекты внешнего вида диаграммы?

Да, вы можете настроить различные аспекты внешнего вида диаграммы, включая метки осей, заголовки, легенды и многое другое, используя Aspose.Slides для Java. Подробные инструкции по настройке элементов и внешнего вида диаграммы см. в документации.

### Могу ли я сохранить диаграмму в разных форматах?

 Да, вы можете сохранить диаграмму в разных форматах, используя Aspose.Slides для Java. В приведенном примере кода мы сохранили презентацию как файл PPTX. Вы можете использовать разные`SaveFormat` варианты сохранения в других форматах, таких как PDF, PNG или SVG, в зависимости от ваших требований.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

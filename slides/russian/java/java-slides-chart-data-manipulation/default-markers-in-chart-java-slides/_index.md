---
"description": "Узнайте, как создавать Java Slides с маркерами по умолчанию в диаграммах с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом."
"linktitle": "Маркеры по умолчанию в диаграмме в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Маркеры по умолчанию в диаграмме в Java Slides"
"url": "/ru/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Маркеры по умолчанию в диаграмме в Java Slides


## Введение в маркеры по умолчанию в диаграммах в Java Slides

В этом уроке мы рассмотрим, как создать диаграмму с маркерами по умолчанию с помощью Aspose.Slides для Java. Маркеры по умолчанию — это символы или фигуры, добавляемые к точкам данных на диаграмме для их выделения. Мы создадим линейную диаграмму с маркерами для визуализации данных.

## Предпосылки

Прежде чем начать, убедитесь, что в вашем проекте Java установлена и настроена библиотека Aspose.Slides for Java.

## Шаг 1: Создайте презентацию

Сначала создадим презентацию и добавим в нее слайд. Затем добавим на слайд диаграмму.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Шаг 2: Добавьте линейную диаграмму с маркерами

Теперь добавим на слайд линейную диаграмму с маркерами. Также удалим все данные по умолчанию из диаграммы.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Шаг 3: Заполнение диаграммы данными

Заполним диаграмму образцами данных. В этом примере мы создадим две серии с точками данных и категориями.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Серия 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Серия 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Заполнение рядов данных
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Шаг 4: Настройте диаграмму

Вы можете дополнительно настроить диаграмму, например, добавить легенду и изменить ее внешний вид.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Шаг 5: Сохраните презентацию

Наконец, сохраните презентацию с диаграммой в желаемом месте.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Вот и все! Вы создали линейную диаграмму с маркерами по умолчанию с помощью Aspose.Slides для Java.

## Полный исходный код для маркеров по умолчанию в диаграммах в Java Slides

```java
        // Путь к каталогу документов.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Возьмите вторую серию диаграмм
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Сейчас заполняем данные серий
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Заключение

В этом всеобъемлющем руководстве вы узнали, как создавать Java Slides с маркерами по умолчанию в диаграммах с помощью Aspose.Slides для Java. Мы рассмотрели весь процесс, от настройки презентации до настройки внешнего вида диаграммы и сохранения результата.

## Часто задаваемые вопросы

### Как изменить символы маркера?

Вы можете настроить символы маркера, установив стиль маркера для каждой точки данных. Используйте `IDataPoint.setMarkerStyle()` для изменения символа маркера.

### Как настроить цвета диаграммы?

Чтобы изменить цвета диаграммы, вы можете использовать `IChartSeriesFormat` и `IShapeFillFormat` интерфейсы для настройки свойств заливки и линий.

### Могу ли я добавлять метки к точкам данных?

Да, вы можете добавлять метки к точкам данных с помощью `IDataPoint.getLabel()` метод и настройте их по мере необходимости.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
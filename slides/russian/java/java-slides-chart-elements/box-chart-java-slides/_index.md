---
"description": "Узнайте, как создавать диаграммы-ящики в презентациях Java с помощью Aspose.Slides. Пошаговое руководство и исходный код включены для эффективной визуализации данных."
"linktitle": "Диаграмма в формате Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Диаграмма в формате Java Slides"
"url": "/ru/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Диаграмма в формате Java Slides


## Введение в блочную диаграмму в Aspose.Slides для Java

В этом уроке мы проведем вас через процесс создания диаграммы ящиков с помощью Aspose.Slides для Java. Диаграммы ящиков полезны для визуализации статистических данных с различными квартилями и выбросами. Мы предоставим пошаговые инструкции вместе с исходным кодом, чтобы помочь вам начать работу.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлена и настроена библиотека Aspose.Slides для Java.
- Настроена среда разработки Java.

## Шаг 1: Инициализация презентации

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

На этом этапе мы инициализируем объект презентации, используя путь к существующему файлу PowerPoint (в данном примере «test.pptx»).

## Шаг 2: Создание диаграммы-ящика

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

На этом этапе мы создаем форму Box Chart на первом слайде презентации. Мы также очищаем все существующие категории и серии из диаграммы.

## Шаг 3: Определите категории

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

На этом этапе мы определяем категории для диаграммы Box Chart. Мы используем `IChartDataWorkbook` добавлять категории и маркировать их соответствующим образом.

## Шаг 4: Создание серии

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Здесь мы создаем ряд BoxAndWhisker для диаграммы и настраиваем различные параметры, такие как метод квартилей, средняя линия, средние маркеры, внутренние точки и точки выбросов.

## Шаг 5: Добавьте точки данных

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

На этом этапе мы добавляем точки данных в ряд BoxAndWhisker. Эти точки данных представляют статистические данные для диаграммы.

## Шаг 6: Сохраните презентацию

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Наконец, мы сохраняем презентацию с блочной диаграммой в новый файл PowerPoint с именем «BoxAndWhisker.pptx».

Поздравляем! Вы успешно создали диаграмму Box Chart с помощью Aspose.Slides для Java. Вы можете дополнительно настроить диаграмму, настроив различные свойства и добавив больше точек данных по мере необходимости.

## Полный исходный код для диаграммы в Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы узнали, как создать диаграмму Box Chart с помощью Aspose.Slides для Java. Диаграммы Box Chart являются ценными инструментами для визуализации статистических данных, включая квартили и выбросы. Мы предоставили пошаговое руководство вместе с исходным кодом, чтобы помочь вам начать создавать диаграммы Box Chart в ваших приложениях Java.

## Часто задаваемые вопросы

### Как изменить внешний вид диаграммы?

Вы можете настроить внешний вид диаграммы Box Chart, изменив такие свойства, как стили линий, цвета и шрифты. Обратитесь к документации Aspose.Slides for Java для получения подробной информации о настройке диаграммы.

### Могу ли я добавить дополнительные ряды данных в блочную диаграмму?

Да, вы можете добавить несколько рядов данных в диаграмму Box Chart, создав дополнительные `IChartSeries` объектов и добавления к ним точек данных.

### Что означает QuartileMethodType.Exclusive?

The `QuartileMethodType.Exclusive` настройка указывает, что расчеты квартилей должны выполняться с использованием исключительного метода. Вы можете выбрать различные методы расчета квартилей в зависимости от ваших данных и требований.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
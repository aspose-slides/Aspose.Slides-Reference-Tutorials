---
title: Добавьте выноску в виде пончика в слайды Java
linktitle: Добавьте выноску в виде пончика в слайды Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Научитесь добавлять выноски в виде пончиков в слайды Java с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом для расширенных презентаций.
type: docs
weight: 12
url: /ru/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## Введение в добавление кольцевой выноски в слайды Java с использованием Aspose.Slides для Java

В этом уроке мы покажем вам процесс добавления кольцевой выноски на слайд в Java с помощью Aspose.Slides для Java. Кольцевая выноска — это элемент диаграммы, который можно использовать для выделения определенных точек данных на кольцевой диаграмме. Для вашего удобства мы предоставим вам пошаговые инструкции и полный исходный код.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

1. Среда разработки Java
2. Aspose.Slides для библиотеки Java
3. Интегрированная среда разработки (IDE), такая как Eclipse или IntelliJ IDEA.
4. Презентация PowerPoint, в которую вы хотите добавить выноску в виде пончика.

## Шаг 1. Настройте свой Java-проект

1. Создайте новый проект Java в выбранной вами среде IDE.
2. Добавьте библиотеку Aspose.Slides for Java в свой проект в качестве зависимости.

## Шаг 2. Инициализируйте презентацию

Чтобы начать работу, вам необходимо инициализировать презентацию PowerPoint и создать слайд, на который вы хотите добавить выноску в виде пончика. Вот код для достижения этой цели:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Обязательно замените`"Your Document Directory"` с фактическим путем к файлу презентации PowerPoint.

## Шаг 3. Создайте кольцевую диаграмму

Далее вы создадите на слайде кольцевую диаграмму. Вы можете настроить положение и размер диаграммы в соответствии с вашими требованиями. Вот код для добавления кольцевой диаграммы:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Шаг 4. Настройте кольцевую диаграмму

Теперь пришло время настроить кольцевую диаграмму. Мы установим различные свойства, такие как удаление легенды, настройка размера отверстия и настройка угла первого среза. Вот код:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Этот фрагмент кода устанавливает свойства кольцевой диаграммы. Вы можете настроить значения в соответствии с вашими конкретными потребностями.

## Шаг 5. Добавьте данные в кольцевую диаграмму

Теперь давайте добавим данные в кольцевую диаграмму. Мы также настроим внешний вид точек данных. Вот код для этого:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Здесь можно настроить внешний вид точки данных.
        i++;
    }
    categoryIndex++;
}
```

В этом коде мы добавляем категории и точки данных на кольцевую диаграмму. При необходимости вы можете дополнительно настроить внешний вид точек данных.

## Шаг 6. Сохраните презентацию

Наконец, не забудьте сохранить презентацию после добавления выноски в виде пончика. Вот код для сохранения презентации:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Обязательно замените`"chart.pptx"` с желаемым именем файла.

Поздравляем! Вы успешно добавили кольцевую выноску на слайд Java с помощью Aspose.Slides for Java. Теперь вы можете запустить приложение Java для создания презентации PowerPoint с кольцевой диаграммой и выноской.

## Полный исходный код для добавления выноски пончика в слайды Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы рассмотрели процесс добавления кольцевой выноски на слайд Java с помощью Aspose.Slides для Java. Вы узнали, как создать кольцевую диаграмму, настроить ее внешний вид и добавить точки данных. Не стесняйтесь улучшать свои презентации с помощью этой мощной библиотеки и изучите дополнительные возможности построения диаграмм.

## Часто задаваемые вопросы

### Как я могу изменить внешний вид выноски в виде пончика?

Вы можете настроить внешний вид кольцевой выноски, изменив свойства точек данных на диаграмме. В предоставленном коде вы можете увидеть, как установить цвет заливки, цвет линии, стиль шрифта и другие атрибуты точек данных.

### Могу ли я добавить дополнительные точки данных на кольцевую диаграмму?

Да, вы можете добавить в кольцевую диаграмму столько точек данных, сколько необходимо. Просто расширьте циклы кода, в которых добавляются категории и точки данных, и предоставьте соответствующие данные и форматирование.

### Как настроить положение и размер кольцевой диаграммы на слайде?

Вы можете изменить положение и размер кольцевой диаграммы, изменив параметры в`addChart` метод. Четыре числа в этом методе соответствуют координатам X и Y верхнего левого угла диаграммы, а также ее ширине и высоте соответственно.
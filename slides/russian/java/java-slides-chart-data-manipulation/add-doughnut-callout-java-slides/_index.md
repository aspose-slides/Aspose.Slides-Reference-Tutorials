---
"description": "Научитесь добавлять выноски-кольцевые диаграммы в слайды Java с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом для улучшенных презентаций."
"linktitle": "Добавить выноску в виде пончика в слайды Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Добавить выноску в виде пончика в слайды Java"
"url": "/ru/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Добавить выноску в виде пончика в слайды Java


## Введение в добавление выноски кольцевой формы в слайды Java с использованием Aspose.Slides для Java

В этом уроке мы проведем вас через процесс добавления выноски Doughnut на слайд в Java с помощью Aspose.Slides для Java. Выноска Doughnut — это элемент диаграммы, который можно использовать для выделения определенных точек данных в диаграмме Doughnut. Для вашего удобства мы предоставим вам пошаговые инструкции и полный исходный код.

## Предпосылки

Прежде чем начать, убедитесь, что выполнены следующие предварительные условия:

1. Среда разработки Java
2. Библиотека Aspose.Slides для Java
3. Интегрированная среда разработки (IDE), например Eclipse или IntelliJ IDEA
4. Презентация PowerPoint, в которую вы хотите добавить выноску «Кольцо»

## Шаг 1: Настройте свой проект Java

1. Создайте новый проект Java в выбранной вами среде IDE.
2. Добавьте библиотеку Aspose.Slides для Java в свой проект в качестве зависимости.

## Шаг 2: Инициализация презентации

Для начала вам нужно инициализировать презентацию PowerPoint и создать слайд, на который вы хотите добавить выноску «Кольцо». Вот код для этого:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Обязательно замените `"Your Document Directory"` с фактическим путем к файлу презентации PowerPoint.

## Шаг 3: Создайте кольцевую диаграмму

Далее вы создадите на слайде кольцевую диаграмму. Вы можете настроить положение и размер диаграммы в соответствии с вашими требованиями. Вот код для добавления кольцевой диаграммы:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Шаг 4: Настройте кольцевую диаграмму

Теперь пришло время настроить кольцевую диаграмму. Мы зададим различные свойства, например, удалив легенду, настроив размер отверстия и отрегулировав угол первого среза. Вот код:

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

Этот фрагмент кода устанавливает свойства для кольцевой диаграммы. Вы можете настроить значения в соответствии с вашими конкретными потребностями.

## Шаг 5: Добавьте данные в кольцевую диаграмму

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
        // Настройте внешний вид точки данных здесь
        i++;
    }
    categoryIndex++;
}
```

В этом коде мы добавляем категории и точки данных в кольцевую диаграмму. Вы можете дополнительно настроить внешний вид точек данных по мере необходимости.

## Шаг 6: Сохраните презентацию

Наконец, не забудьте сохранить презентацию после добавления выноски Donut Callout. Вот код для сохранения презентации:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Обязательно замените `"chart.pptx"` с желаемым именем файла.

Поздравляем! Вы успешно добавили кольцевую выноску на слайд Java с помощью Aspose.Slides для Java. Теперь вы можете запустить свое приложение Java для создания презентации PowerPoint с кольцевой диаграммой и выноской.

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

В этом уроке мы рассмотрели процесс добавления выноски Doughnut на слайд Java с помощью Aspose.Slides для Java. Вы узнали, как создать кольцевую диаграмму, настроить ее внешний вид и добавить точки данных. Не стесняйтесь и дальше улучшать свои презентации с помощью этой мощной библиотеки и исследовать больше возможностей построения диаграмм.

## Часто задаваемые вопросы

### Как изменить внешний вид выноски «Пончик»?

Вы можете настроить внешний вид выноски кольцевой диаграммы, изменив свойства точек данных в диаграмме. В предоставленном коде вы можете увидеть, как задать цвет заливки, цвет линии, стиль шрифта и другие атрибуты точек данных.

### Могу ли я добавить больше точек данных в кольцевую диаграмму?

Да, вы можете добавить столько точек данных, сколько нужно, в кольцевую диаграмму. Просто расширьте циклы в коде, где добавляются категории и точки данных, и предоставьте соответствующие данные и форматирование.

### Как настроить положение и размер кольцевой диаграммы на слайде?

Вы можете изменить положение и размер кольцевой диаграммы, изменив параметры в `addChart` метод. Четыре числа в этом методе соответствуют координатам X и Y верхнего левого угла диаграммы и ее ширине и высоте соответственно.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
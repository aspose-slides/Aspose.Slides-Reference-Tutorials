---
"description": "Узнайте, как настроить выноски для меток данных в Aspose.Slides для Java. Пошаговое руководство с исходным кодом."
"linktitle": "Настройка выноски для метки данных в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Настройка выноски для метки данных в слайдах Java"
"url": "/ru/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Настройка выноски для метки данных в слайдах Java


## Введение в настройку выноски для метки данных в Aspose.Slides для Java

В этом уроке мы покажем, как настроить выноски для меток данных в диаграмме с помощью Aspose.Slides для Java. Выноски могут быть полезны для выделения определенных точек данных в вашей диаграмме. Мы пройдемся по коду шаг за шагом и предоставим необходимый исходный код.

## Предпосылки

- У вас должен быть установлен Aspose.Slides для Java.
- Создайте проект Java и добавьте в него библиотеку Aspose.Slides.

## Шаг 1: Создайте презентацию и добавьте диаграмму

Сначала нам нужно создать презентацию и добавить диаграмму на слайд. Обязательно замените `"Your Document Directory"` с фактическим путем к каталогу ваших документов.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Шаг 2: Настройте диаграмму

Далее мы настроим диаграмму, задав такие свойства, как легенда, серии и категории.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Настройте серии и категории (Вы можете настроить количество серий и категорий)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Добавьте точки данных здесь
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Шаг 3: Настройте метки данных

Теперь мы настроим метки данных, включая настройку выносок для последней серии.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Настройте форматирование точек данных (заливка, линия и т. д.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Настройте форматирование этикетки (шрифт, заливка и т. д.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Включить выноски
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Шаг 4: Сохраните презентацию

Наконец, сохраните презентацию с настроенной диаграммой.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Теперь вы успешно настроили выноски для меток данных в диаграмме с помощью Aspose.Slides для Java. Настройте код в соответствии с вашими конкретными требованиями к диаграмме и данным.

## Полный исходный код для настройки выноски для метки данных в слайдах Java

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
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы изучили, как настроить выноски для меток данных в диаграмме с помощью Aspose.Slides для Java. Выноски — это ценные инструменты для выделения определенных точек данных в ваших диаграммах и презентациях. Мы предоставили пошаговое руководство вместе с исходным кодом, чтобы помочь вам достичь этой настройки.

## Часто задаваемые вопросы

### Как настроить внешний вид меток данных?

Чтобы настроить внешний вид меток данных, вы можете изменить такие свойства, как шрифт, заливка и стили линий. Например:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Как включить или отключить выноски для меток данных?

Чтобы включить или отключить выноски для меток данных, используйте `setShowLabelAsDataCallout` Метод. Установите его на `true` для включения выносок и `false` чтобы отключить их.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Включить выноски
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Отключить выноски
```

### Могу ли я настроить линии указателей для меток данных?

Да, вы можете настроить линии выноски для меток данных, используя такие свойства, как стиль линии, цвет и ширина. Например:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Включить линии выноски
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Это некоторые общие параметры настройки для меток данных и выносок в Aspose.Slides для Java. Вы можете дополнительно настроить внешний вид в соответствии со своими конкретными потребностями.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
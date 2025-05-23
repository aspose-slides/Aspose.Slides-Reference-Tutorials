---
"description": "Узнайте, как получить фактическое положение меток данных диаграммы в Java Slides с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом."
"linktitle": "Получить фактическое положение метки данных диаграммы в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Получить фактическое положение метки данных диаграммы в слайдах Java"
"url": "/ru/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Получить фактическое положение метки данных диаграммы в слайдах Java


## Введение в получение фактического положения метки данных диаграммы в слайдах Java

В этом уроке вы узнаете, как получить фактическое положение меток данных диаграммы с помощью Aspose.Slides для Java. Мы создадим программу Java, которая сгенерирует презентацию PowerPoint с диаграммой, настроит метки данных, а затем добавит фигуры, представляющие положения этих меток данных.

## Предпосылки

Прежде чем начать, убедитесь, что в вашем проекте Java настроена библиотека Aspose.Slides для Java.

## Шаг 1: Создайте презентацию PowerPoint

Сначала давайте создадим новую презентацию PowerPoint и добавим в нее диаграмму. Позже в этом уроке мы настроим метки данных диаграммы.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Шаг 2: Настройте метки данных
Теперь давайте настроим метки данных для серии диаграмм. Мы зададим их положение и покажем значения.

```java
try {
    // ... (предыдущий код)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (оставшийся код)
} finally {
    if (pres != null) pres.dispose();
}
```

## Шаг 3: Получите фактическое положение меток данных
На этом этапе мы выполним итерацию по точкам данных серии диаграммы и получим фактическое положение меток данных, имеющих значение больше 4. Затем мы добавим эллипсы для представления этих положений.

```java
try {
    // ... (предыдущий код)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (оставшийся код)
} finally {
    if (pres != null) pres.dispose();
}
```

## Шаг 4: Сохраните презентацию
Наконец, сохраните созданную презентацию в файл.

```java
try {
    // ... (предыдущий код)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Полный исходный код для получения фактического положения метки данных диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//ДЕЛО
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке вы узнали, как получить фактическое положение меток данных диаграммы в Java Slides с помощью Aspose.Slides для Java. Теперь вы можете использовать эти знания для улучшения ваших презентаций PowerPoint с помощью настраиваемых меток данных и визуальных представлений их положений.

## Часто задаваемые вопросы

### Как настроить метки данных на диаграмме?

Чтобы настроить метки данных на диаграмме, вы можете использовать `setDefaultDataLabelFormat` метод на серии диаграмм и задать свойства, такие как положение и видимость. Например:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Как добавить фигуры для представления позиций меток данных?

Вы можете перебирать точки данных серии диаграмм и использовать `getActualX`, `getActualY`, `getActualWidth`, и `getActualHeight` методы метки данных, чтобы получить ее положение. Затем вы можете добавить фигуры, используя `addAutoShape` метод. Вот пример:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Как сохранить созданную презентацию?

Вы можете сохранить созданную презентацию с помощью `save` метод. Укажите желаемый путь к файлу и `SaveFormat` как параметры. Например:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
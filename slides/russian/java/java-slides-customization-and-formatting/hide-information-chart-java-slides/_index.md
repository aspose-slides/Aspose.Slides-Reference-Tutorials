---
title: Скрыть информацию из диаграммы в слайдах Java
linktitle: Скрыть информацию из диаграммы в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как скрыть элементы диаграммы в слайдах Java с помощью Aspose.Slides для Java. Настраивайте презентации для ясности и эстетики с помощью пошаговых инструкций и исходного кода.
weight: 13
url: /ru/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Скрыть информацию из диаграммы в слайдах Java


## Введение в скрытие информации из диаграммы в слайдах Java

В этом уроке мы рассмотрим, как скрыть различные элементы диаграммы в Java Slides с помощью API Aspose.Slides для Java. Вы можете использовать этот код для настройки диаграмм по мере необходимости для ваших презентаций.

## Шаг 1: Настройка среды

 Прежде чем мы начнем, убедитесь, что в ваш проект добавлена библиотека Aspose.Slides for Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).

## Шаг 2. Создайте новую презентацию

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 3. Добавление диаграммы на слайд

Мы добавим на слайд линейную диаграмму с маркерами, а затем продолжим скрывать различные элементы диаграммы.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Шаг 4. Скройте заголовок диаграммы

Вы можете скрыть заголовок диаграммы следующим образом:

```java
chart.setTitle(false);
```

## Шаг 5. Скройте ось значений

Чтобы скрыть ось значений (вертикальную ось), используйте следующий код:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Шаг 6. Скройте ось категорий

Чтобы скрыть ось категорий (горизонтальную ось), используйте этот код:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Шаг 7: Скрыть легенду

Вы можете скрыть легенду диаграммы следующим образом:

```java
chart.setLegend(false);
```

## Шаг 8: скройте основные линии сетки

Чтобы скрыть основные линии сетки горизонтальной оси, вы можете использовать следующий код:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Шаг 9: Удалить серию

Если вы хотите удалить все серии из диаграммы, вы можете использовать такой цикл:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Шаг 10. Настройка серии диаграмм

Серию диаграмм можно настроить по мере необходимости. В этом примере мы меняем стиль маркера, положение метки данных, размер маркера, цвет линии и стиль штриха:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Шаг 11: Сохраните презентацию

Наконец, сохраните презентацию в файл:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно скрыли различные элементы диаграммы в слайдах Java с помощью Aspose.Slides для Java. Вы можете дополнительно настроить диаграммы и презентации в соответствии с вашими конкретными требованиями.

## Полный исходный код для скрытия информации из диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Скрытие названия диаграммы
	chart.setTitle(false);
	///Скрытие оси значений
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Видимость оси категории
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Скрытие легенды
	chart.setLegend(false);
	//Скрытие MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Настройка цвета линии серии
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Заключение

В этом пошаговом руководстве мы рассмотрели, как скрыть различные элементы диаграммы в слайдах Java с помощью API Aspose.Slides для Java. Это может быть невероятно полезно, когда вам нужно настроить диаграммы для презентаций и сделать их более визуально привлекательными или адаптированными к вашим конкретным потребностям.

## Часто задаваемые вопросы

### Как мне дополнительно настроить внешний вид элементов диаграммы?

Вы можете настроить различные свойства элементов диаграммы, такие как цвет линии, цвет заливки, стиль маркера и т. д., открыв соответствующие свойства серии диаграммы, маркеров, меток и формата.

### Могу ли я скрыть определенные точки данных на диаграмме?

Да, вы можете скрыть определенные точки данных, манипулируя данными в серии диаграмм. Вы можете удалить точки данных или установить для них значение null, чтобы скрыть их.

### Как добавить на диаграмму дополнительные серии?

 Вы можете добавить дополнительные серии на диаграмму, используя`IChartData.getSeries().add` метод и указание точек данных для новой серии.

### Можно ли динамически менять тип диаграммы?

Да, вы можете изменить тип диаграммы динамически, создав новую диаграмму нужного типа и скопировав данные из старой диаграммы в новую.

### Как программно изменить заголовок диаграммы и метки осей?

Вы можете установить заголовок и метки диаграммы и осей, открыв их соответствующие свойства и задав нужный текст и форматирование.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

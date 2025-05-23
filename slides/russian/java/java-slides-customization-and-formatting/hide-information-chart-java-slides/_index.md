---
"description": "Узнайте, как скрыть элементы диаграммы в Java Slides с помощью Aspose.Slides для Java. Настройте презентации для ясности и эстетики с помощью пошагового руководства и исходного кода."
"linktitle": "Скрыть информацию из диаграммы в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Скрыть информацию из диаграммы в Java Slides"
"url": "/ru/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Скрыть информацию из диаграммы в Java Slides


## Введение в скрытие информации из диаграммы в Java Slides

В этом уроке мы рассмотрим, как скрыть различные элементы диаграммы в Java Slides с помощью API Aspose.Slides для Java. Вы можете использовать этот код для настройки диаграмм по мере необходимости для ваших презентаций.

## Шаг 1: Настройка среды

Прежде чем начать, убедитесь, что в ваш проект добавлена библиотека Aspose.Slides for Java. Вы можете загрузить ее с [здесь](https://releases.aspose.com/slides/java/).

## Шаг 2: Создайте новую презентацию

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 3: Добавление диаграммы на слайд

Мы добавим на слайд линейную диаграмму с маркерами, а затем приступим к скрытию различных элементов диаграммы.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Шаг 4: Скрыть заголовок диаграммы

Вы можете скрыть заголовок диаграммы следующим образом:

```java
chart.setTitle(false);
```

## Шаг 5: Скрыть ось значений

Чтобы скрыть ось значений (вертикальную ось), используйте следующий код:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Шаг 6: Скрыть ось категорий

Чтобы скрыть ось категорий (горизонтальную ось), используйте этот код:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Шаг 7: Скрыть легенду

Скрыть легенду диаграммы можно следующим образом:

```java
chart.setLegend(false);
```

## Шаг 8: Скройте основные линии сетки

Чтобы скрыть основные линии сетки горизонтальной оси, можно использовать следующий код:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Шаг 9: Удалить серию

Если вы хотите удалить все ряды из диаграммы, вы можете использовать такой цикл:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Шаг 10: Настройте ряд диаграмм

Вы можете настроить ряд диаграмм по мере необходимости. В этом примере мы изменим стиль маркера, положение метки данных, размер маркера, цвет линии и стиль штриха:

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

Вот и все! Вы успешно скрыли различные элементы диаграммы в Java Slides с помощью Aspose.Slides для Java. Вы можете дополнительно настроить диаграммы и презентации по мере необходимости для ваших конкретных требований.

## Полный исходный код для скрытия информации из диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Скрытие заголовка диаграммы
	chart.setTitle(false);
	///Скрытие оси значений
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Категория Видимость оси
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Скрытая легенда
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
	//Установка цвета линии серии
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

В этом пошаговом руководстве мы изучили, как скрыть различные элементы диаграммы в Java Slides с помощью API Aspose.Slides для Java. Это может быть невероятно полезно, когда вам нужно настроить диаграммы для презентаций и сделать их более визуально привлекательными или подогнать под ваши конкретные потребности.

## Часто задаваемые вопросы

### Как еще можно настроить внешний вид элементов диаграммы?

Вы можете настраивать различные свойства элементов диаграммы, такие как цвет линии, цвет заливки, стиль маркера и многое другое, получая доступ к соответствующим свойствам серии диаграммы, маркеров, меток и формата.

### Могу ли я скрыть определенные точки данных на диаграмме?

Да, вы можете скрыть определенные точки данных, манипулируя данными в серии диаграмм. Вы можете удалить точки данных или установить их значения на ноль, чтобы скрыть их.

### Как добавить дополнительные ряды в диаграмму?

Вы можете добавить больше рядов на диаграмму, используя `IChartData.getSeries().add` метода и указания точек данных для нового ряда.

### Можно ли динамически менять тип диаграммы?

Да, вы можете динамически изменить тип диаграммы, создав новую диаграмму нужного типа и скопировав данные из старой диаграммы в новую.

### Как программно изменить заголовок диаграммы и подписи осей?

Вы можете задать заголовок и метки диаграммы и осей, открыв их соответствующие свойства и задав нужный текст и форматирование.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
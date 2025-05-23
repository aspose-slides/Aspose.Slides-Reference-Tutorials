---
"description": "Научитесь создавать и настраивать диаграммы Java Slides с помощью Aspose.Slides. Улучшите свои презентации с помощью мощных сущностей диаграмм."
"linktitle": "Диаграммы сущностей в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Диаграммы сущностей в слайдах Java"
"url": "/ru/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Диаграммы сущностей в слайдах Java


## Введение в сущности диаграмм в слайдах Java

Диаграммы — это мощные инструменты для визуализации данных в презентациях. Независимо от того, создаете ли вы бизнес-отчеты, академические презентации или любую другую форму контента, диаграммы помогают эффективно передавать информацию. Aspose.Slides для Java предоставляет надежные функции для работы с диаграммами, что делает его выбором номер один для разработчиков Java.

## Предпосылки

Прежде чем погрузиться в мир сущностей диаграмм, убедитесь, что у вас выполнены следующие предварительные условия:

- Установлен комплект разработки Java (JDK)
- Библиотека Aspose.Slides для Java загружена и добавлена в ваш проект
- Базовые знания программирования на Java

Теперь приступим к созданию и настройке диаграмм с помощью Aspose.Slides для Java.

## Шаг 1: Создание презентации

Первый шаг — создать новую презентацию, в которую вы добавите свою диаграмму. Вот фрагмент кода для создания презентации:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2: Добавление диаграммы

Когда ваша презентация будет готова, пора добавить диаграмму. В этом примере мы добавим простую линейную диаграмму с маркерами. Вот как это можно сделать:

```java
// Доступ к первому слайду
ISlide slide = pres.getSlides().get_Item(0);

// Добавление образца диаграммы
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Шаг 3: Настройка заголовка диаграммы

Хорошо определенная диаграмма должна иметь заголовок. Давайте зададим заголовок для нашей диаграммы:

```java
// Установка заголовка диаграммы
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Шаг 4: Форматирование линий сетки

Вы можете форматировать основные и второстепенные линии сетки вашей диаграммы. Давайте установим форматирование для линий сетки вертикальной оси:

```java
// Настройка формата основных линий сетки для оси значений
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Настройка формата линий дополнительной сетки для оси значений
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Шаг 5: Настройка оси ценностей

У вас есть контроль над числовым форматом, максимальными и минимальными значениями оси значений. Вот как это настроить:

```java
// Формат числа оси значений настройки
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Установка максимальных и минимальных значений диаграммы
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Шаг 6: Добавление заголовка оси ценности

Чтобы сделать диаграмму более информативной, вы можете добавить заголовок к оси значений:

```java
// Установка заголовка оси значений
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Шаг 7: Форматирование оси категорий

Ось категорий, которая обычно представляет категории данных, также можно настраивать:

```java
// Настройка формата основных линий сетки для оси категорий
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Настройка формата линий дополнительной сетки для оси категорий
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Шаг 8: Добавление легенд

Легенды помогают объяснить ряд данных на вашей диаграмме. Давайте настроим легенды:

```java
// Настройка свойств текста легенды
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Установить отображение легенд диаграммы без перекрытия диаграммы
chart.getLegend().setOverlay(true);
```

## Шаг 9: Сохранение презентации

Наконец, сохраните вашу презентацию с диаграммой:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для диаграммных сущностей в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если его еще нет.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Создание презентации// Создание презентации
Presentation pres = new Presentation();
try
{
	// Доступ к первому слайду
	ISlide slide = pres.getSlides().get_Item(0);
	// Добавление образца диаграммы
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Настройка заголовка диаграммы
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Настройка формата основных линий сетки для оси значений
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Настройка формата линий дополнительной сетки для оси значений
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Формат числа оси значений настройки
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Установка максимальных и минимальных значений диаграммы
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Настройка свойств текста оси значений
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Установка заголовка оси значений
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Настройка формата линии оси значений: теперь устарело
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Настройка формата основных линий сетки для оси категорий
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Настройка формата линий дополнительной сетки для оси категорий
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Настройка свойств текста оси категорий
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Настройка заголовка категории
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Установка положения метки оси категории
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Установка угла поворота метки оси категории
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Настройка свойств текста легенды
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Установить отображение легенд диаграммы без перекрытия диаграммы
	chart.getLegend().setOverlay(true);
	// Построение первой серии на вторичной оси значений
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Настройка цвета задней стенки диаграммы
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Настройка цвета области построения
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Сохранить презентацию
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этой статье мы изучили мир сущностей диаграмм в Java Slides с помощью Aspose.Slides для Java. Вы узнали, как создавать, настраивать и управлять диаграммами для улучшения ваших презентаций. Диаграммы не только делают ваши данные визуально привлекательными, но и помогают вашей аудитории легче понимать сложную информацию.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

Чтобы изменить тип диаграммы, используйте `chart.setType()` метод и укажите желаемый тип диаграммы.

### Можно ли добавить несколько рядов данных на диаграмму?

Да, вы можете добавить несколько рядов данных в диаграмму с помощью `chart.getChartData().getSeries().addSeries()` метод.

### Как настроить цвета диаграммы?

Вы можете настроить цвета диаграммы, задав формат заливки для различных элементов диаграммы, таких как линии сетки, заголовок и легенды.

### Могу ли я создавать 3D-диаграммы?

Да, Aspose.Slides for Java поддерживает создание 3D-диаграмм. Вы можете задать `ChartType` к типу 3D-диаграммы, чтобы создать ее.

### Совместим ли Aspose.Slides для Java с последними версиями Java?

Да, Aspose.Slides для Java регулярно обновляется для поддержки последних версий Java и обеспечивает совместимость с широким спектром сред Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
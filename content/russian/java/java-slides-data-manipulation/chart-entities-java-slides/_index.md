---
title: Объекты диаграммы в слайдах Java
linktitle: Объекты диаграммы в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Научитесь создавать и настраивать диаграммы Java Slides с помощью Aspose.Slides. Улучшите свои презентации с помощью мощных объектов диаграмм.
type: docs
weight: 13
url: /ru/java/data-manipulation/chart-entities-java-slides/
---

## Введение в объекты диаграммы в слайдах Java

Диаграммы — это мощные инструменты для визуализации данных в презентациях. Независимо от того, создаете ли вы бизнес-отчеты, научные презентации или любой другой вид контента, диаграммы помогают эффективно передавать информацию. Aspose.Slides для Java предоставляет надежные функции для работы с диаграммами, что делает его идеальным выбором для разработчиков Java.

## Предварительные условия

Прежде чем мы углубимся в мир объектов диаграммы, убедитесь, что у вас есть следующие предварительные условия:

- Установлен пакет разработки Java (JDK).
- Библиотека Aspose.Slides для Java загружена и добавлена в ваш проект.
- Базовые знания программирования на Java

Теперь давайте начнем с создания и настройки диаграмм с помощью Aspose.Slides для Java.

## Шаг 1: Создание презентации

Первый шаг — создать новую презентацию, в которую вы добавите диаграмму. Вот фрагмент кода для создания презентации:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2. Добавление диаграммы

Когда презентация готова, пришло время добавить диаграмму. В этом примере мы добавим простую линейную диаграмму с маркерами. Вот как вы можете это сделать:

```java
// Доступ к первому слайду
ISlide slide = pres.getSlides().get_Item(0);

// Добавление образца диаграммы
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Шаг 3. Настройка названия диаграммы

Четко определенная диаграмма должна иметь заголовок. Давайте зададим заголовок для нашей диаграммы:

```java
// Установка названия диаграммы
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Шаг 4. Форматирование линий сетки

Вы можете отформатировать основные и второстепенные линии сетки диаграммы. Давайте зададим форматирование для линий сетки по вертикальной оси:

```java
// Настройка формата основных линий сетки для оси значений
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Настройка формата второстепенных линий сетки для оси значений
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Шаг 5. Настройка оси значений

У вас есть контроль над числовым форматом, максимальными и минимальными значениями оси значений. Вот как его настроить:

```java
// Настройка формата номера оси значения
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Установка диаграммы максимальных и минимальных значений
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Шаг 6. Добавление названия оси значений

Чтобы сделать диаграмму более информативной, вы можете добавить заголовок к оси значений:

```java
// Название оси значений настройки
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Шаг 7. Форматирование оси категорий

Ось категорий, которая обычно представляет категории данных, также может быть настроена:

```java
// Настройка формата основных линий сетки для оси категорий
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//Настройка формата второстепенных линий сетки для оси категорий
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Шаг 8: Добавление легенд

Легенды помогают объяснить ряды данных на диаграмме. Давайте настроим легенды:

```java
// Настройка свойств текста легенды
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Установите легенды диаграммы без перекрытия диаграммы
chart.getLegend().setOverlay(true);
```

## Шаг 9: Сохранение презентации

Наконец, сохраните презентацию с диаграммой:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Полный исходный код для объектов диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте каталог, если он еще не существует.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Создание экземпляра презентации// Создание экземпляра представления
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
	// Настройка формата второстепенных линий сетки для оси значений
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Настройка формата номера оси значения
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Установка диаграммы максимальных и минимальных значений
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
	// Название оси значений настройки
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Формат линии оси значений настройки: Устарело.
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Настройка формата основных линий сетки для оси категорий
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//Настройка формата второстепенных линий сетки для оси категорий
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
	// Настройка положения метки оси категории
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Настройка угла поворота метки оси категории
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Настройка свойств текста легенды
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Установите легенды диаграммы без перекрытия диаграммы
	chart.getLegend().setOverlay(true);
	// Построение первой серии на вторичной оси значений
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Настройка цвета задней стенки диаграммы
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Настройка цвета области графика
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

В этой статье мы изучили мир объектов диаграммы в Java Slides, используя Aspose.Slides для Java. Вы узнали, как создавать, настраивать диаграммы и манипулировать ими для улучшения своих презентаций. Диаграммы не только делают ваши данные визуально привлекательными, но и помогают вашей аудитории легче понимать сложную информацию.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

 Чтобы изменить тип диаграммы, используйте`chart.setType()` метод и укажите желаемый тип диаграммы.

### Могу ли я добавить на диаграмму несколько рядов данных?

 Да, вы можете добавить на диаграмму несколько рядов данных, используя`chart.getChartData().getSeries().addSeries()` метод.

### Как настроить цвета диаграммы?

Вы можете настроить цвета диаграммы, задав формат заливки для различных элементов диаграммы, таких как линии сетки, заголовок и легенды.

### Могу ли я создавать 3D-диаграммы?

 Да, Aspose.Slides для Java поддерживает создание трехмерных диаграмм. Вы можете установить`ChartType` к типу трехмерной диаграммы, чтобы создать ее.

### Совместим ли Aspose.Slides for Java с последними версиями Java?

Да, Aspose.Slides для Java регулярно обновляется для поддержки последних версий Java и обеспечивает совместимость с широким спектром сред Java.
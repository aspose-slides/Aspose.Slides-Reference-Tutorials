---
title: Настройка формата даты для оси категорий в слайдах Java
linktitle: Настройка формата даты для оси категорий в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как установить формат даты для оси категорий в диаграмме PowerPoint с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом.
type: docs
weight: 26
url: /ru/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Введение в настройку формата даты для оси категорий в слайдах Java

В этом уроке мы узнаем, как установить формат даты для оси категорий в диаграмме PowerPoint с помощью Aspose.Slides для Java. Aspose.Slides for Java — это мощная библиотека, которая позволяет вам программно создавать, манипулировать и управлять презентациями PowerPoint.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Библиотека Aspose.Slides для Java (ее можно скачать с сайта[здесь](https://releases.aspose.com/slides/java/).
2. Настроена среда разработки Java.

## Шаг 1. Создайте презентацию PowerPoint

Сначала нам нужно создать презентацию PowerPoint, в которую мы добавим диаграмму. Убедитесь, что вы импортировали необходимые классы Aspose.Slides.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2. Добавьте диаграмму на слайд

Теперь давайте добавим диаграмму на слайд PowerPoint. В этом примере мы будем использовать диаграмму областей.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Шаг 3. Подготовьте данные диаграммы

Мы настроим данные и категории диаграммы. В этом примере мы будем использовать категории дат.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Добавление категорий дат
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Добавление ряда данных
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Шаг 4. Настройте ось категорий
Теперь давайте настроим ось категорий для отображения дат в определенном формате (например, гггг).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Шаг 5. Сохраните презентацию
Наконец, сохраните презентацию PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно установили формат даты для оси категорий в диаграмме PowerPoint с помощью Aspose.Slides для Java.

## Полный исходный код для установки формата даты для оси категорий в слайдах Java

```java
	// Путь к каталогу документов.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Заключение

Вы успешно настроили формат даты для оси категорий на диаграмме слайдов Java с помощью Aspose.Slides for Java. Это позволяет вам представлять значения дат в нужном формате на ваших диаграммах. Не стесняйтесь изучать дополнительные варианты настройки в соответствии с вашими конкретными требованиями.

## Часто задаваемые вопросы

### Как изменить формат даты для оси категорий?

 Чтобы изменить формат даты для оси категорий, используйте команду`setNumberFormat` на оси категорий и укажите желаемый шаблон формата даты, например «гггг-ММ-дд» или «ММ/гггг». Обязательно установите`setNumberFormatLinkedToSource(false)` чтобы переопределить формат по умолчанию.

### Могу ли я использовать разные форматы дат для разных диаграмм в одной презентации?

Да, вы можете установить разные форматы дат для осей категорий на разных диаграммах в одной презентации. Просто настройте ось категорий для каждой диаграммы по мере необходимости.

### Как добавить на диаграмму дополнительные точки данных?

 Чтобы добавить дополнительные точки данных на диаграмму, используйте`getDataPoints().addDataPointForLineSeries`метод для ряда данных и укажите значения данных.
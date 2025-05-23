---
"description": "Узнайте, как задать формат даты для оси категорий в диаграмме PowerPoint с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом."
"linktitle": "Настройка формата даты для оси категорий в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Настройка формата даты для оси категорий в слайдах Java"
"url": "/ru/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Настройка формата даты для оси категорий в слайдах Java


## Введение в настройку формата даты для оси категорий в слайдах Java

В этом уроке мы научимся устанавливать формат даты для оси категорий в диаграмме PowerPoint с помощью Aspose.Slides для Java. Aspose.Slides для Java — это мощная библиотека, которая позволяет вам создавать, изменять и управлять презентациями PowerPoint программным способом.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Библиотека Aspose.Slides для Java (ее можно загрузить с сайта [здесь](https://releases.aspose.com/slides/java/).
2. Настроена среда разработки Java.

## Шаг 1: Создайте презентацию PowerPoint

Сначала нам нужно создать презентацию PowerPoint, в которую мы добавим диаграмму. Убедитесь, что вы импортировали необходимые классы Aspose.Slides.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Шаг 2: Добавьте диаграмму на слайд

Теперь давайте добавим диаграмму на слайд PowerPoint. В этом примере мы будем использовать диаграмму с областями.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Шаг 3: Подготовка данных диаграммы

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

## Шаг 4: Настройте ось категорий
Теперь давайте настроим ось категорий для отображения дат в определенном формате (например, гггг).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Шаг 5: Сохраните презентацию
Наконец, сохраните презентацию PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно установили формат даты для оси категорий в диаграмме PowerPoint с помощью Aspose.Slides для Java.

## Полный исходный код для настройки формата даты для оси категорий в слайдах Java

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
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
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

Вы успешно настроили формат даты для оси категорий в диаграмме Java Slides с помощью Aspose.Slides для Java. Это позволяет вам представлять значения даты в желаемом формате на ваших диаграммах. Не стесняйтесь исследовать дополнительные параметры настройки на основе ваших конкретных требований.

## Часто задаваемые вопросы

### Как изменить формат даты для оси категорий?

Чтобы изменить формат даты для оси категорий, используйте `setNumberFormat` метод на оси категорий и укажите желаемый шаблон формата даты, например "yyyy-MM-dd" или "MM/yyyy". Обязательно установите `setNumberFormatLinkedToSource(false)` для переопределения формата по умолчанию.

### Можно ли использовать разные форматы дат для разных диаграмм в одной презентации?

Да, вы можете задать разные форматы дат для осей категорий в разных диаграммах в рамках одной презентации. Просто настройте ось категорий для каждой диаграммы по мере необходимости.

### Как добавить больше точек данных на диаграмму?

Чтобы добавить больше точек данных на диаграмму, используйте `getDataPoints().addDataPointForLineSeries` метод на рядах данных и предоставить значения данных.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
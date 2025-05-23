---
"description": "Узнайте, как создавать радиальные диаграммы в презентациях Java PowerPoint с помощью API Aspose.Slides для Java."
"linktitle": "Создание диаграммы-радиолокатора в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Создание диаграммы-радиолокатора в слайдах Java"
"url": "/ru/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Создание диаграммы-радиолокатора в слайдах Java


## Введение в создание радиальной диаграммы в Java Slides

В этом уроке мы проведем вас через процесс создания диаграммы Radar с использованием API Aspose.Slides для Java. Диаграммы Radar полезны для визуализации данных в круговой схеме, что упрощает сравнение нескольких рядов данных. Мы предоставим пошаговые инструкции вместе с исходным кодом Java.

## Предпосылки

Прежде чем начать, убедитесь, что в ваш проект интегрирована библиотека Aspose.Slides for Java. Вы можете загрузить библиотеку с сайта [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Настройка презентации

Начнем с создания новой презентации PowerPoint и добавления в нее слайда.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## Шаг 2: Добавление радиарной диаграммы

Далее мы добавим на слайд лепестковую диаграмму. Укажем положение и размеры диаграммы.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## Шаг 3: Настройка данных диаграммы

Теперь мы настроим данные диаграммы. Это включает в себя создание рабочей книги данных, добавление категорий и добавление серий.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Установить заголовок диаграммы
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Удалить созданные по умолчанию серии и категории
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Добавление новых категорий
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Добавление новых серий
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## Шаг 4: Заполнение рядов данных

Теперь мы заполним ряд данных для нашей лепестковой диаграммы.

```java
// Заполнить данные серии для серии 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Установить цвет серии
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// Заполнить данные серии для серии 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Установить цвет серии
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## Шаг 5: Настройка осей и легенд

Давайте настроим оси и легенды для нашей радиарной диаграммы.

```java
// Установить положение легенды
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Настройка свойств текста оси категорий
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Настройка свойств текста легенды
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Настройка свойств текста оси значений
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Формат числа оси значений настройки
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Значение основной единицы диаграммы настройки
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## Шаг 6: Сохранение презентации

Наконец, сохраните созданную презентацию с радиарной диаграммой.

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Вот и все! Вы успешно создали радиальную диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Теперь вы можете настроить этот пример в соответствии со своими конкретными потребностями.

## Полный исходный код для создания радиальной диаграммы в Java Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Доступ к первому слайду
	ISlide sld = pres.getSlides().get_Item(0);
	// Добавить диаграмму Радар
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Установка индекса листа данных диаграммы
	int defaultWorksheetIndex = 0;
	// Получение данных диаграммы WorkSheet
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Установить заголовок диаграммы
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Удалить созданные по умолчанию серии и категории
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Добавление новых категорий
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Добавление новых серий
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Сейчас заполняем данные серий
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Установить цвет серии
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Сейчас заполняем данные другой серии
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Установить цвет серии
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Установить положение легенды
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Настройка свойств текста оси категорий
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Настройка свойств текста легенды
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Настройка свойств текста оси значений
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Формат числа оси значений настройки
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Значение основной единицы диаграммы настройки
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Сохранить созданную презентацию
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке вы узнали, как создать радиальную диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете применять эти концепции для эффективной визуализации и представления данных в приложениях Java.

## Часто задаваемые вопросы

### Как изменить название диаграммы?

Чтобы изменить заголовок диаграммы, измените следующую строку:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Могу ли я добавить больше рядов данных в радиальную диаграмму?

Да, вы можете добавить больше рядов данных, выполнив действия, описанные в «Шаге 3» и «Шаге 4» для каждого дополнительного ряда, который вы хотите включить.

### Как настроить цвета диаграммы?

Вы можете настроить цвета серии, изменив строки, которые задают `SolidFillColor` свойство для каждой серии. Например:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Как изменить подписи и форматирование осей?

Чтобы настроить метки осей и форматирование, включая размер и цвет шрифта, обратитесь к «Шагу 5».

### Как сохранить диаграмму в другом формате файла?

Вы можете изменить выходной формат, изменив расширение файла в `outPath` переменная и использование соответствующего `SaveFormat`. Например, чтобы сохранить в формате PDF, используйте `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
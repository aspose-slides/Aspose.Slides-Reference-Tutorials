---
title: Настройка автоматических цветов фрагментов круговой диаграммы в слайдах Java
linktitle: Настройка автоматических цветов фрагментов круговой диаграммы в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать динамические круговые диаграммы с автоматическими цветами фрагментов в презентациях Java PowerPoint с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом.
weight: 24
url: /ru/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Настройка автоматических цветов фрагментов круговой диаграммы в слайдах Java


## Введение в настройку автоматических цветов фрагментов круговой диаграммы в слайдах Java

В этом уроке мы рассмотрим, как создать круговую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java и установить автоматические цвета фрагментов для диаграммы. Мы предоставим пошаговое руководство вместе с исходным кодом.

## Предварительные условия

 Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем Java-проекте. Скачать библиотеку можно с сайта Aspose:[Скачать Aspose.Slides для Java](https://releases.aspose.com/slides/java/).

## Шаг 1. Импортируйте необходимые пакеты

Сначала вам необходимо импортировать необходимые пакеты из Aspose.Slides for Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Шаг 2. Создайте презентацию PowerPoint

 Создайте экземпляр`Presentation` класс для создания новой презентации PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Шаг 3. Добавьте слайд

Откройте первый слайд презентации и добавьте к нему диаграмму с данными по умолчанию:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Шаг 4: Установите заголовок диаграммы

Задайте заголовок диаграммы:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Шаг 5. Настройка данных диаграммы

Настройте диаграмму для отображения значений для первой серии и настройте данные диаграммы:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Шаг 6. Добавьте категории и серии

Добавьте в диаграмму новые категории и серии:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Шаг 7. Заполнение данных серии

Заполните данные ряда для круговой диаграммы:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Шаг 8. Включите различные цвета фрагментов

Включите различные цвета фрагментов для круговой диаграммы:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Шаг 9: Сохраните презентацию

Наконец, сохраните презентацию в файл PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Полный исходный код для настройки автоматических цветов фрагментов круговой диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать класс презентации, представляющий файл PPTX.
Presentation presentation = new Presentation();
try
{
	// Доступ к первому слайду
	ISlide slides = presentation.getSlides().get_Item(0);
	// Добавить диаграмму с данными по умолчанию
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Название диаграммы настроек
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// Установите для первой серии значение «Показать значения».
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Установка индекса таблицы данных диаграммы
	int defaultWorksheetIndex = 0;
	// Получение листа данных диаграммы
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Удалить созданные по умолчанию серии и категории
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// Добавление новых категорий
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Добавляем новую серию
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Теперь заполняем данные серии
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

Вы успешно создали круговую диаграмму в презентации PowerPoint с помощью Aspose.Slides for Java и настроили для нее автоматические цвета фрагментов. Это пошаговое руководство предоставит вам необходимый для этого исходный код. При необходимости вы можете дополнительно настроить диаграмму и презентацию.

## Часто задаваемые вопросы

### Как настроить цвета отдельных фрагментов круговой диаграммы?

 Чтобы настроить цвета отдельных фрагментов круговой диаграммы, вы можете использовать`getAutomaticSeriesColors` метод для получения цветовой схемы по умолчанию и последующего изменения цветов по мере необходимости. Вот пример:

```java
//Получить цветовую схему по умолчанию
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Измените цвета по мере необходимости
colors.get_Item(0).setColor(Color.RED); // Установите цвет первого фрагмента на красный.
colors.get_Item(1).setColor(Color.BLUE); // Установите цвет второго фрагмента на синий.
// При необходимости добавьте дополнительные модификации цвета.
```

### Как добавить легенду на круговую диаграмму?

 Чтобы добавить легенду к круговой диаграмме, вы можете использовать команду`getLegend` метод и настройте его следующим образом:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Установите положение легенды
legend.setOverlay(true); // Отображение легенды над диаграммой
```

### Могу ли я изменить шрифт и стиль заголовка?

Да, вы можете изменить шрифт и стиль заголовка. Используйте следующий код, чтобы установить шрифт и стиль заголовка:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Установить размер шрифта
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Сделайте заголовок жирным
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Сделайте заголовок курсивом
```

При необходимости вы можете настроить размер, жирность и курсив шрифта.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

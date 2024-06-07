---
title: Добавить пользовательскую ошибку в слайды Java
linktitle: Добавить пользовательскую ошибку в слайды Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как добавить пользовательские полосы ошибок в диаграммы PowerPoint в Java Slides с помощью Aspose.Slides. Пошаговое руководство с исходным кодом для точной визуализации данных.
type: docs
weight: 11
url: /ru/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Введение в добавление пользовательских полос ошибок в слайды Java с использованием Aspose.Slides

В этом уроке вы узнаете, как добавить пользовательские полосы ошибок на диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Столбики ошибок полезны для отображения изменчивости или неопределенности точек данных на диаграмме.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

- Библиотека Aspose.Slides for Java установлена и настроена в вашем проекте.
- Настроена среда разработки Java.

## Шаг 1. Создайте пустую презентацию

Сначала создайте пустую презентацию PowerPoint.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
```

## Шаг 2. Добавьте пузырьковую диаграмму

Далее мы добавим в презентацию пузырьковую диаграмму.

```java
// Создание пузырьковой диаграммы
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Шаг 3. Добавьте пользовательские панели ошибок

Теперь давайте добавим пользовательские полосы ошибок в серию диаграмм.

```java
// Добавление пользовательских полос ошибок и настройка их формата
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Шаг 4. Установите данные о планках ошибок

На этом этапе мы получим доступ к точкам данных серии диаграмм и установим пользовательские значения планок ошибок для каждой точки.

```java
// Доступ к точкам данных серии диаграмм и установка значений планок погрешностей для отдельных точек.
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Установка планок погрешностей для точек ряда диаграмм
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Шаг 5. Сохраните презентацию

Наконец, сохраните презентацию с настраиваемыми полосами ошибок.

```java
// Сохранение презентации
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно добавили пользовательские полосы ошибок на диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java.

## Полный исходный код для добавления пользовательской ошибки в слайды Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
try
{
	// Создание пузырьковой диаграммы
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Добавление пользовательских полос ошибок и настройка их формата
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Доступ к точкам данных серии диаграмм и установка значений планок погрешностей для отдельной точки
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Установка планок погрешностей для точек ряда диаграмм
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Сохранение презентации
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

В этом подробном руководстве вы узнали, как улучшить ваши презентации PowerPoint, добавив к диаграммам пользовательские полосы ошибок с помощью Aspose.Slides для Java. Столбики ошибок предоставляют ценную информацию об изменчивости и неопределенности данных, делая диаграммы более информативными и визуально привлекательными.

## Часто задаваемые вопросы

### Как настроить внешний вид полос ошибок?

 Вы можете настроить внешний вид полос ошибок, изменив свойства`IErrorBarsFormat` объект, например стиль линии, цвет линии и ширина полосы ошибок.

### Могу ли я добавить полосы ошибок в другие типы диаграмм?

Да, вы можете добавлять полосы ошибок к различным типам диаграмм, поддерживаемым Aspose.Slides for Java, включая гистограммы, линейные диаграммы и точечные диаграммы.

### Как установить разные значения шкалы ошибок для каждой точки данных?

Вы можете перебирать точки данных и устанавливать собственные значения шкалы ошибок для каждой точки, как показано в приведенном выше коде.

### Можно ли скрыть полосы ошибок для определенных точек данных?

Да, вы можете контролировать видимость полос погрешностей для отдельных точек данных, установив`setVisible` собственность`IErrorBarsFormat` объект.
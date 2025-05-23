---
"description": "Узнайте, как добавлять пользовательские планки погрешностей в диаграммы PowerPoint в Java Slides с помощью Aspose.Slides. Пошаговое руководство с исходным кодом для точной визуализации данных."
"linktitle": "Добавить пользовательскую ошибку в слайды Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Добавить пользовательскую ошибку в слайды Java"
"url": "/ru/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Добавить пользовательскую ошибку в слайды Java


## Введение в добавление пользовательских планок погрешностей в слайды Java с помощью Aspose.Slides

В этом уроке вы узнаете, как добавлять пользовательские планки погрешностей в диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Планки погрешностей полезны для отображения изменчивости или неопределенности в точках данных на диаграмме.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Библиотека Aspose.Slides для Java установлена и настроена в вашем проекте.
- Настроена среда разработки Java.

## Шаг 1: Создайте пустую презентацию

Сначала создайте пустую презентацию PowerPoint.

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
```

## Шаг 2: Добавьте пузырьковую диаграмму

Далее мы добавим в презентацию пузырьковую диаграмму.

```java
// Создание пузырьковой диаграммы
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Шаг 3: Добавьте пользовательские планки погрешностей

Теперь давайте добавим пользовательские планки погрешностей в ряд диаграмм.

```java
// Добавление пользовательских планок погрешностей и настройка их формата
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Шаг 4: Установка данных планок погрешностей

На этом этапе мы получим доступ к точкам данных серии диаграммы и зададим пользовательские значения планок погрешностей для каждой точки.

```java
// Доступ к точкам данных серии диаграмм и установка значений планок погрешностей для отдельных точек
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Установка планок погрешностей для точек серии диаграммы
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Шаг 5: Сохраните презентацию

Наконец, сохраните презентацию с пользовательскими планками погрешностей.

```java
// Сохранение презентации
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно добавили пользовательские планки погрешностей в диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java.

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
	// Добавление пользовательских полос погрешностей и настройка их формата
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Доступ к точкам данных серии диаграмм и установка значений планок погрешностей для отдельных точек
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Установка планок погрешностей для точек серии диаграммы
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

В этом всеобъемлющем руководстве вы узнали, как улучшить презентации PowerPoint, добавляя пользовательские планки погрешностей к диаграммам с помощью Aspose.Slides для Java. Планки погрешностей предоставляют ценную информацию об изменчивости и неопределенности данных, делая ваши диаграммы более информативными и визуально привлекательными.

## Часто задаваемые вопросы

### Как настроить внешний вид планок погрешностей?

Вы можете настроить внешний вид планок погрешностей, изменив свойства `IErrorBarsFormat` объект, такой как стиль линии, цвет линии и ширина полосы погрешности.

### Могу ли я добавлять планки погрешностей к другим типам диаграмм?

Да, вы можете добавлять планки погрешностей к различным типам диаграмм, поддерживаемым Aspose.Slides для Java, включая столбчатые диаграммы, линейные диаграммы и точечные диаграммы.

### Как установить разные значения погрешности для каждой точки данных?

Вы можете перебрать точки данных и задать пользовательские значения планки погрешностей для каждой точки, как показано в коде выше.

### Можно ли скрыть планки погрешностей для определенных точек данных?

Да, вы можете контролировать видимость планок погрешностей для отдельных точек данных, установив `setVisible` собственность `IErrorBarsFormat` объект.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
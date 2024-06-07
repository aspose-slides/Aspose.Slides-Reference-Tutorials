---
title: Добавьте полосы ошибок в слайды Java
linktitle: Добавьте полосы ошибок в слайды Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как добавить полосы ошибок в диаграммы PowerPoint на Java с помощью Aspose.Slides. Пошаговое руководство с исходным кодом для настройки панелей ошибок.
type: docs
weight: 13
url: /ru/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Введение в добавление полос ошибок в слайды Java с использованием Aspose.Slides

В этом уроке мы покажем, как добавить полосы ошибок к диаграмме на слайде PowerPoint с помощью Aspose.Slides для Java. Столбики ошибок предоставляют ценную информацию об изменчивости или неопределенности точек данных на диаграмме. Мы создадим пузырьковую диаграмму и добавим к ней полосы ошибок. Давайте начнем!

## Предварительные условия

 Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем проекте Java. Вы можете скачать библиотеку с сайта[Веб-сайт Aspose](https://downloads.aspose.com/slides/java).

## Шаг 1. Создайте пустую презентацию

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
```

На этом этапе мы создаем пустую презентацию, куда добавим нашу диаграмму с полосами ошибок.

## Шаг 2. Создайте пузырьковую диаграмму

```java
// Создание пузырьковой диаграммы
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Здесь мы создаем пузырьковую диаграмму и указываем ее положение и размеры на слайде.

## Шаг 3. Добавление полос ошибок и настройка формата

```java
// Добавление панели ошибок и установка ее формата
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

На этом этапе мы добавляем на диаграмму полосы ошибок и устанавливаем их формат. Вы можете настроить панели ошибок, изменив значения, типы и другие свойства.

- `errBarX` представляет полосы погрешностей вдоль оси X.
- `errBarY` представляет полосы погрешностей вдоль оси Y.
- Мы делаем видимыми полосы ошибок X и Y.
- `setValueType` указывает тип значения для полос погрешностей (например, «Фиксированный» или «Процент»).
- `setValue` устанавливает значение для планок погрешностей.
- `setType` определяет тип шкалы ошибок (например, «Плюс» или «Минус»).
-  Мы устанавливаем ширину линий шкалы ошибок, используя`getFormat().getLine().setWidth(2)`.
- `setEndCap` указывает, включать ли концевые заглушки в полосы погрешностей.

## Шаг 4. Сохраните презентацию

```java
// Сохранение презентации
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Наконец, мы сохраняем презентацию с добавленными полосами ошибок в указанное место.

Вот и все! Вы успешно добавили полосы ошибок на диаграмму на слайде PowerPoint с помощью Aspose.Slides для Java.

## Полный исходный код для добавления полос ошибок в слайды Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
try
{
	// Создание пузырьковой диаграммы
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Добавление панели ошибок и установка ее формата
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Сохранение презентации
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

В этом уроке мы рассмотрели, как улучшить ваши презентации PowerPoint, добавив полосы ошибок в диаграммы с помощью Aspose.Slides для Java. Столбики ошибок предоставляют ценную информацию об изменчивости и неопределенности данных, делая ваши презентации более информативными и визуально привлекательными.

## Часто задаваемые вопросы

### Как я могу дополнительно настроить внешний вид полос ошибок?

Вы можете настроить панели ошибок, изменив их свойства, такие как стиль линии, цвет и ширина, как показано в шаге 3.

### Могу ли я добавлять полосы ошибок к разным типам диаграмм?

Да, вы можете добавлять полосы ошибок к различным типам диаграмм, поддерживаемым Aspose.Slides для Java. Просто создайте нужный тип диаграммы и выполните те же действия по настройке панели ошибок.

### Как настроить положение и размер диаграммы на слайде?

Вы можете контролировать положение и размеры диаграммы, регулируя параметры в`addChart` метод, как показано в шаге 2.

### Где я могу найти дополнительную информацию об Aspose.Slides для Java?

 Вы можете обратиться к[Документация Aspose.Slides для Java](https://reference.aspose.com/slides/java/) для получения подробной информации об использовании библиотеки.
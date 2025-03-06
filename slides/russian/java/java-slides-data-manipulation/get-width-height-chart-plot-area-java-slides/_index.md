---
title: Получить ширину и высоту из области графика диаграммы в слайдах Java
linktitle: Получить ширину и высоту из области графика диаграммы в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как получить размеры области графика диаграммы в Java Slides с помощью Aspose.Slides для Java. Совершенствуйте свои навыки автоматизации PowerPoint.
type: docs
weight: 21
url: /ru/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## Введение

Диаграммы — это мощный способ визуализации данных в презентациях PowerPoint. Иногда вам может потребоваться узнать размеры области построения диаграммы по разным причинам, например для изменения размера или расположения элементов внутри диаграммы. В этом руководстве будет показано, как получить ширину и высоту области графика с помощью Java и Aspose.Slides для Java.

## Предварительные условия

 Прежде чем мы углубимся в код, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем Java-проекте. Скачать библиотеку можно с сайта Aspose.[здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Настройка среды

Убедитесь, что в ваш проект Java добавлена библиотека Aspose.Slides for Java. Вы можете сделать это, включив библиотеку в зависимости вашего проекта или добавив файл JAR вручную.

## Шаг 2. Создание презентации PowerPoint

Начнем с создания презентации PowerPoint и добавления в нее слайда. Это будет контейнером для нашей диаграммы.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Заменять`"Your Document Directory"` с путем к каталогу вашего документа.

## Шаг 3. Добавление диаграммы

Теперь давайте добавим на слайд гистограмму с кластеризацией. Мы также проверим макет диаграммы.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Этот код создает кластеризованную гистограмму в позиции (100, 100) с размерами (500, 350).

## Шаг 4. Получение размеров области графика

Чтобы получить ширину и высоту области графика диаграммы, мы можем использовать следующий код:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Теперь переменные`x`, `y`, `w` , и`h` содержат соответствующие значения координаты X, координаты Y, ширины и высоты области графика.

## Шаг 5: Сохранение презентации

Наконец, сохраните презентацию с диаграммой.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Обязательно замените`"Chart_out.pptx"` с желаемым именем выходного файла.

## Полный исходный код для получения ширины и высоты из области графика диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Сохранить презентацию с диаграммой
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этой статье мы рассмотрели, как получить ширину и высоту области построения диаграммы в Java Slides с помощью API Aspose.Slides для Java. Эта информация может быть полезна, когда вам нужно динамически настраивать макет диаграмм в презентациях PowerPoint.

## Часто задаваемые вопросы

### Как изменить тип диаграммы на другой, кроме кластеризованных столбцов?

 Вы можете изменить тип диаграммы, заменив`ChartType.ClusteredColumn` с нужным перечислением типа диаграммы, например`ChartType.Line` или`ChartType.Pie`.

### Могу ли я изменить другие свойства диаграммы?

Да, вы можете изменять различные свойства диаграммы, такие как данные, метки и форматирование, с помощью API Aspose.Slides для Java. Более подробную информацию можно найти в документации.

### Подходит ли Aspose.Slides for Java для профессиональной автоматизации PowerPoint?

Да, Aspose.Slides for Java — это мощная библиотека для автоматизации задач PowerPoint в приложениях Java. Он предоставляет комплексные функции для работы с презентациями, слайдами, фигурами, диаграммами и многим другим.

### Как я могу узнать больше об Aspose.Slides для Java?

 Вы можете найти обширную документацию и примеры на странице документации Aspose.Slides for Java.[здесь](https://reference.aspose.com/slides/java/).

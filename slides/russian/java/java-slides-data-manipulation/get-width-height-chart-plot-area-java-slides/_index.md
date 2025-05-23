---
"description": "Узнайте, как получить размеры области построения диаграммы в Java Slides с помощью Aspose.Slides для Java. Улучшите свои навыки автоматизации PowerPoint."
"linktitle": "Получить ширину и высоту области построения диаграммы в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Получить ширину и высоту области построения диаграммы в слайдах Java"
"url": "/ru/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Получить ширину и высоту области построения диаграммы в слайдах Java


## Введение

Диаграммы — это мощный способ визуализации данных в презентациях PowerPoint. Иногда вам может понадобиться узнать размеры области построения диаграммы по разным причинам, например, для изменения размера или перемещения элементов в диаграмме. В этом руководстве будет показано, как получить ширину и высоту области построения с помощью Java и Aspose.Slides для Java.

## Предпосылки

Прежде чем погрузиться в код, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем проекте Java. Вы можете загрузить библиотеку с веб-сайта Aspose [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Настройка среды

Убедитесь, что библиотека Aspose.Slides for Java добавлена в ваш проект Java. Это можно сделать, включив библиотеку в зависимости вашего проекта или вручную добавив файл JAR.

## Шаг 2: Создание презентации PowerPoint

Начнем с создания презентации PowerPoint и добавления в нее слайда. Он будет служить контейнером для нашей диаграммы.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Заменять `"Your Document Directory"` с путем к каталогу ваших документов.

## Шаг 3: Добавление диаграммы

Теперь добавим на слайд кластеризованную столбчатую диаграмму. Также проверим макет диаграммы.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Этот код создает кластеризованную столбчатую диаграмму в позиции (100, 100) с измерениями (500, 350).

## Шаг 4: Получение размеров участка

Чтобы получить ширину и высоту области построения диаграммы, мы можем использовать следующий код:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Теперь переменные `x`, `y`, `w`, и `h` содержат соответствующие значения координаты X, координаты Y, ширины и высоты области графика.

## Шаг 5: Сохранение презентации

Наконец, сохраните презентацию с диаграммой.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Обязательно замените `"Chart_out.pptx"` с желаемым именем выходного файла.

## Полный исходный код для получения ширины и высоты из области построения диаграммы в слайдах Java

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

В этой статье мы рассмотрели, как получить ширину и высоту области построения диаграммы в Java Slides с помощью API Aspose.Slides для Java. Эта информация может быть ценной, когда вам нужно динамически настраивать макет диаграмм в презентациях PowerPoint.

## Часто задаваемые вопросы

### Как изменить тип диаграммы на какой-либо другой, отличный от кластеризованных столбцов?

Вы можете изменить тип диаграммы, заменив `ChartType.ClusteredColumn` с желаемым перечислением типов диаграмм, например `ChartType.Line` или `ChartType.Pie`.

### Могу ли я изменить другие свойства диаграммы?

Да, вы можете изменять различные свойства диаграммы, такие как данные, метки и форматирование, используя API Aspose.Slides for Java. Более подробную информацию см. в документации.

### Подходит ли Aspose.Slides for Java для профессиональной автоматизации PowerPoint?

Да, Aspose.Slides for Java — это мощная библиотека для автоматизации задач PowerPoint в приложениях Java. Она предоставляет комплексные функции для работы с презентациями, слайдами, фигурами, диаграммами и многим другим.

### Как я могу узнать больше об Aspose.Slides для Java?

Подробную документацию и примеры можно найти на странице документации Aspose.Slides для Java. [здесь](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
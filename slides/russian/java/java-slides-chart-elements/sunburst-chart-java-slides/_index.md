---
"description": "Создавайте потрясающие диаграммы Sunburst в Java Slides с помощью Aspose.Slides. Изучите пошаговое создание диаграмм и обработку данных."
"linktitle": "Диаграмма солнечных лучей в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Диаграмма солнечных лучей в слайдах Java"
"url": "/ru/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Диаграмма солнечных лучей в слайдах Java


## Введение в диаграмму Sunburst в слайдах Java с Aspose.Slides

В этом уроке вы узнаете, как создать диаграмму Sunburst в презентации PowerPoint с помощью API Aspose.Slides for Java. Диаграмма Sunburst — это радиальная диаграмма, используемая для представления иерархических данных. Мы предоставим пошаговые инструкции вместе с исходным кодом.

## Предпосылки

Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем проекте Java. Вы можете загрузить библиотеку с [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Импорт необходимых библиотек

Сначала импортируйте необходимые библиотеки для работы с Aspose.Slides и создайте диаграмму Sunburst в своем приложении Java.

```java
import com.aspose.slides.*;
```

## Шаг 2: Инициализация презентации

Инициализируйте презентацию PowerPoint и укажите каталог, в котором будет сохранен файл презентации.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Шаг 3: Создайте диаграмму солнечных лучей

Создаем диаграмму Sunburst на слайде. Указываем положение (X, Y) и размеры (ширина, высота) диаграммы.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Шаг 4: Подготовка данных диаграммы

Удалите все существующие категории и данные серий из диаграммы и создайте книгу данных для диаграммы.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Шаг 5: Определите иерархию диаграммы

Определите иерархическую структуру диаграммы Sunburst. Вы можете добавлять ветви, стебли и листья в качестве категорий.

```java
// Филиал 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Филиал 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Шаг 6: Добавьте данные в диаграмму

Добавьте точки данных в серию диаграмм Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Шаг 7: Сохраните презентацию

Наконец, сохраните презентацию с диаграммой Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Полный исходный код для диаграммы Sunburst в Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//филиал 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//ветвь 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке вы узнали, как создать диаграмму Sunburst в презентации PowerPoint с помощью API Aspose.Slides for Java. Вы увидели, как инициализировать презентацию, создать диаграмму, определить иерархию диаграммы, добавить точки данных и сохранить презентацию. Теперь вы можете использовать эти знания для создания интерактивных и информативных диаграмм Sunburst в своих приложениях Java.

## Часто задаваемые вопросы

### Как настроить внешний вид диаграммы Sunburst?

Вы можете настроить внешний вид диаграммы Sunburst, изменив такие свойства, как цвета, метки и стили. Подробные параметры настройки см. в документации Aspose.Slides.

### Могу ли я добавить больше точек данных на диаграмму?

Да, вы можете добавить больше точек данных на диаграмму, используя `series.getDataPoints().addDataPointForSunburstSeries()` метод для каждой точки данных, которую вы хотите включить.

### Как добавить всплывающие подсказки к диаграмме Sunburst?

Чтобы добавить всплывающие подсказки к диаграмме Sunburst, можно настроить формат метки данных для отображения дополнительной информации, например значений или описаний, при наведении курсора на сегменты диаграммы.

### Можно ли создавать интерактивные диаграммы Sunburst с гиперссылками?

Да, вы можете создавать интерактивные диаграммы Sunburst с гиперссылками, добавляя гиперссылки к определенным элементам или сегментам диаграммы. Подробности добавления гиперссылок см. в документации Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
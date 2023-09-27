---
title: Управление диаграммами свойств в слайдах Java
linktitle: Управление диаграммами свойств в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Научитесь создавать потрясающие диаграммы и управлять свойствами слайдов Java с помощью Aspose.Slides. Пошаговое руководство с исходным кодом для создания мощных презентаций.
type: docs
weight: 13
url: /ru/java/data-manipulation/manage-properties-charts-java-slides/
---

## Введение в управление свойствами и диаграммами в слайдах Java с использованием Aspose.Slides

В этом уроке мы рассмотрим, как управлять свойствами и создавать диаграммы в слайдах Java с помощью Aspose.Slides. Aspose.Slides — мощный Java API для работы с презентациями PowerPoint. Мы рассмотрим пошаговый процесс, включая примеры исходного кода.

## Предварительные условия

 Прежде чем мы начнем, убедитесь, что в вашем проекте установлена и настроена библиотека Aspose.Slides для Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).

## Добавление диаграммы на слайд

Чтобы добавить диаграмму на слайд, выполните следующие действия:

1. Импортируйте необходимые классы и создайте экземпляр класса Presentation.

```java
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
```

2. Откройте слайд, на который вы хотите добавить диаграмму. В этом примере мы получаем доступ к первому слайду.

```java
// Доступ к первому слайду
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Добавьте диаграмму с данными по умолчанию. В данном случае мы добавляем диаграмму StackedColumn3D.

```java
// Добавить диаграмму с данными по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Настройка данных диаграммы

Чтобы установить данные диаграммы, нам нужно создать книгу данных диаграммы и добавить серии и категории. Следуй этим шагам:

4. Установите индекс таблицы данных диаграммы.

```java
// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;
```

5. Получите книгу данных диаграммы.

```java
//Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Добавьте серию на диаграмму. В этом примере мы добавляем две серии с именами «Серия 1» и «Серия 2».

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Добавьте категории в диаграмму. Здесь мы добавляем три категории.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Настройка свойств 3D-вращения

Теперь давайте установим свойства трехмерного вращения диаграммы:

8. Установите оси под прямым углом.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Установите углы поворота для осей X и Y. В этом примере мы поворачиваем X на 40 градусов, а Y на 270 градусов.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Установите процент глубины на 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Заполнение данных серии

11. Возьмите вторую серию диаграмм и заполните ее точками данных.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Заполнение данных серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Настройка перекрытия

12. Установите значение перекрытия для серий. Например, вы можете установить значение 100, чтобы не было перекрытия.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Сохранение презентации

Наконец, сохраните презентацию на диск.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Вот и все! Вы успешно создали трехмерную столбчатую диаграмму с настраиваемыми свойствами с помощью Aspose.Slides в Java.

## Полный исходный код для управления диаграммами свойств в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
// Доступ к первому слайду
ISlide slide = presentation.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;
//Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Добавить серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Добавить категории
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Установить свойства Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Возьмите вторую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Теперь заполняем данные серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Установите значение перекрытия
series.getParentSeriesGroup().setOverlap((byte) 100);
// Записать презентацию на диск
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы углубились в мир управления свойствами и создания диаграмм в слайдах Java с помощью Aspose.Slides. Aspose.Slides — это надежный Java API, который позволяет разработчикам эффективно работать с презентациями PowerPoint. Мы рассмотрели основные шаги и предоставили примеры исходного кода, которые помогут вам в этом процессе.

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

 Вы можете изменить тип диаграммы, изменив`ChartType`параметр при добавлении диаграммы. Обратитесь к документации Aspose.Slides для получения информации о доступных типах диаграмм.

### Могу ли я настроить цвета диаграммы?

Да, вы можете настроить цвета диаграммы, задав свойства заливки точек данных или категорий рядов.

### Как добавить в ряд дополнительные точки данных?

 Вы можете добавить дополнительные точки данных в ряд, используя`series.getDataPoints().addDataPointForBarSeries()` метод и указание ячейки, содержащей значение данных.

### Как установить другой угол поворота?

 Чтобы установить другой угол поворота для осей X и Y, используйте`chart.getRotation3D().setRotationX()` и`chart.getRotation3D().setRotationY()` с желаемыми значениями угла.

### Какие еще 3D-свойства я могу настроить?

Вы можете изучить другие трехмерные свойства диаграммы, такие как глубина, перспектива и освещение, обратившись к документации Aspose.Slides.
---
title: Существующая диаграмма в слайдах Java
linktitle: Существующая диаграмма в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Улучшите свои презентации PowerPoint с помощью Aspose.Slides для Java. Научитесь программно изменять существующие диаграммы. Пошаговое руководство с исходным кодом для настройки диаграммы.
weight: 12
url: /ru/java/chart-elements/existing-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Введение в существующую диаграмму в слайдах Java с использованием Aspose.Slides для Java

В этом уроке мы покажем, как изменить существующую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Мы выполним шаги, чтобы изменить данные диаграммы, имена категорий, названия серий и добавить новую серию в диаграмму. Убедитесь, что в вашем проекте настроен Aspose.Slides for Java.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Библиотека Aspose.Slides для Java, включенная в ваш проект.
2. Существующая презентация PowerPoint с диаграммой, которую вы хотите изменить.
3. Настроена среда разработки Java.

## Шаг 1. Загрузите презентацию

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создать класс презентации, представляющий файл PPTX.
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Шаг 2. Доступ к слайду и диаграмме

```java
// Доступ к первому слайду
ISlide sld = pres.getSlides().get_Item(0);

// Доступ к диаграмме на слайде
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Шаг 3. Измените данные диаграммы и названия категорий

```java
// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;

// Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Изменение названий категорий диаграмм
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Шаг 4. Обновите первую серию диаграмм.

```java
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Обновить название серии
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Обновить данные серии
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Шаг 5. Обновите вторую серию диаграмм.

```java
// Возьмите вторую серию диаграмм.
series = chart.getChartData().getSeries().get_Item(1);

// Обновить название серии
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Обновить данные серии
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Шаг 6. Добавьте новую серию на диаграмму

```java
// Добавляем новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Возьмите третью серию диаграмм.
series = chart.getChartData().getSeries().get_Item(2);

// Заполнение данных серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Шаг 7: Измените тип диаграммы

```java
//Измените тип диаграммы на «Кластерный цилиндр».
chart.setType(ChartType.ClusteredCylinder);
```

## Шаг 8. Сохраните измененную презентацию

```java
// Сохраните презентацию с измененной диаграммой.
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Поздравляем! Вы успешно изменили существующую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Теперь вы можете использовать этот код для программной настройки диаграмм в презентациях PowerPoint.

## Полный исходный код существующей диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Класс создания экземпляра презентации, представляющий файл PPTX // Класс создания экземпляра представления, представляющий файл PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Доступ к первому слайд-маркеру
ISlide sld = pres.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Установка индекса таблицы данных диаграммы
int defaultWorksheetIndex = 0;
// Получение листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Изменение названия категории диаграммы
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Сейчас обновляются данные серии
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Изменение названия серии
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Сейчас обновляются данные серии
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Изменение названия серии
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Теперь добавляю новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Возьмите 3-ю серию диаграмм.
series = chart.getChartData().getSeries().get_Item(2);
// Теперь заполняем данные серии
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Сохранить презентацию с диаграммой
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Заключение

В этом подробном руководстве мы узнали, как изменить существующую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Следуя пошаговому руководству и используя примеры исходного кода, вы можете легко настроить и обновить диаграммы в соответствии с вашими конкретными требованиями. Вот краткий обзор того, что мы рассмотрели:

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

 Вы можете изменить тип диаграммы, используя`chart.setType(ChartType.ChartTypeHere)` метод. Заменять`ChartTypeHere` с желаемым типом диаграммы, например`ChartType.ClusteredCylinder` в нашем примере.

### Могу ли я добавить больше точек данных в ряд?

 Да, вы можете добавить в ряд больше точек данных, используя`series.getDataPoints().addDataPointForBarSeries(cell)` метод. Обязательно укажите соответствующие данные ячейки.

### Как обновить названия категорий?

 Вы можете обновить названия категорий, используя`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` чтобы установить новые имена категорий.

### Как изменить названия серий?

 Чтобы изменить имена серий, используйте`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` чтобы установить названия новых серий.

### Есть ли способ удалить серию из диаграммы?

 Да, вы можете удалить серию из диаграммы, используя`chart.getChartData().getSeries().removeAt(index)` метод, где`index`— это индекс серии, которую вы хотите удалить.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

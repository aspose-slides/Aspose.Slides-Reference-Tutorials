---
"description": "Улучшите свои презентации PowerPoint с помощью Aspose.Slides для Java. Узнайте, как программно изменять существующие диаграммы. Пошаговое руководство с исходным кодом для настройки диаграмм."
"linktitle": "Существующая диаграмма в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Существующая диаграмма в Java Slides"
"url": "/ru/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Существующая диаграмма в Java Slides


## Введение в существующие диаграммы в слайдах Java с использованием Aspose.Slides для Java

В этом уроке мы покажем, как изменить существующую диаграмму в презентации PowerPoint с помощью Aspose.Slides for Java. Мы рассмотрим шаги по изменению данных диаграммы, названий категорий, названий серий и добавлению новой серии в диаграмму. Убедитесь, что в вашем проекте настроен Aspose.Slides for Java.

## Предпосылки

Прежде чем начать, убедитесь, что выполнены следующие предварительные условия:

1. Библиотека Aspose.Slides для Java включена в ваш проект.
2. Существующая презентация PowerPoint с диаграммой, которую вы хотите изменить.
3. Настроена среда разработки Java.

## Шаг 1: Загрузите презентацию

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создать экземпляр класса Presentation, представляющего файл PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Шаг 2: Доступ к слайду и диаграмме

```java
// Доступ к первому слайду
ISlide sld = pres.getSlides().get_Item(0);

// Доступ к диаграмме на слайде
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Шаг 3: Измените данные диаграммы и названия категорий

```java
// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;

// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Изменить названия категорий диаграмм
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Шаг 4: Обновите первую серию диаграмм

```java
// Возьмем первую серию диаграмм.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Обновить название серии
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Обновление данных серии
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Шаг 5: Обновите вторую серию диаграмм

```java
// Возьмем вторую серию диаграмм.
series = chart.getChartData().getSeries().get_Item(1);

// Обновить название серии
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Обновление данных серии
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Шаг 6: Добавьте новую серию в диаграмму

```java
// Добавление новой серии
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Возьмем третью серию диаграмм.
series = chart.getChartData().getSeries().get_Item(2);

// Заполнить ряд данных
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Шаг 7: Измените тип диаграммы

```java
// Измените тип диаграммы на «Кластерный цилиндр».
chart.setType(ChartType.ClusteredCylinder);
```

## Шаг 8: Сохраните измененную презентацию.

```java
// Сохраните презентацию с измененной диаграммой.
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Поздравляем! Вы успешно изменили существующую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Теперь вы можете использовать этот код для настройки диаграмм в ваших презентациях PowerPoint программным способом.

## Полный исходный код для существующей диаграммы в Java Slides

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса презентации, представляющего файл PPTX // Создать экземпляр класса презентации, представляющего файл PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Доступ к первому слайдуМаркер
ISlide sld = pres.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;
// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Изменение названия категории диаграммы
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Возьмите первую серию диаграмм
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Сейчас обновляются данные серий
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Изменение названия серии
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Возьмите вторую серию диаграмм
series = chart.getChartData().getSeries().get_Item(1);
// Сейчас обновляются данные серий
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Изменение названия серии
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Сейчас, добавляем новую серию
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Возьмите 3-ю серию диаграмм
series = chart.getChartData().getSeries().get_Item(2);
// Сейчас заполняем данные серий
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Сохранить презентацию с диаграммой
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Заключение

В этом всеобъемлющем руководстве мы узнали, как изменить существующую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Следуя пошаговому руководству и используя примеры исходного кода, вы можете легко настраивать и обновлять диаграммы в соответствии с вашими конкретными требованиями. Вот краткий обзор того, что мы рассмотрели:

## Часто задаваемые вопросы

### Как изменить тип диаграммы?

Вы можете изменить тип диаграммы, используя `chart.setType(ChartType.ChartTypeHere)` Метод. Заменить `ChartTypeHere` с желаемым типом диаграммы, например `ChartType.ClusteredCylinder` в нашем примере.

### Могу ли я добавить больше точек данных в ряд?

Да, вы можете добавить больше точек данных в ряд, используя `series.getDataPoints().addDataPointForBarSeries(cell)` метод. Обязательно укажите соответствующие данные ячейки.

### Как обновить названия категорий?

Вы можете обновить названия категорий, используя `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` чтобы задать новые названия категорий.

### Как изменить названия серий?

Чтобы изменить названия серий, используйте `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` для установки новых названий серий.

### Есть ли способ удалить серию из диаграммы?

Да, вы можете удалить ряд из диаграммы, используя `chart.getChartData().getSeries().removeAt(index)` метод, где `index` — индекс серии, которую вы хотите удалить.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
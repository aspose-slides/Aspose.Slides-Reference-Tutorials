---
title: Установить данные диаграммы из книги в слайдах Java
linktitle: Установить данные диаграммы из книги в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как установить данные диаграммы из книги Excel в Java Slides с помощью Aspose.Slides. Пошаговое руководство с примерами кода для динамических презентаций.
type: docs
weight: 15
url: /ru/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Введение в установку данных диаграммы из книги в слайдах Java

Aspose.Slides for Java — это мощная библиотека, которая позволяет разработчикам программно работать с презентациями PowerPoint. Он предоставляет обширные возможности для создания, манипулирования и управления слайдами PowerPoint. Одним из распространенных требований при работе с презентациями является динамическая установка данных диаграммы из внешнего источника данных, например книги Excel. В этом уроке мы покажем, как этого добиться с помощью Java.

## Предварительные условия

Прежде чем мы углубимся в реализацию, убедитесь, что у вас есть следующие предварительные условия:

- В вашей системе установлен Java Development Kit (JDK).
- В ваш проект добавлена библиотека Aspose.Slides for Java.
- Книга Excel с данными, которые вы хотите использовать для диаграммы.

## Шаг 1. Создайте презентацию

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
```

Начнем с создания новой презентации PowerPoint с использованием Aspose.Slides для Java.

## Шаг 2. Добавьте диаграмму

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Далее мы добавляем диаграмму на один из слайдов презентации. В этом примере мы добавляем круговую диаграмму, но вы можете выбрать тип диаграммы, который соответствует вашим потребностям.

## Шаг 3. Очистите данные диаграммы

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Мы удаляем все существующие данные из диаграммы, чтобы подготовить их для новых данных из книги Excel.

## Шаг 4. Загрузите книгу Excel

```java
Workbook workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
```

 Мы загружаем книгу Excel, содержащую данные, которые мы хотим использовать для диаграммы. Заменять`"book1.xlsx"` с путем к вашему файлу Excel.

## Шаг 5. Запись потока книги в данные диаграммы

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Мы преобразуем данные книги Excel в поток и записываем их в данные диаграммы.

## Шаг 6: Установите диапазон данных диаграммы

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Указываем диапазон ячеек из книги Excel, которые следует использовать в качестве данных для диаграммы. Отрегулируйте диапазон по мере необходимости для ваших данных.

## Шаг 7. Настройка серии диаграмм

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Вы можете настроить различные свойства серии диаграмм в соответствии со своими требованиями. В этом примере мы включаем различные цвета для серии диаграмм.

## Шаг 8: Сохраните презентацию

```java
pres.save(outPath, SaveFormat.Pptx);
```

Наконец, мы сохраняем презентацию с обновленными данными диаграммы в указанном пути вывода.

## Полный исходный код для набора данных диаграммы из книги в слайдах Java

```java
String outPath = RunExamples.getOutPath() + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook(RunExamples.getDataDir_Charts() + "book1.xlsx");
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы узнали, как установить данные диаграммы из книги Excel в слайдах Java с помощью библиотеки Aspose.Slides для Java. Следуя пошаговому руководству и используя предоставленные примеры исходного кода, вы можете легко интегрировать данные динамических диаграмм в свои презентации PowerPoint.

## Часто задаваемые вопросы

### Как настроить внешний вид диаграммы в презентации?

Вы можете настроить внешний вид диаграммы, изменив такие свойства, как цвета, шрифты, метки и т. д. Подробную информацию о параметрах настройки диаграммы см. в документации Aspose.Slides for Java.

### Могу ли я использовать для диаграммы данные из другого файла Excel?

Да, вы можете использовать данные из любого файла Excel, указав правильный путь к файлу при загрузке книги в коде.

### Какие еще типы диаграмм я могу создавать с помощью Aspose.Slides для Java?

Aspose.Slides for Java поддерживает различные типы диаграмм, включая гистограммы, линейные диаграммы, точечные диаграммы и многое другое. Вы можете выбрать тип диаграммы, который лучше всего соответствует вашим потребностям в представлении данных.

### Можно ли динамически обновлять данные диаграммы в работающей презентации?

Да, вы можете динамически обновлять данные диаграммы в презентации, изменяя базовую книгу, а затем обновляя данные диаграммы.

### Где я могу найти больше примеров и ресурсов для работы с Aspose.Slides для Java?

 Вы можете изучить дополнительные примеры и ресурсы на странице[Веб-сайт Aspose](https://www.aspose.com/). Кроме того, документация Aspose.Slides for Java содержит подробные инструкции по работе с библиотекой.
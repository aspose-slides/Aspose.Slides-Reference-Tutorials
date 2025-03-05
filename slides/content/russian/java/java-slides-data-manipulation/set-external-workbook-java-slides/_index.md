---
title: Установить внешнюю книгу в слайдах Java
linktitle: Установить внешнюю книгу в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как настроить внешние книги в слайдах Java с помощью Aspose.Slides для Java. Создавайте динамические презентации с интеграцией данных Excel.
type: docs
weight: 19
url: /ru/java/data-manipulation/set-external-workbook-java-slides/
---

## Введение в настройку внешней книги в слайдах Java

В этом уроке мы рассмотрим, как настроить внешнюю книгу в Java Slides с помощью Aspose.Slides. Вы узнаете, как создать презентацию PowerPoint с диаграммой, ссылающейся на данные из внешней книги Excel. К концу этого руководства вы получите четкое представление о том, как интегрировать внешние данные в презентации Java Slides.

## Предварительные условия

Прежде чем мы углубимся в реализацию, убедитесь, что у вас есть следующие предварительные условия:

- В вашей системе установлен Java Development Kit (JDK).
- В ваш проект добавлена библиотека Aspose.Slides for Java.
- Книга Excel с данными, которые вы хотите использовать в своей презентации.

## Шаг 1. Создайте новую презентацию

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Начнем с создания новой презентации PowerPoint с помощью Aspose.Slides.

## Шаг 2. Добавьте диаграмму

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Далее вставляем в презентацию круговую диаграмму. При необходимости вы можете настроить тип и положение диаграммы.

## Шаг 3. Доступ к внешней книге

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Для доступа к внешней книге мы используем команду`setExternalWorkbook` метод и укажите путь к книге Excel, содержащей данные.

## Шаг 4. Привязка данных диаграммы

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Мы привязываем диаграмму к данным из внешней книги, указывая ссылки на ячейки для серий и категорий.

## Шаг 5. Сохраните презентацию

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Наконец, мы сохраняем презентацию со ссылкой на внешнюю книгу в виде файла PowerPoint.

## Полный исходный код для установки внешней книги в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы узнали, как настроить внешнюю книгу в Java Slides с помощью Aspose.Slides. Теперь вы можете создавать презентации, динамически ссылающиеся на данные из книг Excel, что повышает гибкость и интерактивность ваших слайдов.

## Часто задаваемые вопросы

### Как установить Aspose.Slides для Java?

Aspose.Slides for Java можно установить, добавив библиотеку в ваш Java-проект. Вы можете скачать библиотеку с сайта Aspose и следовать инструкциям по установке, приведенным в документации.

### Могу ли я использовать разные типы диаграмм с внешними книгами?

Да, вы можете использовать различные типы диаграмм, поддерживаемые Aspose.Slides, и привязывать их к данным из внешних книг. Процесс может незначительно отличаться в зависимости от выбранного типа диаграммы.

### Что делать, если структура данных моей внешней книги изменится?

Если структура данных внешней книги изменится, вам может потребоваться обновить ссылки на ячейки в коде Java, чтобы гарантировать точность данных диаграммы.

### Совместим ли Aspose.Slides с последними версиями Java?

Aspose.Slides для Java регулярно обновляется, чтобы обеспечить совместимость с последними версиями Java. Обязательно проверяйте наличие обновлений и используйте последнюю версию библиотеки для оптимальной производительности и совместимости.

### Могу ли я добавить несколько диаграмм, ссылающихся на одну и ту же внешнюю книгу?

Да, вы можете добавить в презентацию несколько диаграмм, каждая из которых ссылается на одну и ту же внешнюю книгу. Просто повторите шаги, описанные в этом руководстве, для каждой диаграммы, которую вы хотите создать.
---
"description": "Узнайте, как устанавливать внешние рабочие книги в Java Slides с помощью Aspose.Slides для Java. Создавайте динамические презентации с интеграцией данных Excel."
"linktitle": "Установить внешнюю рабочую книгу в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Установить внешнюю рабочую книгу в Java Slides"
"url": "/ru/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Установить внешнюю рабочую книгу в Java Slides


## Введение в установку внешней рабочей книги в слайдах Java

В этом руководстве мы рассмотрим, как настроить внешнюю книгу в Java Slides с помощью Aspose.Slides. Вы узнаете, как создать презентацию PowerPoint с диаграммой, которая ссылается на данные из внешней книги Excel. К концу этого руководства у вас будет четкое понимание того, как интегрировать внешние данные в ваши презентации Java Slides.

## Предпосылки

Прежде чем приступить к реализации, убедитесь, что у вас выполнены следующие предварительные условия:

- В вашей системе установлен Java Development Kit (JDK).
- Библиотека Aspose.Slides для Java добавлена в ваш проект.
- Книга Excel с данными, на которые вы хотите ссылаться в своей презентации.

## Шаг 1: Создайте новую презентацию

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Начнем с создания новой презентации PowerPoint с помощью Aspose.Slides.

## Шаг 2: Добавьте диаграмму

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Далее мы вставляем в презентацию круговую диаграмму. Вы можете настроить тип диаграммы и ее положение по своему усмотрению.

## Шаг 3: Доступ к внешней рабочей книге

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Для доступа к внешней рабочей книге мы используем `setExternalWorkbook` метод и укажите путь к книге Excel, содержащей данные.

## Шаг 4: Привязка данных диаграммы

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Мы привязываем диаграмму к данным из внешней книги, указывая ссылки на ячейки для рядов и категорий.

## Шаг 5: Сохраните презентацию

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Наконец, мы сохраняем презентацию со ссылкой на внешнюю книгу как файл PowerPoint.

## Полный исходный код для установки внешней рабочей книги в слайдах Java

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

В этом уроке мы узнали, как установить внешнюю книгу в Java Slides с помощью Aspose.Slides. Теперь вы можете создавать презентации, которые динамически ссылаются на данные из книг Excel, повышая гибкость и интерактивность ваших слайдов.

## Часто задаваемые вопросы

### Как установить Aspose.Slides для Java?

Aspose.Slides для Java можно установить, добавив библиотеку в свой проект Java. Вы можете загрузить библиотеку с веб-сайта Aspose и следовать инструкциям по установке, приведенным в документации.

### Могу ли я использовать разные типы диаграмм во внешних рабочих книгах?

Да, вы можете использовать различные типы диаграмм, поддерживаемые Aspose.Slides, и привязывать их к данным из внешних рабочих книг. Процесс может немного отличаться в зависимости от выбранного вами типа диаграммы.

### Что делать, если структура данных моей внешней книги изменится?

Если структура данных внешней рабочей книги изменится, вам может потребоваться обновить ссылки на ячейки в коде Java, чтобы гарантировать точность данных диаграммы.

### Совместим ли Aspose.Slides с последними версиями Java?

Aspose.Slides for Java регулярно обновляется для обеспечения совместимости с последними версиями Java. Обязательно проверяйте наличие обновлений и используйте последнюю версию библиотеки для оптимальной производительности и совместимости.

### Можно ли добавить несколько диаграмм, ссылающихся на одну и ту же внешнюю книгу?

Да, вы можете добавить несколько диаграмм в свою презентацию, ссылаясь на одну и ту же внешнюю книгу. Просто повторите шаги, описанные в этом руководстве, для каждой диаграммы, которую вы хотите создать.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
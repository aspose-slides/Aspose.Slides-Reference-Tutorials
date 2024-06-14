---
title: Свойства шрифта для отдельной легенды в слайдах Java
linktitle: Свойства шрифта для отдельной легенды в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Улучшайте презентации PowerPoint с помощью пользовательских стилей, размеров и цветов шрифтов для отдельных легенд в слайдах Java с помощью Aspose.Slides для Java.
type: docs
weight: 12
url: /ru/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

## Введение в свойства шрифта для отдельных легенд в слайдах Java

В этом уроке мы рассмотрим, как установить свойства шрифта для отдельной легенды в Java Slides с помощью Aspose.Slides для Java. Настраивая свойства шрифта, вы можете сделать легенды в презентациях PowerPoint более привлекательными и информативными.

## Предварительные условия

 Прежде чем начать, убедитесь, что в ваш проект интегрирована библиотека Aspose.Slides for Java. Вы можете скачать его с сайта[Документация Aspose.Slides для Java](https://reference.aspose.com/slides/java/).

## Шаг 1. Инициализируйте презентацию и добавьте диаграмму

Во-первых, давайте начнем с инициализации презентации PowerPoint и добавления в нее диаграммы. В этом примере мы будем использовать кластерную гистограмму в качестве иллюстрации.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Остальная часть кода находится здесь
} finally {
    if (pres != null) pres.dispose();
}
```

 Заменять`"Your Document Directory"` с фактическим каталогом, в котором находится ваш документ PowerPoint.

## Шаг 2. Настройте свойства шрифта для легенды

Теперь давайте настроим свойства шрифта для отдельной записи легенды на диаграмме. В этом примере мы ориентируемся на вторую запись легенды (индекс 1), но вы можете настроить индекс в соответствии с вашими конкретными требованиями.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Вот что делает каждая строка кода:

- `get_Item(1)` извлекает вторую запись легенды (индекс 1). Вы можете изменить индекс, чтобы выбрать другую запись легенды.
- `setFontBold(NullableBool.True)` устанавливает шрифт полужирным.
- `setFontHeight(20)` устанавливает размер шрифта 20 пунктов.
- `setFontItalic(NullableBool.True)` устанавливает шрифт курсивом.
- `setFillType(FillType.Solid)` указывает, что текст записи легенды должен иметь сплошную заливку.
- `getSolidFillColor().setColor(Color.BLUE)` устанавливает синий цвет заливки. Вы можете заменить`Color.BLUE` с желаемым цветом.

## Шаг 3. Сохраните измененную презентацию

Наконец, сохраните измененную презентацию в новом файле, чтобы сохранить изменения.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Заменять`"output.pptx"` с предпочтительным именем выходного файла.

Вот и все! Вы успешно настроили свойства шрифта для отдельной записи легенды в презентации Java Slides с помощью Aspose.Slides for Java.

## Полный исходный код свойств шрифта для отдельных легенд в слайдах Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке мы узнали, как настроить свойства шрифта для отдельной легенды в Java Slides с помощью Aspose.Slides для Java. Настраивая стили, размеры и цвета шрифтов, вы можете повысить визуальную привлекательность и четкость своих презентаций PowerPoint.

## Часто задаваемые вопросы

### Как я могу изменить цвет шрифта?

 Чтобы изменить цвет шрифта, используйте`tf.getPortionFormat().getFontColor().setColor(yourColor)` вместо изменения цвета заливки. Заменять`yourColor` с желаемым цветом шрифта.

### Как изменить другие свойства легенды?

Вы можете изменить различные другие свойства легенды, такие как положение, размер и формат. Подробную информацию о работе с легендами см. в документации Aspose.Slides for Java.

### Могу ли я применить эти изменения к нескольким записям легенды?

 Да, вы можете просматривать записи легенды и применять эти изменения к нескольким записям, корректируя индекс в`get_Item(index)` и повторение кода настройки.

Не забудьте удалить объект презентации, когда закончите освобождать ресурсы:

```java
if (pres != null) pres.dispose();
```
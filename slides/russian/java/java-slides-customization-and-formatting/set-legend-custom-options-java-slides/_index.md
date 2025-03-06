---
title: Установка пользовательских параметров легенды в слайдах Java
linktitle: Установка пользовательских параметров легенды в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как настроить пользовательские параметры легенды в слайдах Java с помощью Aspose.Slides для Java. Настройте положение и размер легенды на диаграммах PowerPoint.
weight: 14
url: /ru/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Введение в установку пользовательских параметров легенды в слайдах Java

В этом уроке мы покажем, как настроить свойства легенды диаграммы в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете изменить положение, размер и другие атрибуты легенды в соответствии с потребностями вашей презентации.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлен Aspose.Slides для Java API.
- Настроена среда разработки Java.

## Шаг 1. Импортируйте необходимые классы:

```java
// Импортируйте Aspose.Slides для классов Java
import com.aspose.slides.*;
```

## Шаг 2. Укажите путь к папке с вашими документами:

```java
String dataDir = "Your Document Directory";
```

##  Шаг 3. Создайте экземпляр`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Шаг 4. Добавьте слайд в презентацию:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Шаг 5. Добавьте на слайд гистограмму с кластеризацией:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Шаг 6. Установите свойства легенды:

- Установите положение легенды по оси X (относительно ширины диаграммы):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Установите положение легенды по оси Y (относительно высоты диаграммы):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Установите ширину легенды (относительно ширины диаграммы):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Установите высоту легенды (относительно высоты диаграммы):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Шаг 7: Сохраните презентацию на диск:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Вот и все! Вы успешно настроили свойства легенды диаграммы в презентации PowerPoint с помощью Aspose.Slides для Java.

## Полный исходный код для установки пользовательских параметров легенды в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
try
{
	// Получить ссылку на слайд
	ISlide slide = presentation.getSlides().get_Item(0);
	// Добавьте кластеризованную столбчатую диаграмму на слайд
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Установить свойства легенды
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Записать презентацию на диск
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Заключение

В этом уроке мы узнали, как настроить свойства легенды диаграммы в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете изменить положение, размер и другие атрибуты легенды, чтобы создать визуально привлекательные и информативные презентации.

## Часто задаваемые вопросы

## Как изменить положение легенды?

 Чтобы изменить положение легенды, используйте`setX` и`setY` методы объекта легенды. Значения указаны относительно ширины и высоты диаграммы.

## Как настроить размер легенды?

 Вы можете настроить размер легенды, используя`setWidth` и`setHeight` методы объекта легенды. Эти значения также относятся к ширине и высоте диаграммы.

## Могу ли я настроить другие атрибуты легенды?

Да, вы можете настроить различные атрибуты легенды, такие как стиль шрифта, рамка, цвет фона и т. д. Изучите документацию Aspose.Slides для получения подробной информации о дальнейшей настройке легенд.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

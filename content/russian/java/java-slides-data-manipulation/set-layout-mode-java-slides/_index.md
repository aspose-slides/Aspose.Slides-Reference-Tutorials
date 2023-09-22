---
title: Установить режим макета в слайдах Java
linktitle: Установить режим макета в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как установить режимы макета для слайдов Java с помощью Aspose.Slides. Настройте расположение и размер диаграммы в этом пошаговом руководстве с исходным кодом.
type: docs
weight: 23
url: /ru/java/data-manipulation/set-layout-mode-java-slides/
---

## Введение в установку режима макета в слайдах Java

В этом уроке мы узнаем, как установить режим макета диаграммы в слайдах Java с помощью Aspose.Slides для Java. Режим макета определяет расположение и размер диаграммы на слайде.

## Предварительные условия

 Прежде чем мы начнем, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем Java-проекте. Вы можете скачать библиотеку с[здесь](https://releases.aspose.com/slides/java/).

## Шаг 1. Создайте презентацию

Сначала нам нужно создать новую презентацию.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Шаг 2. Добавьте слайд и диаграмму

Далее мы добавим к нему слайд и диаграмму. В этом примере мы создадим кластеризованную столбчатую диаграмму.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Шаг 3. Установите макет диаграммы

 Теперь давайте настроим макет диаграммы. Мы отрегулируем положение и размер диаграммы на слайде с помощью`setX`, `setY`, `setWidth`, `setHeight` методы. Дополнительно мы установим`LayoutTargetType` для определения режима макета.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

В этом примере мы установили для диаграммы целевой тип макета «Внутренний», что означает, что она будет расположена и иметь размер относительно внутренней области слайда.

## Шаг 4. Сохраните презентацию

Наконец, сохраним презентацию с настройками макета диаграммы.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Полный исходный код для установки режима макета в слайдах Java

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

В этом уроке мы узнали, как установить режим макета диаграммы в слайдах Java с помощью Aspose.Slides для Java. Вы можете настроить положение и размер диаграммы в соответствии с вашими требованиями, изменив значения в`setX`, `setY`, `setWidth`, `setHeight` , и`setLayoutTargetType` методы. Это дает вам контроль над размещением диаграмм на слайдах.

## Часто задаваемые вопросы

### Как изменить режим макета диаграммы в Aspose.Slides для Java?

 Чтобы изменить режим макета диаграммы в Aspose.Slides для Java, вы можете использовать`setLayoutTargetType` метод в области графика диаграммы. Вы можете установить его либо`LayoutTargetType.Inner` или`LayoutTargetType.Outer` в зависимости от желаемой планировки.

### Могу ли я настроить положение и размер диаграммы на слайде?

 Да, вы можете настроить положение и размер диаграммы на слайде, используя`setX`, `setY`, `setWidth` , и`setHeight` методы в области графика диаграммы. Отрегулируйте эти значения, чтобы расположить и изменить размер диаграммы в соответствии с вашими требованиями.

### Где я могу найти дополнительную информацию об Aspose.Slides для Java?

 Дополнительную информацию об Aspose.Slides для Java можно найти в[документация](https://reference.aspose.com/slides/java/)Он включает подробные ссылки и примеры API, которые помогут вам эффективно работать со слайдами и диаграммами в Java.
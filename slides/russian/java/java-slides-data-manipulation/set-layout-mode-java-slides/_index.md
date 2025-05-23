---
"description": "Узнайте, как устанавливать режимы макета для слайдов Java с помощью Aspose.Slides. Настройте расположение и размер диаграммы в этом пошаговом руководстве с исходным кодом."
"linktitle": "Установить режим макета в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Установить режим макета в Java Slides"
"url": "/ru/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Установить режим макета в Java Slides


## Введение в установку режима макета в Java Slides

В этом уроке мы научимся устанавливать режим макета для диаграммы в слайдах Java с помощью Aspose.Slides для Java. Режим макета определяет положение и размер диаграммы на слайде.

## Предпосылки

Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем проекте Java. Вы можете загрузить библиотеку с [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Создайте презентацию

Для начала нам нужно создать новую презентацию.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Шаг 2: Добавьте слайд и диаграмму

Далее мы добавим слайд и диаграмму к нему. В этом примере мы создадим кластеризованную столбчатую диаграмму.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Шаг 3: Настройте макет диаграммы

Теперь давайте настроим макет для диаграммы. Мы настроим положение и размер диаграммы на слайде с помощью `setX`, `setY`, `setWidth`, `setHeight` методы. Кроме того, мы установим `LayoutTargetType` для определения режима макета.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

В этом примере мы установили для диаграммы целевой тип макета «Внутренний», что означает, что она будет позиционироваться и иметь размер относительно внутренней области слайда.

## Шаг 4: Сохраните презентацию

Наконец, сохраним презентацию с настройками макета диаграммы.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Полный исходный код для установки режима макета в Java Slides

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

В этом уроке мы узнали, как установить режим макета для диаграммы в слайдах Java с помощью Aspose.Slides для Java. Вы можете настроить положение и размер диаграммы в соответствии с вашими конкретными требованиями, отрегулировав значения в `setX`, `setY`, `setWidth`, `setHeight`, и `setLayoutTargetType` методы. Это дает вам контроль над размещением диаграмм на слайдах.

## Часто задаваемые вопросы

### Как изменить режим макета диаграммы в Aspose.Slides для Java?

Чтобы изменить режим макета диаграммы в Aspose.Slides для Java, вы можете использовать `setLayoutTargetType` Метод на области построения диаграммы. Вы можете установить его на `LayoutTargetType.Inner` или `LayoutTargetType.Outer` в зависимости от желаемой планировки.

### Могу ли я настроить положение и размер диаграммы на слайде?

Да, вы можете настроить положение и размер диаграммы на слайде с помощью `setX`, `setY`, `setWidth`, и `setHeight` методы в области построения диаграммы. Отрегулируйте эти значения, чтобы расположить и изменить размер диаграммы в соответствии с вашими требованиями.

### Где я могу найти более подробную информацию об Aspose.Slides для Java?

Более подробную информацию об Aspose.Slides для Java можно найти в [документация](https://reference.aspose.com/slides/java/). Он содержит подробные справочные материалы по API и примеры, которые помогут вам эффективно работать со слайдами и диаграммами в Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Узнайте, как добавлять планки погрешностей в диаграммы PowerPoint в Java с помощью Aspose.Slides. Пошаговое руководство с исходным кодом для настройки планок погрешностей."
"linktitle": "Добавить планки погрешностей в слайды Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Добавить планки погрешностей в слайды Java"
"url": "/ru/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Добавить планки погрешностей в слайды Java


## Введение в добавление планок погрешностей в слайды Java с помощью Aspose.Slides

В этом уроке мы покажем, как добавить планки погрешностей на диаграмму в слайде PowerPoint с помощью Aspose.Slides для Java. Планки погрешностей предоставляют ценную информацию об изменчивости или неопределенности точек данных на диаграмме. Мы создадим пузырьковую диаграмму и добавим в нее планки погрешностей. Давайте начнем!

## Предпосылки

Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем проекте Java. Вы можете загрузить библиотеку с [Сайт Aspose](https://downloads.aspose.com/slides/java).

## Шаг 1: Создайте пустую презентацию

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
```

На этом этапе мы создадим пустую презентацию, куда добавим нашу диаграмму с планками погрешностей.

## Шаг 2: Создайте пузырьковую диаграмму

```java
// Создание пузырьковой диаграммы
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Здесь мы создаем пузырьковую диаграмму и указываем ее положение и размеры на слайде.

## Шаг 3: Добавление планок погрешностей и настройка формата

```java
// Добавление планок погрешностей и настройка их формата
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

На этом этапе мы добавляем полосы погрешностей на диаграмму и задаем их формат. Вы можете настроить полосы погрешностей, изменив значения, типы и другие свойства.

- `errBarX` представляет собой полосы погрешностей по оси X.
- `errBarY` представляет собой полосы погрешностей по оси Y.
- Мы делаем видимыми планки погрешностей как по оси X, так и по оси Y.
- `setValueType` указывает тип значения для планок погрешностей (например, фиксированный или процентный).
- `setValue` устанавливает значение для планок погрешностей.
- `setType` определяет тип планок погрешностей (например, «плюс» или «минус»).
- Мы устанавливаем ширину линий погрешности с помощью `getFormat().getLine().setWidth(2)`.
- `setEndCap` указывает, следует ли включать конечные заглушки в планки погрешностей.

## Шаг 4: Сохраните презентацию

```java
// Сохранение презентации
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Наконец, мы сохраняем презентацию с добавленными планками погрешностей в указанном месте.

Вот и все! Вы успешно добавили планки погрешностей в диаграмму на слайде PowerPoint с помощью Aspose.Slides для Java.

## Полный исходный код для добавления планок погрешностей в слайды Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создание пустой презентации
Presentation presentation = new Presentation();
try
{
	// Создание пузырьковой диаграммы
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Добавление планок погрешностей и настройка их формата
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Сохранение презентации
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

В этом уроке мы рассмотрели, как улучшить ваши презентации PowerPoint, добавив планки погрешностей к диаграммам с помощью Aspose.Slides для Java. Планки погрешностей предоставляют ценную информацию об изменчивости и неопределенности данных, делая ваши презентации более информативными и визуально привлекательными.

## Часто задаваемые вопросы

### Как можно еще больше настроить внешний вид планок погрешностей?

Вы можете настроить планки погрешностей, изменив их свойства, такие как стиль линии, цвет и ширину, как показано в шаге 3.

### Можно ли добавлять планки погрешностей к разным типам диаграмм?

Да, вы можете добавлять планки погрешностей к различным типам диаграмм, поддерживаемым Aspose.Slides для Java. Просто создайте нужный тип диаграммы и следуйте тем же шагам настройки планки погрешностей.

### Как изменить положение и размер диаграммы на слайде?

Вы можете контролировать положение и размеры диаграммы, настраивая параметры в `addChart` метод, как показано в Шаге 2.

### Где я могу найти более подробную информацию об Aspose.Slides для Java?

Вы можете обратиться к [Aspose.Slides для документации Java](https://reference.aspose.com/slides/java/) для получения подробной информации об использовании библиотеки.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
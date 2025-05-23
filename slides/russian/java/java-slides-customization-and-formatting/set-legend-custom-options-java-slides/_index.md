---
"description": "Узнайте, как задать пользовательские параметры легенды в Java Slides с помощью Aspose.Slides для Java. Настройте положение и размер легенды в диаграммах PowerPoint."
"linktitle": "Установка пользовательских параметров легенды в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Установка пользовательских параметров легенды в слайдах Java"
"url": "/ru/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Установка пользовательских параметров легенды в слайдах Java


## Введение в настройку пользовательских параметров легенды в слайдах Java

В этом уроке мы покажем, как настроить свойства легенды диаграммы в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете изменить положение легенды, ее размер и другие атрибуты в соответствии с потребностями вашей презентации.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

- Установлен API Aspose.Slides для Java.
- Настроена среда разработки Java.

## Шаг 1: Импорт необходимых классов:

```java
// Импорт Aspose.Slides для классов Java
import com.aspose.slides.*;
```

## Шаг 2: Укажите путь к каталогу ваших документов:

```java
String dataDir = "Your Document Directory";
```

## Шаг 3: Создайте экземпляр `Presentation` сорт:

```java
Presentation presentation = new Presentation();
```

## Шаг 4: Добавьте слайд в презентацию:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Шаг 5: Добавьте на слайд кластеризованную столбчатую диаграмму:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Шаг 6. Задайте свойства легенды:

- Установите X-положение легенды (относительно ширины диаграммы):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Установите Y-положение легенды (относительно высоты диаграммы):

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
// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
try
{
	// Получить ссылку на слайд
	ISlide slide = presentation.getSlides().get_Item(0);
	// Добавьте на слайд кластеризованную столбчатую диаграмму
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

В этом уроке мы узнали, как настроить свойства легенды диаграммы в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете изменить положение легенды, ее размер и другие атрибуты, чтобы создать визуально привлекательные и информативные презентации.

## Часто задаваемые вопросы

## Как изменить положение легенды?

Чтобы изменить положение легенды, используйте `setX` и `setY` методы объекта легенды. Значения указываются относительно ширины и высоты диаграммы.

## Как изменить размер легенды?

Вы можете настроить размер легенды с помощью `setWidth` и `setHeight` методы объекта легенды. Эти значения также относятся к ширине и высоте диаграммы.

## Могу ли я настроить другие атрибуты легенды?

Да, вы можете настроить различные атрибуты легенды, такие как стиль шрифта, граница, цвет фона и т. д. Изучите документацию Aspose.Slides для получения подробной информации о дальнейшей настройке легенд.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
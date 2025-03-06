---
title: Дыра в виде кольцевой диаграммы в слайдах Java
linktitle: Дыра в виде кольцевой диаграммы в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Создавайте кольцевые диаграммы с нестандартными размерами отверстий в слайдах Java, используя Aspose.Slides для Java. Пошаговое руководство с исходным кодом для настройки диаграммы.
weight: 11
url: /ru/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Введение в кольцевую диаграмму с дыркой в слайдах Java

В этом уроке мы покажем вам, как создать кольцевую диаграмму с отверстием с помощью Aspose.Slides для Java. Это пошаговое руководство проведет вас через весь процесс с примерами исходного кода.

## Предварительные условия

 Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем Java-проекте. Вы можете скачать его с сайта[Документация Aspose.Slides для Java](https://reference.aspose.com/slides/java/).

## Шаг 1. Импортируйте необходимые библиотеки

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Шаг 2. Инициализируйте презентацию

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 3. Создайте кольцевую диаграмму

```java
try {
    // Создайте кольцевую диаграмму на первом слайде
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Установите размер отверстия в кольцевой диаграмме (в процентах)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Сохраните презентацию на диск
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Удалить объект презентации
    if (presentation != null) presentation.dispose();
}
```

## Шаг 4. Запустите код

 Запустите код Java в интегрированной среде разработки или текстовом редакторе, чтобы создать кольцевую диаграмму с указанным размером отверстий. Обязательно замените`"Your Document Directory"` с фактическим путем, по которому вы хотите сохранить презентацию.

## Полный исходный код для отверстия кольцевой диаграммы в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создайте экземпляр класса Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Записать презентацию на диск
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Заключение

 В этом уроке вы узнали, как создать кольцевую диаграмму с отверстием с помощью Aspose.Slides для Java. Вы можете настроить размер отверстия, отрегулировав`setDoughnutHoleSize` параметр метода.

## Часто задаваемые вопросы

### Как изменить цвет сегментов диаграммы?

 Чтобы изменить цвет сегментов диаграммы, вы можете использовать`setDataPointsInLegend` метод на`IChart` объект и установите желаемый цвет для каждой точки данных.

### Могу ли я добавлять метки к сегментам кольцевой диаграммы?

 Да, вы можете добавлять метки к сегментам кольцевой диаграммы, используя`setDataPointsLabelValue` метод на`IChart` объект.

### Можно ли добавить заголовок к диаграмме?

 Конечно! Вы можете добавить заголовок к диаграмме, используя`setTitle` метод на`IChart` объект и предоставление желаемого текста заголовка.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

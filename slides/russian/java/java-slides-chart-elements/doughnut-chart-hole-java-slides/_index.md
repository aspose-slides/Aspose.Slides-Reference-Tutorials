---
"description": "Создание кольцевых диаграмм с пользовательскими размерами отверстий в Java Slides с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом для настройки диаграмм."
"linktitle": "Дыра в кольцевой диаграмме в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Дыра в кольцевой диаграмме в слайдах Java"
"url": "/ru/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Дыра в кольцевой диаграмме в слайдах Java


## Введение в кольцевую диаграмму с отверстием в Java Slides

В этом уроке мы покажем вам, как создать кольцевую диаграмму с отверстием, используя Aspose.Slides для Java. Это пошаговое руководство проведет вас через весь процесс с примерами исходного кода.

## Предпосылки

Прежде чем начать, убедитесь, что у вас установлена и настроена библиотека Aspose.Slides for Java в вашем проекте Java. Вы можете загрузить ее с [Aspose.Slides для документации Java](https://reference.aspose.com/slides/java/).

## Шаг 1: Импорт необходимых библиотек

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Шаг 2: Инициализация презентации

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создать экземпляр класса Presentation
Presentation presentation = new Presentation();
```

## Шаг 3: Создание кольцевой диаграммы

```java
try {
    // Создайте кольцевую диаграмму на первом слайде
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Установите размер отверстия в кольцевой диаграмме (в процентах)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Сохранить презентацию на диск
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Утилизировать презентационный объект
    if (presentation != null) presentation.dispose();
}
```

## Шаг 4: Запустите код

Запустите код Java в IDE или текстовом редакторе, чтобы создать кольцевую диаграмму с указанным размером отверстия. Обязательно замените `"Your Document Directory"` на фактический путь, по которому вы хотите сохранить презентацию.

## Полный исходный код для кольцевой диаграммы Hole в Java Slides

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation
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

В этом уроке вы узнали, как создать кольцевую диаграмму с отверстием с помощью Aspose.Slides для Java. Вы можете настроить размер отверстия, отрегулировав `setDoughnutHoleSize` параметр метода.

## Часто задаваемые вопросы

### Как изменить цвет сегментов диаграммы?

Чтобы изменить цвет сегментов диаграммы, вы можете использовать `setDataPointsInLegend` метод на `IChart` объект и установите желаемый цвет для каждой точки данных.

### Могу ли я добавлять метки к сегментам кольцевой диаграммы?

Да, вы можете добавлять метки к сегментам кольцевой диаграммы с помощью `setDataPointsLabelValue` метод на `IChart` объект.

### Можно ли добавить заголовок к диаграмме?

Конечно! Вы можете добавить заголовок к диаграмме с помощью `setTitle` метод на `IChart` объекта и предоставления желаемого текста заголовка.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
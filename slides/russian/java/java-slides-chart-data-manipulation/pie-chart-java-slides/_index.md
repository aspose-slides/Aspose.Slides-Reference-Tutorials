---
"description": "Узнайте, как создавать потрясающие круговые диаграммы в презентациях PowerPoint с помощью Aspose.Slides для Java. Пошаговое руководство с исходным кодом для разработчиков Java."
"linktitle": "Круговая диаграмма в слайдах Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Круговая диаграмма в слайдах Java"
"url": "/ru/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Круговая диаграмма в слайдах Java


## Введение в создание круговой диаграммы в Java Slides с использованием Aspose.Slides

В этом уроке мы покажем, как создать круговую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Мы предоставим вам пошаговые инструкции и исходный код Java, чтобы помочь вам начать работу. Это руководство предполагает, что вы уже настроили свою среду разработки с помощью Aspose.Slides для Java.

## Предпосылки

Прежде чем начать, убедитесь, что в вашем проекте установлена и настроена библиотека Aspose.Slides for Java. Вы можете загрузить ее с [здесь](https://releases.aspose.com/slides/java/).

## Шаг 1: Импорт необходимых библиотек

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Обязательно импортируйте необходимые классы из библиотеки Aspose.Slides.

## Шаг 2: Инициализация презентации

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Создать экземпляр класса Presentation, представляющего файл PPTX
Presentation presentation = new Presentation();
```

Создайте новый объект Presentation для представления вашего файла PowerPoint. Заменить `"Your Document Directory"` на фактический путь, по которому вы хотите сохранить презентацию.

## Шаг 3: Добавьте слайд

```java
// Доступ к первому слайду
ISlide slide = presentation.getSlides().get_Item(0);
```

Откройте первый слайд презентации, на который вы хотите добавить круговую диаграмму.

## Шаг 4: Добавьте круговую диаграмму

```java
// Добавить круговую диаграмму с данными по умолчанию
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Добавьте круговую диаграмму на слайд в указанном месте и размере.

## Шаг 5: Задайте название диаграммы

```java
// Установить заголовок диаграммы
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Задайте заголовок для круговой диаграммы. Вы можете настроить заголовок по своему усмотрению.

## Шаг 6: Настройте данные диаграммы

```java
// Установите первую серию для отображения значений
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;

// Получение рабочего листа данных диаграммы
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Добавление новых категорий
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Добавление новых серий
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Заполнение рядов данных
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Настройте данные диаграммы, добавив категории и серии и задав их значения. В этом примере у нас есть три категории и одна серия с соответствующими точками данных.

## Шаг 7: Настройте секторы круговой диаграммы

```java
// Установить цвета секторов
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Настройте внешний вид каждого сектора
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Настроить границу сектора
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Настройте другие сектора аналогичным образом.
```

Настройте внешний вид каждого сектора в круговой диаграмме. Вы можете изменить цвета, стили границ и другие визуальные свойства.

## Шаг 8: Настройте метки данных

```java
// Настройте метки данных
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Настройте метки данных для других точек данных аналогичным образом.
```

Настройте метки данных для каждой точки данных в круговой диаграмме. Вы можете контролировать, какие значения отображаются на диаграмме.

## Шаг 9: Покажите направляющие линии

```java
// Показать линии указателя для диаграммы
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Включите линии выноски для соединения меток данных с соответствующими им секторами.

## Шаг 10: Установка угла поворота круговой диаграммы

```java
// Установите угол поворота для секторов круговой диаграммы
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Установите угол поворота для секторов круговой диаграммы. В этом примере мы устанавливаем его на 180 градусов.

## Шаг 11: Сохраните презентацию

```java
// Сохраните презентацию с круговой диаграммой
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Сохраните презентацию с круговой диаграммой в указанном каталоге.

## Полный исходный код для круговой диаграммы в Java Slides

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation, представляющего файл PPTX
Presentation presentation = new Presentation();
// Доступ к первому слайду
ISlide slides = presentation.getSlides().get_Item(0);
// Добавить диаграмму с данными по умолчанию
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Настройка диаграммы Название
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Установить первую серию для показа значений
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Установка индекса листа данных диаграммы
int defaultWorksheetIndex = 0;
// Получение рабочего листа данных диаграммы
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Удалить созданные по умолчанию серии и категории
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Добавление новых категорий
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Добавление новых серий
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Сейчас заполняем данные серий
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Не работает в новой версии
// Добавление новых точек и настройка цвета сектора
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Установка границы сектора
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Установка границы сектора
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Установка границы сектора
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Создавайте индивидуальные метки для каждой категории для новых серий
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(истина);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Отображение линий указателей для диаграммы
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Установка угла поворота для секторов круговой диаграммы
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Сохранить презентацию с диаграммой
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Заключение

Вы успешно создали круговую диаграмму в презентации PowerPoint с помощью Aspose.Slides для Java. Вы можете настроить внешний вид диаграммы и метки данных в соответствии с вашими конкретными требованиями. В этом руководстве представлен базовый пример, и вы можете дополнительно улучшить и настроить свои диаграммы по мере необходимости.

## Часто задаваемые вопросы

### Как изменить цвета отдельных секторов круговой диаграммы?

Чтобы изменить цвета отдельных секторов в круговой диаграмме, вы можете настроить цвет заливки для каждой точки данных. В приведенном примере кода мы продемонстрировали, как задать цвет заливки для каждого сектора с помощью `getSolidFillColor().setColor()` Метод. Вы можете изменить значения цвета, чтобы добиться желаемого вида.

### Могу ли я добавить больше категорий и рядов данных в круговую диаграмму?

Да, вы можете добавлять дополнительные категории и ряды данных в круговую диаграмму. Для этого вы можете использовать `getChartData().getCategories().add()` и `getChartData().getSeries().add()` методы, как показано в примере. Просто предоставьте соответствующие данные и метки для новых категорий и серий, чтобы расширить вашу диаграмму.

### Как настроить внешний вид меток данных?

Вы можете настроить внешний вид меток данных с помощью `getDataLabelFormat()` метод на каждой метке точки данных. В этом примере мы продемонстрировали, как показать значение на метках данных, используя `getDataLabelFormat().setShowValue(true)`. Вы можете дополнительно настроить метки данных, управляя отображаемыми значениями, показывая ключи легенды и настраивая другие параметры форматирования.

### Могу ли я изменить название круговой диаграммы?

Да, вы можете изменить заголовок круговой диаграммы. В предоставленном коде мы задаем заголовок диаграммы с помощью `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. Вы можете заменить `"Sample Title"` с желаемым текстом заголовка.

### Как сохранить созданную презентацию с круговой диаграммой?

Чтобы сохранить презентацию с круговой диаграммой, используйте `presentation.save()` метод. Укажите желаемый путь к файлу и имя вместе с форматом, в котором вы хотите сохранить презентацию. Например:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Обязательно укажите правильный путь к файлу и формат.

### Могу ли я создавать другие типы диаграмм с помощью Aspose.Slides для Java?

Да, Aspose.Slides для Java поддерживает различные типы диаграмм, включая столбчатые диаграммы, линейные диаграммы и т. д. Вы можете создавать различные типы диаграмм, изменяя `ChartType` при добавлении диаграммы. Более подробную информацию о создании различных типов диаграмм см. в документации Aspose.Slides.

### Где я могу найти дополнительную информацию и примеры по работе с Aspose.Slides для Java?

Для получения дополнительной информации, подробной документации и дополнительных примеров вы можете посетить [Aspose.Slides для документации Java](https://reference.aspose.com/slides/java/). Он предоставляет комплексные ресурсы, которые помогут вам эффективно использовать библиотеку.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
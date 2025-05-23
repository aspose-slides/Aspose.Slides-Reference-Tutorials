---
"date": "2025-04-17"
"description": "Узнайте, как создавать потрясающие кольцевые диаграммы в Java с помощью Aspose.Slides. Это всеобъемлющее руководство охватывает инициализацию, конфигурацию данных и сохранение презентаций."
"title": "Создание кольцевых диаграмм в Java с помощью Aspose.Slides&#58; Подробное руководство"
"url": "/ru/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание кольцевых диаграмм в Java с помощью Aspose.Slides: пошаговое руководство

## Введение

В сегодняшней среде, основанной на данных, эффективная визуализация информации является ключом к улучшению понимания и вовлеченности. Хотя создание профессиональных диаграмм программным способом может показаться сложным, особенно с помощью Java, это руководство проведет вас через использование Aspose.Slides для Java для создания кольцевых диаграмм без усилий.

Выполняя эти шаги, разработчики получат практический опыт работы со слайдами презентаций и беспрепятственной интеграции визуализации данных.

**Основные выводы:**
- Инициализируйте объект Presentation с помощью Aspose.Slides Java.
- Настраивайте данные диаграммы и управляйте существующими сериями или категориями.
- Добавляйте и настраивайте серии и категории для своих диаграмм.
- Эффективное форматирование и отображение точек данных.
- С легкостью сохраняйте свою презентацию в различных форматах.

Прежде чем приступить к внедрению, убедитесь, что у вас есть все необходимое для начала работы.

## Предпосылки

Чтобы следовать этому руководству, убедитесь, что у вас есть:

- **Требуемые библиотеки:**
  - Aspose.Slides для Java версии 25.4 или более поздней.
  
- **Настройка среды:**
  - В вашей системе установлен JDK 16 или выше.
  - IDE, например IntelliJ IDEA, Eclipse или NetBeans.

- **Необходимые знания:**
  - Базовое понимание концепций программирования на Java.
  - Знакомство с управлением зависимостями в проектах Maven или Gradle.

## Настройка Aspose.Slides для Java

Чтобы интегрировать Aspose.Slides в свой проект, выполните следующие действия в зависимости от вашего инструмента сборки:

**Настройка Maven:**
Добавьте следующую зависимость к вашему `pom.xml` файл:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Настройка Gradle:**
Включите в свой план следующее: `build.gradle` файл:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямая загрузка:**
Либо загрузите последнюю версию непосредственно с сайта [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

### Получение лицензии

Чтобы использовать Aspose.Slides без ограничений по оценке:
- **Бесплатная пробная версия:** Начните с временной лицензии, чтобы изучить все функции.
- **Временная лицензия:** Получите один через [Сайт Aspose](https://purchase.aspose.com/temporary-license/).
- **Покупка:** Рассмотрите возможность приобретения для постоянного использования.

Примените лицензию в своем приложении Java, используя:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Руководство по внедрению

### Инициализация презентации и диаграммы

#### Обзор
Начните с инициализации объекта презентации и добавления кольцевой диаграммы на первый слайд.

**Шаг 1: Инициализация презентации**
Загрузите существующий файл PPTX или создайте новый:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Шаг 2: Добавьте кольцевую диаграмму**
Создайте диаграмму на первом слайде по указанным координатам:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Настройка рабочей книги данных диаграммы и очистка существующих серий/категорий

#### Обзор
Настройте рабочую книгу данных диаграммы и удалите все существующие ряды или категории.

**Шаг 1: Доступ к рабочей книге данных диаграммы**
Получите рабочую книгу, связанную с вашей диаграммой:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Шаг 2: Очистите существующие серии и категории**
Убедитесь, что нет остаточных точек данных:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Добавление серии в диаграмму

#### Обзор
Заполните свою диаграмму несколькими сериями, каждая из которых имеет индивидуальный внешний вид и поведение.

**Шаг 1: Итеративное добавление серий**
Пройдитесь по индексам, чтобы добавить серии:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Настройте серию
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Добавление категорий и точек данных в диаграмму

#### Обзор
Настройте категории и добавьте точки данных с определенным форматированием для меток.

**Шаг 1: Добавьте категории**
Перебор индексов для каждой категории:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Шаг 2: Добавьте точки данных в каждую серию**
Повторите каждую серию для текущей категории:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Настройки формата точек данных
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Форматирование этикетки для последней серии
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Настройте параметры отображения
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Отрегулируйте положение этикетки
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Сохранение презентации

#### Обзор
После настройки диаграммы сохраните презентацию в указанном каталоге.

**Шаг 1: Сохраните презентацию**
Используйте `save` метод записи изменений:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Заключение

Теперь вы узнали, как создавать и настраивать кольцевые диаграммы в Java с помощью Aspose.Slides. Эти шаги обеспечивают основу для интеграции сложных визуализаций данных в ваши презентации.

**Следующие шаги:**
- Поэкспериментируйте с различными типами диаграмм, доступными в Aspose.Slides.
- Изучите дополнительные параметры настройки, такие как цвета, шрифты и стили, которые соответствуют вашим потребностям в брендинге.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
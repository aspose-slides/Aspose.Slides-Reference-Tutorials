---
date: '2026-03-07'
description: Узнайте, как создать кольцевую диаграмму в Java с помощью Aspose.Slides.
  Это пошаговое руководство охватывает настройку зависимости Maven Aspose Slides,
  конфигурацию диаграммы и сохранение презентаций.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: 'Создание кольцевой диаграммы в Java с Aspose.Slides: руководство'
url: /ru/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание кольцевой диаграммы Java с руководством Aspose.Slides

## Введение

Создание **кольцевой диаграммы** программно может превратить сырые цифры в привлекающий внимание визуальный элемент, который мгновенно рассказывает историю. В Java **Aspose.Slides** упрощает этот процесс, позволяя генерировать готовые к использованию в презентациях диаграммы без открытия PowerPoint. В этом руководстве вы узнаете, как **создать кольцевую диаграмму java** шаг за шагом — от настройки зависимости Maven Aspose Slides до настройки рядов, категорий и, наконец, сохранения презентации.

К концу этого руководства вы сможете внедрять динамические кольцевые диаграммы в любой файл PPTX, что идеально подходит для отчетов, панелей мониторинга или автоматических наборов слайдов.

### Быстрые ответы
- **Какая библиотека используется?** Aspose.Slides for Java  
- **Основная задача?** Создать кольцевую диаграмму java в файле PPTX  
- **Как добавить библиотеку?** Использовать зависимость Maven Aspose Slides (или Gradle)  
- **Минимальная версия Java?** JDK 16 или выше  
- **Можно ли настроить цвета и подписи?** Да, API предоставляет полный контроль над форматированием  

## Что такое кольцевая диаграмма и зачем её использовать?

Кольцевая диаграмма — это вариант круговой диаграммы с пустым центром, позволяющий отображать несколько рядов данных в концентрических кольцах. Это делает её идеальной для сравнения частей целого по нескольким категориям — например, продажи по регионам за несколько кварталов или распределение бюджета по отделам.

## Почему использовать Aspose.Slides для Java?

- **Не требуется установка Office** – генерировать файлы PPTX на любом сервере.  
- **Богатый API** – полный контроль над типами диаграмм, точками данных и стилями.  
- **Высокая производительность** – оптимизировано для больших презентаций.  
- **Кросс‑платформенный** – работает на Windows, Linux и macOS.

## Предварительные требования

- **Необходимые библиотеки:**  
  - Aspose.Slides for Java версии 25.4 или новее.  

- **Настройка окружения:**  
  - JDK 16 или выше.  
  - Ваш любимый IDE (IntelliJ IDEA, Eclipse, NetBeans и т.д.).  

- **Требования к знаниям:**  
  - Базовое программирование на Java.  
  - Знакомство с Maven или Gradle для управления зависимостями.

## Зависимость Maven Aspose Slides

Добавьте следующую зависимость Maven в ваш `pom.xml`. Это **зависимость maven aspose slides**, необходимая для подключения библиотеки к вашему проекту.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Если вы предпочитаете Gradle, используйте эквивалентный фрагмент ниже.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Вы также можете скачать JAR напрямую со страницы официальных релизов:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Получение лицензии

Чтобы убрать водяной знак оценки и разблокировать полный набор функций:

- **Бесплатная пробная версия** – начните с временной лицензии.  
- **Временная лицензия** – запросите её на [веб‑сайте Aspose](https://purchase.aspose.com/temporary-license/).  
- **Коммерческая лицензия** – приобретите для использования в продакшене.

Примените лицензию в вашем коде:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Руководство по реализации

### Инициализация презентации и добавление кольцевой диаграммы

Сначала создайте или загрузите презентацию и добавьте кольцевую диаграмму на первый слайд.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Настройка рабочей книги данных диаграммы и очистка существующих данных

Затем получите рабочую книгу, поддерживающую диаграмму, и очистите любые стандартные ряды или категории.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Добавление рядов к диаграмме

Теперь мы добавим до 15 рядов. Каждый ряд можно настроить — здесь мы задаём взрыв, размер отверстия кольца и угол первого сектора.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Добавление категорий и точек данных

Мы создадим 15 категорий и заполним каждый ряд точкой данных. Последний ряд получает специальное форматирование меток.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
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

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Сохранение презентации

Наконец, запишите обновлённую презентацию на диск.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Распространённые проблемы и решения

- **Лицензия не найдена** – Проверьте, что путь к `license.lic` правильный и файл доступен для чтения.  
- **Диаграмма отображается пустой** – Убедитесь, что вы очистили существующие ряды/категории перед добавлением новых.  
- **Неправильные цвета** – Убедитесь, что `FillType.Solid` установлен как для заливки, так и для формата линии.  
- **Производительность при большом количестве рядов** – Ограничьте количество рядов/категорий или переиспользуйте ячейки рабочей книги.

## Часто задаваемые вопросы

**В: Можно ли создать кольцевую диаграмму без предварительно существующего файла PPTX?**  
О: Да, создайте экземпляр `new Presentation()`, чтобы начать с пустой колоды слайдов.

**В: Поддерживает ли Aspose.Slides экспорт в PDF?**  
О: Конечно. После создания диаграммы вызовите `pres.save("output.pdf", SaveFormat.Pdf);`.

**В: Как изменить размер отверстия кольца?**  
О: Используйте `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, где value — значение от 0 до 100.

**В: Можно ли добавить подписи данных ко всем рядам, а не только к последнему?**  
О: Да, переместите блок форматирования меток за пределы условия `if (i == ...)` и примените его к каждому `dataPoint`.

**В: Какие версии Java поддерживаются?**  
О: Aspose.Slides 25.4 поддерживает JDK 16 и новее. Более ранние версии JDK требуют соответствующего классификатора.

---

**Последнее обновление:** 2026-03-07  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
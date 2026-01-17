---
date: '2026-01-17'
description: Узнайте, как добавить серии в диаграмму и настроить сложенные столбчатые
  диаграммы в .NET‑презентациях с помощью Aspose.Slides для Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Добавить серию в диаграмму с Aspose.Slides for Java в .NET
url: /ru/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение настройки диаграмм в .NET‑презентациях с помощью Aspose.Slides for Java

## Введение
В мире презентаций, основанных на данных, диаграммы — незаменимый инструмент, превращающий сырые цифры в убедительные визуальные истории. Когда требуется **add series to chart** программно, особенно внутри .NET‑файлов презентаций, задача может показаться сложной. К счастью, **Aspose.Slides for Java** предоставляет мощный, независимый от языка API, который делает создание и настройку диаграмм простыми — даже если ваш целевой формат — .NET PPTX.

В этом руководстве вы узнаете, как **add series to chart**, как **add chart** типа stacked column, а также как точно настроить визуальные параметры, такие как ширина промежутка. К концу вы сможете генерировать динамические, насыщенные данными слайды, выглядящие профессионально.

**Что вы узнаете**
- Как создать пустую презентацию с помощью Aspose.Slides  
- Как **add stacked column chart** на слайд  
- Как **add series to chart** и определить категории  
- Как заполнить точки данных и скорректировать визуальные настройки  

Давайте подготовим вашу среду разработки.

## Быстрые ответы
- **Какой основной класс для начала работы с презентацией?** `Presentation`  
- **Каким методом добавить диаграмму на слайд?** `slide.getShapes().addChart(...)`  
- **Как добавить новую серию?** `chart.getChartData().getSeries().add(...)`  
- **Можно ли изменить ширину промежутка между столбцами?** Да, используя `setGapWidth()` у группы серий  
- **Нужна ли лицензия для продакшна?** Да, требуется действующая лицензия Aspose.Slides for Java  

## Что такое “add series to chart”?
Добавление серии к диаграмме означает вставку новой коллекции данных, которую диаграмма отобразит как отдельный визуальный элемент (например, новый столбец, линию или сектор). Каждая серия может иметь собственные значения, цвета и форматирование, позволяя сравнивать несколько наборов данных рядом.

## Почему стоит использовать Aspose.Slides for Java для изменения .NET‑презентаций?
- **Кросс‑платформенность**: Пишете код на Java один раз и получаете PPTX‑файлы, используемые в .NET‑приложениях.  
- **Без COM и Office**: Работает на серверах, в CI‑конвейерах и контейнерах.  
- **Богатый API диаграмм**: Поддерживает более 50 типов диаграмм, включая stacked column.  

## Предварительные требования
1. Библиотека **Aspose.Slides for Java** (версия 25.4 или новее).  
2. Инструмент сборки Maven или Gradle, либо ручная загрузка JAR‑файла.  
3. Базовые знания Java и знакомство со структурой PPTX.  

## Установка Aspose.Slides for Java
### Maven
Добавьте следующую зависимость в ваш `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Включите эту строку в ваш `build.gradle` файл:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка
Или скачайте последний JAR с официальной страницы релизов: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Получение лицензии**  
Начните с бесплатной пробной версии, загрузив временную лицензию [здесь](https://purchase.aspose.com/temporary-license/). Для продакшн‑использования приобретите полную лицензию, чтобы разблокировать все возможности.

## Пошаговое руководство по реализации
Ниже каждый шаг сопровождается лаконичным фрагментом кода (оставлен без изменений) и пояснением его назначения.

### Шаг 1: Создать пустую презентацию
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Мы начинаем с чистого PPTX‑файла, который служит холстом для добавления диаграмм.*

### Шаг 2: Добавить stacked column chart на слайд
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Метод `addChart` создает **add stacked column chart** и размещает её в левом верхнем углу слайда.*

### Шаг 3: Добавить серии к диаграмме (основная цель)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Здесь мы **add series to chart** — каждый вызов создает новую серию данных, которая появится как отдельная группа столбцов.*

### Шаг 4: Добавить категории к диаграмме
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Категории выступают в роли меток оси X, придавая смысл каждому столбцу.*

### Шаг 5: Заполнить данные серии
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Точки данных задают числовые значения каждой серии, которые диаграмма отобразит в виде высоты столбцов.*

### Шаг 6: Установить ширину промежутка для группы серий
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Регулирование ширины промежутка улучшает читаемость, особенно при большом количестве категорий.*

## Распространённые сценарии использования
- **Финансовая отчётность** — сравнение квартального дохода по бизнес‑единицам.  
- **Проектные дашборды** — отображение процентов выполнения задач по командам.  
- **Маркетинговая аналитика** — визуализация эффективности кампаний рядом друг с другом.

## Советы по производительности
- **Повторно используйте объект `Presentation`** при создании нескольких диаграмм, чтобы снизить нагрузку на память.  
- **Ограничьте количество точек данных** только теми, которые необходимы для визуального рассказа.  
- **Освобождайте ресурсы** (`presentation.dispose()`) после сохранения, чтобы освободить память.

## Часто задаваемые вопросы
**В: Можно ли добавить другие типы диаграмм, кроме stacked column?**  
О: Да, Aspose.Slides поддерживает линейные, круговые, областные и многие другие типы диаграмм.

**В: Нужна ли отдельная лицензия для вывода в .NET?**  
О: Нет, одна Java‑лицензия работает со всеми форматами вывода, включая .NET PPTX.

**В: Как изменить цветовую палитру диаграммы?**  
О: Используйте `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` и задайте нужный `Color`.

**В: Можно ли программно добавить подписи данных?**  
О: Конечно. Вызовите `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`, чтобы отобразить значения.

**В: Как обновить существующую презентацию?**  
О: Загрузите файл с помощью `new Presentation("existing.pptx")`, измените диаграмму и сохраните обратно.

## Заключение
Теперь у вас есть полное пошаговое руководство по **add series to chart**, созданию **stacked column chart** и тонкой настройке её внешнего вида в .NET‑презентациях с помощью Aspose.Slides for Java. Экспериментируйте с различными типами диаграмм, цветами и источниками данных, чтобы создавать убедительные визуальные отчёты, которые произведут впечатление на заинтересованные стороны.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose
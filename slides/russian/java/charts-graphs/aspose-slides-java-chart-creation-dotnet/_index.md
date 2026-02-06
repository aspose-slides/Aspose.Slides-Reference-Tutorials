---
date: '2026-02-06'
description: Узнайте, как инициализировать презентацию Aspose Slides и настроить сгруппированную
  столбчатую диаграмму в .NET с использованием Aspose.Slides for Java. Следуйте этому
  пошаговому руководству, чтобы улучшить визуализацию данных.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Инициализация презентации с Aspose Slides: графики .NET'
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание диаграмм в .NET презентациях с использованием Aspose.Slides for Java

## Введение
В этом руководстве вы **initialize presentation Aspose Slides** и узнаете, как внедрять динамические, настраиваемые диаграммы в ваши .NET слайды. Визуальные данные — такие как сгруппированные столбчатые диаграммы — помогают аудитории мгновенно понять тенденции, а Aspose.Slides for Java предоставляет полный программный контроль даже при работе в .NET‑среде. Мы пройдём настройку библиотеки, создание новой презентации, добавление диаграммы, заполнение данными и применение приёмов форматирования, например окрашивание отрицательных значений.

**Что вы узнаете**
- Как настроить Aspose.Slides for Java в .NET проекте.  
- Как **initialize presentation Aspose Slides** и добавить диаграмму.  
- Как **customize clustered column chart** серии и категории.  
- Управление рабочей книгой данных диаграммы и применение условного форматирования.  

### Быстрые ответы
- **Какой первый шаг?** Инициализировать объект `Presentation`.  
- **Какой тип диаграммы используется в примере?** `ClusteredColumn`.  
- **Можно ли форматировать отрицательные значения иначе?** Да, используя условные цвета заливки.  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная лицензия подходит для разработки.  
- **Какой Maven‑артефакт требуется?** `com.aspose:aspose-slides:25.4` с классификатором `jdk16`.

## Что такое «initialize presentation Aspose Slides»?
Инициализация презентации создаёт в памяти файл PPTX, который можно изменять перед сохранением. Aspose.Slides абстрагирует формат файла, позволяя добавлять слайды, фигуры и диаграммы без работы с низкоуровневыми структурами OPC.

## Почему настраивать сгруппированную столбчатую диаграмму?
Сгруппированные столбчатые диаграммы идеальны для сравнения нескольких рядов данных по категориям. Настройка цветов, точек данных и подписей позволяет выделять ключевые инсайты — например, подчёркивать отрицательные значения красным, а положительные — зелёным, делая слайды более убедительными.

## Предварительные требования
- **Aspose.Slides for Java** ≥ 25.4  
- .NET‑среда разработки (Visual Studio, рекомендуется .NET 6+)  
- Базовые знания Java (вы будете писать Java‑код, который работает на JVM и вызывается из .NET через JNI или мостовой слой)  

### Требуемые библиотеки и версии
- **Aspose.Slides for Java**: версия 25.4 или новее.

### Требования к настройке среды
- Совместимая с .NET Java‑среда выполнения (например, AdoptOpenJDK 16).  
- Maven или Gradle для управления зависимостями.

### Требования к знаниям
- Знакомство с созданием презентаций в .NET‑контексте.  
- Понимание конфигурации Java‑проекта (Maven/Gradle).

## Настройка Aspose.Slides for Java
Добавьте библиотеку в проект, используя предпочитаемый инструмент сборки.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямое скачивание
Вы также можете загрузить последнюю JAR‑файл со страницы официальных релизов: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Шаги получения лицензии
- **Free Trial** – сгенерировать временный файл лицензии для разработки.  
- **Purchase** – приобрести полную лицензию для продакшн‑развёртываний.

#### Базовая инициализация и настройка
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Блок `try/finally` гарантирует освобождение нативных ресурсов, предотвращая утечки памяти.

## Как инициализировать презентацию Aspose Slides
Далее мы подробно рассмотрим шаги создания новой презентации и подготовки её к вставке диаграммы.

### Инициализация презентации
**Обзор:**  
Создание экземпляра презентации закладывает основу для всех последующих операций.

#### Шаг 1: Импорт необходимых пакетов
```java
import com.aspose.slides.Presentation;
```

#### Шаг 2: Создать новый объект Presentation
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Это гарантирует корректное освобождение объекта презентации после использования, предотвращая утечки памяти.*

## Как настроить сгруппированную столбчатую диаграмму
Теперь, когда презентация готова, добавим и настроим сгруппированную столбчатую диаграмму.

### Добавление диаграммы на слайд
**Обзор:**  
Добавление диаграммы оживляет данные на слайде.

#### Шаг 1: Импорт необходимых пакетов
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Шаг 2: Инициализировать презентацию и добавить диаграмму
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Здесь мы добавляем сгруппированную столбчатую диаграмму на первый слайд с указанными координатами и размерами.*

### Управление рабочей книгой данных диаграммы
**Обзор:**  
Эффективное управление рабочей книгой данных диаграммы позволяет без труда манипулировать рядами и категориями.

#### Шаг 1: Импорт необходимых пакетов
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Шаг 2: Доступ к рабочей книге и её очистка
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Очистка рабочей книги важна для начала с чистого листа при добавлении новых рядов и категорий.*

### Добавление рядов и категорий в диаграмму
**Обзор:**  
Этот шаг показывает, как добавить значимые точки данных, управляя рядами и категориями.

#### Шаг 1: Добавить ряды и категории
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Добавление рядов и категорий обеспечивает более упорядоченную презентацию данных.*

### Заполнение данных рядов и форматирование
**Обзор:**  
Заполните диаграмму точками данных и отформатируйте её внешний вид для улучшения читаемости, особенно при работе с отрицательными значениями.

#### Шаг 1: Заполнить данные рядов
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Этот раздел демонстрирует, как заполнять данные и применять цветовое форматирование для лучшей визуализации.*

## Распространённые проблемы и решения
- **Утечки памяти** – Всегда оборачивайте объект `Presentation` в блок `try/finally`, как показано, чтобы гарантировать его освобождение.  
- **Неправильные координаты ячеек** – Помните, что строки и столбцы нумеруются с нуля; несоответствие индексов приводит к `NullPointerException`.  
- **Лицензия не найдена** – Поместите файл лицензии в рабочий каталог приложения или явно укажите путь через `License.setLicense("Aspose.Slides.Java.lic")`.

## Часто задаваемые вопросы

**В: Можно ли использовать этот подход с .NET Core?**  
О: Да. Aspose.Slides for Java работает на любой JVM, и вы можете вызывать Java‑код из .NET Core через мост, такой как IKVM или JNI.

**В: Нужна ли платная лицензия для разработки?**  
О: Бесплатная пробная лицензия достаточна для разработки и тестирования. Для продакшн‑развёртываний требуется приобретённая лицензия.

**В: Как изменить тип диаграммы после её создания?**  
О: Вы можете вызвать `chart.getChartData().setChartType(ChartType.Pie)`, чтобы переключить тип диаграммы.

**В: Можно ли программно добавить подписи данных?**  
О: Да. Используйте `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)`, чтобы отобразить значения на диаграмме.

**В: В каких форматах можно сохранять презентацию?**  
О: Aspose.Slides поддерживает PPTX, PPT, PDF, XPS и несколько графических форматов, таких как PNG и JPEG.

---

**Последнее обновление:** 2026-02-06  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
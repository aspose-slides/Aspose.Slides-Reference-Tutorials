---
date: '2026-02-24'
description: Узнайте, как настраивать диаграмму рассеяния Aspose с помощью Aspose.Slides
  для Java. Это руководство проведёт вас через процесс создания, стилизации и сохранения
  динамических диаграмм рассеяния в ваших презентациях.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Настройка диаграммы рассеяния Aspose в Java
url: /ru/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

 Tips" bullet list.

Also FAQ sections.

Also "Last Updated", "Tested With", "Author".

All need translation.

We must keep code placeholders unchanged.

Also keep markdown formatting.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Настройка диаграммы рассеяния Aspose в Java

В этом руководстве вы узнаете, как **настроить диаграмму рассеяния aspose** с помощью мощной библиотеки Aspose.Slides for Java. Мы пройдём настройку проекта, создание диаграммы рассеяния, изменение типов рядов и маркеров, а затем сохранение презентации. К концу вы сможете программно генерировать профессиональные диаграммы рассеяния и подгонять каждый визуальный элемент под ваш бренд или требования отчётности.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Slides for Java (v25.4+).  
- **Какая версия Java поддерживается?** JDK 8 или выше.  
- **Можно ли менять форму маркеров?** Да – используйте `MarkerStyleType` для выбора звёзд, кругов и т.д.  
- **Как сохранить файл?** Вызовите `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшна требуется коммерческая лицензия.

## Что такое «customize scatter chart aspose»?
Настройка диаграммы рассеяния с помощью Aspose означает программное определение данных диаграммы, её внешнего вида и поведения — от координат точек до символов маркеров — без ручного открытия PowerPoint. Такой подход идеален для автоматизированных отчётов, презентаций, основанных на данных, или любой ситуации, где требуются повторяемые визуализации высокого качества.

## Почему стоит настраивать диаграммы рассеяния с Aspose.Slides?
- **Полный контроль** — изменяйте типы рядов, стили маркеров, цвета и многое другое через Java‑код.  
- **Автоматизация** — генерируйте десятки диаграмм «на лету» для панелей мониторинга или пакетных отчётов.  
- **Кросс‑платформенность** — работает на любой ОС, поддерживающей Java, без необходимости установки Office.  
- **Производительность** — лёгкое API, эффективно обрабатывающее большие наборы данных.

## Требования

Чтобы следовать инструкциям, убедитесь, что у вас есть:

- **Aspose.Slides for Java** (v25.4 или новее).  
- **Java Development Kit (JDK)** 8 + установлен.  
- Maven или Gradle для управления зависимостями (или можно скачать JAR вручную).  
- Базовые знания Java и знакомство с выбранным инструментом сборки.

## Установка Aspose.Slides for Java

Подключите библиотеку к вашему проекту одним из способов ниже.

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

Или загрузите последнюю версию с [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Приобретение лицензии
- **Бесплатная пробная** – 30‑дневная оценка.  
- **Временная лицензия** – продлённый тестовый период.  
- **Полная лицензия** – использование в продакшне с премиум‑поддержкой.

## Пошаговое руководство по настройке диаграммы рассеяния Aspose

### 1️⃣ Подготовьте папку для файлов презентации
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Почему это важно:* наличие выходной папки предотвращает `FileNotFoundException` при последующем сохранении PPTX.

### 2️⃣ Создайте новую презентацию и получите первый слайд
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Новая `Presentation` предоставляет чистый холст; первый слайд — место, где мы разместим диаграмму.

### 3️⃣ Добавьте диаграмму рассеяния с плавными линиями
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` создаёт диаграмму рассеяния с плавными линиями, идеально подходящую для визуализации трендов.

### 4️⃣ Очистите любые рядки по умолчанию и добавьте свои
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Удаление рядов по умолчанию даёт вам полный контроль над отображаемыми данными.

### 5️⃣ Заполните первый ряд данными точек
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` принимает ячейку X‑значения и ячейку Y‑значения, формируя точку за точкой.

### 6️⃣ Настройте тип ряда и внешний вид маркеров
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Здесь мы **настраиваем диаграмму рассеяния aspose**, переключаясь на прямые линии, увеличивая маркеры и выбирая разные символы (звезда vs. круг) для лучшей визуальной различимости.

### 7️⃣ Сохраните презентацию
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Сохранение в формате `Pptx` сохраняет все настройки диаграммы и делает файл готовым к распространению или дальнейшему редактированию.

## Типичные сценарии использования настроенных диаграмм рассеяния
- **Финансовые панели** – построение цены акции против объёма.  
- **Научные исследования** – отображение экспериментальных измерений с маркерами ошибок.  
- **Управление проектами** – сравнение плановых и фактических усилий по задачам.  

## Советы по производительности
- После сохранения вызовите `pres.dispose()` для освобождения нативных ресурсов.  
- Для больших наборов данных сначала заполните рабочую книгу, а затем привяжите ряд к ней, чтобы избежать повторных обновлений UI.  
- Переиспользуйте один экземпляр `IChartDataWorkbook` при добавлении множества рядов.

## Часто задаваемые вопросы

### Как изменить цвет маркеров?
Используйте `series.getMarker().getFillFormat().setFillColor(Color)`, где `Color` — экземпляр `java.awt.Color` (например, `Color.RED`).

### Можно ли добавить более двух рядов в диаграмму рассеяния?
Конечно. Повторите вызов `chart.getChartData().getSeries().add(...)` для каждого дополнительного ряда и заполните его точки соответственно.

### Можно ли задать пользовательскую подпись легенды для каждого ряда?
Да. После создания ряда вызовите `series.getLegend().setText("Your Legend Text")`, чтобы переопределить имя по умолчанию.

### Как экспортировать диаграмму как изображение вместо PPTX?
Вызовите `chart.getImage().save("chart.png", ImageFormat.Png)` после настройки диаграммы. Вы получите отдельный PNG‑файл.

### Что делать, если нужно анимировать точки рассеяния?
Aspose.Slides поддерживает анимационные эффекты. Используйте `chart.getTimeline().getMainSequence().addEffect(...)` для добавления анимаций появления или акцента к диаграмме или отдельным рядам.

---

**Последнее обновление:** 2026-02-24  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
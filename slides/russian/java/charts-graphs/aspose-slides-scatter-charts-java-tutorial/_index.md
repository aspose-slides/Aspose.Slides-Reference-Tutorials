---
date: '2026-01-24'
description: Пошаговое руководство по созданию точечной диаграммы в Java с использованием
  Aspose.Slides, добавлению точек данных и работе с несколькими сериями точечной диаграммы.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Создайте точечную диаграмму Java с Aspose.Slides – настройте и сохраните
url: /ru/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
 Java с Aspose.Slides

В этом руководния с несколькимидание диаграммы рассеяния на слайде
- Добавление и управление точками данных для каждой серии
- Настройка типов серий, маркеров и работа с диаграммой рассеяния с несколькими сериями
- Сохранение готовой презентации  

Давайте начнём с предварительных требований.

## Быстрые ответы
- **Какова основная библиотека?** Aspose.Slides for Java  
- **Какая версия Java требуется?** JDK 8 или выше (рекомендовано JDK 16)  
- **Можно ли добавить более двух серий?** Да — вы можете добавить любое количество серий в диаграмму рассеяния  
- **Как изменить цвета().getFillFormat().setFillColor(Color)`  
- **Нужна ли лицензия** – версия 25.4 или новее.  
- **Java Development Kit (JDK)** – JDK 8 или новее.  
- Базовые знания Java и знакомство с Maven или Gradle

Интегрируйте Aspose.Slides в ваш проект одним из следующих способов.

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

Or download the latest package from [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Приобретение лицензии
- **Free Trial** – 30‑дневная оценка.  
- **Temporary License** – Расширенное тестирование.  
- **Commercial License** – Полное использование в продакшн.  

Теперь перейдём к коду.

## Руководство по реализации

### Шаг 1: Настройка каталога
Сначала убедитесь, что папка вывода существует, чтобы презентацию можно было сохранить без ошибок.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Шаг 2: Инициализация презентации
Создайте новую презентацию и получите первый слайд.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Шаг 3: Добавление диаграммы рассеяния
Вставьте диаграмму рассеяния с плавными линиями на слайд.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Шаг 4: Управление данными диаграммы (очистка и добавление серий)
Очистите любые серии по умолчанию и добавьте свои серии для **multiple series scatter chart**.

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

### Шаг 5: Добавление точек данных scatter
Заполните каждую серию значениями X‑Y, используя **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Шаг 6: Настройка типов серий и маркеров
Отрегулируйте визуальный стиль — переключитесь на прямые линии с маркерами и задайте различные символы маркеров.

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

### Шаг 7: Сохранение презентации
Сохраните файл на диск.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Практические применения
- Research** – Визуализация экспериментальных измерений с использованием add data points scatter Management** – Показ тенденций распределения ресурсов по нескольким проектам на одной диаграмме рассеяния.  

## Соображения по производительности
- Освободите объект `Presentation` после сохранения, чтобы освобод точки данных добавлены в правильную серию и индексы книги соответствуют. |
| **Маркер не виден** | Убедитесь, что `series.getMarker().setSize()` установлен в значение больше 0 и символ маркера определён. |
| **OutOfMemoryError при больших диаграммах** | Вызовите `pres.dispose()` после сохранения и рассмотрите увеличение размера кучи JVM (`-Xmx`). |

## Часто задаваемые — экземпляр серий в диаграмму рассеяния?
Конечно. Повторите блок создания серии (Шаг 4) для каждой дополнительной серии.

### Можно ли экспортировать диаграмму как изображение?
Да. Вызовите `chart.exportChartImage("chart.png", ImageFormat.Png)` после добавления всех данных.

### Поддерживает ли Aspose.Slides интерактивные подсказки на точках рассе`, чтобы добавить прост25:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
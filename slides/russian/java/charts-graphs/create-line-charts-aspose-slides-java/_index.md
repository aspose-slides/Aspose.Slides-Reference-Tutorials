---
date: '2026-03-23'
description: Узнайте, как использовать Aspose.Slides for Java для создания линейных
  диаграмм с маркерами, добавления второй серии и обработки null‑данных в презентациях
  PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Как использовать Aspose.Slides для Java: создавайте линейные диаграммы с маркерами
  по умолчанию'
url: /ru/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание линейных диаграмм с маркерами по умолчанию с помощью Aspose.Slides for Java

## Введение
Если вы задаётесь вопросом **how to use Aspose** для автоматизации создания PowerPoint, вы попали по адресу. В этом руководстве мы пройдёмся по созданию **line chart with markers**, добавлению второй серии и обработке пустых (null) данных — всё с помощью Aspose.Slides for Java. К концу вы получите готовый к запуску фрагмент кода, который генерирует профессионально выглядящую диаграмму без необходимости вручную открывать PowerPoint.

### Быстрые ответы
- **Какая библиотека нужна?** Aspose.Slides for Java (рекомендуется последняя версия)  
- **Можно ли добавить вторую серию?** Да — API позволяет легко добавлять несколько серий.  
- **Как обрабатываются пустые (null) данные?** Используйте `null` в значении ячейки; диаграмма пропустит точку.  
- **Нужен ли Maven?** Maven или Gradle работают; см. раздел *aspose slides maven* ниже.  
- **Требуется ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшена нужна коммерческая лицензия.

## Как использовать Aspose.Slides for Java для создания линейных диаграмм
Программное создание диаграмм экономит часы ручного форматирования и гарантирует единообразие презентаций. Будь то функция **create powerpoint chart** в инструменте отчётности или генерация наборов слайдов «на лету», Aspose.Slides предоставляет полный контроль из Java‑кода.

## Требования
Перед началом убедитесь, что ваша среда разработки готова:

1. **Libraries & Dependencies**
   - Aspose.Slides for Java library (версия 25.4 рекомендуется) — покрывает сценарий *aspose slides maven*.
   - Java Development Kit (JDK) версии 16 или выше.
2. **Environment Setup**
   - IDE с поддержкой Maven или Gradle.
   - Действительный файл лицензии Aspose, если планируете запускать код вне пробной версии.
3. **Knowledge Prerequisites**
   - Базовое программирование на Java.
   - Знакомство со сборочными файлами Maven или Gradle.

## Настройка Aspose.Slides for Java
### Maven
Добавьте следующую зависимость в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Поместите это в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Прямое скачивание
При желании вы можете скачать последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Шаги получения лицензии:**
- Для бесплатной пробной версии посетите [free trial page](https://releases.aspose.com/slides/java/).
- Чтобы получить временную лицензию, перейдите на [temporary license page](https://purchase.aspose.com/temporary-license/).
- Приобретите полную лицензию через их [purchase portal](https://purchase.aspose.com/buy).

**Базовая инициализация:**
Вот как можно инициализировать Aspose.Slides в вашем Java‑приложении:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Теперь перейдём к созданию диаграмм!

## Руководство по реализации
### Функция 1: Создание диаграммы с маркерами по умолчанию
Этот раздел демонстрирует, как создать **line chart with markers**, идеальную для выделения отдельных точек данных на трендовой линии.

#### Добавление линейной диаграммы
Чтобы добавить линейную диаграмму с маркерами:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Очистка серий и категорий
Чтобы начать с чистого листа:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Функция 2: Добавление серий и категорий
Добавление серий и категорий критично для наполнения диаграмм осмысленными данными.

#### Создание новой серии
Чтобы добавить новую серию с именем "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Заполнение категорий и точек данных
Чтобы добавить категории и соответствующие точки данных:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Функция 3: Добавление второй серии и заполнение точек данных
Добавление дополнительных серий придаёт визуальному анализу большую глубину.

#### Создание и заполнение второй серии
Чтобы добавить "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Функция 4: Настройка легенды диаграммы
Настройка легенды повышает читаемость диаграммы, особенно когда **add second series**.

#### Настройка параметров легенды
Чтобы сконфигурировать:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Функция 5: Сохранение презентации
Когда ваша диаграмма готова, вы захотите **создать PowerPoint‑диаграмму**, которую можно будет поделиться или дальше редактировать.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Практические применения
1. **Бизнес‑отчётность:** Используйте линейную диаграмму с маркерами для иллюстрации финансовых тенденций по кварталам.  
2. **Анализ данных:** Визуализируйте экспериментальные данные, где каждый маркер подчёркивает точку измерения.  
3. **Образовательные материалы:** Создавайте слайды лекций, показывающие пошаговые изменения процесса.  
4. **Управление проектами:** Отслеживайте вехи на временной шкале с отдельными маркерами для ключевых дат.  
5. **Маркетинговые презентации:** Демонстрируйте всплески эффективности кампаний с чёткими символами маркеров.

## Распространённые проблемы и решения
- **Пустые (null) точки данных вызывают ошибки:** Передайте `null` как значение ячейки (как показано) — Aspose просто пропустит эту точку.  
- **Диаграмма отображается без маркеров:** Убедитесь, что используете `ChartType.LineWithMarkers`, а не `ChartType.Line`.  
- **Легенда перекрывает данные:** Установите `chart.getLegend().setOverlay(false)`, чтобы легенда оставалась отдельной.  

## Часто задаваемые вопросы

**В: Можно ли использовать этот подход для генерации диаграмм в веб‑службе?**  
О: Абсолютно. Библиотека работает в любой Java‑среде, включая серверные приложения.

**В: Нужна ли лицензия для сборок разработки?**  
О: Бесплатная пробная версия подходит для разработки и тестирования. Для продакшена требуется коммерческая лицензия.

**В: Как Aspose обрабатывает большие наборы данных?**  
О: API эффективно потокирует данные; однако рекомендуется ограничивать количество точек, чтобы избежать больших размеров файлов.

**В: Поддерживает ли библиотека другие типы диаграмм?**  
О: Да — Aspose.Slides поддерживает столбчатые, круговые, точечные и многие другие типы диаграмм.

**В: Можно ли настроить форму и цвет маркеров?**  
О: Формат маркера можно изменить через свойство `Marker` у каждой точки данных.

## Заключение
Теперь вы знаете **how to use Aspose** для создания линейной диаграммы с маркерами по умолчанию, добавления второй серии, обработки пустых данных и сохранения результата в файл PowerPoint. Эти приёмы позволяют автоматизировать генерацию отчётов, улучшать повествование данных и поддерживать единообразие ваших презентаций.

Для более глубокого изучения обратитесь к [official documentation](https://docs.aspose.com/slides/java/) или присоединитесь к сообществу на форумах, таких как Stack Overflow.

---

**Последнее обновление:** 2026-03-23  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-03-07'
description: Узнайте, как создать линейный график в Java с помощью Aspose.Slides,
  добавить заголовок диаграммы, добавить линии сетки, отформатировать подписи диаграммы
  и сохранить профессиональные презентации.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Как создать линейный график с помощью Aspose.Slides в Java – Полное руководство
url: /ru/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать линейный график с помощью Aspose.Slides в Java

## Как создать линейный график в Java с использованием Aspose.Slides

### Введение
Создание визуально привлекательных презентаций имеет решающее значение для эффективной коммуникации. Будь то бизнес‑профессионал или преподаватель, вам часто требуется **создать линейный график**, который будет одновременно информативным и эстетически приятным. В этом руководстве мы пройдемся по использованию **Aspose.Slides for Java** для генерации линейного графика, добавления заголовка графика, сетки, форматирования подписей и сохранения результата в файл PowerPoint.

#### Быстрые ответы
- **Какая библиотека лучше всего подходит для создания графиков в Java?** Aspose.Slides for Java
- **Какой тип графика рассматривается в этом руководстве?** Линейный график с маркерами
- **Нужна ли лицензия для запуска примера?** Бесплатная временная лицензия подходит для оценки
- **Какую IDE можно использовать?** Любую Java‑IDE, например IntelliJ IDEA, Eclipse или NetBeans
- **Как форматируются элементы графика?** С помощью цепочки вызовов Fluent API для заголовков, осей, сетки, легенд и фонов

### Что такое линейный график и почему использовать Aspose.Slides?
Линейный график отображает точки данных, соединённые прямыми линиями, что делает его идеальным для демонстрации тенденций во времени. Aspose.Slides позволяет создавать и полностью настраивать такие графики программно, избавляя от необходимости ручного редактирования PowerPoint.

### Предварительные требования
- **Java Development Kit (JDK) 8+** установлен
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans и т.д.)
- **Aspose.Slides for Java** библиотека (добавлена через Maven или Gradle)

#### Требуемые библиотеки и зависимости
**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Или загрузите последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Получение лицензии
- Получите [бесплатную пробную лицензию](https://purchase.aspose.com/temporary-license/) для тестирования.
- Приобретите полную лицензию на [официальном сайте Aspose](https://purchase.aspose.com/buy) для использования в продакшене.

### Настройка Aspose.Slides for Java
1. **Добавьте зависимость**, показанную выше, в ваш проект.
2. **Примените лицензию** (если она у вас есть) перед созданием любых объектов презентации.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Пошаговая реализация

### Шаг 1: Создайте выходной каталог (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Почему это важно:* Наличие папки предотвращает `FileNotFoundException`, когда позже сохраняется презентация.

### Шаг 2: Добавьте слайд и вставьте линейный график
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Объяснение:* Этот код создаёт новый слайд и размещает **линейный график с маркерами** в указанных координатах.

### Шаг 3: Добавьте заголовок графика (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Совет:* Жирный серый заголовок делает график сразу узнаваемым.

### Шаг 4: Форматирование осей и добавление сетки (add grid lines)
#### Форматирование вертикальной оси
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Форматирование горизонтальной оси
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Почему это важно:* Чёткая сетка и повернутые подписи повышают читаемость, особенно при плотных данных.

### Шаг 5: Настройка легенды (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Шаг 6: Установка цветов фона (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Шаг 7: Сохраните презентацию
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Результат:* У вас теперь есть файл PowerPoint (`FormattedChart_out.pptx`) с полностью отформатированным линейным графиком.

## Практические применения
- **Бизнес‑отчёты:** Демонстрация квартальных результатов с помощью трендовых линий.
- **Образовательные слайды:** Визуализация научных данных для лекций.
- **Проектные предложения:** Выделение этапов и прогнозов.
- **Маркетинговый анализ:** Представление тенденций ROI кампаний.
- **Интеграция в дашборды:** Экспорт живых данных в PowerPoint для встреч со стейкхолдерами.

## Соображения по производительности
- **Управление памятью:** Всегда вызывайте `dispose()` у объекта `Presentation`, чтобы своевременно освобождать нативные ресурсы.

## Распространённые проблемы и решения
| Проблема | Решение |
|----------|---------|
| **Лицензия не применена** | Загрузите пробную/полную лицензию до создания любых объектов `Presentation`. |
| **График пустой** | Убедитесь, что слайд действительно содержит серии данных; при необходимости добавьте серии. |
| **Файл не сохраняется** | Проверьте, что выходной каталог существует (используйте шаг «create directory java»). |
| **Цвета не применяются** | Используйте константы `Color` из `java.awt.Color` или `PresetColor`. |

## Часто задаваемые вопросы

**В: Могу ли я создавать другие типы графиков, кроме линейных?**  
О: Да, Aspose.Slides поддерживает столбчатые, круговые, точечные и многие другие типы графиков.

**В: Как добавить несколько серий данных в линейный график?**  
О: Используйте `chart.getChartData().getSeries().add(...)` для вставки дополнительных серий перед форматированием.

**В: Можно ли экспортировать график как изображение?**  
О: Конечно. Вызовите `chart.getChartData().getChartDataWorkbook().save(...)` или отрендерите слайд в формат изображения.

**В: Нужна ли платная лицензия для разработки?**  
О: Бесплатная временная лицензия подходит для оценки; коммерческая лицензия требуется для продакшн‑развёртываний.

**В: Какие версии Java поддерживаются?**  
О: Библиотека работает с JDK 8‑до JDK 22 (используйте соответствующий классификатор, например `jdk16`). 

---

**Последнее обновление:** 2026-03-07  
**Тестировано с:** Aspose.Slides for Java 25.4 (классификатор jdk16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
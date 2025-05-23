---
"date": "2025-04-17"
"description": "Узнайте, как создавать и управлять диаграммами с помощью Aspose.Slides для Java. Это руководство охватывает кластеризованные столбчатые диаграммы, управление рядами данных и многое другое."
"title": "Освоение создания диаграмм на Java с помощью Aspose.Slides&#58; Подробное руководство"
"url": "/ru/java/charts-graphs/aspose-slides-java-chart-creation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение создания диаграмм на Java с помощью Aspose.Slides

## Как создавать и управлять диаграммами с помощью Aspose.Slides для Java

### Введение
Создание динамических презентаций часто подразумевает визуализацию данных с помощью диаграмм. **Aspose.Slides для Java**, вы можете без усилий создавать и управлять различными типами диаграмм, повышая как ясность, так и воздействие. Это руководство проведет вас через создание пустой презентации, добавление кластеризованных столбчатых диаграмм, управление рядами и настройку инверсии точек данных — все с помощью Aspose.Slides для Java.

**Что вы узнаете:**
- Как настроить Aspose.Slides для Java.
- Действия по созданию кластеризованной столбчатой диаграммы в презентации.
- Методы эффективного управления рядами диаграмм и точками данных.
- Методы условного инвертирования отрицательных точек данных для лучшей визуализации.
- Как безопасно сохранить презентацию.

Прежде чем начать, давайте рассмотрим предварительные условия.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

1. **Требуемые библиотеки:**
   - Aspose.Slides для Java (версия 25.4 или более поздняя).

2. **Требования к настройке среды:**
   - Совместимая версия JDK (например, JDK 16).
   - Установите Maven или Gradle, если вы предпочитаете управление зависимостями.

3. **Необходимые знания:**
   - Базовые знания программирования на Java.
   - Знакомство с обработкой зависимостей в вашей среде разработки.

## Настройка Aspose.Slides для Java
Чтобы начать использовать Aspose.Slides, выполните следующие действия:

**Установка Maven:**
Добавьте следующую зависимость к вашему `pom.xml` файл:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Установка Gradle:**
Добавьте следующую строку в ваш `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямая загрузка:**
Либо загрузите последнюю версию с сайта [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
- **Бесплатная пробная версия:** Вы можете начать с бесплатной пробной версии, чтобы изучить функции.
- **Временная лицензия:** Получите временную лицензию для полного доступа на период оценки.
- **Покупка:** Рассмотрите возможность покупки, если вы считаете, что она соответствует вашим долгосрочным потребностям.

### Базовая инициализация
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Ваш код здесь...
pres.dispose(); // Всегда выбрасывайте презентационный объект после окончания работы.
```

## Руководство по внедрению
Теперь давайте разберем каждую функцию на выполнимые шаги.

### Создание презентации с кластеризованной столбчатой диаграммой
#### Обзор
В этом разделе рассказывается, как создать пустую презентацию и добавить кластеризованную столбчатую диаграмму в определенных координатах на слайде.

**Шаги:**
1. **Инициализируйте объект презентации:**
   - Создайте новый экземпляр `Presentation`.
2. **Добавьте кластеризованную столбчатую диаграмму:**
   - Использовать `getSlides().get_Item(0).getShapes().addChart()` чтобы добавить диаграмму.
   - Укажите положение, размеры и тип.

**Пример кода:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Добавьте кластеризованную столбчатую диаграмму в точке (50, 50) шириной 600 и высотой 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Управление серией диаграмм
#### Обзор
Узнайте, как очистить существующие ряды и добавить новые с настраиваемыми точками данных.

**Шаги:**
1. **Очистить существующие серии:**
   - Использовать `series.clear()` для удаления любых ранее существовавших данных.
2. **Добавить новую серию:**
   - Добавьте новую серию, используя `series.add()`.
3. **Вставьте точки данных:**
   - Использовать `getDataPoints().addDataPointForBarSeries()` для сложения значений, в том числе отрицательных.

**Пример кода:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Очистите существующую серию и добавьте новую.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Добавьте точки данных с различными значениями (положительными и отрицательными).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Инвертирование точек данных ряда на основе условий
#### Обзор
Настройте визуализацию отрицательных точек данных, условно инвертировав их.

**Шаги:**
1. **Установить поведение инверсии по умолчанию:**
   - Использовать `setInvertIfNegative(false)` для определения общего поведения инверсии.
2. **Условно инвертировать определенные точки данных:**
   - Применять `setInvertIfNegative(true)` на конкретной точке данных, если она отрицательная.

**Пример кода:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Добавьте точки данных с различными значениями (положительными и отрицательными).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Установить поведение инверсии по умолчанию
    series.get_Item(0).invertIfNegative(false);
    
    // Условно инвертировать определенную точку данных
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Заключение
В этом уроке вы узнали, как настроить Aspose.Slides для Java и создать кластеризованную столбчатую диаграмму. Вы также изучили управление рядами данных и настройку визуализации отрицательных точек данных. С этими навыками вы теперь можете уверенно создавать динамические диаграммы в своих приложениях Java.

**Следующие шаги:**
- Поэкспериментируйте с различными типами диаграмм, доступными в Aspose.Slides для Java.
- Изучите дополнительные возможности настройки, чтобы улучшить свои презентации.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
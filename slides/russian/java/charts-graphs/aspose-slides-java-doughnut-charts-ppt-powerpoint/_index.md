---
date: '2026-02-17'
description: Узнайте, как создать кольцевую диаграмму PowerPoint с помощью Aspose.Slides
  для Java и добавить точки данных диаграммы программно. Следуйте простым шагам и
  примерам кода.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Создание кольцевой диаграммы PowerPoint с помощью Aspose.Slides для Java
url: /ru/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание кольцевой диаграммы в PowerPoint с помощью Aspose.Slides for Java

## Введение
Создание убедительных презентаций часто требует не только текста и изображений; диаграммы могут значительно улучшить повествование, эффективно визуализируя данные. Однако многие разработчики сталкиваются с трудностями при программном добавлении динамических диаграмм в файлы PowerPoint. В этом руководстве показано, как **создать кольцевую диаграмму в PowerPoint** с помощью Aspose.Slides for Java — мощного инструмента, сочетающего гибкость и простоту использования.

**Что вы узнаете:**
- Как инициализировать презентацию с помощью Aspose.Slides for Java
- Пошаговое руководство по добавлению кольцевой диаграммы на слайды
- Настройка точек данных и параметров меток
- Сохранение изменённой презентации с высоким качеством

Давайте посмотрим, как использовать эти возможности для улучшения ваших презентаций. Прежде чем начать, убедитесь, что вы знакомы с базовыми концепциями программирования на Java.

## Быстрые ответы
- **Какая библиотека создаёт кольцевую диаграмму в PowerPoint?** Aspose.Slides for Java
- **Можно ли программно добавлять точки данных в диаграмму?** Да, с помощью API диаграмм
- **Нужна ли лицензия для продакшна?** Требуется действующая лицензия Aspose.Slides
- **Какие версии Java поддерживаются?** Java 8 и выше (показан классификатор JDK 16)
- **Сколько серий можно добавить?** В примере добавлено до 15 серий, но вы можете изменить это по необходимости

## Что такое кольцевая диаграмма в PowerPoint?
Кольцевая диаграмма — это вариант круговой диаграммы с пустым центром, позволяющий отображать несколько серий данных в компактной и визуально привлекательной форме. Она идеальна для демонстрации отношений часть‑целое при сохранении чистого дизайна.

## Почему стоит использовать Aspose.Slides for Java для создания кольцевых диаграмм?
- **Полный контроль** над внешним видом, данными и расположением диаграммы без открытия PowerPoint
- **Без COM‑интеропа** — работает на любой платформе, поддерживающей Java
- **Высокая производительность** при генерации больших наборов слайдов или интеграции с веб‑службами
- **Широкие возможности настройки**: взрыв, размер отверстия, углы секторов, форматирование меток и др.

## Предварительные требования
- Базовые знания программирования на Java.
- IDE, например IntelliJ IDEA или Eclipse.
- Maven или Gradle для управления зависимостями.
- Действующая лицензия Aspose.Slides for Java (доступна бесплатная пробная версия).

## Настройка Aspose.Slides for Java
Выберите менеджер зависимостей, соответствующий вашему проекту.

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

Если вы предпочитаете загрузить библиотеку вручную, посетите страницу [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Получение лицензии
Вы можете начать с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides. Для длительного использования приобретите лицензию или запросите временную на сайте [Aspose's website](https://purchase.aspose.com/temporary-license/). Следуйте инструкциям по настройке среды и инициализации Aspose.Slides в вашем приложении.

## Как создать кольцевую диаграмму в PowerPoint с помощью Aspose.Slides for Java
Ниже представлено полное пошаговое руководство. Каждый блок кода объясняется непосредственно перед ним, чтобы вы точно знали, что происходит.

### Шаг 1: Инициализация презентации
Сначала загрузите существующий PPTX или создайте новый. Это подготовит коллекцию слайдов для дальнейших изменений.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Шаг 2: Добавление кольцевой диаграммы на слайд
Мы добавляем форму диаграммы, очищаем любые серии/категории по умолчанию и задаём базовые визуальные свойства.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Шаг 3: Добавление точек данных и настройка меток
Здесь мы заполняем категории, добавляем точки данных для каждой серии и тонко настраиваем внешний вид меток. Именно здесь используется ключевое слово **add chart data points**.

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

### Шаг 4: Сохранение обновлённой презентации
Наконец, сохраняем изменения в новый файл PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Практические применения
Кольцевые диаграммы могут использоваться в различных реальных сценариях:
- **Финансовые отчёты:** визуализация распределения бюджета или структуры расходов.
- **Анализ рынка:** отображение доли рынка среди конкурентов.
- **Результаты опросов:** представление категориальных данных опросов в компактной форме.
- **Генерация дашбордов:** комбинирование с запросами к базе данных для создания слайдов с живыми данными.

## Соображения по производительности
- **Освобождение ресурсов**: вызывайте `pres.dispose()` после завершения работы, чтобы освободить нативную память.
- **Ограничение количества диаграмм**: добавление сотен диаграмм может увеличить потребление памяти; при необходимости используйте пакетную обработку.
- **Использование потоков**: для огромных наборов данных заполняйте рабочую книгу напрямую из потоков, а не из массивов в памяти.

## Распространённые проблемы и решения
| Проблема | Причина | Решение |
|----------|---------|---------|
| **Диаграмма отображается пустой** | Ячейки данных не заполнены корректно | Проверьте, что `workBook.getCell(...)` ссылается на правильные индексы строк/столбцов. |
| **Меток перекрываются** | Слишком много категорий в ограниченном пространстве | Увеличьте `DoughnutHoleSize` или скорректируйте `FirstSliceAngle`. |
| **OutOfMemoryError** | Большие презентации без освобождения ресурсов | Вызовите `pres.dispose()` после сохранения и при необходимости увеличьте размер кучи JVM. |

## Часто задаваемые вопросы

**В: Можно ли использовать Aspose.Slides for Java в коммерческих приложениях?**  
О: Да, но требуется действующая коммерческая лицензия. Бесплатная пробная версия доступна для оценки.

**В: Как добавить более 15 серий?**  
О: Увеличьте предел цикла в шаге «Add Doughnut Chart» и убедитесь, что в рабочей книге достаточно строк.

**В: Можно ли изменить размер отверстия кольца после создания?**  
О: Да, вызовите `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` в любой момент до сохранения.

**В: Можно ли экспортировать диаграмму как изображение вместо PPTX?**  
О: Конечно. Используйте `chart.getImage()` и сохраните полученный `java.awt.image.BufferedImage` в нужном формате.

**В: Поддерживает ли Aspose.Slides анимированные диаграммы?**  
О: Анимацию можно добавить через API `ISlide.getTimeline()`, однако это выходит за рамки данного руководства.

## Заключение
Теперь у вас есть полностью готовый к производству метод **создания кольцевой диаграммы в PowerPoint** с помощью Aspose.Slides for Java, включая добавление точек данных, настройку меток и учёт производительности. Экспериментируйте с различными цветами, источниками данных и типами диаграмм, чтобы ваши презентации действительно выделялись.

---

**Последнее обновление:** 2026-02-17  
**Тестировано с:** Aspose.Slides for Java 25.4 (классификатор JDK 16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-03-20'
description: Узнайте, как добавить диаграмму в Java‑презентации с помощью Aspose.Slides
  и быстро создавать файлы диаграмм презентаций.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Как добавить диаграмму в презентации Java с помощью Aspose.Slides
url: /ru/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как добавить chart в презентацию с помощью Aspose.Slides for Java

## Введение

Создание динамичных презентаций, эффективно передающих данные, является необходимостью в современном быстро меняющемся деловом окружении. Независимо от того, готовите ли вы финансовый отчёт, маркетинговую презентацию или обновление статуса проекта, **знание того, как добавить chart** в ваши слайды может значительно повысить вовлечённость аудитории. В этом руководстве вы пошагово узнаете, как добавить 3D stacked column chart, настроить его данные и сохранить итоговый файл — всё с помощью Aspose.Slides for Java.

### Быстрые ответы
- **Какова основная библиотека?** Aspose.Slides for Java  
- **Какой тип диаграммы демонстрируется?** 3D Stacked Column  
- **Могу ли я программно генерировать файлы диаграмм презентаций?** Да, используя методы API, показанные ниже  
- **Какая версия Java рекомендуется?** JDK 16 или новее  
- **Нужна ли лицензия для продакшн?** Для коммерческого использования требуется действующая лицензия Aspose.Slides  

## Что такое “how to add chart” в Aspose.Slides?

Aspose.Slides for Java предоставляет обширный набор объектов, позволяющих создавать, редактировать и экспортировать файлы PowerPoint без Microsoft Office. Добавление chart сводится к созданию объекта `Presentation`, вставке формы диаграммы и передаче данных через встроенную рабочую книгу.

## Почему стоит добавлять chart в Java‑презентации?

- **Визуальное воздействие:** Диаграммы превращают сырые цифры в мгновенно понятные визуальные образы.  
- **Автоматизация:** Генерируйте отчёты «на лету» — идеально для запланированных email‑дайджестов или панелей мониторинга.  
- **Последовательность:** Используйте одинаковый стиль и фирменный дизайн во всех автоматически создаваемых презентациях.  
- **Переносимость:** Экспортируйте в PPTX, PDF или изображения одним вызовом метода.

## Предварительные требования

- **Библиотеки и зависимости:** Необходимо установить Aspose.Slides for Java.  
- **Настройка окружения:** Работайте в Java‑среде (рекомендовано JDK 16 или новее).  
- **База знаний:** Знание базовых концепций программирования на Java будет полезным.

## Настройка Aspose.Slides для Java

### Установка

Чтобы интегрировать Aspose.Slides в ваш проект, выполните один из вариантов ниже.

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

**Direct Download**: При необходимости скачайте последнюю версию с сайта [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
- **Бесплатная пробная версия:** Начните с бесплатной пробной версии, чтобы оценить возможности.  
- **Временная лицензия:** Получите временную лицензию для расширенного тестирования.  
- **Покупка:** Приобретите полную лицензию для коммерческого использования.

После установки вы можете создать экземпляр класса `Presentation`, который служит точкой входа для всех операций, связанных с chart.

## Руководство по реализации

### Как добавить chart в презентацию с 3D stacked column

#### Обзор
Создание презентации с нуля простo с Aspose.Slides. В этом разделе мы добавим 3D stacked column chart на первый слайд нашей презентации.

**Шаги:**

1. **Инициализировать объект Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Объяснить параметры**  
   - `ChartType.StackedColumn3D`: Указывает тип диаграммы.  
   - Позиция и размер `(0, 0, 500, 500)`: Определяют, где диаграмма будет размещена на слайде.

### Настройка данных диаграммы

#### Обзор
Чтобы ваша диаграмма имела смысл, необходимо настроить её серии данных и категории. В этом разделе показано, как добавить конкретные точки данных в вашу диаграмму.

**Шаги:**

1. **Получить доступ к рабочей книге данных диаграммы**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Установка свойств Rotation3D для диаграммы

#### Обзор
Улучшите визуальную привлекательность диаграммы, задав свойства 3D‑поворота. Эта настройка позволяет регулировать перспективу и глубину.

**Шаги:**

1. **Настроить 3D‑повороты**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Объяснить параметры**  
   - `setRightAngleAxes(true)`: Обеспечивает перпендикулярность осей.  
   - Значения поворота: Регулируют угол и глубину 3D‑вида.

### Заполнение серии данными в диаграмме

#### Обзор
Заполнение диаграммы точками данных критично для анализа. Здесь мы добавим конкретные значения в одну из серий диаграммы.

**Шаги:**

1. **Добавить точки данных**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Регулировка перекрытия серий в диаграмме

#### Обзор
Точная настройка внешнего вида диаграммы может улучшить её читаемость. В этом разделе рассматривается, как изменить свойство overlap для лучшей визуализации данных.

**Шаги:**

1. **Установить перекрытие серий**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Сохранение презентации

#### Обзор
После настройки презентации сохраните её на диск в нужном формате. Этот шаг гарантирует, что все изменения будут сохранены.

**Шаги:**

1. **Сохранить презентацию**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Диаграмма выглядит плоской** | Не задан 3D‑поворот | Вызовите `setRotation3D` с подходящими значениями X/Y. |
| **Данные не отображаются** | Ячейки рабочей книги не связаны | Убедитесь, что `fact.getCell` ссылается на правильные индексы строк/столбцов. |
| **Файл не сохраняется** | Неправильный путь или отсутствие прав | Проверьте, что `outputFilePath` доступен для записи и папка существует. |

## Часто задаваемые вопросы

**В: Можно ли генерировать файлы диаграмм презентаций в форматах, отличных от PPTX?**  
О: Да, Aspose.Slides поддерживает PDF, ODP и форматы изображений через перечисление `SaveFormat`.

**В: Нужна ли лицензия для запуска кода в процессе разработки?**  
О: Временная или оценочная лицензия подходит для разработки, но для продакшн‑развёртываний требуется полная лицензия.

**В: Можно ли добавить несколько диаграмм на один слайд?**  
О: Конечно. Вызывайте `slide.getShapes().addChart` несколько раз, задавая разные позиции или размеры.

**В: Как изменить цветовую палитру диаграммы?**  
О: Используйте `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` и задайте `SolidFillColor`.

**В: Можно ли привязать диаграмму к внешнему источнику данных, например базе данных?**  
О: Да. Получите данные через JDBC, затем программно заполните ячейки рабочей книги перед сохранением.

## Заключение

Теперь вы знаете **how to add chart** в Java‑презентацию, как настроить её данные, задать 3D‑поворот, отрегулировать перекрытие серий и сохранить итоговый файл. Эти знания позволяют автоматизировать генерацию отчётов, поддерживать единый фирменный стиль и создавать презентации, основанные на данных, без ручного труда. Для более глубокой кастомизации — например, стилизации легенд, осей или применения тем — изучайте полный набор возможностей в официальной документации.

Для получения более продвинутых функций и вариантов настройки обратитесь к [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-03-20  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16)  
**Автор:** Aspose
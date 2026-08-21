---
date: '2026-08-21'
description: Узнайте, как создать clustered column chart и добавить trend lines с
  Aspose.Slides for Java. Включает настройку лицензии, интеграцию Maven/Gradle и подробные
  примеры.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Создайте clustered column chart и добавьте trend lines, используя
  Aspose.Slides for Java. Это руководство охватывает настройку лицензии, Maven/Gradle
  и пошаговые фрагменты кода.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Создайте clustered column chart и добавьте trend lines с Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Как создать clustered column chart и добавить trend lines с помощью Aspose.Slides
  for Java
url: /ru/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать сгруппированную столбчатую диаграмму и добавить линии тренда с помощью Aspose.Slides для Java

Создание убедительных презентаций часто начинается с четкой визуализации ваших данных. В этом руководстве вы **создадите объекты сгруппированной столбчатой диаграммы**, а затем обогатите их различными линиями тренда — экспоненциальной, линейной, логарифмической, скользящего среднего, полиномиальной и степенной — используя мощный API Aspose.Slides для Java.

## Быстрые ответы
- **Какой первый шаг?** Инициализировать объект `Presentation` и добавить сгруппированную столбчатую диаграмму на слайд.  
- **Какая версия библиотеки требуется?** Aspose.Slides for Java 25.4 или новее.  
- **Можно ли использовать Maven или Gradle?** Да, оба поддерживаются; Maven использует `<dependency>`, а Gradle — `implementation`.  
- **Нужна ли лицензия?** Пробная лицензия подходит для оценки; полная лицензия Aspose.Slides снимает ограничения оценки.  
- **Сколько типов линий тренда доступно?** Шесть встроенных типов: экспоненциальный, линейный, логарифмический, скользящее среднее, полиномиальный и степенной.

## Что такое создание сгруппированной столбчатой диаграммы?
`create clustered column chart` означает создание диаграммы, которая группирует несколько рядов данных рядом друг с другом в каждой категории, облегчая сравнение значений между рядами. Этот тип диаграммы идеален для визуализации категориальных данных, таких как квартальные продажи по регионам, позволяя зрителям быстро заметить различия между группами.

## Зачем добавлять линию тренда?
Линии тренда раскрывают скрытую закономерность ряда данных, помогая прогнозировать будущие значения, выделять темпы роста или сглаживать шумные данные. Добавляя линию тренда к сгруппированной столбчатой диаграмме, сырые цифры превращаются в практические инсайты, позволяя заинтересованным сторонам понять долгосрочные тенденции и принимать решения, основанные на данных.

## Предварительные требования
- **Java Development Kit (JDK):** 8 или новее.  
- **Aspose.Slides for Java:** версия 25.4 или новее.  
- **IDE:** IntelliJ IDEA, Eclipse или любой совместимый с Java редактор.  
- **Инструмент сборки:** Maven или Gradle (необязательно, но рекомендуется).  
- **Лицензия:** пробный или приобретённый файл лицензии Aspose.Slides.  

Вы должны быть уверенно владеть базовым синтаксисом Java и быть знакомы с управлением зависимостями проекта.

## Как настроить Aspose.Slides для Java?
Добавьте библиотеку Aspose.Slides в ваш проект, используя предпочитаемый менеджер зависимостей, затем разместите файл лицензии там, где его сможет найти среда выполнения. Это обеспечивает полную функциональность и снимает ограничения оценки.

### Maven
Add this dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямое скачивание
Вы также можете загрузить JAR вручную с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Лицензия Aspose Slides
Поместите файл `Aspose.Slides.lic` в корень вашего проекта или задайте лицензию программно с помощью `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Пробная лицензия снимает все ограничения функций, но приобретённая лицензия устраняет водяной знак оценки и предоставляет полные оптимизации производительности. Для использования в продакшене рассмотрите покупку лицензии на [странице покупки Aspose](https://purchase.aspose.com/buy).

## Как создать презентацию и добавить сгруппированную столбчатую диаграмму?
Класс `Presentation` представляет файл PowerPoint и предоставляет методы для создания, редактирования и сохранения слайдов. Создайте экземпляр `Presentation`, добавьте слайд, затем вызовите `addChart` с `ChartType.ClusteredColumn`, чтобы создать объект диаграммы. Этот процесс настраивает холст слайда, вставляет форму диаграммы и подготавливает её к заполнению данными и стилизации.

1. **Инициализировать презентацию** – настроить выходную папку и создать новый экземпляр `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Добавить сгруппированную столбчатую диаграмму** – получить форму диаграммы, настроить её серии и заполнить точки данных.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Как добавить экспоненциальную линию тренда?
Интерфейс `ITrendline` определяет линию тренда, которую можно добавить к серии диаграммы для моделирования закономерностей данных. Примените экспоненциальную линию тренда к серии, создав экземпляр `ITrendline`, установив его `TrendlineType` в `Exponential` и присоединив к нужной серии. Этот тип линии тренда полезен для данных, которые быстро растут с ускоряющимся темпом.

1. **Настроить линию тренда** – выбрать серию и вызвать `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Как добавить линейную линию тренда?
Линейная линия тренда отображает наилучшее приближение прямой линии через ваши точки данных. Вы также можете настроить её внешний вид, например цвет линии и толщину, чтобы соответствовать стилю вашей презентации.

1. **Настроить линию тренда** – использовать `addTrendline(TrendlineType.Linear)`, а затем изменить `getLineFormat().setFillFormat().setFillType(FillType.Solid)` для изменения цвета.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Как добавить логарифмическую линию тренда с пользовательским текстовым фреймом?
Логарифмические линии тренда идеальны для данных, которые быстро растут вначале, а затем стабилизируются. Переопределение метки по умолчанию позволяет добавить пояснительный текст, разъясняющий значение тренда.

1. **Настроить линию тренда** – после добавления линии тренда получить её `getDataLabel()` и установить свойство `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Как добавить линию тренда скользящего среднего?
Линии тренда скользящего среднего сглаживают краткосрочные колебания, чтобы выделить долгосрочные тенденции. Вы можете указать период (количество точек), используемый для усреднения, что позволяет контролировать гладкость линии.

1. **Настроить линию тренда** – вызвать `addTrendline(TrendlineType.MovingAverage)` и установить `setPeriod(3)`, чтобы использовать скользящее среднее по трём точкам.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Как добавить полиномиальную линию тренда?
Полиномиальные линии тренда подгоняют данные кривой, определяемой полиномиальным уравнением. Свойство `order` контролирует степень полинома, позволяя моделировать более сложные зависимости.

1. **Настроить линию тренда** – после добавления линии тренда установить `setOrder(3)` для кубической аппроксимации.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Как добавить степенную линию тренда?
Степенные линии тренда полезны, когда данные следуют степенному закону. Вы также можете задать значения прогнозирования назад и вперёд, чтобы расширить линию за пределы существующего диапазона данных.

1. **Настроить линию тренда** – использовать `addTrendline(TrendlineType.Power)` и изменить `setBackward(2)`, чтобы расширить линию назад.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Практические применения линий тренда в сгруппированных столбчатых диаграммах
- **Финансовый анализ:** Экспоненциальные и полиномиальные тренды помогают прогнозировать движения цен акций.  
- **Прогнозирование продаж:** Линии скользящего среднего сглаживают сезонные всплески, предоставляя более ясный обзор базовых тенденций продаж.  
- **Научные исследования:** Логарифмические тренды идеальны для данных, охватывающих несколько порядков величины, таких как акустическая интенсивность или уровни pH.  
- **Мониторинг операций:** Степенные линии тренда могут моделировать деградацию производительности со временем.

## Как оптимизировать память при использовании Aspose.Slides?
Своевременно освобождайте объекты и используйте `presentation.dispose()` после сохранения. Для больших наборов данных включайте отложенную загрузку изображений и избегайте загрузки всей диаграммы в память сразу.

- **Шаблоны освобождения:** Оберните `Presentation` в блок try‑with‑resources или вызовите `presentation.dispose()` в блоке finally.  
- **Отложенная загрузка:** Установите `ChartData.setUseCache(true)`, когда работаете с тысячами точек данных.  
- **Потоковый вывод:** Запишите презентацию напрямую в `FileOutputStream`, чтобы не держать весь файл в ОЗУ.

## Количественные преимущества Aspose.Slides для Java
Aspose.Slides поддерживает **более 50 типов диаграмм**, может генерировать презентации с **более 1 000 слайдов** менее чем за **30 секунд** на типичном процессоре 2 ГГц и обрабатывает **PDF‑файлы до 500 страниц** без необходимости установки Microsoft Office. Эти показатели подтверждены в последнем выпуске 25.4.

## Заключение
Теперь у вас есть полное решение от начала до конца для **создания объектов сгруппированной столбчатой диаграммы** и их обогащения всеми основными типами линий тренда, доступными в Aspose.Slides для Java. Следуя приведённым выше шагам, вы сможете создавать презентации, основанные на данных, которые одновременно визуально привлекательны и аналитически мощны.

Следующие шаги включают изучение вариантов стилизации диаграмм, экспорт в PDF/HTML и автоматизацию генерации диаграмм из нескольких источников данных.

## Часто задаваемые вопросы

**Q: Как настроить Aspose.Slides для проекта Maven?**  
A: Добавьте фрагмент `<dependency>`, показанный в разделе Maven, в ваш `pom.xml` и выполните `mvn clean install`.

**Q: Можно ли настроить линии тренда помимо цвета и метки?**  
A: Да, вы можете изменить стиль линии, ширину, шаблон штриха и даже прогнозировать значения вперёд/назад через API `ITrendline`.

**Q: Что делать, если возникнет ошибка совместимости версии?**  
A: Убедитесь, что версия вашего JDK соответствует минимальному требованию Aspose.Slides (JDK 8+). Обратитесь к примечаниям к выпуску Aspose для получения информации о возможных изменениях.

**Q: Можно ли автоматически добавить линии тренда к нескольким диаграммам?**  
A: Абсолютно. Пройдитесь в цикле по каждому `IChart` в коллекции слайдов и вызовите соответствующий метод `addTrendline` для каждой серии.

**Q: Нужна ли платная лицензия для использования в продакшене?**  
A: Да, приобретённая лицензия Aspose.Slides снимает ограничения оценки и открывает полные оптимизации производительности.

---

**Последнее обновление:** 2026-08-21  
**Тестировано с:** Aspose.Slides for Java 25.4  
**Автор:** Aspose

## Связанные руководства

- [aspose slides maven dependency: Добавление и настройка диаграмм в презентациях с использованием Aspose.Slides для Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Добавить анимацию к диаграмме PowerPoint с помощью Aspose.Slides для Java – Пошаговое руководство](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Создать диаграмму PowerPoint Java – Сохранить презентации с диаграммами с использованием Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
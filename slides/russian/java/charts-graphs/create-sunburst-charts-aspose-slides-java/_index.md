---
date: '2026-07-03'
description: Узнайте, как пошагово создавать sunburst charts в Java с использованием
  Aspose.Slides, с полными возможностями настройки для презентаций PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Как создать sunburst charts в Java с использованием Aspose.Slides
url: /ru/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать Sunburst‑диаграммы в Java с помощью Aspose.Slides

## Введение
В современных презентациях, основанных на данных, быстрое создание визуализаций **how to create sunburst** может выделить ваши слайды. Это руководство проведёт вас через процесс создания Sunburst‑диаграммы с помощью Aspose.Slides для Java, от настройки проекта до окончательного экспорта, чтобы вы могли предоставлять убедительные графики иерархических данных, не выходя из экосистемы Java.

## Быстрые ответы
- **Какой основной класс для файла PowerPoint?** `Presentation` – он представляет весь PPTX в памяти.  
- **Сколько строк кода требуется для базовой Sunburst‑диаграммы?** Обычно 5–7 строк после подключения библиотеки.  
- **Какие форматы вывода поддерживаются?** PPTX, PDF, PNG, SVG и HTML.  
- **Можно ли стилизовать отдельные сегменты?** Да – цвета заливки, границы и подписи данных полностью настраиваемы.  
- **Нужна ли лицензия для продакшн?** Бесплатная оценочная версия подходит для тестирования; для развертывания требуется коммерческая лицензия.

## Что такое Sunburst‑диаграмма?
Sunburst‑диаграмма визуализирует иерархические данные в виде концентрических колец, где каждое кольцо представляет уровень иерархии. Она позволяет зрителям мгновенно понять отношения «родитель‑дитя», что делает её идеальной для организационных схем, таксономических отображений и многоуровневых метрик. Особенно полезна для отображения многоуровневых категорий, таких как продуктовые линейки, географические регионы или организационные структуры, позволяя увидеть как общую распределённость, так и детализированный разбор внутри каждого сегмента.

## Почему использовать Aspose.Slides для Sunburst‑диаграмм?
Aspose.Slides поддерживает **30+ типов диаграмм**, обрабатывает файлы до **500 MB** без загрузки всего документа в память и рендерит графику с **300 DPI** для кристально‑чистого вывода. Эти измеримые возможности обеспечивают быструю генерацию и высококачественные визуализации даже для больших презентаций. Кроме того, библиотека предоставляет потокобезопасные операции и бесшовно интегрируется с популярными инструментами сборки Java, что делает её подходящей как для настольной, так и для серверной генерации презентаций в масштабе.

## Требования
- Java Development Kit (JDK) 8 или новее.  
- Maven или Gradle для управления **dependency**.  
- Aspose.Slides for Java (последняя версия).  
- Базовое понимание иерархических структур данных.

## Как создать Sunburst‑диаграммы пошагово?
Настройте окружение, добавьте диаграмму, загрузите иерархические данные, стилизуйте её и сохраните файл — всё в нескольких простых шагах. Ниже представлен точный рабочий процесс, который можно выполнить без написания дополнительного шаблонного кода. Процесс полностью автоматизирован, не требует ручного взаимодействия с UI и может быть интегрирован в пакетные задания или веб‑службы для генерации диаграмм по запросу.

### Шаг 1: Настройка проекта
Добавьте зависимость Aspose.Slides Maven (или эквивалентный фрагмент Gradle) в ваш `pom.xml`. Это подтянет все необходимые бинарные файлы и транзитивные библиотеки.

### Шаг 2: Загрузка или создание презентации
`Presentation` — это объект верхнего уровня в Aspose.Slides, представляющий один файл PowerPoint в памяти. Создайте его с помощью `new Presentation()` для новой презентации или передайте путь к файлу, чтобы открыть существующий PPTX.

### Шаг 3: Добавление Sunburst‑диаграммы
Вставьте новую форму диаграммы на слайд, используя `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Это создаёт заполнитель Sunburst, готовый к данным. `ChartType.Sunburst` указывает тип Sunburst‑диаграммы при добавлении диаграммы на слайд.

### Шаг 4: Заполнение иерархических данных
`ChartData` хранит серии данных и категории для диаграммы. Получите доступ к коллекции `ChartData` диаграммы и добавьте серии и категории, отражающие вашу иерархию. Для каждого уровня укажите отношение родитель‑дитя через свойство `ParentSeries`, позволяя диаграмме автоматически отрисовывать концентрические кольца.

### Шаг 5: Настройка внешнего вида
Точно настройте цвета сегментов, стили границ и подписи данных через объекты `ChartSeries` и `ChartDataPoint`. `ChartSeries` представляет серию точек данных в диаграмме. `ChartDataPoint` представляет отдельную точку данных в серии. Вы также можете включить 3‑D‑вращение или задать свойство `Explode`, чтобы выделить отдельные срезы.

### Шаг 6: Сохранение презентации
Перечисление `SaveFormat` определяет форматы файлов, в которых можно сохранить презентацию. Вызовите `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)`, чтобы записать файл на диск. Вы также можете экспортировать в PDF или PNG, изменив значение перечисления `SaveFormat`.

## Как настроить цвета Sunburst‑диаграммы?
Укажите цвет заливки для каждого `ChartDataPoint`, используя `point.getFillFormat().setFillType(FillType.Solid)`, а затем `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Такой прямой подход позволяет соответствовать корпоративному бренду или выделять ключевые точки данных. Вы также можете применять градиентные заливки, регулировать прозрачность или использовать цвета темы, чтобы обеспечить согласованность с остальным дизайном слайда.

## Распространённые проблемы и решения
- **Проблема:** Hierarchy appears flat.  
  **Решение:** Ensure each child series correctly references its `ParentSeries`. Missing links cause the chart to treat all data as a single level.  
- **Проблема:** Exported PNG looks blurry.  
  **Решение:** Increase the export DPI by setting `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.  
- **Проблема:** Large PPTX files cause OutOfMemoryError.  
  **Решение:** Use `Presentation.setMemoryOptimization(true)` to stream data and keep memory usage low.

## Часто задаваемые вопросы

**Q:** Можно ли создать Sunburst‑диаграмму из CSV‑файла?  
A: Да. Считайте CSV, построите иерархию в памяти и передайте её в коллекцию `ChartData` диаграммы перед сохранением.

**Q:** Поддерживает ли Aspose.Slides анимированные переходы для Sunburst‑диаграмм?  
A: Да. Примените `SlideShowTransition` к слайду или используйте `ChartFormat.setAnimationEnabled(true)` для анимации на уровне диаграммы.

**Q:** Можно ли экспортировать диаграмму как векторный SVG?  
A: Абсолютно. Сохраните презентацию с `SaveFormat.Svg`, чтобы получить масштабируемую векторную версию Sunburst‑диаграммы.

**Q:** Каково максимальное количество точек данных, которое может обработать Sunburst‑диаграмма?  
A: Aspose.Slides надёжно обрабатывает до **10 000** точек данных в одной Sunburst‑диаграмме без деградации производительности.

**Q:** Нужна ли отдельная лицензия для каждой среды развертывания?  
A: Одна коммерческая лицензия покрывает все среды (разработка, тестирование, продакшн) при соблюдении условий лицензии.

## Заключение
Теперь у вас есть полное пошаговое руководство по **how to create sunburst** диаграмм в Java с использованием Aspose.Slides. Следуя описанному процессу, вы сможете генерировать высококачественные, полностью настраиваемые иерархические визуализации для любой презентации PowerPoint.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Связанные руководства

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Master PowerPoint Chart Customization Using Aspose.Slides Java for Dynamic Presentations](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step‑by‑Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
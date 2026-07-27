---
date: '2026-07-27'
description: Узнайте, как создать doughnut chart java с помощью Aspose.Slides – краткое
  руководство по настройке библиотеки, добавлению настраиваемого doughnut chart, изменению
  hole size и сохранению presentation.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Узнайте, как создать doughnut chart java с помощью Aspose.Slides –
  краткое руководство по настройке библиотеки, добавлению настраиваемого doughnut
  chart, изменению hole size и сохранению presentation.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Создание doughnut chart java – Пошаговое руководство с Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Создание doughnut chart java – Пошаговое руководство с Aspose.Slides
url: /ru/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать кольцевые диаграммы в Java с помощью Aspose.Slides for Presentations

## Введение
Создание визуально привлекательных презентаций необходимо для эффективной передачи информации. **Create doughnut chart java** — распространённая задача, когда нужно проиллюстрировать пропорциональные данные современным видом. В этом руководстве вы узнаете, как настроить Aspose.Slides for Java, построить кольцевую диаграмму, настроить размер отверстия и цвета, а затем сохранить файл презентации. К концу у вас будет переиспользуемый шаблон, который можно добавить в любой Java‑проект, автоматически генерирующий наборы PowerPoint.

**Что вы узнаете:**
- Настройка Aspose.Slides for Java
- Создание и настройка кольцевых диаграмм в презентациях
- Регулировка внешнего вида диаграммы, например размера отверстия
- Сохранение презентации с новой диаграммой

Давайте начнём с настройки нашей среды!

## Быстрые ответы
- **Какая библиотека создает doughnut chart java?** Aspose.Slides for Java.  
- **Сколько строк кода требуется для базовой doughnut chart?** Около 8–10 строк после создания объекта презентации.  
- **Могу ли я изменить размер отверстия?** Да, метод `setHoleSize(double)` принимает значения от 0 % до 100 %.  
- **Какие форматы вывода поддерживаются?** PPTX, PDF, XPS, PNG, JPEG и несколько других (более 50 всего).  
- **Нужна ли лицензия для продакшна?** Требуется коммерческая лицензия для неограниченного использования; бесплатная пробная версия подходит для оценки.

## Что такое Aspose.Slides for Java?
**Aspose.Slides for Java** — полностью управляемый API, позволяющий разработчикам создавать, изменять, конвертировать и рендерить файлы PowerPoint без Microsoft Office. Он поддерживает более 50 форматов файлов и может обрабатывать презентации с тысячами слайдов, при этом потребление памяти остаётся низким.

## Почему использовать кольцевые диаграммы в презентациях?
Кольцевые диаграммы отображают отношения часть‑целое, освобождая место в центре для подписей или изображений. Aspose.Slides может рендерить кольцевые диаграммы со скоростью до **500 слайдов в минуту** на типичном сервере с 2.5 ГГц, и обрабатывает **многостраничные презентации** без загрузки всего файла в память, что делает его идеальным для масштабных решений по отчетности.

## Предпосылки
Прежде чем начать, убедитесь, что вы выполнили следующие требования:

### Требуемые библиотеки и версии
Для работы с Aspose.Slides for Java включите её в проект через Maven или Gradle, либо скачайте напрямую.

#### Требования к настройке среды
- Рабочий Java Development Kit (JDK), предпочтительно версии 8 или выше.
- Интегрированная среда разработки (IDE), такая как IntelliJ IDEA или Eclipse.

### Требования к знаниям
Знание Java и базовых концепций программирования будет полезным. Базовые знания Maven или Gradle помогут упростить процесс настройки.

## Настройка Aspose.Slides for Java
Включение Aspose.Slides в ваш проект может быть выполнено несколькими способами:

**Maven:**  
Добавьте эту зависимость в ваш файл `pom.xml`:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Включите это в ваш файл `build.gradle`:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямое скачивание:**  
Скачайте последнюю версию с сайта [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
- **Free Trial:** Начните с загрузки пробной версии, чтобы изучить возможности Aspose.Slides.  
- **Temporary License:** Получите временную лицензию для расширенной функциональности без ограничений.  
- **Purchase:** Для постоянного использования требуется покупка лицензии.

После того как библиотека настроена и среда готова, перейдём к реализации нашей кольцевой диаграммы.

## Как создать кольцевую диаграмму в Java?
Загрузите новый объект `Presentation`, добавьте кольцевую диаграмму на слайд, задайте размер отверстия и сохраните файл — всё это в нескольких простых вызовах API. Такой подход даёт полный контроль над данными диаграммы, её внешним видом и форматом экспорта, и работает без необходимости установки Microsoft PowerPoint на сервере.

### Инициализация объекта Presentation
Класс `Presentation` — верхнеуровневый объект Aspose.Slides, представляющий файл PowerPoint в памяти.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Этот шаг создаёт пустую презентацию, в которую можно добавлять слайды, фигуры и диаграммы.

### Добавление кольцевой диаграммы на слайд
`ISlide` — интерфейс отдельного слайда; можно получить первый слайд или добавить новый.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Метод `addChart` создаёт кольцевую диаграмму; параметры определяют её позицию (X, Y) и размер (ширина, высота) на слайде.

### Настройка размера отверстия кольцевой диаграммы
`Chart` предоставляет метод `setHoleSize(double)` для управления внутренним радиусом в процентах от радиуса диаграммы.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Установка размера отверстия в 90 % делает диаграмму почти полной окружностью, что полезно, когда нужно подчеркнуть внешние сегменты.

### Сохранение презентации
`presentation.save(String, SaveFormat)` записывает файл на диск в выбранном формате.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Пример сохраняет результат как `DoughnutHoleSize_out.pptx`, но вы также можете выбрать PDF, PNG или любой из более чем 50 поддерживаемых форматов.

### Очистка ресурсов
Вызов `presentation.dispose()` освобождает нативные ресурсы и предотвращает утечки памяти, что особенно важно в длительно работающих серверных приложениях.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Практические применения
Кольцевые диаграммы универсальны. Ниже приведены сценарии, где они особенно эффективны:
1. **Budget Allocation:** Отображение распределения бюджета по отделам.  
2. **Survey Results:** Визуализация ответов на вопросы с вариантами выбора.  
3. **Website Traffic Sources:** Показ процента трафика, поступающего из разных каналов (органический, платный, реферальный и т.д.).

## Соображения по производительности
При работе с Aspose.Slides учитывайте следующие рекомендации для оптимальной производительности:
- Освобождайте объекты `Presentation` сразу после завершения работы, чтобы освободить нативную память.  
- Используйте потоки (`FileInputStream`, `ByteArrayOutputStream`) для больших наборов данных, чтобы избежать загрузки целых файлов в ОЗУ.  
- Переиспользуйте объекты диаграмм при генерации множества слайдов в цикле, чтобы снизить нагрузку на создание объектов.

## Распространённые проблемы и решения
- **Error while saving:** Убедитесь, что целевой каталог существует и приложение имеет права записи.  
- **Missing chart data:** Убедитесь, что вы заполнили коллекцию `ChartData` диаграммы перед вызовом `setHoleSize`.  
- **Memory spikes:** Для презентаций с тысячами слайдов включите `Presentation.setSlideSize` на меньший размер и своевременно освобождайте промежуточные слайды.

## Часто задаваемые вопросы

**Q: Могу ли я изменить цвета сегментов моей кольцевой диаграммы?**  
A: Да. Используйте `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`, а затем укажите нужный RGB‑цвет.

**Q: Как добавить подписи данных к диаграмме?**  
A: Вызовите `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`, чтобы отобразить значение внутри каждого сегмента.

**Q: Можно ли сохранять диаграммы в форматах, отличных от PPTX?**  
A: Конечно. Aspose.Slides поддерживает PDF, XPS, PNG, JPEG, TIFF и многие другие форматы — более 50 в общей сложности.

**Q: Что делать, если при загрузке большой презентации возникает исключение?**  
A: Используйте конструктор `Presentation`, принимающий поток, и включите `loadOptions.setLoadFormat(LoadFormat.Pptx)`, чтобы потоково читать файл и снизить потребление памяти.

**Q: Можно ли автоматизировать обновление диаграмм с живыми источниками данных?**  
A: Да. Получайте данные из базы данных или REST API, обновляйте коллекцию `ChartData` и вызывайте `chart.refresh()` перед сохранением презентации.

## Ресурсы
- **Documentation:** Изучите подробные ссылки API на сайте [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Download:** Получите последнюю версию библиотеки с [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Purchase:** Для полного доступа приобретите лицензию на [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Free Trial:** Опробуйте Aspose.Slides с бесплатной пробной версией, доступной на странице загрузки.  
- **Temporary License:** Получите временную лицензию для расширенного тестирования без ограничений.  
- **Support:** Есть вопросы? Посетите [Aspose Forum](https://forum.aspose.com/c/slides/11) для получения помощи.

---

**Последнее обновление:** 2026-07-27  
**Тестировано с:** Aspose.Slides for Java 24.12  
**Автор:** Aspose

## Связанные руководства

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
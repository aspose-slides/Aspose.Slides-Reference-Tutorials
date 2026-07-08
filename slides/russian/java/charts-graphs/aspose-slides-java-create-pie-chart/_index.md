---
date: '2026-07-08'
description: Узнайте, как добавить диаграмму pie chart в презентации PowerPoint с
  помощью Aspose.Slides for Java. Следуйте этому пошаговому руководству, чтобы создавать
  и настраивать профессиональные диаграммы pie chart.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Добавьте диаграмму pie chart в PowerPoint с помощью Aspose.Slides
  for Java. Этот учебник показывает, как программно генерировать и настраивать диаграммы
  pie chart, идеально подходящие для автоматизированных отчетов.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Добавить диаграмму Pie Chart в PowerPoint с Aspose.Slides for Java – Быстрое
  руководство
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Как добавить диаграмму pie chart в PowerPoint с Aspose.Slides for Java
url: /ru/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Добавить круговую диаграмму PowerPoint с Aspose.Slides для Java

## Введение

Если вам нужно **добавить круговую диаграмму PowerPoint** слайды без ручного открытия PowerPoint, вы попали в нужное место. В этом руководстве мы пройдем настройку Aspose.Slides для Java, создание круговой диаграммы и настройку каждого сегмента — идеально для автоматизированных отчетов, панелей мониторинга или персонализированных презентаций. К концу вы получите переиспользуемый фрагмент Java, который генерирует отшлифованный файл PowerPoint с круговой диаграммой за секунды.

### Быстрые ответы
- **Какая библиотека создает диаграмму?** Aspose.Slides for Java (последний релиз).  
- **Можно ли запускать его без графического интерфейса?** Да — установка Office не требуется.  
- **Какая версия Java оптимальна?** JDK 16+ для лучшей производительности и улучшений сборки мусора.  
- **Как «взрывать» сегмент?** Вызовите `setExplosion` у `IDataPoint` и задайте смещение в пикселях.  
- **Нужна ли лицензия для продакшн?** Пробная версия работает для разработки; постоянная лицензия снимает все ограничения оценки.

## Зачем добавлять круговую диаграмму PowerPoint с помощью Aspose.Slides для Java?

Вы можете генерировать актуальные визуальные отчеты напрямую из ваших бэкенд‑сервисов, устраняя ошибки ручного копирования‑вставки и гарантируя стили, соответствующие бренду. Aspose.Slides поддерживает **70+ типов диаграмм** и может обрабатывать презентации с **10 000+ слайдов** без загрузки всего файла в память, что делает его идеальным для масштабной автоматизации.

## Требования

- **Aspose.Slides for Java** – в руководстве используется версия 25.4 (последняя на момент написания).  
- **Java Development Kit** – рекомендуется JDK 16 или новее.  
- **Maven** или **Gradle** для управления зависимостями.  

## Настройка Aspose.Slides для Java

### Maven
Добавьте эту зависимость в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Включите следующее в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

В качестве альтернативы загрузите последнюю версию напрямую с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Лицензирование
To use Aspose.Slides without limitations:

- Начните с **бесплатной пробной версии**, чтобы оценить API.  
- Запросите **временную лицензию** для расширенного тестирования на странице [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Приобретите полную подписку через [Purchase page](https://purchase.aspose.com/buy).

## Как добавить круговую диаграмму PowerPoint с помощью Aspose.Slides для Java

Загрузите новую презентацию, вставьте круговую диаграмму и сохраните файл — всё в три лаконичных шага. Этот шаблон работает с набором данных любого размера и может быть обернут в цикл для автоматической генерации десятков слайдов. Подход лёгкий, требует лишь нескольких строк кода и никаких внешних ресурсов, что делает его подходящим как для небольших утилит, так и для крупных пакетных задач.

### Шаг 1: Инициализация презентации
`Presentation` класс представляет один файл PowerPoint в памяти. Создание экземпляра предоставляет вам чистую, пустую колоду слайдов для работы.
```java
Presentation pres = new Presentation();
```

### Шаг 2: Добавить круговую диаграмму
Вставьте круговую диаграмму на первый слайд. Координаты (50, 50) и размер (600 × 400) подходят для стандартного макета 16:9 и оставляют место для заголовков.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Шаг 3: Сохранить презентацию
Запишите презентацию на диск. Замените `YOUR_OUTPUT_DIRECTORY` на папку, в которой вы хотите сохранить файл.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Шаг 4: Очистить ресурсы
Вызовите `dispose` у объекта `Presentation`, чтобы освободить нативные ресурсы и избежать утечек памяти.
```java
if (pres != null) pres.dispose();
```

## Как настроить взрыв и цвет отдельного сегмента?

Загрузите диаграмму, найдите целевой сегмент данных, а затем примените смещение взрыва и сплошной цвет заливки. Это делает сегмент более заметным для акцента. Такие настройки помогают привлечь внимание аудитории к критическим значениям и улучшить общую читаемость диаграммы.

### Шаг 1: Загрузить существующую презентацию (или переиспользовать только что созданную)
Объект `Presentation` загружает существующий файл PowerPoint в память, позволяя вам изменять его содержимое.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Шаг 2: Доступ к диаграмме и целевому сегменту данных
Интерфейс `IDataPoint` представляет отдельный сегмент данных (срез) в серии диаграммы.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Шаг 3: Применить взрыв и цвет
`setExplosion(int)` задает расстояние в пикселях, на которое сегмент смещается от центра диаграммы. Визуально отделите сегмент, вызвав `setExplosion(20)`, и измените его заливку на синюю с помощью `setFillType(FillType.Solid)` и `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Шаг 4: Сохранить и освободить
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Практические применения
- **Sales Reports:** Выделите топ‑продаваемые продукты с помощью «взрыва» сегментов.  
- **Budget Analysis:** Присвойте отделам разные цвета для быстрой визуальной сравнения.  
- **Educational Slides:** Разбейте сложные концепции на усваиваемые сегменты диаграмм.  

## Соображения по производительности
- **Dispose objects** своевременно, чтобы избежать утечек памяти, особенно при генерации большого количества слайдов в цикле.  
- **Monitor heap usage** для больших презентаций; используйте перегрузку `Save`, принимающую `OutputStream`, чтобы передавать данные потоково и сохранять низкое потребление памяти.  
- Оставайтесь на **JDK 16+**, чтобы воспользоваться последними улучшениями сборки мусора, которые могут сократить время обработки до 30 % для наборов из 1 000 слайдов.

## Заключение
Теперь у вас есть полный, готовый к продакшн рабочий процесс для **добавления круговой диаграммы PowerPoint** с помощью Aspose.Slides для Java. Экспериментируйте с различными расстояниями взрыва, цветами и наборами данных, чтобы соответствовать вашему бренду. Когда будете готовы, изучите другие типы диаграмм — столбчатые, линейные или точечные — чтобы построить полноценную аналитическую панель внутри PowerPoint.

## Часто задаваемые вопросы

**Q: Каково главное преимущество использования Aspose.Slides для Java?**  
A: Он позволяет программно создавать, редактировать и рендерить файлы PowerPoint без необходимости установки Microsoft Office, поддерживая более 70 типов диаграмм и более 100 форматов файлов.

**Q: Можно ли сгенерировать файл PowerPoint с нуля?**  
A: Да, создайте объект `Presentation`, добавьте слайды, диаграммы или фигуры, затем вызовите `save` — всё на чистом Java.

**Q: Как «взорвать» конкретный сегмент круговой диаграммы?**  
A: Получите `IDataPoint` для нужного сегмента и вызовите `setExplosion(pixelOffset)`. Смещение определяет, насколько далеко сегмент будет смещён наружу.

**Q: Есть ли ограничение на количество слайдов, которые я могу создать?**  
A: Aspose.Slides может обрабатывать презентации с до **10 000 слайдов** в одном файле, при условии потоковой передачи вывода, чтобы не загружать всё в память.

**Q: Где можно найти более продвинутые примеры настройки диаграмм?**  
A: Обратитесь к официальной [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) для подробных справок по API и примеров проектов.

## Ресурсы
- **Документация:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Скачать библиотеку:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Приобрести лицензию:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Бесплатная пробная версия:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Временная лицензия:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Форум поддержки:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Последнее обновление:** 2026-07-08  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
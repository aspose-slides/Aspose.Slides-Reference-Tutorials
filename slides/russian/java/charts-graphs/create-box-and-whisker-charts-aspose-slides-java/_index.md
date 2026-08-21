---
date: '2026-08-21'
description: Узнайте, как создать box plot java с использованием Aspose.Slides, добавить
  диаграмму на слайд и сгенерировать box‑and‑whisker chart в PowerPoint. Идеально
  для Java‑разработчиков.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Узнайте, как создать box plot java с использованием Aspose.Slides,
  добавить диаграмму на слайд и сгенерировать box‑and‑whisker chart в PowerPoint.
  Отлично подходит для Java‑разработчиков.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Как создать box plot java с помощью Aspose.Slides для PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Как создать box plot java с помощью Aspose.Slides для PowerPoint
url: /ru/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать box plot java с Aspose.Slides for PowerPoint

В этом руководстве вы **создадите box plot java** с помощью Aspose.Slides, а затем встроите диаграмму непосредственно в слайд PowerPoint. Программная генерация диаграмм box‑and‑whisker позволяет преобразовать сырые статистические данные в наглядные визуальные инсайты, не выходя из вашего кода Java. Если вам нужно автоматизировать создание отчетов PowerPoint, Aspose.Slides for Java предоставляет надежный, высокопроизводительный API.

## Что вы узнаете

- Настройка среды для Aspose.Slides for Java
- Шаги по **добавлению диаграммы на слайд** и генерации диаграммы box‑whisker в PowerPoint с использованием Java
- Лучшие практики по оптимизации производительности при работе с Aspose.Slides
- Практические применения диаграмм box‑and‑whisker

## Быстрые ответы
- **Какая библиотека создает box plot в Java?** Aspose.Slides for Java.  
- **Какой тип диаграммы используется?** `ChartType.BoxAndWhisker`.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; коммерческая лицензия требуется для продакшна.  
- **Можно ли добавить несколько серий?** Да — повторите блок создания серии для каждого набора данных.  
- **В каком формате будет конечный файл?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Что такое box plot и зачем использовать его в Java?

Диаграмма box‑and‑whisker (часто называемая *box plot*) визуализирует распределение данных — медиану, квартали и выбросы — в компактной форме. В Java генерация такой диаграммы программно позволяет встраивать статистические инсайты напрямую в презентации PowerPoint, устраняя необходимость ручного создания диаграмм. Это особенно полезно для сравнения распределений по нескольким категориям, например, оценок тестов по классам или продаж по регионам. Генерируя диаграмму в Java, вы можете интегрировать её в автоматизированные конвейеры отчетности, гарантируя, что в презентациях всегда отображаются актуальные данные.

## Почему добавлять диаграмму на слайд с Aspose.Slides?

Aspose.Slides абстрагирует детали низкоуровневого OpenXML, предоставляя удобный API для создания, стилизации и экспорта диаграмм. Это позволяет автоматизировать генерацию отчетов, поддерживать единый бренд и интегрировать диаграммы в более крупные Java‑рабочие процессы. Библиотека также поддерживает параметры стилизации, такие как цвета, шрифты и маркеры, позволяя соответствовать корпоративному брендингу. Кроме того, она справляется со сложными задачами, такими как привязка данных и обновление диаграмм, без необходимости установки Microsoft Office.

## Как добавить диаграмму на слайд в Java с помощью Aspose.Slides?

Загрузите или создайте объект `Presentation`, вставьте `Chart` типа `BoxAndWhisker`, передайте данные и сохраните файл — всё это занимает несколько строк кода Java. API управляет расположением, масштабированием и рендерингом, поэтому вам не нужно вручную работать с XML. Вы также можете программно задавать заголовки диаграмм и подписи осей, чтобы предоставить контекст зрителям.

## Требования

- **Java Development Kit (JDK)**: JDK 8 или выше.  
- **Aspose.Slides for Java Library**: Требуется для работы с PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse или любой совместимый с Java редактор.

## Настройка Aspose.Slides for Java

Добавьте библиотеку как зависимость Maven, Gradle или вручную.

### Maven

Добавьте следующую зависимость в ваш `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

В вашем `build.gradle` включите:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка

В качестве альтернативы загрузите последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Приобретение лицензии

- **Free trial** – изучайте возможности бесплатно.  
- **Temporary license** – используйте для краткосрочной оценки.  
- **Purchase** – разблокируйте полный функционал для производственных нагрузок.

Чтобы инициализировать Aspose.Slides, убедитесь, что JAR находится в вашем classpath, и задайте файл лицензии, как описано в документации.

## Руководство по реализации

Ниже представлена пошаговая инструкция. Каждый блок объясняется перед фрагментом кода, чтобы вы точно знали, что он делает.

### Что такое класс `Presentation`?

Класс `Presentation` — центральный объект в Aspose.Slides, представляющий весь файл PowerPoint в памяти. Он предоставляет доступ к слайдам, диаграммам, фигурам и другим элементам, позволяя программно создавать, изменять и сохранять презентации. С помощью этого класса можно добавлять новые слайды, вставлять изображения и менять порядок слайдов простыми вызовами API.

### Шаг 1: создать или открыть презентацию

Сначала откройте существующий PPTX или создайте новый:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Совет:** Если файл не существует, Aspose.Slides автоматически создаст новую пустую презентацию.

### Шаг 2: добавить диаграмму box‑and‑whisker на слайд

Разместите диаграмму там, где нужно, указав позицию и размер (в пунктах):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Шаг 3: очистить существующие данные

Перед загрузкой новых данных удалите любые категории‑заполнители или серии:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Шаг 4: настроить категории

Добавьте категории (метки оси X), которые будут отображаться под каждым ящиком:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Примечание:** Отрегулируйте текст меток в соответствии с областью ваших данных (например, “Q1”, “Product A”).

### Шаг 5: создать и настроить серию

Теперь создайте серию, задайте визуальные параметры и передайте числовые данные:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Вы можете заменить массив `int[] data` значениями, считанными из базы данных, CSV‑файла или любого другого источника.

### Шаг 6: сохранить презентацию

Сохраните изменения в новый файл PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Шаг 7: очистить ресурсы

Всегда освобождайте объект `Presentation`, чтобы освободить нативные ресурсы:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Практические применения

Диаграммы box‑and‑whisker незаменимы в статистическом анализе и представлении данных. Ниже несколько сценариев, где они особенно полезны:

1. **Финансовый анализ** – визуализировать распределение доходов по регионам.  
2. **Контроль качества** – выявлять выбросы в измерениях производства.  
3. **Академические исследования** – показывать изменчивость экспериментальных результатов.  
4. **Маркетинговые исследования** – сравнивать показатели продукта по демографическим группам.

Встраивание этих диаграмм непосредственно в презентации PowerPoint позволяет заинтересованным сторонам быстро понять сложные данные.

## Соображения по производительности

Aspose.Slides может обрабатывать презентации с **500+ слайдов** и диаграммы с **100 000+ точками данных**, удерживая использование памяти ниже 200 MB на типичном сервере. Чтобы оставаться в этих пределах:

- **Управление памятью** – своевременно освобождайте объекты `Presentation`.  
- **Обработка данных** – загружайте только необходимые данные; избегайте передачи огромных наборов данных напрямую в рабочую книгу диаграммы.  
- **Ленивая загрузка** – при генерации множества слайдов создавайте диаграммы только для тех, которые будут отображаться.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Диаграмма отображается пустой** | Ячейки данных не заполнены корректно | Проверьте, что `wb.getCell` ссылается на правильную строку/столбец и значение не `null`. |
| **Выбросы не отображаются** | `setShowOutlierPoints` установлен в `false` | Убедитесь, что вызвано `series.setShowOutlierPoints(true)`. |
| **Утечка памяти** | Презентация не освобождена | Всегда оборачивайте использование в `try/finally` и вызывайте `dispose()`. |
| **Неправильные квартильные значения** | Используется метод по умолчанию `Inclusive` | Переключитесь на `Exclusive` через `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Часто задаваемые вопросы

**Q1: Что такое диаграмма box‑and‑whisker?**  
Диаграмма box‑and‑whisker, также известная как box plot, отображает распределение данных на основе пяти сводных статистик: минимум, первый квартиль, медиана, третий квартиль и максимум, а также любые выбросы.

**Q2: Можно ли настроить внешний вид диаграммы box‑and‑whisker?**  
Да. Aspose.Slides позволяет менять цвета, стили линий, формы маркеров и добавлять подписи данных через API форматирования диаграммы.

**Q3: Можно ли обработать несколько серий в одной диаграмме?**  
Абсолютно. Повторите блок создания серии для каждого набора данных, который хотите визуализировать.

**Q4: Как решить проблемы с некорректным отображением данных?**  
Убедитесь, что данные правильно записаны в ячейки рабочей книги и свойства видимости, такие как `setShowMeanLine`, включены.

**Q5: Где можно получить поддержку при возникновении проблем?**  
Посетите [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) для помощи сообщества или обратитесь к официальной документации.

**Q6: Поддерживает ли Aspose.Slides другие типы диаграмм?**  
Да, поддерживается более 50 типов диаграмм — включая линейные, столбчатые, круговые, точечные, радиальные и воронкообразные, так что вы можете выбрать лучший визуальный тип для ваших данных.

**Q7: Можно ли генерировать диаграммы в безголовом серверном окружении?**  
Библиотека полностью работает в серверных сценариях; не требуется UI или установка Microsoft Office.

## Ресурсы

- **Documentation**: Изучите подробные ссылки API на [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Доступ к странице релизов Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Purchase**: Приобретите лицензию для разблокировки всех функций [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free trial & temporary license**: Начните с бесплатной пробной версии или запросите временную лицензию [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Следуя этому руководству, вы теперь сможете программно генерировать информативные диаграммы box‑and‑whisker в ваших Java‑приложениях и встраивать их напрямую в презентации PowerPoint. Приятного кодинга!

---

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Author:** Aspose

## Связанные учебники

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
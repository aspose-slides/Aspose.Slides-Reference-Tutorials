---
date: '2026-09-12'
description: Узнайте, как создать clustered column chart в PowerPoint, используя Aspose.Slides
  for Java, получить его data range и эффективно экспортировать chart images.
keywords:
- create clustered column chart
- update powerpoint chart data
- export powerpoint chart image
- create pie chart java
- create powerpoint presentation java
- author: Aspose
  dateModified: '2026-09-12'
  description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  headline: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  type: TechArticle
- description: Master creating and retrieving PowerPoint charts using Aspose.Slides
    for Java. Learn to generate professional visuals efficiently.
  name: Creating PowerPoint Charts Using Aspose.Slides for Java — A Comprehensive
    Guide
  steps:
  - name: Create the Presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: Add a Clustered Column Chart
    text: 'Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters Explained**:
      - `ChartType.ClusteredColumn`: Defines the type of chart. - `(10, 10)`: X and
      Y coordinates for positioning the chart on the slide. - `(400, 300)`: Width
      and height of the chart.'
  - name: Retrieve the Data Range
    text: 'Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving Data**: This method gives you a snapshot of your chart''s
      data, useful for debugging or display purposes.'
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
lastmod: '2026-09-12'
og_description: Узнайте, как создать clustered column chart в PowerPoint, используя
  Aspose.Slides for Java, получить его data range и эффективно экспортировать chart
  images. Поддерживает обновление данных chart в PowerPoint и экспорт chart image.
og_image_alt: 'Developer guide: create clustered column chart in PowerPoint using
  Aspose.Slides for Java'
og_title: Как создать clustered column chart с помощью Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  headline: How to create clustered column chart with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create a clustered column chart in PowerPoint using Aspose.Slides
    for Java, retrieve its data range, and export chart images efficiently.
  name: How to create clustered column chart with Aspose.Slides for Java
  steps:
  - name: create the presentation
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a PowerPoint file in memory.
  - name: add a clustered column chart
    text: Use the `addChart` method to insert a chart into your presentation. Specify
      its type, position (x and y coordinates), and size. - **Parameters explained**
      - `ChartType.ClusteredColumn` – selects the clustered column visual. - `(10,
      10)` – X and Y coordinates (points) for the chart’s top‑left corner.
  - name: add a clustered column chart
    text: Firstly, add a clustered column chart as described previously.
  - name: retrieve the data range
    text: Use `getChartData().getRange()` to get a string representation of the data
      range. - **Retrieving data** – this method gives you a snapshot of your chart's
      data, useful for debugging or display purposes.
  type: HowTo
- questions:
  - answer: Use Maven, Gradle, or download the JAR from the [Aspose.Slides for Java
      releases](https://releases.aspose.com/slides/java/).
    question: How do I install Aspose.Slides for Java?
  - answer: Yes, Aspose.Slides supports over 50 chart types, including bar, line,
      pie, and radar charts.
    question: Can I create other types of charts?
  - answer: Ensure you dispose of resources properly and wrap your code in try‑catch
      blocks to handle `IOException` and `Exception`.
    question: What if my presentation crashes during processing?
  - answer: There is a free trial available. For continued use, consider purchasing
      a license or requesting a temporary one.
    question: Are there licensing costs for using Aspose.Slides?
  - answer: Visit [Aspose's support forum](https://forum.aspose.com/c/slides/11) for
      assistance from the community and Aspose experts.
    question: How do I get support if I encounter issues?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides Java
- PowerPoint chart generation
- Java presentation automation
- chart data retrieval
title: Как создать clustered column chart с помощью Aspose.Slides for Java
url: /ru/java/charts-graphs/create-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать кластерную столбчатую диаграмму в PowerPoint с помощью Aspose.Slides для Java

Создание кластерной столбчатой диаграммы в файле PowerPoint ранее требовало утомительной работы с XML или полной установки Office. С **Aspose.Slides for Java** вы можете генерировать диаграмму программно, корректировать её данные и экспортировать визуализацию за секунды. Этот учебник проведёт вас через создание презентации, вставку кластерной столбчатой диаграммы и чтение базового диапазона данных, чтобы вы могли проверить или записать его позже. Для получения дополнительной информации посетите [веб‑сайт Aspose](https://releases.aspose.com/slides/java/).

## Быстрые ответы
- **Какая библиотека создаёт диаграммы PowerPoint в Java?** Aspose.Slides for Java.  
- **Какой тип диаграммы используется в примере?** Кластерная столбчатая диаграмма.  
- **Нужна ли лицензия для запуска примера?** Бесплатная пробная версия подходит для оценки; для продакшн‑использования требуется коммерческая лицензия.  
- **Можно ли получить данные диаграммы после её создания?** Да — вызовите `getChartData().getRange()` у объекта диаграммы.  
- **Какая версия Java поддерживается?** JDK 16 и новее.

## Что такое Aspose.Slides for Java?

`Aspose.Slides for Java` — это **stand‑alone API**, позволяющее создавать, редактировать и рендерить файлы PowerPoint без Microsoft Office. Он поддерживает **более 50 форматов ввода и вывода** и может работать с презентациями, содержащими **сотни слайдов, используя менее 200 МБ ОЗУ**.

## Почему стоит использовать Aspose.Slides for Java для создания диаграмм?

Aspose.Slides обрабатывает **более 50 типов диаграмм**, рендерит их со **скоростью до 30 кадров/сек** на типичном серверном оборудовании и манипулирует презентациями **без загрузки всего файла в память**. Это делает его идеальным для автоматизированных конвейеров отчётности, которым необходимо генерировать тысячи диаграмм ежедневно, сохраняя низкое потребление CPU и памяти.

## Предварительные требования

Перед началом убедитесь, что у вас есть:

- **Java Development Kit (JDK)** 16 или новее установлен.  
- IDE, например **IntelliJ IDEA** или **Eclipse**.  
- **Maven** или **Gradle** для управления зависимостями.  

### Требуемые библиотеки и зависимости

Добавьте Aspose.Slides в ваш проект, используя один из следующих фрагментов.

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

В качестве альтернативы загрузите последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Приобретение лицензии

Начните с бесплатной пробной версии или запросите временную лицензию, чтобы разблокировать все функции. Для продакшн‑использования приобретите лицензию на [странице покупки Aspose](https://purchase.aspose.com/buy).

## Настройка Aspose.Slides for Java

`Presentation` — основной класс для создания и манипулирования файлами PowerPoint. После добавления зависимости инициализируйте API в вашем коде.

1. **Добавьте зависимость** с помощью Maven или Gradle, как показано выше.  
2. **Создайте экземпляр `Presentation`** — этот объект будет содержать ваши слайды и диаграммы.  

```java
Presentation pres = new Presentation();
```  

3. **Освободите презентацию** после завершения, чтобы освободить нативные ресурсы.  

```java
if (pres != null) pres.dispose();
```  

## Как создать презентацию PowerPoint с кластерной столбчатой диаграммой в Java?

Загрузите новый `Presentation`, добавьте слайд и вставьте кластерную столбчатую диаграмму одним цепочечным вызовом. Объект `Presentation` представляет весь файл PowerPoint в памяти, а метод `addChart` создаёт форму диаграммы на указанном слайде. Ниже приведены основные шаги, которые можно выполнить менее чем за десять строк кода.

### Шаг 1: создать презентацию  

Класс `Presentation` — объект верхнего уровня Aspose.Slides, представляющий файл PowerPoint в памяти.  

```java
Presentation pres = new Presentation();
```  

### Шаг 2: добавить кластерную столбчатую диаграмму  

Используйте метод `addChart`, чтобы вставить диаграмму в вашу презентацию. Укажите её тип, позицию (координаты x и y) и размер.  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

- **Пояснение параметров**  
  - `ChartType.ClusteredColumn` – выбирает визуализацию кластерной столбчатой диаграммы.  
  - `(10, 10)` – координаты X и Y (в пунктах) левого верхнего угла диаграммы.  
  - `(400, 300)` – ширина и высота диаграммы в пунктах.

## Как получить диапазон данных диаграммы в презентации PowerPoint с помощью Aspose.Slides for Java?

Вызовите `getChartData().getRange()` у объекта диаграммы; он мгновенно возвращает строку вида `"Sheet1!A1:B5"`, отражающую диапазон Excel‑подобного источника данных, поддерживающего диаграмму. Этот метод предоставляет лаконичное текстовое представление источника данных без загрузки полной рабочей книги, что делает его идеальным для журналирования, отладки или быстрой проверки в автоматизированных конвейерах.

### Шаг 1: добавить кластерную столбчатую диаграмму  

Сначала добавьте кластерную столбчатую диаграмму, как описано ранее.  

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 10, 10, 400, 300);
```  

### Шаг 2: получить диапазон данных  

Используйте `getChartData().getRange()`, чтобы получить строковое представление диапазона данных.  

```java
String result = chart.getChartData().getRange();
// Output omitted for clarity
```  

- **Получение данных** – этот метод предоставляет снимок данных вашей диаграммы, полезный для отладки или отображения.

## Практические применения

1. **Business reporting** – генерировать KPI‑дашборды, которые автоматически обновляются при изменении исходных данных.  
2. **Data‑driven presentations** – создавать наборы слайдов, отражающие актуальные данные о продажах или запасах без ручного редактирования.  
3. **Educational tools** – создавать динамические диаграммы для учебных пособий, викторин или интерактивных учебников.

## Соображения по производительности

- **Своевременно освобождайте объекты** – вызывайте `presentation.dispose()` в блоке `finally`, чтобы освободить нативную память.  
- **Избегайте полной загрузки документа** – используйте потоковые API при работе с презентациями более 200 МБ.  
- **Получайте только необходимые диапазоны** – `getChartData().getRange()` позволяет избежать загрузки полного набора данных диаграммы, снижая нагрузку на CPU.

## Распространённые проблемы и решения

- **Сбои презентации** – всегда оборачивайте операции ввода‑вывода в блоки `try‑catch` и убеждайтесь, что `dispose()` вызывается в `finally`.  
- **Некорректные размеры диаграммы** – проверьте, что значения X, Y, ширины и высоты находятся внутри холста слайда 960 × 720 пунктов.  
- **Ошибки лицензии** – загрузите файл лицензии перед созданием любых объектов `Presentation`: `License license = new License(); license.setLicense("Aspose.Slides.lic");`.

## Часто задаваемые вопросы

**В: Как установить Aspose.Slides for Java?**  
A: Используйте Maven, Gradle или загрузите JAR с [странице релизов Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

**В: Можно ли создавать другие типы диаграмм?**  
A: Да, Aspose.Slides поддерживает более 50 типов диаграмм, включая гистограммы, линейные, круговые и радиальные диаграммы.

**В: Что делать, если моя презентация падает во время обработки?**  
A: Убедитесь, что правильно освобождаете ресурсы и оборачиваете код в блоки `try‑catch` для обработки `IOException` и `Exception`.

**В: Есть ли стоимость лицензии за использование Aspose.Slides?**  
A: Доступна бесплатная пробная версия. Для продолжительного использования рассмотрите покупку лицензии или запрос временной лицензии.

**В: Как получить поддержку, если возникнут проблемы?**  
A: Посетите [Aspose's support forum](https://forum.aspose.com/c/slides/11) для получения помощи от сообщества и экспертов Aspose.

## Ресурсы
- **Документация**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Скачать**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Купить**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Бесплатная пробная версия**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **Временная лицензия**: [Request Temporary License](https://purchase.aspose.com/temporary-license/)

Удачной работы с диаграммами в Aspose.Slides for Java!

---

**Последнее обновление:** 2026-09-12  
**Тестировано с:** Aspose.Slides for Java 24.12 (latest at time of writing)  
**Автор:** Aspose  

## Связанные руководства

- [Полное руководство по работе с PowerPoint с Aspose.Slides Java: всестороннее руководство по операциям с презентациями](/slides/java/presentation-operations/aspose-slides-java-manipulate-pptx-presentations/)
- [Полное руководство по автоматизации слайдов PowerPoint с Aspose.Slides Java: всестороннее руководство по пакетной обработке](/slides/java/batch-processing/automate-powerpoint-slides-aspose-slides-java/)
- [Создание Sunburst‑диаграмм в Java с использованием Aspose.Slides: всестороннее руководство](/slides/java/charts-graphs/create-sunburst-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-09-17'
description: Узнайте, как создать bubble chart powerpoint с помощью Aspose.Slides
  for Java. Это руководство показывает, как добавить chart на slide, configure bubble
  size и эффективно сохранить PPTX.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Узнайте, как создать bubble chart powerpoint с помощью Aspose.Slides
  for Java. Этот tutorial объясняет, как добавить chart на slide, adjust bubble sizes
  и эффективно сохранить presentation.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Создать bubble chart powerpoint с Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Создать bubble chart powerpoint с Aspose.Slides for Java
url: /ru/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать пузырчатую диаграмму PowerPoint с помощью Aspose.Slides для Java

## Введение
Если вам нужно **создавать пузырчатую диаграмму PowerPoint** программно, Aspose.Slides для Java предоставляет чистый серверный API, который работает без Microsoft Office. В этом руководстве вы узнаете, как добавить диаграмму на слайд, управлять размером пузырей и сохранить итоговый PPTX, эффективно управляя ресурсами. Шаги разбиты так, чтобы вы могли скопировать‑вставить код в любой Java‑проект и увидеть результаты мгновенно.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Slides для Java
- **Какая версия Java требуется?** JDK 16 или выше
- **Как добавить пузырчатую диаграмму?** Вызовите `addChart(ChartType.Bubble, …)` на слайде
- **Можно ли изменить размер пузырей?** Да, через `setBubbleSizeScale()`
- **Как сохранить файл?** Используйте `pres.save("Result.pptx", SaveFormat.Pptx)`

## Что такое создание пузырчатой диаграммы PowerPoint?
Создание пузырчатой диаграммы в PowerPoint означает программную генерацию диаграммы, где каждая точка данных представлена пузырём, а его X‑позиция, Y‑позиция и размер кодируют три измерения данных. Aspose.Slides для Java обрабатывает рендеринг, поэтому установка PowerPoint не требуется.

## Почему стоит использовать Aspose.Slides для Java?
Aspose.Slides поддерживает **более 50 типов диаграмм**, может обрабатывать презентации размером до **2 ГБ** без загрузки всего файла в память и работает на любой платформе, поддерживающей Java 16+. Эти количественные возможности делают её надёжным выбором для корпоративных отчётов.

## Предварительные требования
- **Java Development Kit** 16 или новее, установленный на системе.
- **Библиотека Aspose.Slides для Java** (добавьте через Maven, Gradle или прямую загрузку JAR).
- Базовое знакомство с синтаксисом Java и объектно‑ориентированным программированием.

## Настройка Aspose.Slides для Java
Чтобы начать использовать Aspose.Slides, включите библиотеку в вашу систему сборки.

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
Включите это в ваш `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка
Вы также можете получить последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Приобретение лицензии
- **Бесплатная пробная версия** – исследуйте все функции без оплаты.  
- **Временная лицензия** – расширенная оценка для крупных проектов.  
- **Полная лицензия** – требуется для продуктивных развертываний.

### Базовая инициализация и настройка
Класс `Presentation` является точкой входа для создания или загрузки файлов PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Руководство по реализации
Ниже представлена пошаговая инструкция по созданию пузырчатой диаграммы и управлению ресурсами.

## Как создать пузырчатую диаграмму PowerPoint
В этом разделе вы узнаете точную последовательность вызовов API, необходимых для генерации пузырчатой диаграммы, настройки её визуальных свойств и сохранения результата в файл PPTX. Подход работает в любом Java‑проекте, где подключена Aspose.Slides, и следует лучшим практикам управления ресурсами.

Загрузите презентацию, добавьте пузырчатую диаграмму, настройте её внешний вид и сохраните файл.

### Прямой ответ
Создайте новый `Presentation`, вызовите `addChart(ChartType.Bubble, …)` на нужном слайде, отрегулируйте масштаб пузырей с помощью `setBubbleSizeScale(150)`, затем сохраните с помощью `pres.save("Result.pptx", SaveFormat.Pptx)`. Эта последовательность добавит полностью функциональную пузырчатую диаграмму всего в несколько строк Java.

- **`ChartType.Bubble`** представляет тип пузырчатой диаграммы.  
- **`addChart`** вставляет новую диаграмму указанного типа на слайд.  
- **`setBubbleSizeScale`** регулирует общий размер пузырей в диаграмме.  
- **`SaveFormat.Pptx`** указывает формат файла PPTX для сохранения.  

#### Пошаговая реализация
**1. Инициализировать презентацию** – создайте объект `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Добавить пузырчатую диаграмму** – вставьте диаграмму в выбранные координаты.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` указывает Aspose.Slides создать пузырчатую диаграмму.  
- Числовые параметры определяют позицию X/Y и ширину/высоту в пунктах.

**3. Настроить масштаб пузырей** – увеличьте пузыри для лучшего визуального восприятия.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Установка масштаба в **150 %** делает каждый пузырь в 1,5 × больше, чем по умолчанию.

**4. Сохранить презентацию** – запишите PPTX на диск.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Советы по устранению неполадок
- Проверьте права записи в целевой папке.  
- Убедитесь, что JAR‑файл Aspose.Slides соответствует версии используемого JDK.

## Как эффективно управлять ресурсами PowerPoint
Эффективное управление ресурсами предотвращает утечки памяти и сохраняет небольшой профиль JVM, особенно при обработке больших наборов слайдов или работе в серверной среде. Следуйте приведённому ниже шаблону, чтобы гарантировать освобождение нативных ресурсов даже при возникновении исключения.

Эффективное управление ресурсами предотвращает утечки памяти, особенно при обработке больших наборов слайдов.

### Прямой ответ
После завершения работы с объектом `Presentation` всегда вызывайте `pres.dispose()` внутри блока `try‑finally`; это освобождает нативные ресурсы и позволяет JVM быстро освободить память.

- **`pres.dispose()`** освобождает нативные ресурсы, используемые презентацией.

**1. Создать и изменить** – работайте с презентацией по необходимости.  
```java
Presentation pres = new Presentation();
```

**2. Освободить ресурсы** – освободите память после завершения обработки.  
```java
if (pres != null) pres.dispose();
```

## Практические применения
Пузырчатые диаграммы отлично подходят для сценариев, где необходимо одновременно визуализировать три измерения данных:

1. **Анализ рынка** – размер пузыря представляет доход, а оси X/Y показывают рост и долю рынка.  
2. **Метрики производительности** – сравнение продуктивности сотрудников (X), удовлетворённости (Y) и влияния (размер).  
3. **Географические данные** – отображение городов, где население закодировано в размере пузыря.  
4. **Управление проектами** – визуализация сроков (X), стоимости (Y) и риска (размер) на одном слайде.

## Соображения по производительности
- **Использование ресурсов** – своевременно освобождайте презентации, чтобы снизить нагрузку на кучу.  
- **Управление памятью в Java** – оборачивайте работу с презентацией в `try‑finally`, чтобы гарантировать освобождение даже при исключениях.  
- **Будьте в актуальном состоянии** – обновляйтесь до последней версии Aspose.Slides, чтобы воспользоваться оптимизациями производительности и исправлениями ошибок.

## Часто задаваемые вопросы

**В: Что такое Aspose.Slides для Java?**  
О: Aspose.Slides для Java — это автономная библиотека, позволяющая создавать, редактировать и конвертировать файлы PowerPoint без необходимости установки Microsoft Office.

**В: Как интегрировать Aspose.Slides в мой существующий Java‑проект?**  
О: Добавьте зависимость Maven или Gradle, показанную выше, либо поместите JAR‑файл в classpath, затем импортируйте `com.aspose.slides.*`.

**В: Можно ли использовать Aspose.Slides для больших презентаций?**  
О: Да, библиотека эффективно обрабатывает презентации размером до **2 ГБ** и поддерживает потоковую работу, чтобы избежать загрузки всего файла в память.

**В: Какие типы диаграмм доступны, помимо пузырчатых?**  
О: Поддерживается более **50 типов диаграмм**, включая столбчатые, линейные, круговые, радиальные и водопадные.

**В: Есть ли встроенная поддержка стилизации элементов диаграммы?**  
О: Абсолютно. Вы можете настраивать цвета, шрифты, границы и подписи данных через объекты `ChartSeries` и `ChartTitle` диаграммы.

## Ресурсы
- **Документация**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Загрузка**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Покупка**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Бесплатная пробная версия**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Временная лицензия**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Поддержка**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Последнее обновление:** 2026-09-17  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16)  
**Автор:** Aspose

## Связанные руководства

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java create powerpoint chart using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
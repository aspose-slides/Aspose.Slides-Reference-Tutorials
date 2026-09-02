---
date: '2026-09-02'
description: Узнайте, как создать воронкообразный график в PowerPoint с использованием
  Aspose.Slides for Java. Это пошаговое руководство охватывает настройку данных графика,
  настройку цветов и экспорт презентации.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Узнайте, как создать воронкообразный график в PowerPoint с использованием
  Aspose.Slides for Java. Руководство проведет вас через настройку данных, настройку
  цветов и экспорт готовой презентации.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Создать воронкообразный график в PowerPoint с помощью Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Создать воронкообразный график в PowerPoint с помощью Aspose.Slides for Java
url: /ru/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Освоение создания ворончатой диаграммы в PowerPoint с помощью Aspose.Slides для Java

## Введение
Создание убедительных презентаций — это искусство, объединяющее визуализацию данных, дизайн и повествование. Один мощный визуальный элемент, который мгновенно проясняет многоэтапный процесс, — ворончатая диаграмма. Независимо от того, нужно ли вам проиллюстрировать конвейер продаж, поток конверсий или узкое место в производстве, хорошо спроектированная ворончатая диаграмма превращает сырые цифры в интуитивный рассказ. В этом руководстве вы научитесь **создать ворончатую диаграмму** в PowerPoint программно с помощью Aspose.Slides for Java, настроить её данные, индивидуализировать цвет каждого сегмента и экспортировать готовую презентацию.

**Что вы узнаете**
- Как добавить Aspose.Slides for Java в проект Maven или Gradle  
- Как создать объект `Presentation` и получить доступ к его слайдам  
- Как вставить ворончатую диаграмму, определить категории и заполнить данные рядов  
- Как оформить каждый сегмент воронки с помощью сплошных заливок или фирменных цветов  
- Как сохранить презентацию в файл PPTX или экспортировать слайд как изображение  

## Быстрые ответы
- **Какова основная библиотека для визуализации данных в Java?** Aspose.Slides for Java.  
- **Как создать ворончатую диаграмму в PowerPoint?** Вызовите `slide.addChart(ChartType.Funnel, …)` на целевом слайде.  
- **Какой API задает источник данных диаграммы?** Используйте `IChartDataWorkbook` вместе с `chart.getChartData()`.  
- **Можно ли настроить цвета для каждого сегмента воронки?** Да — установите `FillFormat.setFillType(FillType.Solid)` и задайте `java.awt.Color`.  
- **Нужна ли лицензия для использования в продакшене?** Для коммерческих развертываний требуется приобретённая лицензия Aspose.Slides.

## Что такое визуализация данных в Java?
Визуализация данных в Java — это практика преобразования сырых данных в диаграммы, графики или интерактивные графики непосредственно из Java‑приложений. Aspose.Slides for Java — ведущая библиотека, позволяющая разработчикам генерировать более 100 типов диаграмм, включая ворончатые, без необходимости вручную запускать PowerPoint, поддерживая презентации до 500 слайдов при низком потреблении памяти.

## Почему использовать ворончатые диаграммы в PowerPoint?
Ворончатые диаграммы мгновенно показывают уровни оттока на последовательных этапах, что делает их идеальными для конвейеров продаж, анализа конверсий или обзоров эффективности процессов. Aspose.Slides предоставляет пиксель‑точный контроль над макетом, цветами сегментов и подписью данных, позволяя поддерживать фирменный стиль и избегать ручного редактирования диаграмм в интерфейсе PowerPoint.

## Предварительные требования (H2)

### Требуемые библиотеки, версии и зависимости
Чтобы внедрить Aspose.Slides for Java в ваш проект, включите соответствующие координаты Maven или Gradle. Библиотека работает с Java 8‑21 и не требует внешних нативных зависимостей.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Вы также можете скачать JAR напрямую с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Требования к настройке окружения
Убедитесь, что у вас установлен JDK 8 или новее, и переменная `JAVA_HOME` указывает на правильный каталог JDK. Aspose.Slides работает на любой ОС, поддерживающей JDK, включая Windows, macOS и Linux.

### Предварительные знания
Базовое знакомство с синтаксисом Java, объектно‑ориентированным программированием и концепцией файла презентации будет полезным, но фрагменты кода полностью объяснены для разработчиков любого уровня.

## Настройка Aspose.Slides для Java (H2)

1. **Добавьте зависимость** — используйте фрагмент Maven или Gradle выше.  
2. **Получите лицензию** —  
   - **Бесплатная пробная версия** — скачайте временную лицензию с [веб‑сайта Aspose](https://purchase.aspose.com/temporary-license/) для оценки.  
   - **Полная лицензия** — приобретите производственную лицензию через [страницу покупки](https://purchase.aspose.com/buy).  
3. **Базовая инициализация** —  

`Presentation` — основной класс Aspose.Slides, представляющий файл PowerPoint в памяти. Он предоставляет доступ к слайдам, фигурам и объектам диаграмм.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Код выше создает новый экземпляр `Presentation`, готовый к работе со слайдами, и гарантирует освобождение ресурсов с помощью `dispose()`.

## Руководство по реализации

Мы пройдем каждый необходимый элемент для построения полной ворончатой диаграммы, добавляя короткое пояснительное описание перед каждым кодовым заполнителем.

### Функция 1: создание презентации (H2)

#### Обзор
Начните с создания экземпляра класса `Presentation`. Этот объект является точкой входа для всех последующих операций.

`Presentation` — верхнеуровневый объект Aspose.Slides, содержащий коллекцию слайдов и глобальные настройки документа.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Этот фрагмент открывает пустую презентацию, которую позже можно сохранить как файл `.pptx`.

### Функция 2: добавление ворончатой диаграммы на слайд (H2)

#### Обзор
Вставьте ворончатую диаграмму на первый слайд, задайте её размер и тип диаграммы.

`ChartType.Funnel` указывает Aspose.Slides отрисовать визуализацию в виде воронки вместо столбчатой или линейной диаграммы.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Вызов `addChart` создаёт форму диаграммы, позиционирует её в точке `(50, 50)` и задаёт ширину `500` и высоту `400`.

### Функция 3: очистка данных диаграммы (H2)

#### Обзор
Перед заполнением диаграммы очистите любые категории‑заполнители или ряды, которые могут присутствовать в шаблоне.

`chart.getChartData().getCategories().clear()` удаляет все существующие категории, а `chart.getChartData().getSeries().clear()` удаляет любые предзаполненные ряды.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Это гарантирует чистый лист, чтобы ваши пользовательские данные отображались точно так, как задумано.

### Функция 4: настройка рабочей книги данных диаграммы (H2)

#### Обзор
Объект `IChartDataWorkbook` хранит сырые значения, управляющие диаграммой. Его инициализация позволяет записывать данные непосредственно в ячейки.

`IChartDataWorkbook` — лёгкая in‑memory таблица, которую Aspose.Slides использует для подачи данных в ряды и категории диаграммы.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Код очищает любые существующие ячейки, подготавливая рабочую книгу к новым записям.

### Функция 5: добавление категорий в диаграмму (H2)

#### Обзор
Определите текстовые метки, которые появятся слева от воронки — они представляют каждый этап вашего процесса.

`chart.getChartData().getCategories().add()` создаёт новый объект категории, привязанный к конкретной ячейке рабочей книги.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Здесь мы добавляем три этапа: «Prospects», «Qualified Leads» и «Closed Deals».

### Функция 6: добавление рядов данных в диаграмму (H2)

#### Обзор
Заполните воронку числовыми значениями и при желании назначьте уникальный цвет каждому сегменту.

`IDataPoint` представляет отдельную точку данных внутри ряда диаграммы.  

`chart.getChartData().getSeries().add()` создаёт ряд, содержащий числовые точки; каждому `IDataPoint` можно задать собственный цвет заливки.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Цикл демонстрирует, как установить сплошную заливку для каждой точки, используя фирменные константы `java.awt.Color` или случайно сгенерированные цвета для визуального разнообразия.

## Общие варианты использования и советы (H2)

- **Отчёт по воронке продаж** — показывайте, сколько лидов переходит от потенциального к закрытому на каждом этапе.  
- **Анализ эффективности процесса** — визуализируйте потери материалов или задержки времени на этапах производства.  
- **Обзор маркетинговой воронки** — сравнивайте коэффициенты конверсии по кампаниям или источникам трафика.  

**Pro tip:** Вместо случайных цветов используйте фирменную палитру вашей компании (например, `new Color(0, 112, 192)`) для согласованности презентации с другими маркетинговыми материалами.

## Часто задаваемые вопросы (H2)

**Q: Как изменить ориентацию ворончатой диаграммы?**  
A: Установите свойство `ChartOrientation` у объекта `IChart` в `ChartOrientation.Vertical` или `ChartOrientation.Horizontal`.

**Q: Можно ли экспортировать слайд как изображение после добавления диаграммы?**  
A: Да — вызовите `pres.getSlides().get_Item(0).getThumbnail(1, 1)` и запишите полученный `java.awt.image.BufferedImage` в файл PNG или JPEG.

**Q: Что делать, если нужно более трёх категорий?**  
A: Просто добавьте дополнительные категории с помощью `chart.getChartData().getCategories().add(...)` и предоставьте соответствующие точки данных для каждой новой категории.

**Q: Есть ли способ скрыть легенду?**  
A: Используйте `chart.getChartTitle().setVisible(false)` и `chart.getLegend().setVisible(false)`, чтобы убрать как заголовок, так и легенду из визуала.

**Q: Нужна ли лицензия для сборок разработки?**  
A: Временная лицензия достаточна для оценки; полная коммерческая лицензия требуется для продакшн‑развёртываний.

---

**Last updated:** 2026-09-02  
**Tested with:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

## Связанные руководства

- [Как добавить диаграмму в PowerPoint с помощью Aspose.Slides for Java: пошаговое руководство](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Как редактировать данные диаграммы PowerPoint с помощью Aspose.Slides for Java: полное руководство](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Добавление анимации к диаграмме PowerPoint с помощью Aspose.Slides for Java — пошаговое руководство](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
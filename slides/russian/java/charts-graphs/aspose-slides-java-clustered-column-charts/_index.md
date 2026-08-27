---
date: '2026-08-27'
description: Узнайте, как создать clustered column chart в Java с использованием Aspose.Slides,
  добавить график, установить автоматические цвета серий и сохранить презентацию в
  формате PPTX.
keywords:
- create clustered column chart
- how to add chart
- how to set colors
- how to save pptx
- maven aspose slides dependency
lastmod: '2026-08-27'
og_description: Узнайте, как создать clustered column chart в Java с использованием
  Aspose.Slides, добавить график, установить автоматические цвета серий и сохранить
  презентацию в формате PPTX — все с понятными пошаговыми инструкциями.
og_image_alt: Guide showing Java code to create a clustered column chart with Aspose.Slides
og_title: Создать clustered column chart в Java с Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to create clustered column chart in Java using Aspose.Slides,
    add the chart, set automatic series colors, and save the presentation as PPTX.
  headline: How to create clustered column chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes—Aspose.Slides is platform‑agnostic and works in any Java‑based server
      environment, including Spring Boot and Jakarta EE.
    question: Can I use this code in a web application?
  - answer: Absolutely. `ChartType` enum includes Pie, Bar, Line, Area, Radar, and
      many more.
    question: Does the library support other chart types?
  - answer: Ensure the directory is created beforehand or use `Files.createDirectories(Paths.get(folder))`
      to avoid `FileNotFoundException`.
    question: What if the output folder does not exist?
  - answer: Populate series using streaming APIs or batch inserts, and consider disabling
      chart animation to improve rendering speed.
    question: How do I handle large datasets (thousands of points)?
  - answer: 'Visit the official documentation and sample repository: [Aspose.Slides
      Documentation](https://reference.aspose.com/slides/java/).'
    question: Where can I find more code samples?
  type: FAQPage
tags:
- clustered column chart
- Aspose.Slides
- Java chart tutorial
- PPTX generation
title: Как создать clustered column chart в Java с Aspose.Slides
url: /ru/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать сгруппированную столбчатую диаграмму в Java с Aspose.Slides

## Введение
Создание программно сгруппированной столбчатой диаграммы экономит часы ручного форматирования и гарантирует согласованность в нескольких презентациях. В этом руководстве вы узнаете **как создать сгруппированную столбчатую диаграмму** в Java с Aspose.Slides, **как добавить диаграмму**, **как задать цвета**, и **как сохранить презентацию в формате PPTX**. Мы охватим всё от установки библиотеки до настройки заливки серий и сохранения файла, чтобы вы могли встраивать богатые визуализации данных в любую презентацию PowerPoint.

## Быстрые ответы
- **Какой основной класс для работы с презентациями?** `Presentation` from the `com.aspose.slides` package.  
- **Как добавить сгруппированную столбчатую диаграмму?** Call `slide.getShapes().addChart(ChartType.ClusteredColumn, x, y, width, height)`.  
- **Можно ли автоматически задавать цвета серий?** Yes—enable `setAutomaticSeriesColor(true)` on each series.  
- **Какой формат следует использовать для сохранения файла?** `SaveFormat.Pptx` produces a standard PowerPoint file.  
- **Требуется ли лицензия для продакшн?** A trial works for development; a full license is needed for commercial use.

## Что такое сгруппированная столбчатая диаграмма?
Сгруппированная столбчатая диаграмма отображает несколько серий данных рядом друг с другом для каждой категории, что упрощает сравнение значений между группами. Aspose.Slides поддерживает этот тип диаграммы «из коробки» и позволяет программно управлять каждым визуальным аспектом.

## Почему создавать сгруппированную столбчатую диаграмму с Aspose.Slides?
Aspose.Slides может обрабатывать **более 50 форматов ввода и вывода** и работать с презентациями, содержащими **сотни слайдов**, без загрузки всего файла в память. Такая эффективность позволяет генерировать большие наборы слайдов в серверной среде с минимальными ресурсными затратами.

## Требования
- **Java Development Kit** 16 или новее.  
- **Maven** или **Gradle** для управления зависимостями.  
- Базовое знакомство с синтаксисом Java и объектно‑ориентированными концепциями.  

### Требуемые библиотеки и зависимости
Вам понадобится библиотека Aspose.Slides for Java (версия 25.4 или новее). Библиотека полностью совместима с JDK 16 и предоставляет богатый API для работы с диаграммами.

### Требования к настройке окружения
Ваш IDE (IntelliJ IDEA, Eclipse, VS Code) должен быть настроен для компиляции кода Java 16 и разрешения зависимостей Maven/Gradle.

### Требования к знаниям
Понимание структуры слайдов PowerPoint и базовой терминологии диаграмм (серии, категории, точки данных) поможет быстрее освоить примеры.

## Настройка Aspose.Slides для Java
Интегрируйте библиотеку в проект, используя один из следующих методов.

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

Прямое скачивание — получите JAR с официальной страницы релизов: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
- **Бесплатная пробная версия** — зарегистрируйтесь на сайте Aspose, чтобы получить временный файл лицензии.  
- **Временная лицензия** — запросите 30‑дневную лицензию для более крупных тестовых наборов.  
- **Полная лицензия** — покупка для неограниченного использования в продакшн.

**Базовая инициализация и настройка**  
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```  

## Как добавить сгруппированную столбчатую диаграмму?
`Presentation` представляет файл PowerPoint в памяти.  

**Прямой ответ:**  
Создайте объект `Presentation`, который представляет файл PowerPoint в памяти, получите первый слайд и вызовите `slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400)`. Этот единственный вызов вставит полностью функциональную сгруппированную столбчатую диаграмму, готовую к заполнению данными, и разместит её в указанных координатах на слайде.

### Функция 1: создание сгруппированной столбчатой диаграммы
Класс `Presentation` представляет файл PowerPoint в памяти и предоставляет доступ к слайдам, фигурам и объектам диаграмм.

**Шаг 1: инициализация презентации**  
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```  

**Шаг 2: добавить сгруппированную столбчатую диаграмму**  
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```  

**Шаг 3: очистка ресурсов**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Как задать цвета для диаграммы?
`Series` представляет коллекцию точек данных внутри диаграммы.  

**Прямой ответ:**  
После создания диаграммы получите её данные через `chart.getChartData()` и пройдитесь по каждому объекту `Series`. Для каждой серии вызовите `setAutomaticSeriesColor(true)` у родительской серии. Aspose.Slides автоматически присвоит каждой серии отличительный контрастный цвет из своей палитры, обеспечивая визуальную чёткость без ручного выбора цветов.

### Функция 2: автоматическая заливка серий цветом
`IChart` — интерфейс, представляющий форму диаграммы; он предоставляет `getChartData()` для манипуляций с сериями.

**Шаг 1: доступ к диаграмме и перебор серий**  
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```  

**Шаг 2: управление ресурсами**  
```java
finally {
    if (presentation != null) presentation.dispose();
}
```  

## Как сохранить презентацию в формате PPTX?
`save` записывает презентацию в файл выбранного формата.  

**Прямой ответ:**  
Укажите путь к выходному файлу, например `"output/ClusteredColumnChart.pptx"`, и вызовите `presentation.save(outputPath, SaveFormat.Pptx)`. Метод `save` сериализует весь набор слайдов, включая все фигуры, диаграммы и ресурсы, в стандартный файл PPTX, который можно открыть в PowerPoint 2010 и новее, а также во многих онлайн‑просмотрщиках.

### Функция 3: сохранение презентации на диск
Сохранение с помощью `SaveFormat.Pptx` создаёт файл, совместимый с PowerPoint 2010 и более новыми версиями, а также большинством онлайн‑просмотрщиков.

**Шаг 1: определить путь вывода**  
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```  

**Шаг 2: сохранить презентацию**  
```java
presentation.save(outputPath, SaveFormat.Pptx);
```  

## Практические применения
- **Финансовая отчетность** — сравнение квартального дохода по продуктовым линейкам.  
- **Маркетинговая аналитика** — визуализация эффективности кампаний по регионам.  
- **Управление проектами** — отображение скорости спринтов или распределения ресурсов по командам.  

## Соображения по производительности
- Своевременно освобождайте объекты `Presentation`, чтобы освободить нативные ресурсы.  
- Вызовите `presentation.getSlides().removeUnusedResources()` перед сохранением, чтобы уменьшить размер файла.  
- Заполняйте серии диаграммы легковесными коллекциями (например, `ArrayList<Double>`), чтобы снизить потребление памяти.

## Заключение
Теперь вы знаете, как **создать сгруппированную столбчатую диаграмму**, автоматически **задать цвета** и **сохранить презентацию в формате PPTX** с помощью Aspose.Slides for Java. Эти шаги позволяют программно генерировать слайды с данными, устраняя повторяющуюся ручную работу и обеспечивая визуальную согласованность в вашей организации.

**Следующие шаги:**  
Изучите расширенные настройки, такие как подписи данных, форматирование осей и динамическое привязывание данных из баз данных или CSV‑файлов, чтобы ещё больше обогатить ваши презентации.

## Часто задаваемые вопросы
**Q: Можно ли использовать этот код в веб‑приложении?**  
A: Да — Aspose.Slides платформенно‑независим и работает в любой серверной среде на Java, включая Spring Boot и Jakarta EE.

**Q: Поддерживает ли библиотека другие типы диаграмм?**  
A: Абсолютно. Перечисление `ChartType` включает Pie, Bar, Line, Area, Radar и многие другие.

**Q: Что делать, если папка вывода не существует?**  
A: Убедитесь, что каталог создан заранее, или используйте `Files.createDirectories(Paths.get(folder))`, чтобы избежать `FileNotFoundException`.

**Q: Как работать с большими наборами данных (тысячи точек)?**  
A: Заполняйте серии, используя потоковые API или пакетные вставки, и рассмотрите возможность отключения анимации диаграммы для повышения скорости рендеринга.

**Q: Где найти больше примеров кода?**  
A: Посетите официальную документацию и репозиторий примеров: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/).

## Ресурсы
- **Документация:** [Документация Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Справочник:** [Справочник Aspose.Slides](https://reference.aspose.com/slides/java/)  
- **Скачать Aspose.Slides:** [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Купить лицензию:** [Buy a License](https://purchase.aspose.com/buy)  
- **Начать бесплатный пробный период:** [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Запросить здесь:** [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Форум Aspose:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-27  
**Tested With:** Aspose.Slides 25.4 (JDK 16)  
**Author:** Aspose

## Связанные руководства

- [Создать диаграмму PowerPoint Java — Сохранить презентации с диаграммами, используя Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)  
- [Зависимость Maven Aspose Slides: добавить и настроить диаграммы в презентациях с помощью Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)  
- [Добавить анимацию к диаграмме PowerPoint с Aspose.Slides for Java — пошаговое руководство](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
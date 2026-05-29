---
date: '2026-05-29'
description: Узнайте, как создать pie chart Aspose с помощью Aspose.Slides Maven,
  добавить pie chart Java в слайд и настроить chart data. Пошаговое руководство с
  настройкой Maven и практическими примерами.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Создать pie chart Aspose – Добавить pie chart в презентацию с Maven
url: /ru/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как добавить круговую диаграмму в презентацию с помощью Aspose.Slides Java

## Введение
В этом руководстве вы **создадите круговую диаграмму aspose** с помощью Aspose.Slides Maven и увидите, как встроить её в слайд PowerPoint. Создание визуально привлекательных презентаций имеет решающее значение для эффективной передачи информации, особенно когда визуализация данных играет ключевую роль. Если вы хотите автоматизировать этот процесс с помощью **aspose slides maven**, вы попали по адресу. Мы пройдёмся по добавлению диаграммы на слайд — конкретно круговой диаграммы — и её настройке для реальных сценариев.

### Что вы узнаете
- Как инициализировать объект презентации в Java.  
- Шаги для **добавления круговой диаграммы java** на первый слайд презентации.  
- Доступ к рабочим книгам данных диаграммы и перечисление листов внутри них.  

Давайте погрузимся в то, как вы можете использовать Aspose.Slides Java для улучшения ваших презентаций динамическими диаграммами!

## Быстрые ответы
- **Какая библиотека добавляет диаграммы через Maven?** aspose slides maven  
- **Какой тип диаграммы демонстрируется?** Pie chart (add chart to slide)  
- **Минимальная версия Java?** JDK 16 or later  
- **Нужна ли лицензия для тестирования?** A free trial works; production needs a license  
- **Где найти зависимость Maven?** In the setup section below  

## Что такое Aspose Slides Maven?
Aspose.Slides for Java — это мощный API, позволяющий разработчикам программно создавать, изменять и рендерить файлы PowerPoint. Пакет Maven (`aspose-slides`) упрощает управление зависимостями, позволяя сосредоточиться на построении и настройке слайдов — например, добавлении круговой диаграммы — без работы с низкоуровневой обработкой файлов.

## Почему использовать Aspose.Slides Maven для добавления диаграммы на слайд?
Использование Aspose.Slides Maven позволяет генерировать диаграммы напрямую из кода Java без ручного редактирования PowerPoint. Он предоставляет полный программный контроль над типами диаграмм, источниками данных и стилями, обеспечивая единообразный брендинг и точность. Артефакт Maven также обрабатывает все необходимые зависимости, упрощая сборки и позволяя бесшовную интеграцию в конвейеры CI/CD.

## Требования
- **Aspose.Slides for Java** версии 25.4 или новее (Maven/Gradle).  
- Установлен JDK 16+.  
- IDE (IntelliJ IDEA, Eclipse и т.д.).  
- Базовые знания Java и знакомство с Maven или Gradle.

## Настройка Aspose.Slides для Java
Сначала включите Aspose.Slides в ваш проект через Maven или Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Кроме того, вы можете [скачать последнюю версию](https://releases.aspose.com/slides/java/) напрямую с сайта Aspose.

### Приобретение лицензии
Aspose.Slides for Java предлагает бесплатную пробную версию с временной лицензией для тестирования. Для неограниченного использования в продакшене приобретите лицензию через [страницу покупки](https://purchase.aspose.com/buy).

## Руководство по реализации
Ниже мы разбиваем решение на две функции: добавление круговой диаграммы и доступ к её рабочей книге данных.

### Функция 1: Создание презентации и добавление диаграммы
#### Обзор
Эта часть показывает, как создать новую презентацию и **добавить круговую диаграмму** на первый слайд.

#### Как создать круговую диаграмму aspose?
Загрузите класс `Presentation`, добавьте диаграмму типа `ChartType.Pie` и сохраните файл. Вся операция требует лишь три вызова API и выполняется менее чем за секунду для типичной презентации из 10 слайдов, что делает её идеальной для автоматической генерации отчетов.

#### Пошагово

**Шаг 1: Инициализировать новый объект Presentation**  
Класс `Presentation` — это объект верхнего уровня Aspose.Slides, представляющий файл PowerPoint в памяти.  
```java
Presentation pres = new Presentation();
```
*Создаёт экземпляр `Presentation`, который будет содержать все слайды.*

**Шаг 2: Добавить круговую диаграмму**  
`ChartType.Pie` указывает Aspose отрисовать круговую диаграмму.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Размещает круговую диаграмму с координатами (50, 50), шириной 400 и высотой 500.*

**Шаг 3: Освободить ресурсы**  
Вызов `dispose()` освобождает нативные ресурсы и предотвращает утечки памяти.  
```java
if (pres != null) pres.dispose();
```
*Освобождает нативные ресурсы; всегда вызывайте `dispose()`, когда завершаете работу.*

### Функция 2: Доступ к рабочей книге данных диаграммы и листам
#### Обзор
Изучите, как получить доступ к базовой рабочей книге, хранящей данные диаграммы, и перебрать её листы.

#### Как получить доступ к рабочей книге данных диаграммы?
Получите `IChartDataWorkbook` из диаграммы, затем пройдитесь по её коллекции `Worksheets`. Эта рабочая книга имитирует файл Excel, позволяя программно читать, изменять или добавлять серии данных, которые диаграмма отразит мгновенно при обновлении во время выполнения без перезапуска.

#### Пошагово

**Шаг 1: (Повторное использование) Инициализировать новый объект Presentation**  
*То же, что в Функции 1, Шаг 1.*

**Шаг 2: (Повторное использование) Добавить круговую диаграмму**  
*То же, что в Функции 1, Шаг 2.*

**Шаг 3: Получить рабочую книгу данных диаграммы**  
`IChartDataWorkbook` — это интерфейс, предоставляющий доступ для чтения/записи к внутренней Excel‑подобной рабочей книге диаграммы.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Получает `IChartDataWorkbook`, связанный с диаграммой.*

**Шаг 4: Перебрать листы**  
Объекты `Worksheet` представляют отдельные листы внутри рабочей книги.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Выводит имя каждого листа, позволяя проверить структуру данных.*

**Шаг 5: Освободить ресурсы**  
*То же, что в Функции 1, Шаг 3.*

## Практические применения
- **Отчётность данных:** Автоматическое создание наборов слайдов с актуальными метриками для бизнес‑аналитики.  
- **Академические презентации:** Визуализация результатов исследований без ручного создания диаграмм.  
- **Маркетинговые материалы:** Мгновенно демонстрировать показатели продукта или результаты опросов.

## Соображения по производительности
- Aspose.Slides может работать с **более 50 форматами ввода и вывода** и обрабатывать презентации из сотен страниц без загрузки всего файла в память.  
- Сохраняйте разумное количество слайдов и диаграмм; каждая диаграмма потребляет нативную память.  
- Всегда вызывайте `dispose()`, чтобы своевременно освобождать ресурсы.  
- Оптимизируйте работу с данными рабочей книги — избегайте загрузки огромных наборов данных в одну диаграмму.

## Заключение
Мы рассмотрели, как **aspose slides maven** позволяет **добавлять диаграмму на слайд** программно и как работать с рабочей книгой данных диаграммы. С этими строительными блоками вы можете автоматизировать любой процесс отчётности, требующий качественного вывода PowerPoint.

### Следующие шаги
- Изучите варианты стилизации диаграмм (цвета, легенды, подписи данных).  
- Подключитесь к внешним источникам данных (CSV, базы данных) для динамического заполнения диаграмм.  
- Комбинируйте несколько типов диаграмм в одной презентации для более насыщенного повествования.

## Часто задаваемые вопросы

**Q: Как установить Aspose.Slides for Java?**  
A: Используйте зависимость Maven или Gradle, показанную выше, или скачайте библиотеку со страницы релизов.

**Q: Каковы системные требования для Aspose.Slides?**  
A: JDK 16 или новее; библиотека работает на любой платформе, поддерживающей Java.

**Q: Можно ли добавить другие типы диаграмм, кроме круговых?**  
A: Да, Aspose.Slides поддерживает гистограммы, линейные, точечные, радиальные и более 20 типов диаграмм.

**Q: Как эффективно работать с большими презентациями?**  
A: Своевременно освобождайте объекты, ограничивайте использование изображений высокого разрешения и повторно используйте шаблоны диаграмм, чтобы снизить потребление памяти.

**Q: Где найти более подробную информацию о функциях Aspose.Slides?**  
A: Посетите [Aspose documentation](https://reference.aspose.com/slides/java/) для полного справочника API.

**Q: Требуется ли лицензия для коммерческого использования?**  
A: Для продакшена требуется действующая лицензия; бесплатная пробная версия доступна для оценки.

**Q: Включает ли пакет Maven все возможности построения диаграмм?**  
A: Да, артефакт `aspose-slides` Maven содержит полный движок построения диаграмм.

## Ресурсы
- Документация: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Скачать: [Latest Releases](https://releases.aspose.com/slides/java/)
- Покупка и пробная версия: [Purchase Page](https://purchase.aspose.com/buy)
- Бесплатная пробная версия: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Временная лицензия: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Форум поддержки: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## Связанные руководства

- [How to Customize Pie Chart Colors in Java with Aspose.Slides – A Complete Guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Create a Pie of Pie Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
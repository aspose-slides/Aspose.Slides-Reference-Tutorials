---
date: '2026-08-06'
description: Узнайте, как изменить legend font color и изменить текст chart legend
  с помощью Aspose.Slides for Java. Следуйте step‑by‑step инструкциям, чтобы быстро
  customize chart legends.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Узнайте, как изменить legend font color и изменить текст chart legend
  с помощью Aspose.Slides for Java. Это руководство показывает точные шаги и best
  practices.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Как изменить legend font color в Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Как изменить legend font color в Aspose.Slides for Java
url: /ru/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как изменить цвет шрифта легенды в Aspose.Slides for Java

## Введение
Если вам нужно **change legend font color** в диаграмме, Aspose.Slides for Java предоставляет полный контроль над каждой записью легенды. Это руководство проведёт вас через настройку стилей текста легенды, применение полужирного или курсивного шрифта и установку сплошных цветов, чтобы ваши диаграммы выглядели именно так, как вы хотите. К концу этого руководства вы сможете уверенно изменять текст легенды диаграммы и интегрировать изменения в любую существующую презентацию.

**Что вы узнаете**
- Как **change legend font color** программно.
- Способы **modify chart legend text**, такие как полужирный, курсивный и изменение размера.
- Советы по применению изменений к нескольким диаграммам в одной презентации.
- Как интегрировать эти шаги в более крупный процесс автоматизации.

## Быстрые ответы
- **Могу ли я изменить цвет отдельного элемента легенды?** Да — доступ к элементу осуществляется по его индексу, после чего задаётся сплошной цвет заливки.  
- **Нужна ли лицензия для использования этих API?** Для продакшн‑использования требуется временная или платная лицензия; бесплатная пробная версия подходит для оценки.  
- **Какая версия Java поддерживается?** Aspose.Slides for Java 25.4+ работает с JDK 16 и новее.  
- **Повлияют ли изменения на другие элементы диаграммы?** Нет, форматирование легенды изолировано от стилей рядов данных.  
- **Возможна ли пакетная обработка?** Абсолютно — можно перебрать слайды и диаграммы, применяя одинаковые настройки легенды ко всей презентации.

## Что такое изменение цвета шрифта легенды?
`change legend font color` относится к программной операции установки цвета текста записей легенды диаграммы с помощью API Aspose.Slides. Эта операция изменяет визуальное отображение легенды без изменения исходных данных.

## Зачем настраивать легенды диаграмм?
Aspose.Slides поддерживает **более 50 форматов ввода и вывода** и может работать с презентациями, содержащими **более 500 слайдов**, при этом потребление памяти остаётся ниже 200 МБ. Настройка легенд улучшает читаемость, усиливает фирменные цвета и гарантирует, что ключевые данные выделяются — особенно в бизнес‑ или учебных презентациях, где визуальная чёткость влияет на принятие решений.

## Требования
- **Библиотека Aspose.Slides for Java** (версия 25.4 или новее).  
- Java Development Kit (JDK) 16 или выше.  
- IDE, например IntelliJ IDEA, Eclipse или NetBeans.  
- Maven или Gradle для управления зависимостями.  
- Базовые знания программирования на Java.

## Настройка Aspose.Slides for Java
Чтобы начать настройку легенд диаграмм, добавьте библиотеку в проект одним из способов ниже.

### Maven
Добавьте следующую зависимость в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Включите эту строку в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямое скачивание
Вы также можете получить последнюю JAR‑файл с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Шаги получения лицензии
- **Free trial:** Начните с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides.  
- **Temporary license:** Оформите временную лицензию для расширенной оценки.  
- **Purchase:** Для полного доступа рассмотрите покупку лицензии на [Aspose Purchase](https://purchase.aspose.com/buy).

#### Базовая инициализация и настройка
После добавления библиотеки в проект:
1. Инициализируйте Aspose.Slides в вашем Java‑приложении.  
2. Загрузите существующую презентацию или создайте новую.

## Как изменить цвет шрифта легенды?
Чтобы изменить цвет шрифта легенды, загрузите презентацию, получите объект диаграммы, извлеките её легенду, а затем измените формат текста каждой записи легенды, задав тип заливки — Solid и указав нужный цвет. Эта единственная операция мгновенно меняет цвет текста легенды без необходимости перерисовывать весь слайд. Пример: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Такой подход работает для любого типа диаграммы и не требует повторного рендеринга всего слайда.

### Доступ к свойствам текста легенды и их изменение

#### Определение якоря
Интерфейс `IChart` представляет объект диаграммы на слайде, а его метод `getLegend()` возвращает объект `ILegend`, содержащий коллекцию элементов `ILegendEntry`.

#### Добавление диаграммы в презентацию
1. **Загрузите презентацию:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Добавьте сгруппированную столбчатую диаграмму:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Настройка свойств шрифта
3. **Получите формат текста элемента легенды:**  
   Здесь `legendEntry` — объект `ILegendEntry`, представляющий одну запись в легенде диаграммы.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Установите полужирный и курсивный стили с определённой высотой:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Измените тип заливки на сплошной цвет для лучшей видимости:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Сохранение презентации
6. **Сохраните изменения:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Распространённые подводные камни и устранение неполадок
- Убедитесь, что индекс записи легенды соответствует порядку рядов в вашей диаграмме.  
- Проверьте, что вы используете версию библиотеки, поддерживающую `setSolidFillColor` (доступно, начиная с версии 20.9).  

## Практические применения
Настройка текста легенды полезна в реальных сценариях:

1. **Бизнес‑презентации:** Согласуйте цвета легенды с фирменным стилем для профессионального вида.  
2. **Учебные материалы:** Выделяйте ключевые ряды данных, используя контрастные цвета легенды.  
3. **Маркетинговые презентации:** Подчёркивайте показатели эффективности жирными, цветными легендами, чтобы привлечь внимание заинтересованных сторон.  

Вы также можете автоматизировать обновление легенд, получая значения цветов из базы данных или конфигурационного файла.

## Соображения по производительности
При обработке больших презентаций учитывайте следующие рекомендации:

- **Эффективное управление памятью:** Вызывайте `presentation.dispose()` после сохранения, чтобы освободить нативные ресурсы.  
- **Загрузка только необходимых слайдов:** Используйте `Presentation.load(String path, LoadOptions options)` с `LoadOptions.setLoadOnlySlideIds()`, если нужен только подмножество слайдов.  
- **Пакетная обработка:** Группируйте обновления легенд по слайдам, чтобы уменьшить количество вызовов API и повысить пропускную способность.

## Заключение
Теперь вы знаете, как **change legend font color** и **modify chart legend text** с помощью Aspose.Slides for Java. Эти настройки повышают визуальную чёткость и помогают более эффективно передавать данные. Экспериментируйте с различными шрифтами, размерами и цветами, чтобы соответствовать руководству по стилю вашей презентации, и изучайте другие возможности стилизации диаграмм для создания действительно профессиональных наборов слайдов.

**Следующие шаги**
- Попробуйте применить одинаковое оформление легенд к круговым и линейным диаграммам.  
- Скомбинируйте настройку легенды с форматированием подписей данных для полностью брендированной диаграммы.  

Готовы улучшить свои презентации? Реализуйте описанные шаги и сразу увидьте разницу!

## Раздел FAQ
1. **Как изменить цвет текста элемента легенды?**  
   Используйте `getFillFormat().setFillType(FillType.Solid)`, а затем `setSolidFillColor(Color.YOUR_COLOR)` для формата текста записи легенды.

2. **Можно ли применить эти изменения ко всем легендам в презентации?**  
   Да — пройдитесь по каждому слайду, найдите каждую диаграмму и обновите её записи легенды в цикле.

3. **Можно ли динамически менять размер шрифта в зависимости от длины текста?**  
   Вы можете вычислить необходимый размер с помощью `TextFrame.getTextFrameFormat().getFontHeight()` и установить его через `setFontHeight(double)`.

4. **Что делать, если возникают проблемы с индексацией записей легенды?**  
   Проверьте, что используемый индекс соответствует порядку рядов; помните, что индексы начинаются с нуля.

5. **Где найти больше примеров Aspose.Slides?**  
   Исследуйте [Aspose Documentation](https://reference.aspose.com/slides/java/) для полного руководства и справочника API.

**Additional Q&A**

**Q: Изменение цвета шрифта легенды влияет на экспорт в PDF?**  
A: Нет, изменение цвета сохраняется во всех форматах экспорта, поддерживаемых Aspose.Slides, включая PDF и PPTX.

**Q: Можно ли использовать градиент вместо сплошного цвета?**  
A: Да — задайте `FillType.Gradient` и настройте градиентные стопы через `getGradientStyle()`.

**Q: Сколько записей легенды может содержать диаграмма?**  
A: Диаграмма может иметь до 256 записей легенды, ограничение определяется только количеством рядов данных, которые вы добавляете.

## Ресурсы
- **Документация:** Полное руководство по использованию возможностей Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Скачать:** Получите последнюю версию Aspose.Slides for Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Покупка:** Приобретите лицензию для разблокировки всех возможностей ([Link](https://purchase.aspose.com/buy)).  
- **Free trial & temporary license:** Начните с бесплатных пробных версий и запросите временные лицензии ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Поддержка:** Получите помощь от сообщества на форуме поддержки Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Last Updated:** 2026-08-06  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Связанные руководства

- [Enhancing PowerPoint Charts: Font & Axis Customization with Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Dynamic Text Frames & Font Customization Guide](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
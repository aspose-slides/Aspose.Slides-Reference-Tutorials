---
date: '2026-03-18'
description: Узнайте, как создать сгруппированную столбчатую диаграмму в Java с помощью
  Aspose.Slides, как добавить диаграмму, задать цвета и сохранить презентацию в формате
  PPTX. Пошаговое руководство с примерами кода.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Как создать сгруппированную столбчатую диаграмму в Java с помощью Aspose.Slides
url: /ru/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать сгруппированную столбчатую диаграмму в Java с помощью Aspose.Slides

## Введение
Создание визуально привлекательных представлений данных имеет решающее значение для эффективных бизнес‑презентаций, а изучение **как создать сгруппированную столбчатую диаграмму** программно может сэкономить часы ручной работы. В этом руководстве вы увидите **как добавить диаграмму**, автоматически **установить цвета**, и в конце **сохранить презентацию в формате PPTX** с помощью **Aspose.Slides for Java**. Мы пройдем всё необходимое — от настройки библиотеки до добавления диаграммы, настройки заливки серий и сохранения файла.

### Что вы достигнете
- Установить и настроить Aspose.Slides for Java  
- **Создать сгруппированную столбчатую диаграмму** в новой презентации  
- Автоматически применять цвета заливки серий (**how to set colors**)  
- **Сохранить презентацию в формате PPTX** на диск (**how to save presentation**)  

Давайте сначала разберёмся с предварительными требованиями, прежде чем начнём создавать диаграмму.

## Быстрые ответы
- **Какой основной класс?** `Presentation` из `com.aspose.slides`  
- **Как добавить диаграмму?** Используйте `addChart(ChartType.ClusteredColumn, …)` в коллекции фигур слайда (**how to add chart**)  
- **Можно ли автоматически задавать цвета?** Да, вызовите `setAutomaticSeriesColor(true)` для каждой серии (**how to set colors**)  
- **Какой формат используется для сохранения?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **Нужна ли лицензия?** Пробная версия подходит для тестирования; для продакшна требуется полная лицензия  

## Требования
Прежде чем начать, убедитесь, что у вас есть необходимые инструменты и знания:

### Необходимые библиотеки и зависимости
Вам понадобится библиотека Aspose.Slides for Java. Убедитесь, что вы используете версию 25.4 с поддержкой JDK16.

### Требования к настройке среды
Ваша среда разработки должна поддерживать Java (желательно JDK16) и уметь собирать проекты с помощью Maven или Gradle.

### Требования к знаниям
Знание базового программирования на Java, работы с библиотеками через Maven/Gradle и понимание презентаций PowerPoint будет полезным.

## Настройка Aspose.Slides для Java
Чтобы интегрировать Aspose.Slides в ваш проект, следуйте инструкциям ниже:

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

**Direct Download**  
Для тех, кто предпочитает прямое скачивание, посетите [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
- **Free Trial**: Начните с бесплатной пробной версии, чтобы изучить возможности.  
- **Temporary License**: Получите временную лицензию для тестирования без ограничений.  
- **Purchase**: Для постоянного использования приобретите полную лицензию.

**Basic Initialization and Setup**  
Инициализируйте Aspose.Slides следующим образом:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Как добавить сгруппированную столбчатую диаграмму
Добавление диаграммы — первый функциональный шаг. В этом разделе объясняется **как добавить диаграмму** с помощью API.

### Функция 1: Создать сгруппированную столбчатую диаграмму
Создадим сгруппированную столбчатую диаграмму с помощью Aspose.Slides for Java. Эта функция позволяет без усилий добавлять визуально привлекательные диаграммы в ваши слайды.

#### Обзор
В этом разделе мы инициализируем новую презентацию и вставим сгруппированную столбчатую диаграмму на первый слайд.

**Step 1: Initialize Presentation**  
Создайте объект `Presentation`, чтобы начать работу с файлами PowerPoint:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Step 2: Add Clustered Column Chart**  
Добавьте диаграмму в указанные координаты (100, 50) и размеры (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Step 3: Clean Up Resources**  
Всегда освобождайте ресурсы, чтобы избежать утечек памяти:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Как задать цвета для диаграммы
Повышайте визуальную привлекательность, автоматически применяя цвета заливки серий (**how to set colors**).

### Функция 2: Автоматически задавать цвет заливки серий
Автоматически задавайте цвет каждой серии диаграммы для согласованного вида.

#### Обзор
Автоматически задавайте цвет каждой серии диаграммы для согласованного вида.

**Step 1: Access Chart and Iterate Series**  
После создания диаграммы получите к ней доступ и пройдитесь по её сериям:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Step 2: Resource Management**  
Освободите объект презентации после завершения работы:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Как сохранить презентацию в формате PPTX
Когда диаграмма выглядит отлично, вы захотите сохранить файл (**how to save presentation**).

### Функция 3: Сохранить презентацию на диск
Наконец, легко сохраните свою работу с помощью Aspose.Slides.

#### Обзор
Сохраните отредактированные презентации в нужном формате и месте.

**Step 1: Define Output Path**  
Укажите, куда сохранить файл:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Step 2: Save Presentation**  
Вызовите метод `save` объекта `Presentation`:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Практические применения
- **Financial Reports**: Визуализировать квартальные доходы с ясностью.  
- **Marketing Data Analysis**: Демонстрировать результаты кампаний с помощью убедительных визуалов.  
- **Project Management**: Визуально отслеживать вехи и прогресс на командных встречах.

## Соображения по производительности
При работе с Aspose.Slides учитывайте следующие рекомендации:

- Эффективно управляйте памятью, своевременно освобождая объекты `Presentation`.  
- Оптимизируйте размер файлов при сохранении презентаций, чтобы экономить место на диске.  
- Используйте эффективные структуры данных для серий диаграмм, чтобы повысить производительность.

## Заключение
Поздравляем! Вы научились **создавать сгруппированную столбчатую диаграмму**, автоматически **задавать цвета** и **сохранять презентацию в формате PPTX** с помощью Aspose.Slides for Java. Этот навык не только улучшает ваши презентации, но и упрощает процесс визуального представления данных.

**Следующие шаги:**  
Изучите дополнительные возможности, такие как настройка элементов диаграммы, добавление меток данных или интеграция с внешними источниками данных, чтобы расширить возможности вашего проекта.

## Раздел FAQ
1. **Как установить Aspose.Slides для конкретной версии JDK?**  
   - Используйте зависимости Maven/Gradle, указывая `classifier`, как показано в разделе настройки.  
2. **Что делать, если презентация не сохраняется корректно?**  
   - Убедитесь, что у вас есть права записи в целевой каталог и путь к файлу указан правильно.  
3. **Могу ли я создавать другие типы диаграмм с помощью Aspose.Slides for Java?**  
   - Конечно! Исследуйте варианты `ChartType`, такие как Pie, Bar или Line.  
4. **Как работать с большими наборами данных в диаграмме?**  
   - Оптимизируйте структуры данных и рассмотрите предварительную обработку данных перед их визуализацией.  
5. **Где найти больше примеров использования Aspose.Slides for Java?**  
   - Посетите [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) для подробных руководств и примеров кода.

## Ресурсы
- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy a License](https://purchase.aspose.com/buy)  
- **Free Trial**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary License**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Последнее обновление:** 2026-03-18  
**Тестировано с:** Aspose.Slides 25.4 (JDK16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
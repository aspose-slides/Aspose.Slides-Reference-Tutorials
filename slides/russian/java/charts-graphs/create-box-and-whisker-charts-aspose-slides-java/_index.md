---
date: '2026-03-02'
description: Узнайте, как создать box‑plot в Java, добавить диаграмму на слайд и сгенерировать
  диаграмму box‑whisker в PowerPoint с помощью Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Создать box plot на Java с использованием Aspose.Slides для PowerPoint
url: /ru/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создавать диаграммы «ящик с усами» в PowerPoint с помощью Aspose.Slides для Java

В этом руководстве вы **create box plot java** с Aspose.Slides, а затем внедрите диаграмму непосредственно в слайд PowerPoint. Создание визуально привлекательных презентаций данных имеет решающее значение в современном мире, ориентированном на данные, и диаграммы являются незаменимыми инструментами для этой цели. Если вы хотите генерировать диаграммы box‑and‑whisker в PowerPoint с помощью Java, библиотека Aspose.Slides предлагает надёжное решение. Этот учебник проведёт вас через процесс создания и настройки этих диаграмм с помощью Aspose.Slides for Java.

## Что вы узнаете

- Настройка среды для Aspose.Slides for Java
- Шаги по **add chart to slide** и генерации диаграммы box‑whisker в PowerPoint с использованием Java
- Лучшие практики по оптимизации производительности при работе с Aspose.Slides
- Практические применения диаграмм box‑and‑whisker

## Быстрые ответы
- **Какая библиотека создает box plot в Java?** Aspose.Slides for Java.
- **Какой тип диаграммы используется?** `ChartType.BoxAndWhisker`.
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; для продакшн требуется коммерческая лицензия.
- **Могу ли я добавить несколько серий?** Да — повторите блок создания серии для каждого набора данных.
- **В каком формате будет конечный файл?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Требования

- **Java Development Kit (JDK)**: Требуется установить JDK 8 или новее.
- **Aspose.Slides for Java Library**: Необходима для работы с презентациями PowerPoint в Java.
- **IDE**: Интегрированная среда разработки, например IntelliJ IDEA или Eclipse, для написания и выполнения кода.

## Настройка Aspose.Slides для Java

Чтобы использовать Aspose.Slides, добавьте её как зависимость. Вы можете управлять этим через Maven, Gradle или прямую загрузку.

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

### Direct Download

Кроме того, загрузите последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition

- **Free Trial**: Начните с бесплатной пробной версии, чтобы изучить возможности.  
- **Temporary License**: Получите временную лицензию для целей оценки.  
- **Purchase**: Для полной функциональности рассмотрите покупку лицензии.

Чтобы инициализировать Aspose.Slides, убедитесь, что библиотека находится в вашем classpath и при необходимости настройте лицензионные требования.

## Руководство по реализации

Теперь давайте погрузимся в пошаговый код. Каждый блок объясняется перед фрагментом, чтобы вы точно знали, что он делает.

### Что такое box plot и зачем использовать его в Java?

Диаграмма box‑and‑whisker (часто называемая *box plot*) визуализирует распределение данных — медиану, квартали и выбросы — в компактной форме. В Java генерация этой диаграммы программно позволяет внедрять статистические инсайты непосредственно в презентации PowerPoint, исключая необходимость ручного создания диаграмм.

### Зачем добавлять диаграмму на слайд с помощью Aspose.Slides?

Aspose.Slides абстрагирует детали низкоуровневого OpenXML, предоставляя удобный API для создания, стилизации и экспорта диаграмм. Это позволяет автоматизировать генерацию отчётов, поддерживать единый бренд и интегрировать диаграммы в более крупные Java‑процессы.

### Шаг 1: Создать или открыть презентацию

Сначала откройте существующий PPTX или создайте новый:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** Если файл не существует, Aspose.Slides создаст новую пустую презентацию для вас.

### Шаг 2: Добавить диаграмму Box‑and‑Whisker на слайд

Разместите диаграмму там, где она нужна, указав позицию и размер (в пунктах):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Шаг 3: Очистить существующие данные

Перед загрузкой новых данных удалите любые заполнители категорий или серий:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Шаг 4: Настроить категории

Добавьте категории (метки оси X), которые будут отображаться под каждым ящиком:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Note:** Отрегулируйте текст меток, чтобы он соответствовал вашему домену данных (например, “Q1”, “Product A”).

### Шаг 5: Создать и настроить серию

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

### Шаг 6: Сохранить презентацию

Сохраните изменения в новый PPTX‑файл:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Шаг 7: Очистить ресурсы

Всегда освобождайте объект `Presentation`, чтобы освободить нативные ресурсы:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Практические применения

Диаграммы Box‑and‑Whisker незаменимы в статистическом анализе и представлении данных. Ниже приведены несколько сценариев, где они особенно полезны:

1. **Financial Analysis** – Визуализировать распределение доходов по регионам.  
2. **Quality Control** – Выявлять выбросы в измерениях производства.  
3. **Academic Research** – Показать вариабельность экспериментальных результатов.  
4. **Market Research** – Сравнивать показатели продукта по демографическим группам.

Интеграция этих диаграмм в презентации PowerPoint позволяет заинтересованным сторонам быстро понять сложные данные.

## Соображения по производительности

При работе с Aspose.Slides в Java учитывайте следующие рекомендации:

- **Memory Management** – Своевременно освобождать объекты `Presentation`.  
- **Data Handling** – Загружать только необходимые данные; избегать передачи огромных наборов данных напрямую в рабочую книгу диаграммы.  
- **Lazy Loading** – При генерации большого количества слайдов создавайте диаграммы только для тех, которые будут отображаться.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|----------|
| **Диаграмма отображается пустой** | Ячейки данных не заполнены корректно | Проверьте, что `wb.getCell` ссылается на правильную строку/столбец и значение не `null`. |
| **Выбросы не отображаются** | `setShowOutlierPoints` установлен в `false` | Убедитесь, что вызвано `series.setShowOutlierPoints(true)`. |
| **Утечка памяти** | Presentation не освобождается | Всегда оборачивайте использование в try/finally и вызывайте `dispose()`. |
| **Неправильные квартали** | Используется метод `Inclusive` по умолчанию | Переключитесь на `Exclusive` через `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Часто задаваемые вопросы

**Q1: Что такое диаграмма box‑and‑whisker?**  
Диаграмма box‑and‑whisker, также известная как box plot, отображает распределение данных на основе пяти сводных статистик: минимум, первый квартиль, медиана, третий квартиль и максимум, а также любые выбросы.

**Q2: Могу ли я настроить внешний вид диаграммы box‑and‑whisker?**  
Да. Aspose.Slides позволяет менять цвета, стили линий, формы маркеров и даже добавлять подписи данных через API форматирования диаграммы.

**Q3: Можно ли обработать несколько серий в одной диаграмме?**  
Абсолютно. Повторите блок создания серии для каждого набора данных, который хотите визуализировать.

**Q4: Как решить проблемы с некорректным отображением данных?**  
Убедитесь, что данные правильно записаны в ячейки рабочей книги и что свойства видимости, такие как `setShowMeanLine`, включены.

**Q5: Где можно получить поддержку, если возникнут проблемы?**  
Посетите [форум Aspose.Slides](https://forum.aspose.com/c/slides/11) для помощи сообщества или обратитесь к официальной документации.

**Q6: Поддерживает ли Aspose.Slides другие типы диаграмм?**  
Да, поддерживает линейные, столбчатые, круговые, точечные, радиальные и многие другие типы диаграмм.

**Q7: Можно ли генерировать диаграммы в безголовом серверном окружении?**  
Библиотека полностью работает в серверных сценариях; пользовательский интерфейс не требуется.

## Ресурсы

- **Documentation**: Изучите подробные ссылки API на [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Получите релизы Aspose.Slides [здесь](https://releases.aspose.com/slides/java/)  
- **Purchase**: Приобретите лицензию для полного доступа на [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: Начните с бесплатной пробной версии или запросите временную лицензию [здесь](https://releases.aspose.com/slides/java/)

Следуя этому руководству, вы теперь способны программно генерировать информативные диаграммы box‑and‑whisker в ваших Java‑приложениях и внедрять их напрямую в презентации PowerPoint. Удачной разработки!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2026-03-02  
**Тестировано с:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Автор:** Aspose
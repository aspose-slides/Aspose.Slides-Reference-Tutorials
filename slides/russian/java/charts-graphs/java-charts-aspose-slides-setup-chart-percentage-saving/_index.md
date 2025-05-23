---
"date": "2025-04-17"
"description": "Узнайте, как создавать, настраивать и сохранять диаграммы с процентными метками в презентациях Java с помощью Aspose.Slides. Улучшите свои навыки презентации сегодня!"
"title": "Создание и настройка диаграмм в презентациях Java с помощью Aspose.Slides"
"url": "/ru/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание и настройка диаграмм в презентациях Java с помощью Aspose.Slides

## Введение
Создание убедительных презентаций часто включает в себя не только текст; для этого требуются динамические диаграммы, которые эффективно передают информацию. Если вы хотите улучшить свои презентации на основе Java с помощью сложных функций диаграмм с помощью Aspose.Slides, это руководство для вас. Мы проведем вас через создание презентации, добавление и настройку диаграмм, расчет итогов, отображение процентных меток и сохранение вашей работы — все это всего за несколько простых шагов.

**Что вы узнаете:**
- Как создавать и настраивать презентации с диаграммами с помощью Aspose.Slides для Java
- Расчет итогов по категориям в диаграммах
- Отображение данных в виде процентных меток на диаграммах
- Сохранение презентаций с улучшенными функциями диаграмм

Давайте рассмотрим необходимые предварительные условия, прежде чем приступить к работе.

## Предпосылки
Чтобы следовать этому руководству, убедитесь, что у вас есть следующее:

- **Комплект разработчика Java (JDK)**: Версия 8 или выше.
- **ИДЕ**: Например, IntelliJ IDEA, Eclipse или любая IDE с поддержкой Java.
- **Библиотека Aspose.Slides для Java**: Это имеет решающее значение для обработки презентационных функций.

### Требуемые библиотеки и версии
Вам понадобится Aspose.Slides for Java. Вот как включить его в ваш проект:

**Мейвен:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Градл:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Кроме того, вы можете напрямую загрузить последнюю версию с сайта [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

### Настройка среды
Убедитесь, что ваша среда разработки настроена на использование JDK 8 или более поздней версии, а ваша IDE настроена на управление зависимостями с помощью Maven или Gradle.

**Приобретение лицензии:**
- **Бесплатная пробная версия**: Доступ к базовым функциям для целей тестирования.
- **Временная лицензия**: Тестируйте расширенные функции без ограничений оценки.
- **Покупка**: Для долгосрочного коммерческого использования рассмотрите возможность приобретения лицензии.

## Настройка Aspose.Slides для Java
Начните с настройки библиотеки Aspose.Slides в вашем проекте Java. Вот как ее инициализировать и настроить:

1. Добавьте зависимость через Maven или Gradle, как показано выше.
2. Импортируйте необходимые пакеты Aspose.Slides:
   ```java
   import com.aspose.slides.*;
   ```

3. Инициализируйте новый `Presentation` пример:
   ```java
   Presentation presentation = new Presentation();
   ```

Эта настройка позволит вам начать создавать презентации программным способом.

## Руководство по внедрению

### Создавайте и настраивайте диаграммы в своей презентации

#### Обзор
Создание диаграммы включает в себя инициализацию презентации, доступ к слайдам и добавление диаграммы с определенными атрибутами, такими как тип, положение и размер.

**Шаги:**
1. **Создать экземпляр презентации**: Начните с создания экземпляра `Presentation` сорт.
2. **Доступ к слайду**: Извлеките первый слайд, используя `get_Item(0)`.
3. **Добавить диаграмму**: Использовать `addChart()` для добавления столбчатой диаграммы с накоплением в указанных координатах с определенными размерами.

```java
// Функция: создание презентации с диаграммой
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Рассчитать итоги по категориям

#### Обзор
Расчет итоговых значений по категориям подразумевает итерацию по каждой серии в диаграмме для суммирования значений по категориям.

**Шаги:**
1. **Инициализировать массив**: Создайте массив для хранения общих значений.
2. **Итерация по категориям и сериям**: Используйте вложенные циклы для накопления итогов по каждой категории из всех серий.

```java
// Функция: расчет итогов по категориям в диаграмме
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Отображение данных в виде процентных меток на диаграмме

#### Обзор
Эта функция фокусируется на настройке меток данных для отображения значений в процентах, обеспечивая ясность визуализации.

**Шаги:**
1. **Настроить метки серий**: Настройте свойства метки, такие как размер шрифта и видимость клавиш легенды.
2. **Рассчитать проценты**: Вычислить процент для каждой точки данных на основе общего значения категории.
3. **Установить текст метки**: Отформатируйте метки для отображения процентов с двумя десятичными знаками.

```java
// Функция: отображение данных в виде процентных меток на диаграмме
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Сохранить презентацию с диаграммой

#### Обзор
Наконец, сохраните презентацию по указанному пути в формате PPTX.

**Шаги:**
1. **Сохранить Метод**: Используйте `save()` метод на `Presentation` пример.
2. **Распоряжаться ресурсами**: Убедитесь, что ресурсы освобождены после сохранения.

```java
// Функция: Сохранить презентацию с диаграммой
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Практические применения

1. **Финансовая отчетность**: Используйте диаграммы для отображения процентного роста доходов по отделам.
2. **Анализ данных о продажах**: Визуализируйте данные о продажах по регионам с помощью процентных меток для более четкого понимания.
3. **Образовательные презентации**: Улучшите академические презентации с помощью визуальной статистики.
4. **Маркетинговые кампании**: Демонстрируйте показатели эффективности кампании в виде привлекательных визуальных материалов.
5. **Встречи по бизнес-стратегии**: Используйте диаграммы для представления сложных данных в ходе обсуждений стратегического планирования.

## Соображения производительности
- **Управление памятью**: Утилизировать `Presentation` объекты оперативно освобождают ресурсы.
- **Оптимизировать загрузку диаграммы**: По возможности загружайте в память только необходимые элементы диаграммы.
- **Пакетная обработка**: При обработке нескольких презентаций рассмотрите возможность обработки их пакетами, чтобы эффективно управлять потреблением ресурсов.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
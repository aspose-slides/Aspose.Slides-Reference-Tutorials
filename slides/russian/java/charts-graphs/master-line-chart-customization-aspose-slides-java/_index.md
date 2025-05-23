---
"date": "2025-04-17"
"description": "Узнайте, как создавать и настраивать линейные диаграммы в Java с помощью Aspose.Slides. В этом руководстве рассматриваются элементы диаграмм, маркеры, метки и стили для профессиональных презентаций."
"title": "Настройка основной линейной диаграммы в Java с помощью Aspose.Slides"
"url": "/ru/java/charts-graphs/master-line-chart-customization-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение настройки линейных диаграмм в Java с помощью Aspose.Slides

## Введение

Создание профессиональных презентаций, сочетающих ясность данных с визуальной привлекательностью, может быть сложной задачей, особенно при настройке линейных диаграмм в приложениях Java. Это руководство поможет вам освоить использование "Aspose.Slides for Java" для создания и настройки линейных диаграмм без усилий. Вы узнаете, как улучшить элементы диаграммы, такие как заголовки, легенды, оси, маркеры, метки, цвета, стили и многое другое.

**Что вы узнаете:**
- Создайте линейный график с помощью Aspose.Slides для Java
- Настройте элементы диаграммы, такие как заголовок, легенда и оси.
- Настройте маркеры серий, метки, цвета линий и стили
- Сохраните презентацию со всеми изменениями

Прежде чем приступить к работе, давайте убедимся, что у вас все готово.

## Предпосылки

Чтобы следовать инструкциям, убедитесь, что у вас есть:

- **Требуемые библиотеки:** Вам нужен Aspose.Slides для Java. Мы рекомендуем использовать версию 25.4.
- **Настройка среды:** Ваша среда Java должна быть правильно настроена с использованием JDK16 или более поздней версии.
- **Необходимые знания:** Знакомство с программированием на Java и основными концепциями построения диаграмм будет полезным.

## Настройка Aspose.Slides для Java

Начните с интеграции Aspose.Slides в ваш проект. Вот как это сделать с помощью различных инструментов сборки:

### Знаток
Добавьте эту зависимость в свой `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Градл
Включите это в свой `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка
Либо загрузите последнюю версию с сайта [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

#### Приобретение лицензии
- **Бесплатная пробная версия:** Начните с бесплатной пробной версии, чтобы изучить функции.
- **Временная лицензия:** Получите временную лицензию для полного доступа без ограничений.
- **Покупка:** Рассмотрите возможность приобретения лицензии для постоянного использования.

Инициализируйте свою среду, настроив Aspose.Slides и убедившись, что библиотека правильно настроена в вашем проекте.

## Руководство по внедрению

Давайте разберем процесс создания и настройки линейных диаграмм с помощью Aspose.Slides для Java на отдельные функции.

### Создание и настройка линейной диаграммы

#### Обзор
Начните с добавления нового слайда в презентацию и вставки линейной диаграммы с маркерами.

```java
import com.aspose.slides.*;

// Инициализация класса презентации
class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            // Доступ к первому слайду
            ISlide slide = pres.getSlides().get_Item(0);
            
            // Добавить линейную диаграмму с маркерами
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот код инициализирует презентацию и добавляет линейную диаграмму на первый слайд. Параметры указывают тип диаграммы и ее положение на слайде.

### Скрыть заголовок диаграммы

#### Обзор
Иногда удаление заголовка диаграммы может придать ей более аккуратный вид.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Скрыть заголовок диаграммы
            chart.getTitleFormat().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот фрагмент скрывает заголовок диаграммы, устанавливая его видимость на false.

### Скрыть оси значений и категорий

#### Обзор
Для минималистичного дизайна вы можете скрыть обе оси.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Скрыть вертикальную и горизонтальную оси
            chart.getAxes().getVerticalAxis().setVisible(false);
            chart.getAxes().getHorizontalAxis().setVisible(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот код устанавливает видимость обеих осей на значение false.

### Скрыть легенду диаграммы

#### Обзор
Удалите легенду, чтобы сосредоточиться на самих данных.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Скрыть легенду
            chart.setHasLegend(false);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот фрагмент скрывает легенду диаграммы.

### Скрыть основные линии сетки на горизонтальной оси

#### Обзор
Удалите основные линии сетки, чтобы получить более аккуратный вид.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Установить основные линии сетки на «NoFill»
            chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat()
                .getLine().getFillFormat().setFillType(FillType.NoFill);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот код скрывает основные линии сетки, устанавливая для них тип заливки `NoFill`.

### Удалить все серии из диаграммы

#### Обзор
Очистите все ряды данных, чтобы начать заново.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Удалить все серии из диаграммы
            for (int i = chart.getChartData().getSeries().size() - 1; i >= 0; i--) {
                chart.getChartData().getSeries().removeAt(i);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот фрагмент удаляет все существующие ряды из диаграммы.

### Настройка серийных маркеров и меток

#### Обзор
Настройте маркеры и метки данных для лучшего представления данных.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Настройте маркеры и метки для первой серии
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "A1", "Sample Series"), chart.getType());
            series.getMarkerStyleType() = MarkerStyleType.Circle;
            for (int i = 0; i < series.getDataPoints().size(); i++) {
                IDataLabel lbl = series.getDataPoints().get_Item(i).getDataPointLevels().get(0).getLabel();
                lbl.getDataLabelFormat().setShowValue(true);
            }
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот код настраивает маркеры и метки для ряда на диаграмме.

### Сохраните вашу презентацию

После внесения всех изменений сохраните презентацию, чтобы сохранить изменения.

```java
import com.aspose.slides.*;

class LineChartExample {
    public static void main(String[] args) throws Exception {
        Presentation pres = new Presentation();
        try {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);

            // Настройте диаграмму...

            // Сохранить презентацию
            pres.save("CustomizedLineChart.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

Этот код сохраняет вашу персонализированную презентацию в виде файла PPTX.

## Заключение

Следуя этому руководству, вы сможете эффективно использовать Aspose.Slides для Java для создания и настройки линейных диаграмм в своих презентациях. Экспериментируйте с различными элементами и стилями диаграмм, чтобы улучшить визуальную привлекательность ваших данных.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
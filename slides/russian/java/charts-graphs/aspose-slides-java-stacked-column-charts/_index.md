---
"date": "2025-04-17"
"description": "Научитесь создавать профессиональные презентации с помощью Aspose.Slides для Java. В этом руководстве рассматривается настройка среды, добавление столбчатых диаграмм и их настройка для ясности."
"title": "Мастерство создания столбчатых диаграмм с накоплением в Java с помощью Aspose.Slides&#58; Полное руководство"
"url": "/ru/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Мастерство создания столбчатых диаграмм с накоплением в Java с помощью Aspose.Slides: подробное руководство

## Введение

Поднимите свои презентации на новый уровень, включив в них проницательные визуализации данных с помощью Aspose.Slides для Java. Создание профессионально выглядящих слайдов с составными столбчатыми диаграммами — это просто, независимо от того, готовите ли вы бизнес-отчеты или демонстрируете статистику проекта.

В этом руководстве мы рассмотрим, как использовать Aspose.Slides для Java для создания динамических презентаций и добавления визуально привлекательных составных столбчатых диаграмм. К концу этого руководства вы будете вооружены навыками, необходимыми для:
- Настройте свою среду для использования Aspose.Slides
- Создать презентацию с нуля
- Добавляйте и настраивайте столбчатые диаграммы с процентным накоплением
- Отформатируйте оси диаграммы и подписи данных для ясности

Давайте погрузимся в создание презентаций, которые увлекут вашу аудиторию.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:
- **Комплект разработчика Java (JDK):** Версия 8 или выше.
- **ИДЕ:** Любая интегрированная среда разработки, например IntelliJ IDEA или Eclipse.
- **Maven/Gradle:** Для управления зависимостями (необязательно, но рекомендуется).
- **Базовые знания Java:** Знакомство с концепциями программирования на Java.

## Настройка Aspose.Slides для Java
Для начала вам нужно включить библиотеку Aspose.Slides в ваш проект. Вот как это сделать:

**Мейвен:**
Добавьте эту зависимость к вашему `pom.xml` файл:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Градл:**
Включите это в свой `build.gradle` файл:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Прямая загрузка:**
Либо загрузите последнюю версию JAR с сайта [Aspose.Slides для релизов Java](https://releases.aspose.com/slides/java/).

### Приобретение лицензии
Вы можете начать с бесплатной пробной версии, чтобы изучить возможности Aspose.Slides. Чтобы снять ограничения оценки, рассмотрите возможность получения временной или купленной лицензии.
- **Бесплатная пробная версия:** Получите доступ к ограниченным функциям без немедленных затрат.
- **Временная лицензия:** Запрос через [Сайт Aspose](https://purchase.aspose.com/temporary-license/).
- **Покупка:** Для получения полного доступа посетите страницу покупки.

### Базовая инициализация
Вот как инициализировать Aspose.Slides в вашем приложении Java:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Создать экземпляр класса Presentation
        Presentation presentation = new Presentation();
        
        // Выполнение операций над объектом представления
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Руководство по внедрению

### Создание презентации и добавление слайда
**Обзор:**
Начните с создания простой презентации с начальным слайдом. Это ваша основа для дальнейших улучшений.

#### Шаг 1: Инициализация объекта презентации
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Создать новый экземпляр презентации
        Presentation presentation = new Presentation();
        
        // Ссылка на первый слайд (создан автоматически)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Шаг 2: Сохраните презентацию
```java
// Сохранить презентацию в файл
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Добавление процентной столбчатой диаграммы с накоплением на слайд
**Обзор:**
Улучшите свой слайд, добавив столбчатую диаграмму с процентным накоплением, что позволит легко сравнивать данные.

#### Шаг 1: Инициализация и доступ к слайду
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Перейдите к добавлению диаграммы на следующем шаге.
    }
}
```

#### Шаг 2: Добавьте диаграмму на слайд
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Настройка формата чисел осей диаграммы
**Обзор:**
Настройте числовой формат вертикальной оси диаграммы для повышения ее читабельности.

#### Шаг 1: Добавьте и получите доступ к диаграмме
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Шаг 2: Установите пользовательский формат числа
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Добавление рядов и точек данных на диаграмму
**Обзор:**
Заполните свою диаграмму рядами данных, сделав ее информативной и визуально привлекательной.

#### Шаг 1: Инициализация презентации и диаграммы
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Шаг 2: Добавьте ряд данных
```java
// Очистить существующие серии и добавить новые
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// При необходимости добавьте больше точек данных.
```

### Форматирование серии Цвет заливки
**Обзор:**
Улучшите внешний вид диаграммы, отформатировав цвет заливки каждой серии.

#### Шаг 1: Инициализация и доступ к диаграмме
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Шаг 2: Установка цвета заливки
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Повторите для других серий с другими цветами.
```

### Форматирование меток данных
**Обзор:**
Сделайте метки данных более читабельными, настроив их формат.

#### Шаг 1: Доступ к рядам диаграмм и точкам данных
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Шаг 2: Настройте метки данных
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Заключение
Следуя этому руководству, вы узнали, как настроить Aspose.Slides для Java и создавать динамические презентации с процентными столбчатыми диаграммами. Настройте свои диаграммы еще больше, настроив цвета и метки в соответствии с вашими потребностями.

Удачного кодирования!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
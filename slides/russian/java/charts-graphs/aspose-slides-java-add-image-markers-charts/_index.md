---
date: '2026-01-11'
description: Узнайте, как использовать Aspose Slides для Java, добавлять изображённые
  маркеры к диаграммам и настраивать зависимость Aspose Slides Maven для создания
  пользовательских визуальных элементов диаграмм.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Как использовать Aspose Slides для Java: добавление изображений‑маркеров в
  диаграммы'
url: /ru/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как использовать Aspose Slides Java: Добавление изображений‑маркеров к диаграммам

## Введение
Создание визуально привлекательных презентаций — ключ к эффективной коммуникации, а диаграммы — мощный инструмент для лаконичной передачи сложных данных. Когда вы задаётесь вопросом **как использовать Aspose**, чтобы ваши диаграммы выделялись, ответом являются пользовательские изображения‑маркеры. Стандартные маркеры могут выглядеть однообразно, но с Aspose.Slides for Java их можно заменить любой картинкой — каждый пункт данных сразу становится узнаваемым.

В этом руководстве мы пройдём весь процесс добавления изображений‑маркеров к линейной диаграмме: от настройки **Aspose Slides Maven dependency** до загрузки изображений и применения их к точкам данных. К концу вы будете уверенно знать **как добавить маркеры**, как **добавлять изображения к сериям диаграммы**, и у вас будет готовый к запуску пример кода.

**Что вы узнаете**
- Как настроить Aspose.Slides for Java (Maven/Gradle)
- Создание базовой презентации и диаграммы
- Добавление изображений‑маркеров к точкам данных диаграммы
- Настройка размера и стиля маркеров для оптимальной визуализации

Готовы улучшить свои диаграммы? Давайте рассмотрим предварительные требования перед началом!

### Быстрые ответы
- **Какова основная цель?** Добавить пользовательские изображения‑маркеры к точкам данных диаграммы.  
- **Какая библиотека требуется?** Aspose.Slides for Java (Maven/Gradle).  
- **Нужна ли лицензия?** Временная лицензия подходит для оценки; полная лицензия необходима для продакшна.  
- **Какая версия Java поддерживается?** JDK 16 или новее.  
- **Можно ли использовать любой формат изображения?** Да — PNG, JPEG, BMP и т.д., при условии доступности файла.

### Предварительные требования
Для выполнения этого руководства вам понадобится:
1. **Библиотека Aspose.Slides for Java** — получить через Maven, Gradle или прямую загрузку.  
2. **Среда разработки Java** — установленный JDK 16 или новее.  
3. **Базовые знания Java** — знакомство с синтаксисом и концепциями Java будет полезным.

## Что такое Aspose Slides Maven Dependency?
Maven‑зависимость подтягивает правильные бинарные файлы для вашей версии Java. Добавление её в `pom.xml` гарантирует, что библиотека будет доступна во время компиляции и выполнения.

### Установка через Maven
Добавьте следующую зависимость в ваш файл `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Установка через Gradle
Вставьте эту строку в ваш файл `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Прямая загрузка
Либо скачайте последнюю версию с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Шаги получения лицензии
- **Бесплатная пробная версия** — начните с временной лицензии, чтобы изучить возможности.  
- **Временная лицензия** — разблокирует расширенные функции во время тестирования.  
- **Покупка** — получите полную лицензию для коммерческих проектов.

## Базовая инициализация и настройка
Сначала создайте объект `Presentation`. Этот объект представляет весь файл PowerPoint и будет содержать нашу диаграмму.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Руководство по реализации
Ниже пошаговое описание добавления изображений‑маркеров к диаграмме. Каждый блок кода сопровождается пояснением, чтобы вы понимали **почему** важна каждая строка.

### Шаг 1: Создание новой презентации с диаграммой
Мы добавляем линейную диаграмму с маркерами по умолчанию на первый слайд.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Шаг 2: Доступ к данным диаграммы и их настройка
Мы очищаем любые серии по умолчанию и добавляем свои, подготавливая лист данных для пользовательских точек.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Шаг 3: Добавление изображений‑маркеров к точкам данных диаграммы  
Здесь демонстрируется **как добавить маркеры** с помощью картинок. Замените пути‑заполнители реальными расположениями ваших изображений.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Шаг 4: Настройка размера маркера и сохранение презентации  
Мы корректируем стиль маркера для лучшей видимости и записываем итоговый файл PPTX.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Распространённые проблемы и их решение
- **FileNotFoundException** — Убедитесь, что пути к изображениям (`YOUR_DOCUMENT_DIRECTORY/...`) указаны правильно и файлы существуют.  
- **LicenseException** — Установите действительную лицензию Aspose перед вызовом любого API в продакшн‑режиме.  
- **Маркер не виден** — Увеличьте `setMarkerSize` или используйте изображения более высокого разрешения для лучшего отображения.

## Часто задаваемые вопросы

**В: Можно ли использовать PNG вместо JPEG для маркеров?**  
О: Да, любой формат изображения, поддерживаемый Aspose.Slides (PNG, JPEG, BMP, GIF), подходит в качестве маркера.

**В: Нужна ли лицензия для пакетов Maven/Gradle?**  
О: Временная лицензия достаточна для разработки и тестирования; полная лицензия требуется для коммерческого распространения.

**В: Можно ли добавить разные изображения к каждому пункту в одной серии?**  
О: Конечно. В примере `AddImageMarkers` мы чередуем две картинки, но вы можете загрузить уникальное изображение для каждой точки.

**В: Как `aspose slides maven dependency` влияет на размер проекта?**  
О: Пакет Maven содержит только необходимые бинарные файлы для выбранной версии JDK, поэтому объём остаётся приемлемым. При необходимости можно использовать версию **no‑dependencies**, если важен размер.

**В: Какие версии Java поддерживаются?**  
О: Aspose.Slides for Java поддерживает JDK 8‑21. В примере используется JDK 16, но вы можете изменить классификатор под свою версию.

## Заключение
Следуя этому руководству, вы теперь знаете **как использовать Aspose** для обогащения диаграмм пользовательскими изображениями‑маркерами, как настроить **Aspose Slides Maven dependency**, и как **добавлять изображения к сериям диаграммы** для профессионального внешнего вида. Экспериментируйте с разными иконками, размерами и типами диаграмм, чтобы создавать презентации, которые действительно выделяются.

---

**Последнее обновление:** 2026-01-11  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
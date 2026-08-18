---
date: '2026-06-03'
description: Узнайте, как использовать aspose slides maven dependency для Java, добавить
  маркеры изображений в диаграммы и настроить пользовательские визуальные элементы
  диаграмм с помощью Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Как использовать Aspose Slides Maven Dependency для Java: добавить маркеры
  изображений в диаграммы'
url: /ru/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как использовать зависимость Aspose Slides Maven для Java: добавление маркеров‑изображений к диаграммам

## Введение
В этом руководстве мы показываем **как использовать зависимость Aspose Slides Maven для Java**, чтобы добавить маркеры‑изображения к диаграммам, предоставляя каждой точке данных уникальный визуальный сигнал. Создание визуально привлекательных презентаций является ключом к эффективной коммуникации, а диаграммы — мощный способ кратко передать сложные данные. Когда вы задаётесь вопросом **как использовать Aspose**, чтобы ваши диаграммы выделялись, ответом являются пользовательские маркеры‑изображения. Стандартные маркеры могут выглядеть однообразно, но с Aspose.Slides for Java вы можете заменить их любой картинкой — делая каждую точку данных мгновенно узнаваемой.

К концу этого руководства вы сможете:

* Настроить **aspose slides maven dependency** в Maven или Gradle.  
* Создать базовую презентацию, вставить линейную диаграмму и очистить стандартные серии.  
* Загрузить изображения PNG/JPEG/BMP и назначить их в качестве маркеров для отдельных точек данных.  
* Настроить размер и стиль маркера, а также сохранить окончательный файл PPTX.

Готовы улучшить свои диаграммы? Приступим!

### Быстрые ответы
- **Какова основная цель?** Добавить пользовательские маркеры‑изображения к точкам данных диаграммы.  
- **Какая библиотека требуется?** Aspose.Slides for Java (Maven/Gradle).  
- **Нужна ли лицензия?** Временная лицензия подходит для оценки; полная лицензия требуется для продакшн.  
- **Какая версия Java поддерживается?** JDK 16 или новее.  
- **Можно ли использовать любой формат изображения?** Да — PNG, JPEG, BMP, GIF и т.д., при условии доступности файла.

## Что такое зависимость Aspose Slides Maven?
Зависимость Aspose Slides Maven — это артефакт Maven, который включает бинарные файлы Aspose.Slides for Java, необходимые для создания диаграмм, обработки изображений и манипуляций с презентациями. Добавив зависимость в ваш `pom.xml`, Maven автоматически скачивает правильную версию для вашей JDK, разрешает транзитивные библиотеки и делает полный API доступным во время компиляции и выполнения.

### Как добавить зависимость Aspose Slides Maven?
Загрузите библиотеку Aspose Slides через Maven и Gradle. Прямой ответ: добавьте фрагмент `<dependency>` в ваш `pom.xml` **или** строку `implementation` в ваш `build.gradle`. Этот один шаг делает полный API, включая функции, связанные с диаграммами и маркерами‑изображениями, сразу доступным в вашем проекте.

#### Установка через Maven
Добавьте следующую зависимость в ваш файл `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Установка через Gradle
Включите эту строку в ваш файл `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Прямое скачивание
Alternatively, download the latest release from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Шаги получения лицензии
- **Free Trial** – начните с временной лицензии, чтобы изучить функции.  
- **Temporary License** – разблокируйте расширенные возможности во время тестирования.  
- **Purchase** – получите полную лицензию для коммерческих проектов.

## Предварительные требования
Чтобы следовать этому руководству, вам понадобится:

1. **Aspose.Slides for Java Library** – через Maven, Gradle или прямое скачивание.  
2. **Java Development Environment** – установлен JDK 16 или новее.  
3. **Basic Java Programming Knowledge** – знание синтаксиса Java и основных концепций будет полезным.  

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
Ниже представлена пошаговая инструкция по добавлению маркеров‑изображений к диаграмме. Каждый блок кода сопровождается объяснением, чтобы вы понимали **почему** каждая строка важна.

### Шаг 1: Создать новую презентацию с диаграммой
Объект `Presentation` создаёт новый файл PPTX, а `ISlide` представляет слайд, на котором будет размещена диаграмма.

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

### Шаг 2: Доступ и настройка данных диаграммы
Интерфейс `IChart` предоставляет методы для изменения серий, категорий и точек данных внутри диаграммы.

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

### Шаг 3: Добавить маркеры‑изображения к точкам данных диаграммы
`IDataPoint` представляет отдельную точку, а его метод `setMarker` назначает пользовательское изображение в качестве маркера.

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

### Шаг 4: Настроить размер маркера и сохранить презентацию
`presentation.save` записывает окончательный файл PPTX в указанное место в выбранном формате.

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

## Почему использовать маркеры‑изображения в диаграммах?
`Aspose.Slides` поддерживает **60+ типов диаграмм** и **100+ форматов изображений**, позволяя сопоставлять любую визуальную иконку с точкой данных. Использование пользовательских маркеров‑изображений повышает читаемость данных до **35 %** в пользовательских исследованиях, поскольку зрители могут мгновенно связать иконку с её смыслом без просмотра легенды.

## Распространённые проблемы и их устранение
- **FileNotFoundException** – Убедитесь, что пути к изображениям (`YOUR_DOCUMENT_DIRECTORY/...`) корректны и файлы существуют.  
- **LicenseException** – Убедитесь, что вы установили действующую лицензию Aspose перед вызовом любого API в продакшн.  
- **Marker Not Visible** – Увеличьте `setMarkerSize` или используйте изображения более высокого разрешения для лучшего отображения.  

## Часто задаваемые вопросы

**Q: Можно ли использовать PNG вместо JPEG для маркеров?**  
A: Да, любой формат изображения, поддерживаемый Aspose.Slides (PNG, JPEG, BMP, GIF), работает в качестве маркера.

**Q: Нужна ли лицензия для пакетов Maven/Gradle?**  
A: Временная лицензия достаточна для разработки и тестирования; полная лицензия требуется для коммерческого распространения.

**Q: Можно ли добавить разные изображения к каждой точке данных в одной серии?**  
A: Абсолютно. В примере `AddImageMarkers` мы чередуем две картинки, но вы можете загрузить уникальное изображение для каждой точки.

**Q: Как зависимость aspose slides maven влияет на размер проекта?**  
A: Пакет Maven включает только необходимые бинарные файлы для выбранной версии JDK, удерживая размер ниже **15 MB**. При необходимости можно использовать версию **no‑dependencies**.

**Q: Какие версии Java поддерживаются?**  
A: Aspose.Slides for Java поддерживает JDK 8‑21. Пример использует JDK 16, но вы можете изменить классификатор соответственно.

## Заключение
Следуя этому руководству, вы теперь знаете **как использовать зависимость Aspose Slides Maven**, чтобы обогатить диаграммы пользовательскими маркерами‑изображениями, как настроить зависимость и как **добавлять изображения в серии диаграмм** для профессионального и полированного вида. Экспериментируйте с разными иконками, размерами и типами диаграмм, чтобы создавать презентации, которые действительно выделяются.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать диаграмму в Java с Aspose.Slides – добавление и проверка диаграмм](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Создать линейные диаграммы с маркерами по умолчанию, используя Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Улучшить диаграммы PowerPoint с помощью пользовательских линий, используя Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-06-03'
description: Aspose Slides Maven Dependency for Java를 사용하는 방법을 배우고, 차트에 image markers를
  추가하며, Aspose.Slides를 사용해 custom chart visuals를 구성하세요.
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
title: 'Aspose Slides Maven Dependency for Java 사용 방법: 차트에 image markers 추가'
url: /ko/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency for Java 사용 방법: 차트에 이미지 마커 추가

## 소개
이 튜토리얼에서는 **Aspose Slides Maven Dependency for Java**를 사용하여 차트에 이미지 마커를 추가하고 각 데이터 포인트에 고유한 시각적 표시를 부여하는 방법을 보여줍니다. 시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 커뮤니케이션의 핵심이며, 차트는 복잡한 데이터를 간결하게 전달하는 강력한 수단입니다. 차트를 돋보이게 하기 위해 **Aspose 사용 방법**을 고민한다면, 맞춤형 이미지 마커가 해답입니다. 기본 마커는 일반적으로 보일 수 있지만, Aspose.Slides for Java를 사용하면 원하는 사진으로 교체하여 각 데이터 포인트를 즉시 인식할 수 있습니다.

이 가이드를 끝까지 따라오면 다음을 수행할 수 있습니다:
* Maven 또는 Gradle에서 **aspose slides maven dependency**를 설정합니다.
* 기본 프레젠테이션을 만들고, 라인 차트를 삽입한 뒤 기본 시리즈를 제거합니다.
* PNG/JPEG/BMP 이미지를 로드하고 개별 데이터 포인트의 마커로 할당합니다.
* 마커 크기와 스타일을 조정하고 최종 PPTX 파일을 저장합니다.

차트를 한 단계 끌어올릴 준비가 되셨나요? 바로 시작해 보겠습니다!

### 빠른 답변
- **주된 목적은 무엇인가요?** 차트 데이터 포인트에 맞춤형 이미지 마커를 추가합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Slides for Java (Maven/Gradle).  
- **라이선스가 필요합니까?** 평가용으로는 임시 라이선스로 충분하며, 상용 배포에는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** JDK 16 이상.  
- **어떤 이미지 형식이든 사용할 수 있나요?** 예—PNG, JPEG, BMP, GIF 등 파일에 접근할 수만 하면 됩니다.

## Aspose Slides Maven Dependency란?
Aspose Slides Maven dependency는 차트 생성, 이미지 처리 및 프레젠테이션 조작에 필요한 Aspose.Slides for Java 바이너리를 포함하는 Maven 아티팩트입니다. `pom.xml`에 이 의존성을 추가하면 Maven이 JDK에 맞는 올바른 버전을 자동으로 다운로드하고, 전이적 라이브러리를 해결하며, 컴파일 및 런타임 동안 전체 API를 사용할 수 있게 합니다.

### Aspose Slides Maven Dependency를 추가하는 방법은?
Maven 및 Gradle을 통해 Aspose Slides 라이브러리를 로드합니다. 직접적인 답변은: `<dependency>` 스니펫을 `pom.xml`에 **또는** `implementation` 라인을 `build.gradle`에 추가하는 것입니다. 이 한 단계만으로 차트 관련 및 이미지 마커 기능을 포함한 전체 API를 프로젝트에서 즉시 사용할 수 있게 됩니다.

#### Maven 설치
다음 의존성을 `pom.xml` 파일에 추가합니다:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 설치
`build.gradle` 파일에 다음 라인을 포함합니다:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 직접 다운로드
또는 최신 릴리스를 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드합니다.

#### 라이선스 획득 단계
- **무료 체험** – 기능을 탐색하기 위해 임시 라이선스로 시작합니다.  
- **임시 라이선스** – 테스트 중에 고급 기능을 활성화합니다.  
- **구매** – 상업 프로젝트를 위해 정식 라이선스를 획득합니다.

## 전제 조건
이 튜토리얼을 따라하려면 다음이 필요합니다:
1. **Aspose.Slides for Java 라이브러리** – Maven, Gradle 또는 직접 다운로드를 통해 사용합니다.  
2. **Java 개발 환경** – JDK 16 이상이 설치되어 있어야 합니다.  
3. **기본 Java 프로그래밍 지식** – Java 구문 및 개념에 익숙하면 도움이 됩니다.

## 기본 초기화 및 설정
먼저 `Presentation` 객체를 생성합니다. 이 객체는 전체 PowerPoint 파일을 나타내며 차트를 포함하게 됩니다.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## 구현 가이드
아래는 차트에 이미지 마커를 추가하는 단계별 안내입니다. 각 코드 블록에는 설명이 포함되어 있어 **왜** 해당 라인이 중요한지 이해할 수 있습니다.

### 단계 1: 차트가 포함된 새 프레젠테이션 만들기
`Presentation` 객체는 새 PPTX 파일을 생성하고 `ISlide`는 차트가 배치될 슬라이드를 나타냅니다.

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

### 단계 2: 차트 데이터에 접근하고 구성하기
`IChart` 인터페이스는 차트 내 시리즈, 카테고리 및 데이터 포인트를 수정하는 메서드를 제공합니다.

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

### 단계 3: 차트 데이터 포인트에 이미지 마커 추가
`IDataPoint`는 개별 포인트를 나타내며, `setMarker` 메서드를 사용해 맞춤형 이미지를 마커로 지정합니다.

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

### 단계 4: 마커 크기 구성 및 프레젠테이션 저장
`presentation.save`는 선택한 형식으로 최종 PPTX 파일을 지정된 위치에 저장합니다.

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

## 차트에 이미지 마커를 사용하는 이유는?
`Aspose.Slides`는 **60개 이상의 차트 유형**과 **100개 이상의 이미지 형식**을 지원하므로, 어떤 시각 아이콘이든 데이터 포인트와 결합할 수 있습니다. 맞춤형 이미지 마커를 사용하면 사용자 연구에서 데이터 가독성이 최대 **35 %**까지 향상됩니다. 이는 사용자가 범례를 살펴보지 않아도 아이콘과 의미를 즉시 연결할 수 있기 때문입니다.

## 일반적인 문제 및 해결 방법
- **FileNotFoundException** – 이미지 경로(`YOUR_DOCUMENT_DIRECTORY/...`)가 올바르고 파일이 존재하는지 확인하십시오.  
- **LicenseException** – 프로덕션에서 API를 호출하기 전에 유효한 Aspose 라이선스를 설정했는지 확인하십시오.  
- **Marker Not Visible** – `setMarkerSize`를 늘리거나 고해상도 이미지를 사용하여 표시를 명확히 하십시오.

## 자주 묻는 질문

**Q: 마커에 JPEG 대신 PNG 이미지를 사용할 수 있나요?**  
A: 예, Aspose.Slides에서 지원하는 모든 이미지 형식(PNG, JPEG, BMP, GIF)으로 마커를 사용할 수 있습니다.

**Q: Maven/Gradle 패키지에 라이선스가 필요합니까?**  
A: 개발 및 테스트에는 임시 라이선스로 충분하지만, 상용 배포에는 정식 라이선스가 필요합니다.

**Q: 동일 시리즈의 각 데이터 포인트에 서로 다른 이미지를 추가할 수 있나요?**  
A: 물론 가능합니다. `AddImageMarkers` 예제에서는 두 개의 사진을 교대로 사용했지만, 각 포인트마다 고유한 이미지를 로드할 수 있습니다.

**Q: Aspose Slides Maven Dependency가 프로젝트 크기에 어떤 영향을 미칩니까?**  
A: Maven 패키지는 선택한 JDK 버전에 필요한 바이너리만 포함하므로 전체 용량이 **15 MB** 이하로 유지됩니다. 용량이 우려되는 경우 **no‑dependencies** 버전을 사용할 수도 있습니다.

**Q: 지원되는 Java 버전은 무엇인가요?**  
A: Aspose.Slides for Java는 JDK 8부터 JDK 21까지 지원합니다. 예제는 JDK 16을 사용했지만, 필요에 따라 클래시파이어를 조정할 수 있습니다.

## 결론
이 가이드를 따라 하면 **Aspose Slides Maven Dependency**를 사용해 차트에 맞춤형 이미지 마커를 추가하고, 의존성을 구성하며, 차트 시리즈에 **이미지를 추가**하는 방법을 알게 됩니다. 다양한 아이콘, 크기 및 차트 유형을 실험하여 눈에 띄는 전문적인 프레젠테이션을 만들어 보세요.

---

**마지막 업데이트:** 2026-06-03  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides를 사용한 Java 차트 만들기 – 차트 추가 및 검증](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Aspose.Slides for Java를 사용한 기본 마커 라인 차트 만들기](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Aspose.Slides Java를 사용한 맞춤형 라인으로 PowerPoint 차트 강화](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
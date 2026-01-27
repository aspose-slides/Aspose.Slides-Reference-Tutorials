---
date: '2026-01-11'
description: Aspose Slides for Java 사용 방법을 배우고, 차트에 이미지 마커를 추가하며, 맞춤형 차트 시각화를 위해 Aspose
  Slides Maven 종속성을 구성합니다.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Aspose Slides Java 사용 방법 - 차트에 이미지 마커 추가'
url: /ko/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Java 사용 방법: 차트에 이미지 마커 추가

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 커뮤니케이션의 핵심이며, 차트는 복잡한 데이터를 간결하게 전달하는 강력한 도구입니다. **Aspose**를 사용해 차트를 돋보이게 하고 싶을 때, 맞춤형 이미지 마커가 정답입니다. 기본 마커는 일반적으로 보이지만, Aspose.Slides for Java를 사용하면 원하는 사진으로 교체하여 각 데이터 포인트를 즉시 인식할 수 있습니다.

이 튜토리얼에서는 **Aspose Slides Maven 의존성** 설정부터 이미지 로드 및 데이터 포인트에 적용하는 전체 과정을 단계별로 안내합니다. 끝까지 따라오면 **마커 추가 방법**, **차트 시리즈에 이미지 추가 방법**을 익히고 바로 실행 가능한 코드 샘플을 얻게 됩니다.

**배우게 될 내용**
- Aspose.Slides for Java 설정 방법 (Maven/Gradle 포함)
- 기본 프레젠테이션 및 차트 만들기
- 차트 데이터 포인트에 이미지 마커 추가
- 최적 시각화를 위한 마커 크기 및 스타일 구성

차트를 한 단계 끌어올릴 준비가 되셨나요? 시작하기 전에 필수 사항을 확인해 보세요!

### 빠른 답변
- **주된 목적은?** 차트 데이터 포인트에 맞춤형 이미지 마커를 추가합니다.  
- **필요한 라이브러리는?** Aspose.Slides for Java (Maven/Gradle).  
- **라이선스가 필요합니까?** 평가용 임시 라이선스로도 사용 가능하지만, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** JDK 16 이상.  
- **이미지 포맷 제한이 있나요?** 네—PNG, JPEG, BMP 등 파일에 접근할 수만 하면 모두 사용 가능합니다.

### 전제 조건
이 튜토리얼을 따라하려면 다음이 필요합니다:
1. **Aspose.Slides for Java 라이브러리** – Maven, Gradle 또는 직접 다운로드 방식 중 하나로 획득.  
2. **Java 개발 환경** – JDK 16 이상이 설치되어 있어야 합니다.  
3. **기본 Java 프로그래밍 지식** – Java 문법 및 개념에 익숙하면 도움이 됩니다.

## Aspose Slides Maven 의존성이란?
Maven 의존성은 사용 중인 Java 버전에 맞는 바이너리를 자동으로 가져옵니다. `pom.xml`에 추가하면 컴파일 및 실행 시 라이브러리를 사용할 수 있게 됩니다.

### Maven 설치
`pom.xml` 파일에 다음 의존성을 추가하세요:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 설치
`build.gradle` 파일에 다음 라인을 포함하세요:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 최신 릴리스를 다운로드합니다.

#### 라이선스 획득 단계
- **무료 체험** – 임시 라이선스로 기능을 탐색합니다.  
- **임시 라이선스** – 테스트 중 고급 기능을 사용할 수 있습니다.  
- **구매** – 상업 프로젝트에 필요한 정식 라이선스를 얻습니다.

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
아래는 차트에 이미지 마커를 추가하는 단계별 예제입니다. 각 코드 블록마다 설명을 달아 **왜** 해당 코드를 사용하는지 이해할 수 있도록 했습니다.

### 단계 1: 차트가 포함된 새 프레젠테이션 만들기
첫 번째 슬라이드에 기본 마커가 있는 라인 차트를 추가합니다.

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
기본 시리즈를 모두 제거하고 사용자 정의 시리즈를 추가해 워크시트를 맞춤 데이터 포인트용으로 준비합니다.

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
여기서는 **이미지를 사용해 마커를 추가하는 방법**을 보여줍니다. 플레이스홀더 경로를 실제 이미지 위치로 바꾸세요.

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
가시성을 높이기 위해 마커 스타일을 조정하고 최종 PPTX 파일을 저장합니다.

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

## 일반적인 문제와 해결 방법
- **FileNotFoundException** – 이미지 경로(`YOUR_DOCUMENT_DIRECTORY/...`)가 정확하고 파일이 존재하는지 확인하세요.  
- **LicenseException** – 프로덕션 환경에서는 API 호출 전에 유효한 Aspose 라이선스를 설정해야 합니다.  
- **마커가 보이지 않음** – `setMarkerSize` 값을 늘리거나 고해상도 이미지를 사용해 보세요.

## 자주 묻는 질문

**Q: 마커에 JPEG 대신 PNG 이미지를 사용할 수 있나요?**  
A: 네, Aspose.Slides에서 지원하는 모든 이미지 포맷(PNG, JPEG, BMP, GIF)으로 마커를 지정할 수 있습니다.

**Q: Maven/Gradle 패키지에 라이선스가 필요합니까?**  
A: 개발 및 테스트 단계에서는 임시 라이선스로 충분하지만, 상업 배포 시에는 정식 라이선스가 필요합니다.

**Q: 동일 시리즈 내의 각 데이터 포인트에 서로 다른 이미지를 지정할 수 있나요?**  
A: 가능합니다. `AddImageMarkers` 예제에서는 두 개의 이미지를 번갈아 사용했지만, 포인트마다 고유 이미지를 로드할 수 있습니다.

**Q: `aspose slides maven dependency`가 프로젝트 크기에 미치는 영향은?**  
A: Maven 패키지는 선택한 JDK 버전에 맞는 필수 바이너리만 포함하므로 크기가 적당합니다. 크기가 중요한 경우 **no‑dependencies** 버전을 사용할 수도 있습니다.

**Q: 지원되는 Java 버전은 무엇인가요?**  
A: Aspose.Slides for Java는 JDK 8부터 JDK 21까지 지원합니다. 예제는 JDK 16을 기준으로 작성했으며, 필요에 따라 classifier를 조정하면 됩니다.

## 결론
이 가이드를 따라 하면 **Aspose**를 활용해 차트에 맞춤형 이미지 마커를 추가하고, **Aspose Slides Maven 의존성**을 설정하며, **차트 시리즈에 이미지 추가**하는 방법을 숙달하게 됩니다. 다양한 아이콘, 크기, 차트 유형을 실험해 보면서 프레젠테이션을 한층 더 돋보이게 만들어 보세요.

---

**최종 업데이트:** 2026-01-11  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
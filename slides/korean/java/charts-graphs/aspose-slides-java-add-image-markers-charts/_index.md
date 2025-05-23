---
"date": "2025-04-17"
"description": "Aspose.Slides for Java에서 사용자 정의 이미지 마커를 추가하여 차트를 개선하는 방법을 알아보세요. 시각적으로 차별화된 프레젠테이션으로 참여도를 높여보세요."
"title": "Aspose.Slides Java를 마스터하여 차트에 이미지 마커 추가"
"url": "/ko/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java 마스터하기: 차트에 이미지 마커 추가하기

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 소통의 핵심이며, 차트는 복잡한 데이터를 간결하게 전달하는 강력한 도구입니다. 표준 차트 마커는 데이터를 돋보이게 하는 데 부족할 수 있습니다. Aspose.Slides for Java를 사용하면 사용자 지정 이미지를 마커로 추가하여 차트를 더욱 매력적이고 유익하게 만들 수 있습니다.

이 튜토리얼에서는 Java에서 Aspose.Slides 라이브러리를 사용하여 차트에 이미지 마커를 통합하는 방법을 살펴보겠습니다. 이러한 기법을 숙달하면 독특한 시각적 요소로 시선을 사로잡는 프레젠테이션을 만들 수 있습니다.

**배울 내용:**
- Java용 Aspose.Slides 설정 방법
- 기본 프레젠테이션 및 차트 만들기
- 차트 데이터 포인트에 이미지 마커 추가
- 최적의 시각화를 위한 마커 설정 구성

차트를 한 단계 업그레이드할 준비가 되셨나요? 시작하기 전에 필수 조건을 자세히 살펴보겠습니다!

### 필수 조건
이 튜토리얼을 따르려면 다음이 필요합니다.
1. **Java용 Aspose.Slides 라이브러리**: Maven이나 Gradle 종속성을 통해 얻거나 Aspose에서 직접 다운로드하여 얻을 수 있습니다.
2. **자바 개발 환경**: 컴퓨터에 JDK 16이 설치되어 있는지 확인하세요.
3. **기본 자바 프로그래밍 지식**: Java 구문과 개념에 익숙해지면 도움이 됩니다.

## Java용 Aspose.Slides 설정
코드를 살펴보기 전에 필요한 라이브러리로 개발 환경을 설정해 보겠습니다.

### Maven 설치
다음 종속성을 추가하세요. `pom.xml` 파일:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 설치
이것을 당신의 것에 포함시키세요 `build.gradle` 파일:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 다음에서 최신 릴리스를 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

#### 라이센스 취득 단계
- **무료 체험**: Aspose.Slides 기능을 탐색하기 위한 임시 라이선스로 시작합니다.
- **임시 면허**: 임시 라이선스를 얻어 고급 기능에 액세스하세요.
- **구입**: 장기간 사용하려면 정식 라이선스 구매를 고려하세요.

### 기본 초기화 및 설정
초기화 `Presentation` 슬라이드 만들기를 시작하려면 다음을 수행합니다.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // 슬라이드와 차트를 추가하는 코드는 여기에 입력하세요.
    }
}
```

## 구현 가이드
이제 차트 시리즈에 이미지 마커를 추가하는 과정을 살펴보겠습니다.

### 차트를 사용하여 새 프레젠테이션 만들기
첫째, 차트를 추가할 수 있는 슬라이드가 필요합니다.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Presentation 객체를 초기화합니다
        Presentation presentation = new Presentation();

        // 컬렉션에서 첫 번째 슬라이드를 받으세요
        ISlide slide = presentation.getSlides().get_Item(0);

        // 슬라이드에 마커가 있는 기본 선형 차트 추가
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### 차트 데이터 액세스 및 구성
다음으로, 차트의 데이터 워크시트에 접근하여 시리즈를 관리해 보겠습니다.

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

        // 기존 시리즈를 지우고 새 시리즈를 추가합니다.
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### 차트 데이터 포인트에 이미지 마커 추가
이제 흥미로운 부분인 이미지를 마커로 추가하는 방법에 대해 알아보겠습니다.

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

        // 이미지를 마커로 로드하고 추가합니다.
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // 이미지를 마커로 사용하여 데이터 포인트 추가
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

### 차트 시리즈 마커 구성 및 프레젠테이션 저장
마지막으로, 가시성을 높이기 위해 마커 크기를 조정하고 프레젠테이션을 저장해 보겠습니다.

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

        // 이미지를 마커로 로드하고 추가합니다(플레이스홀더 경로 사용 예)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## 결론
이 가이드를 따라 Aspose.Slides for Java에서 사용자 정의 이미지 마커를 추가하여 차트를 개선하는 방법을 알아보았습니다. 이 방법을 사용하면 프레젠테이션의 참여도와 명확성을 크게 높일 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-02-22'
description: Aspose.Slides를 사용하여 Java에서 누적 세로 막대 차트를 만드는 방법을 배웁니다. 이 튜토리얼에서는 Aspose
  Slides Maven 의존성, 백분율 누적 차트 추가, 차트 데이터 레이블 서식 지정, 그리고 프레젠테이션을 PPTX 형식으로 저장하는 방법을
  다룹니다.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Java와 Aspose.Slides를 사용한 누적 컬럼 차트 만들기 – 종합 가이드
url: /ko/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java와 Aspose.Slides를 사용한 누적 세로 막대 차트 만들기 – 종합 가이드

## 소개

Aspose.Slides for Java의 강력한 기능을 활용하여 통찰력 있는 데이터 시각화를 프레젠테이션에 적용해 보세요. 이 가이드에서는 **누적 세로 막대 차트** 슬라이드를 전문적으로 만드는 방법을 다룹니다. 비즈니스 보고서를 준비하거나 프로젝트 통계를 보여줄 때 모두 활용할 수 있습니다. 이 튜토리얼을 마치면 다음을 수행할 수 있습니다:

- Aspose Slides Maven 종속성을 사용하여 환경을 설정하기
- 처음부터 프레젠테이션 만들기
- **백분율 누적 차트** 추가 및 외관 맞춤
- **차트 데이터 레이블 형식 지정** 및 **세로 축 형식 변경**
- 한 줄의 코드로 프레젠테이션을 PPTX로 **저장**

각 단계를 차근차근 살펴보며 바로 매력적인 프레젠테이션을 만들 수 있습니다.

## 빠른 답변
- **필요한 라이브러리는?** `aspose-slides` Maven/Gradle 종속성 (아래 “aspose slides maven dependency” 참고)  
- **사용되는 차트 유형은?** 백분율‑누적 세로 막대 차트를 위한 `ChartType.PercentsStackedColumn`  
- **축 숫자 형식을 어떻게 변경하나요?** `IAxis.setNumberFormat()`를 사용하고 소스와 연결을 해제하세요  
- **데이터 레이블을 맞춤 설정할 수 있나요?** 예 – `IChartDataPoint` 객체를 순회하며 사용자 정의 `ITextFrame`을 설정합니다  
- **파일을 어떻게 저장하나요?** `presentation.save("output.pptx", SaveFormat.Pptx)`를 호출합니다

## 누적 세로 막대 차트란?
누적 세로 막대 차트는 여러 데이터 시리즈를 세로 막대에 겹쳐서 시각화합니다. **백분율‑누적** 변형을 사용하면 각 막대가 항상 100 %가 되므로 카테고리별 비율 기여도를 쉽게 비교할 수 있습니다.

## 왜 Java용 Aspose.Slides를 사용하나요?
Aspose.Slides는 Microsoft Office가 설치되지 않은 모든 플랫폼에서 작동하는 순수 Java API를 제공합니다. 차트 객체에 대한 세밀한 제어를 가능하게 하고, 다양한 형식을 지원하며, 프로그래밍 방식으로 프레젠테이션을 생성할 수 있어 자동 보고서 작성이나 서버‑사이드 문서 생성에 최적입니다.

## 사전 요구 사항
- **Java Development Kit (JDK):** 8 이상  
- **IDE:** IntelliJ IDEA, Eclipse 또는 Java 호환 편집기  
- **빌드 도구:** Maven 또는 Gradle (선택 사항이지만 권장)  
- **기본 Java 지식** – 클래스와 메서드에 익숙해야 합니다  

## Java용 Aspose.Slides 설정
시작하려면 프로젝트에 Aspose.Slides 라이브러리를 추가합니다.

### Aspose Slides Maven 종속성
`pom.xml`에 다음을 추가합니다 (필요한 **aspose slides maven dependency**입니다):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 대안
Gradle를 선호한다면 `build.gradle`에 다음 라인을 포함하세요:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 최신 JAR 파일을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드합니다.

### 라이선스 획득
Aspose.Slides 기능을 체험하려면 무료 평가판으로 시작할 수 있습니다. 평가 제한을 해제하려면 임시 라이선스 또는 정식 라이선스를 구매하는 것을 고려하세요.

- **무료 평가판:** 비용 없이 제한된 기능에 접근  
- **임시 라이선스:** [Aspose 사이트](https://purchase.aspose.com/temporary-license/)에서 요청  
- **구매:** 전체 기능을 이용하려면 구매 페이지를 방문  

### 기본 초기화
`Presentation` 객체를 생성하는 최소 코드 예시입니다:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 구현 가이드

### 프레젠테이션 생성 및 슬라이드 추가
**개요:** 먼저 빈 프레젠테이션을 만들고 슬라이드가 존재하는지 확인합니다.

#### 단계 1: Presentation 객체 초기화
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 단계 2: 프레젠테이션 저장
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 슬라이드에 백분율 누적 세로 막대 차트 추가
**개요:** 이제 첫 번째 슬라이드에 **백분율 누적 차트**를 배치합니다.

#### 단계 1: 슬라이드 초기화 및 접근
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### 단계 2: 슬라이드에 차트 추가
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### 차트 축 숫자 형식 맞춤
**개요:** 가독성을 높이기 위해 **세로 축 형식**을 백분율로 변경합니다.

#### 단계 1: 차트 추가 및 접근
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

#### 단계 2: 사용자 정의 숫자 형식 설정
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### 차트에 시리즈 및 데이터 포인트 추가
**개요:** 샘플 데이터 시리즈로 차트를 채웁니다.

#### 단계 1: Presentation 및 차트 초기화
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

#### 단계 2: 데이터 시리즈 추가
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### 시리즈 채우기 색상 서식 지정
**개요:** 각 시리즈에 구별되는 색상을 지정해 차트를 읽기 쉽게 만듭니다.

#### 단계 1: 차트 초기화 및 접근
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

#### 단계 2: 채우기 색상 설정
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### 데이터 레이블 서식 지정
**개요:** 이제 **차트 데이터 레이블**을 맞춤 텍스트로 표시하도록 **서식 지정**합니다.

#### 단계 1: 차트 시리즈 및 데이터 포인트 접근
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

#### 단계 2: 데이터 레이블 맞춤 설정
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

## 일반적인 문제 및 해결책
- **차트가 비어 있음:** 저장하기 전에 최소 하나의 데이터 시리즈와 데이터 포인트를 추가했는지 확인하세요.  
- **축 숫자가 백분율로 표시되지 않음:** `verticalAxis.setNumberFormatLinkedToSource(false)`를 설정해야 합니다. 설정하지 않으면 사용자 정의 형식이 무시됩니다.  
- **라이선스 평가 메시지:** `Presentation` 객체를 만들기 전에 유효한 라이선스 파일을 적용해 평가 배너를 숨깁니다.

## 자주 묻는 질문

**Q: 이 코드를 Java 11 이상에서 사용할 수 있나요?**  
A: 예. 라이브러리는 JDK 8 이상을 지원하므로 적절한 classifier(예: JDK 16 이상은 `jdk16`)를 사용하면 됩니다.

**Q: 차트를 PPTX가 아니라 이미지로 내보내려면 어떻게 하나요?**  
A: 슬라이드에 차트를 추가한 후 `chart.getImage().save("chart.png", ImageFormat.Png);`를 사용합니다.

**Q: 누적 세로 막대 차트에 범례를 추가할 수 있나요?**  
A: 물론입니다. `chart.getChartTitle().addTextFrameForOverriding("My Chart");`를 호출하고 필요에 따라 `chart.getLegend()`를 설정합니다.

**Q: 프레젠테이션 생성 후 데이터를 업데이트해야 하면 어떻게 하나요?**  
A: `ChartDataWorkbook` 셀을 수정한 뒤 `chart.refresh();`를 호출하면 변경 사항이 반영됩니다.

**Q: Aspose.Slides가 Linux 서버에서 작동하나요?**  
A: 예. 라이브러리는 순수 Java이며 호환 가능한 JRE가 있는 모든 OS에서 실행됩니다.

## 결론
이 가이드를 따라 하면 Java용 Aspose.Slides를 사용해 **누적 세로 막대 차트** 프레젠테이션을 만드는 방법을 환경 설정부터 세밀한 시각 스타일링까지 배울 수 있습니다. 다양한 데이터 세트, 색상 및 레이블 형식을 실험해 보고서를 돋보이게 만들어 보세요.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
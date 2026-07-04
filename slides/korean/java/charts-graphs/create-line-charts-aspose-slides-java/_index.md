---
date: '2026-03-23'
description: Aspose.Slides for Java를 사용하여 마커가 있는 선 차트를 만들고, 두 번째 시리즈를 추가하며, PowerPoint
  프레젠테이션에서 null 데이터를 처리하는 방법을 배웁니다.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Aspose.Slides for Java 사용 방법: 기본 마커가 있는 선 차트 만들기'
url: /ko/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 기본 마커가 있는 라인 차트 만들기 – Aspose.Slides for Java 사용

## 소개
**Aspose**를 사용해 PowerPoint 생성을 자동화하는 방법을 찾고 계시다면, 바로 여기입니다. 이번 튜토리얼에서는 **마커가 있는 라인 차트**를 만드는 방법, 두 번째 시리즈 추가, 그리고 null 데이터 처리까지 Aspose.Slides for Java로 단계별로 살펴봅니다. 최종적으로 PowerPoint를 직접 열지 않고도 전문적인 차트를 생성할 수 있는 실행 가능한 코드를 얻을 수 있습니다.

### 빠른 답변
- **필요한 라이브러리는?** Aspose.Slides for Java (최신 버전 권장)  
- **두 번째 시리즈를 추가할 수 있나요?** 네 – API를 통해 여러 시리즈를 쉽게 추가할 수 있습니다.  
- **null 데이터 포인트는 어떻게 처리하나요?** 셀 값에 `null`을 사용하면 차트가 해당 포인트를 건너뜁니다.  
- **Maven이 필요한가요?** Maven 또는 Gradle 모두 사용 가능; 아래 *aspose slides maven* 섹션을 참고하세요.  
- **라이선스가 필요한가요?** 개발 단계에서는 무료 체험판으로 충분하지만, 상용 환경에서는 상업용 라이선스가 필요합니다.

## Aspose.Slides for Java로 라인 차트 만들기
프로그래밍 방식으로 차트를 생성하면 수작업 포맷팅에 드는 시간을 크게 절감하고, 프레젠테이션 전반에 걸쳐 일관성을 보장할 수 있습니다. 보고서 도구에 **PowerPoint 차트 생성** 기능을 구현하거나, 실시간으로 슬라이드 덱을 만들 때 Aspose.Slides를 사용하면 Java 코드만으로 전체 제어가 가능합니다.

## 사전 준비
시작하기 전에 개발 환경을 다음과 같이 준비하세요:

1. **라이브러리 및 종속성**
   - Aspose.Slides for Java 라이브러리 (버전 25.4 권장) – *aspose slides maven* 시나리오 포함.
   - Java Development Kit (JDK) 버전 16 이상.
2. **환경 설정**
   - Maven 또는 Gradle를 지원하는 IDE.
   - 체험판이 아닌 경우 유효한 Aspose 라이선스 파일.
3. **지식 사전 조건**
   - 기본 Java 프로그래밍.
   - Maven 또는 Gradle 빌드 파일에 대한 이해.

## Aspose.Slides for Java 설정
### Maven
`pom.xml` 파일에 다음 의존성을 추가하세요:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
`build.gradle` 파일에 다음을 포함하세요:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### 직접 다운로드
또는 최신 버전을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드할 수 있습니다.

**라이선스 획득 단계:**
- 무료 체험판은 [free trial page](https://releases.aspose.com/slides/java/)에서 확인하세요.
- 임시 라이선스는 [temporary license page](https://purchase.aspose.com/temporary-license/)에서 발급받을 수 있습니다.
- 정식 라이선스는 [purchase portal](https://purchase.aspose.com/buy)에서 구매하세요.

**기본 초기화:**
Java 애플리케이션에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

이제 차트 만들기로 넘어갑시다!

## 구현 가이드
### 기능 1: 기본 마커가 있는 차트 생성
이 섹션에서는 추세선상의 개별 데이터 포인트를 강조할 수 있는 **마커가 있는 라인 차트** 생성 방법을 보여줍니다.

#### 라인 차트 추가
마커가 포함된 라인 차트를 추가하려면:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### 시리즈 및 카테고리 초기화
새로 시작하려면:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 기능 2: 시리즈와 카테고리 추가
시리즈와 카테고리를 추가하는 것은 차트에 의미 있는 데이터를 채우는 핵심 단계입니다.

#### 새 시리즈 만들기
이름이 "Series 1"인 새 시리즈를 추가하려면:
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### 카테고리와 데이터 포인트 채우기
카테고리와 해당 데이터 포인트를 추가하려면:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### 기능 3: 두 번째 시리즈 추가 및 데이터 포인트 채우기
추가 시리즈를 넣으면 시각적 분석에 깊이를 더할 수 있습니다.

#### 두 번째 시리즈 만들고 채우기
"Series 2"를 추가하려면:
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### 기능 4: 차트 레전드 구성
레전드를 구성하면 특히 **두 번째 시리즈를 추가**했을 때 차트 가독성이 향상됩니다.

#### 레전드 설정 조정
구성 방법:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### 기능 5: 프레젠테이션 저장
차트가 완성되면 **PowerPoint 차트** 파일을 저장해 공유하거나 추가 편집이 가능하도록 합니다.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## 실무 적용 사례
1. **비즈니스 보고:** 분기별 재무 추세를 나타내는 마커가 있는 라인 차트 활용.  
2. **데이터 분석:** 각 마커가 측정 포인트를 강조하는 실험 데이터 시각화.  
3. **교육 자료:** 프로세스 단계별 변화를 보여주는 강의 슬라이드 제작.  
4. **프로젝트 관리:** 주요 일정에 대한 마커가 있는 타임라인으로 마일스톤 추적.  
5. **마케팅 프레젠테이션:** 캠페인 성과 급증을 명확한 마커 심볼로 표시.

## 흔히 발생하는 문제와 해결책
- **null 데이터 포인트 오류:** 셀 값에 `null`을 전달하면 (예시와 같이) Aspose가 해당 포인트를 자동으로 생략합니다.  
- **마커가 보이지 않음:** `ChartType.LineWithMarkers`를 사용했는지 확인하고, `ChartType.Line`이 아닌지 점검하세요.  
- **레전드가 데이터와 겹침:** `chart.getLegend().setOverlay(false)`를 설정해 레전드를 별도로 배치합니다.  

## 자주 묻는 질문

**Q: 이 방법을 웹 서비스에서 차트를 생성하는 데 사용할 수 있나요?**  
A: 물론 가능합니다. 라이브러리는 서버‑사이드 Java 환경을 포함한 모든 Java 환경에서 동작합니다.

**Q: 개발 빌드에도 라이선스가 필요할까요?**  
A: 개발 및 테스트 단계에서는 무료 체험판으로 충분합니다. 상용 환경에서는 상업용 라이선스가 필요합니다.

**Q: Aspose는 대용량 데이터셋을 어떻게 처리하나요?**  
A: API가 데이터를 효율적으로 스트리밍하지만, 파일 크기가 과도해지지 않도록 데이터 포인트 수를 적절히 제한하는 것이 좋습니다.

**Q: 다른 차트 유형도 지원하나요?**  
A: 네 – Aspose.Slides는 막대, 원형, 산점도 등 다양한 차트 유형을 지원합니다.

**Q: 마커 모양과 색상을 커스터마이징할 수 있나요?**  
A: 각 데이터 포인트의 `Marker` 속성을 통해 마커 형식과 색상을 자유롭게 변경할 수 있습니다.

## 결론
이제 **Aspose**를 활용해 기본 마커가 있는 라인 차트를 만들고, 두 번째 시리즈를 추가하며, null 데이터를 처리하고, 최종적으로 PowerPoint 파일로 저장하는 방법을 알게 되었습니다. 이러한 기술을 통해 보고서 자동화, 데이터 스토리텔링 강화, 프레젠테이션 일관성 유지가 가능해집니다.

자세한 내용은 [공식 문서](https://docs.aspose.com/slides/java/)를 참고하거나 Stack Overflow와 같은 커뮤니티 포럼에 참여해 보세요.

---

**마지막 업데이트:** 2026-03-23  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
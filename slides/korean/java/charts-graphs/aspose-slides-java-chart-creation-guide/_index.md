---
date: '2026-06-03'
description: Java와 Aspose.Slides를 사용하여 클러스터형 열 차트를 만드는 방법을 배웁니다. 이 가이드는 Maven 의존성,
  차트 생성 단계 및 데이터 처리에 대해 다룹니다.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Java와 Aspose.Slides를 사용하여 클러스터형 열 차트 만들기
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java와 Aspose.Slides를 사용한 클러스터형 열 차트 만들기

## Java에서 차트 만들기: 소개
동적인 프레젠테이션을 만들 때는 종종 차트를 통해 데이터를 시각화합니다. **Aspose.Slides for Java**를 사용하면 **클러스터형 열 차트** 객체를 손쉽게 만들고, 명확성을 높이며 청중에게 더 강력한 인상을 줄 수 있습니다. 이 튜토리얼에서는 라이브러리 설정, 클러스터형 열 차트 추가, 시리즈 관리, 그리고 부정적인 데이터 포인트를 조건부로 반전시키는 방법을 단계별로 안내합니다.

**배우게 될 내용**
- Aspose.Slides for Java 설정 방법
- 프레젠테이션에서 **클러스터형 열 차트**를 만드는 단계
- 차트 시리즈와 데이터 포인트를 관리하는 기술
- 시각화를 개선하기 위해 부정적인 데이터 포인트를 조건부로 반전시키는 방법
- 프레젠테이션을 안전하게 저장하는 방법

## 빠른 답변
- **사용된 라이브러리는?** Aspose.Slides for Java.  
- **시연된 차트 유형은?** 클러스터형 열 차트.  
- **음수 값을 반전시킬 수 있나요?** 예, `invertIfNegative`를 사용합니다.  
- **필요한 Java 버전은?** JDK 16 이상.  
- **프로덕션에 라이선스가 필요합니까?** 예, 유효한 Aspose 라이선스가 필요합니다.

## 클러스터형 열 차트란 무엇인가요?
클러스터형 열 차트는 각 범주에 대해 여러 데이터 시리즈를 나란히 배치하여 그룹 간 빠른 비교를 가능하게 하는 시각적 표현입니다. 재무 보고서, 영업 대시보드 및 여러 지표를 한 번에 대비해야 하는 모든 상황에 적합합니다.

## 차트 생성에 Aspose.Slides를 사용하는 이유는?
Aspose.Slides를 사용하면 차트를 프로그래밍 방식으로 생성하고 완전히 사용자 지정할 수 있어 수동 PowerPoint 편집이 필요 없습니다. **70개 이상의 입력 및 출력 형식**을 지원하며 **최대 10,000장의 슬라이드**까지 전체 파일을 메모리에 로드하지 않고 처리할 수 있어 대규모 보고서 작성 시 높은 성능을 보장합니다.

## 전제 조건
1. **필수 라이브러리**  
   - Aspose.Slides for Java (버전 25.4 이상).  

2. **환경**  
   - JDK 16 이상.  
   - Maven 또는 Gradle을 사용한 의존성 관리.  

3. **지식**  
   - 기본 Java 프로그래밍.  
   - 빌드 도구(Maven/Gradle) 사용에 익숙함.

## Aspose.Slides for Java 설정
### Maven 설치
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 설치
Add the following line to your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 최신 버전을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

### 라이선스 획득
- **무료 체험:** 라이선스 없이 기능을 탐색합니다.  
- **임시 라이선스:** 평가 중에 사용합니다.  
- **정식 라이선스:** 프로덕션 배포를 위해 구매합니다.

### 기본 초기화
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 슬라이드에 클러스터형 열 차트를 추가하려면 어떻게 해야 하나요?
`Presentation`은 PowerPoint 파일을 나타내는 핵심 클래스입니다. 새 `Presentation`을 로드하고 슬라이드를 추가한 뒤 `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`을 호출합니다. 이 한 번의 호출로 지정된 좌표에 완전한 기능을 갖춘 클러스터형 열 차트가 생성됩니다. 이후 차트 객체에 접근하여 시리즈, 데이터 포인트 및 시각적 스타일을 수정할 수 있습니다.

## 단계별 가이드

### Step 1: 프레젠테이션을 만들고 클러스터형 열 차트를 추가합니다
`Presentation` 클래스는 PowerPoint 문서를 나타내며 슬라이드 생성을 허용합니다.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Step 2: 차트 시리즈 관리
이제 기본 시리즈를 모두 제거하고 새 시리즈를 추가한 뒤 양수와 음수 값을 모두 채워 넣겠습니다.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Step 3: 부정적인 데이터 포인트를 조건부로 반전시키기
`invertIfNegative` 메서드는 차트 시리즈에서 음수 값을 반전시킬 수 있게 합니다.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## 일반적인 함정 및 팁
- **`Presentation` 객체를 해제하는 것을 잊었나요?** 항상 `finally` 블록에서 `dispose()`를 호출하여 네이티브 리소스를 해제하십시오.  
- **음수 값이 반전되지 않나요?** 데이터 포인트를 추가한 **후에** `invertIfNegative(true)`를 호출했는지 확인하십시오.  
- **차트 크기 문제:** 좌표 (X, Y)와 크기 (width, height)는 포인트 단위이며, 슬라이드 레이아웃에 맞게 조정하십시오.  

## 자주 묻는 질문

**Q:** 같은 방법으로 다른 차트 유형을 만들 수 있나요?  
A: 예, `ChartType.ClusteredColumn`을 다른 `ChartType` 열거값(예: `Line`, `Pie`)으로 교체하면 됩니다.

**Q:** 개발 빌드에 라이선스가 필요합니까?  
A: 전체 기능에 접근하려면 임시 또는 평가 라이선스가 필요합니다; 그렇지 않으면 라이브러리는 워터마크 제한이 있는 체험 모드로 동작합니다.

**Q:** 차트를 추가한 후 프레젠테이션을 PDF로 내보내려면 어떻게 해야 하나요?  
`SaveFormat.Pdf`는 프레젠테이션을 저장할 때 PDF를 출력 형식으로 지정합니다. 차트 작업을 마친 후 `pres.save("output.pdf", SaveFormat.Pdf);`를 사용하십시오.

**Q:** 개별 열(색상, 테두리)을 스타일링할 수 있나요?  
`IChartDataPoint`는 차트의 단일 데이터 포인트를 나타내며 서식을 지정할 수 있습니다. 각 `IChartDataPoint`는 `getFillFormat().setFillType(FillType.Solid)` 및 `getLineFormat()`와 같은 옵션을 제공합니다.

**Q:** 프레젠테이션을 저장한 후 차트 데이터를 업데이트해야 하면 어떻게 해야 하나요?  
A: `new Presentation("file.pptx")`로 프레젠테이션을 다시 로드하고 차트 데이터를 수정한 뒤 다시 저장하십시오.

---

**마지막 업데이트:** 2026-06-03  
**테스트 환경:** Aspose.Slides for Java 25.4 (JDK 16)  
**작성자:** Aspose

## 관련 튜토리얼

- [Java와 Aspose.Slides를 사용한 누적 열 차트 만들기 – 종합 가이드](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Java와 Aspose.Slides를 사용한 차트 만들기 – 차트 생성 및 검증 마스터](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Aspose.Slides를 사용한 Java 차트 만들기 및 서식 지정: 종합 가이드](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
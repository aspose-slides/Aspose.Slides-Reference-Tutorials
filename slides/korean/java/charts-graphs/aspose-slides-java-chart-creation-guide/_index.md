---
date: '2026-01-14'
description: Aspose.Slides를 사용하여 Java에서 클러스터형 열 차트를 만드는 방법을 배웁니다. 빈 프레젠테이션 만들기, 프레젠테이션에
  차트 추가, 시리즈 관리 등을 단계별로 안내합니다.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Java와 Aspose.Slides를 사용하여 클러스터형 열 차트를 만드는 방법
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java와 Aspose.Slides를 활용한 차트 생성 마스터하기

## Aspose.Slides for Java를 사용하여 차트 만들기 및 관리하기

### 소개
동적인 프레젠테이션을 만들 때는 종종 차트를 통해 데이터를 시각화합니다. **Aspose.Slides for Java**를 사용하면 **클러스터형 열 차트**를 손쉽게 **생성**하고 다양한 차트 유형을 관리하여 명확성과 효과를 높일 수 있습니다. 이 튜토리얼에서는 빈 프레젠테이션을 만들고, 클러스터형 열 차트를 추가하고, 시리즈를 관리하며, 데이터 포인트 반전을 사용자 정의하는 방법을 Aspose.Slides for Java를 사용해 단계별로 안내합니다.

**배우게 될 내용:**
- Aspose.Slides for Java 설정 방법
- **빈 프레젠테이션 생성** 및 프레젠테이션에 차트 추가 단계
- 차트 시리즈와 데이터 포인트를 효과적으로 관리하는 기술
- 시각화를 개선하기 위해 음수 데이터 포인트를 조건부로 반전시키는 방법
- 프레젠테이션을 안전하게 저장하는 방법

시작하기 전에 요구 사항을 살펴보겠습니다.

## 빠른 답변
- **시작할 기본 클래스는 무엇인가요?** `com.aspose.slides`의 `Presentation`.
- **클러스터형 열 차트를 만들 차트 유형은?** `ChartType.ClusteredColumn`.
- **슬라이드에 차트를 어떻게 추가하나요?** 슬라이드의 shape 컬렉션에서 `addChart()`를 사용합니다.
- **음수 값을 반전시킬 수 있나요?** 예, 데이터 포인트에 `invertIfNegative(true)`를 사용합니다.
- **필요한 버전은?** Aspose.Slides for Java 25.4 이상.

## 클러스터형 열 차트란 무엇인가요?
클러스터형 열 차트는 각 카테고리마다 여러 데이터 시리즈를 나란히 표시하여 그룹 간 값을 비교하기에 적합합니다. Aspose.Slides를 사용하면 PowerPoint를 열지 않고도 프로그래밍 방식으로 이 차트를 생성할 수 있습니다.

## 프레젠테이션에 차트를 추가할 때 Aspose.Slides for Java를 사용하는 이유는?
- **전체 제어** 차트 데이터, 외관 및 레이아웃
- **서버에 Office 설치 불필요**
- **모든 주요 차트 유형 지원**, 클러스터형 열 차트 포함
- **Maven/Gradle 빌드와 손쉬운 통합**

## 전제 조건
1. **필수 라이브러리:** - Aspose.Slides for Java (버전 25.4 이상).
2. **환경 설정 요구 사항:** - 호환되는 JDK 버전 (예: JDK 16). - 의존성 관리를 원한다면 Maven 또는 Gradle 설치.
3. **지식 전제 조건:** - Java 프로그래밍에 대한 기본 이해. - 개발 환경에서 의존성을 다루는 방법에 익숙함.

## Aspose.Slides for Java 설정하기
Aspose.Slides 사용을 시작하려면 다음 단계를 따르세요:

**Maven 설치:**  
`pom.xml` 파일에 다음 종속성을 추가합니다:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 설치:**  
`build.gradle`에 다음 라인을 추가합니다:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드:**  
또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 최신 버전을 다운로드합니다.

### 라이선스 획득
- **무료 체험:** 기능을 살펴보기 위해 무료 체험을 시작할 수 있습니다.
- **임시 라이선스:** 평가 기간 동안 전체 기능을 사용하려면 임시 라이선스를 획득하세요.
- **구매:** 장기적으로 필요에 맞는다면 구매를 고려하세요.

### 기본 초기화
다음은 새 프레젠테이션 인스턴스를 만들기 위해 필요한 최소 코드입니다:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## 구현 가이드
이제 각 기능을 관리 가능한 단계로 나누어 보겠습니다.

### 클러스터형 열 차트가 포함된 프레젠테이션 만들기
#### 개요
이 섹션에서는 **빈 프레젠테이션 생성**, **클러스터형 열 차트** 추가 및 첫 번째 슬라이드에 배치하는 방법을 보여줍니다.

**단계:**
1. **Presentation 객체 초기화** – 새로운 `Presentation`을 생성합니다.
2. **클러스터형 열 차트 추가** – 적절한 유형과 크기로 `addChart()`를 호출합니다.

**코드 예시:**
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

### 차트 시리즈 관리
#### 개요
기본 시리즈를 제거하고, 새 시리즈를 추가하며, 양수와 음수 값을 모두 채우는 방법을 배웁니다.

**단계:**
1. **기존 시리즈 삭제** – 미리 채워진 데이터를 제거합니다.
2. **새 시리즈 추가** – 워크북 셀을 시리즈 이름으로 사용합니다.
3. **데이터 포인트 삽입** – 나중에 반전을 보여주기 위해 음수를 포함한 값을 추가합니다.

**코드 예시:**
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

### 조건에 따라 시리즈 데이터 포인트 반전
#### 개요
기본적으로 Aspose.Slides는 음수 값을 반전시킬 수 있습니다. 이 동작을 전체적으로 또는 데이터 포인트별로 제어할 수 있습니다.

**단계:**
1. **전체 반전 설정** – 전체 시리즈에 대한 자동 반전을 비활성화합니다.
2. **조건부 반전 적용** – 특정 음수 포인트에만 반전을 활성화합니다.

**코드 예시:**
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

### 일반적인 문제와 해결책
| 문제 | 해결책 |
|------|--------|
| 차트가 비어 보입니다 | 슬라이드 인덱스(`0`)가 존재하고 차트 크기가 슬라이드 범위 내에 있는지 확인하세요. |
| 음수 값이 반전되지 않습니다 | `invertIfNegative(false)`가 시리즈에 설정되고, 특정 데이터 포인트에 `invertIfNegative(true)`가 설정되었는지 확인하세요. |
| 라이선스 예외 발생 | `Presentation` 객체를 만들기 전에 유효한 Aspose 라이선스를 적용하세요. |

## 자주 묻는 질문

**Q: 클러스터형 열 차트 외에 다른 차트 유형을 추가할 수 있나요?**  
A: 예, Aspose.Slides는 선, 원, 막대, 영역 등 다양한 차트 유형을 지원합니다.

**Q: 개발에 라이선스가 필요합니까?**  
A: 평가용으로는 무료 체험으로 충분하지만, 실제 운영에서는 상용 라이선스가 필요합니다.

**Q: 차트를 이미지로 내보내려면?**  
A: 렌더링 후 `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`를 사용합니다.

**Q: 차트의 스타일(색상, 글꼴)을 지정할 수 있나요?**  
A: 물론 가능합니다. 각 `IChartSeries`와 `IChartDataPoint`는 스타일 속성을 제공합니다.

**Q: 기존 PPTX 파일에 차트를 추가하려면?**  
A: `new Presentation("existing.pptx")`로 파일을 로드한 뒤 원하는 슬라이드에 차트를 추가합니다.

## 결론
이 튜토리얼에서는 Java에서 **클러스터형 열 차트**를 만들고, 시리즈를 관리하며, Aspose.Slides를 사용해 음수 데이터 포인트를 조건부로 반전시키는 방법을 배웠습니다. 이러한 기술을 활용하면 프로그래밍 방식으로 설득력 있는 데이터 기반 프레젠테이션을 만들 수 있습니다.

**다음 단계:**
- Aspose.Slides for Java가 제공하는 다른 차트 유형을 실험해 보세요.
- 맞춤 색상, 데이터 레이블, 축 서식 등 고급 스타일 옵션을 탐구하세요.
- 차트 생성을 보고서 또는 분석 파이프라인에 통합하세요.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
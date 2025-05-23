---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 차트를 만들고 관리하는 방법을 알아보세요. 이 가이드에서는 클러스터형 세로 막대형 차트, 데이터 계열 관리 등에 대해 다룹니다."
"title": "Aspose.Slides를 활용한 Java 차트 제작 마스터링 가이드"
"url": "/ko/java/charts-graphs/aspose-slides-java-chart-creation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java로 차트 만들기 마스터하기

## Java용 Aspose.Slides를 사용하여 차트를 만들고 관리하는 방법

### 소개
역동적인 프레젠테이션을 만들려면 차트를 통해 데이터를 시각화하는 것이 필요합니다. **Java용 Aspose.Slides**다양한 차트 유형을 손쉽게 만들고 관리하여 명확성과 효과를 높일 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 빈 프레젠테이션 만들기, 클러스터형 세로 막대형 차트 추가, 시리즈 관리, 데이터 포인트 반전 사용자 지정 방법을 안내합니다.

**배울 내용:**
- Java용 Aspose.Slides를 설정하는 방법.
- 프레젠테이션에 클러스터형 막대형 차트를 만드는 단계입니다.
- 차트 시리즈와 데이터 포인트를 효과적으로 관리하는 기술.
- 더 나은 시각화를 위해 음수 데이터 포인트를 조건부로 반전하는 방법입니다.
- 프레젠테이션을 안전하게 저장하는 방법

시작하기에 앞서 전제 조건을 살펴보겠습니다.

## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.

1. **필수 라이브러리:**
   - Java용 Aspose.Slides(버전 25.4 이상).

2. **환경 설정 요구 사항:**
   - 호환되는 JDK 버전(예: JDK 16).
   - 종속성 관리를 선호하는 경우 Maven이나 Gradle을 설치하세요.

3. **지식 전제 조건:**
   - Java 프로그래밍에 대한 기본적인 이해.
   - 개발 환경에서 종속성을 처리하는 방법에 익숙함.

## Java용 Aspose.Slides 설정
Aspose.Slides를 사용하려면 다음 단계를 따르세요.

**Maven 설치:**
다음 종속성을 추가하세요. `pom.xml` 파일:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 설치:**
다음 줄을 추가하세요 `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드:**
또는 다음에서 최신 버전을 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 라이센스 취득
- **무료 체험:** 무료 체험판을 통해 기능을 탐색해 보세요.
- **임시 면허:** 평가 기간 동안 전체 기능에 액세스할 수 있는 임시 라이선스를 받으세요.
- **구입:** 장기적인 필요에 부합한다고 생각되면 구매를 고려해 보세요.

### 기본 초기화
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// 여기에 코드를 입력하세요...
pres.dispose(); // 작업이 끝나면 항상 프레젠테이션 객체를 폐기하세요.
```

## 구현 가이드
이제 각 기능을 관리 가능한 단계로 나누어 보겠습니다.

### 클러스터형 막대형 차트를 사용하여 프레젠테이션 만들기
#### 개요
이 섹션에서는 빈 프레젠테이션을 만들고 슬라이드의 특정 좌표에 클러스터형 막대형 차트를 추가하는 방법을 설명합니다.

**단계:**
1. **프레젠테이션 객체를 초기화합니다.**
   - 새 인스턴스를 만듭니다. `Presentation`.
2. **클러스터형 막대형 차트 추가:**
   - 사용 `getSlides().get_Item(0).getShapes().addChart()` 차트를 추가하세요.
   - 위치, 크기, 유형을 지정하세요.

**코드 예제:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // 너비 600, 높이 400의 클러스터형 막대형 차트를 (50, 50)에 추가합니다.
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
기존 시리즈를 지우고 사용자 정의 데이터 포인트로 새 시리즈를 추가하는 방법을 알아보세요.

**단계:**
1. **기존 시리즈 삭제:**
   - 사용 `series.clear()` 기존 데이터를 제거합니다.
2. **새로운 시리즈 추가:**
   - 다음을 사용하여 새 시리즈를 추가합니다. `series.add()`.
3. **데이터 포인트 삽입:**
   - 활용하다 `getDataPoints().addDataPointForBarSeries()` 음수를 포함한 값을 추가하는 데 사용됩니다.

**코드 예제:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // 기존 시리즈를 지우고 새로운 시리즈를 추가합니다.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // 다양한 값(양수 및 음수)을 갖는 데이터 포인트를 추가합니다.
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
조건부로 반전시켜 부정적인 데이터 포인트의 시각화를 사용자 정의합니다.

**단계:**
1. **기본 반전 동작 설정:**
   - 사용 `setInvertIfNegative(false)` 전반적인 반전 행동을 결정합니다.
2. **특정 데이터 포인트를 조건부로 반전:**
   - 적용하다 `setInvertIfNegative(true)` 특정 데이터 포인트가 음수이면.

**코드 예제:**
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
    
    // 다양한 값(양수 및 음수)을 갖는 데이터 포인트를 추가합니다.
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
    
    // 기본 반전 동작 설정
    series.get_Item(0).invertIfNegative(false);
    
    // 특정 데이터 포인트를 조건부로 반전
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### 결론
이 튜토리얼에서는 Java용 Aspose.Slides를 설정하고 클러스터형 세로 막대형 차트를 만드는 방법을 알아보았습니다. 또한 데이터 시리즈를 관리하고 음수 데이터 포인트의 시각화를 사용자 정의하는 방법도 살펴보았습니다. 이러한 기술을 활용하면 이제 Java 애플리케이션에서 동적 차트를 자신 있게 만들 수 있습니다.

**다음 단계:**
- Java용 Aspose.Slides에서 제공하는 다양한 차트 유형을 실험해 보세요.
- 프레젠테이션을 더욱 풍부하게 만들기 위해 추가적인 사용자 정의 옵션을 살펴보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
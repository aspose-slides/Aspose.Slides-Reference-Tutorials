---
date: '2026-03-02'
description: Aspose.Slides for Java를 사용하여 박스 플롯을 만들고, 슬라이드에 차트를 추가하며, PowerPoint에서
  박스‑위스커 차트를 생성하는 방법을 배우세요.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Aspose.Slides for PowerPoint를 사용하여 Java로 박스 플롯 만들기
url: /ko/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint에서 Aspose.Slides for Java를 사용하여 Box-and-Whisker 차트 만들기

이 가이드에서는 Aspose.Slides를 사용하여 **create box plot java**를 만든 다음 차트를 PowerPoint 슬라이드에 직접 삽입합니다. 시각적으로 매력적인 데이터 프레젠테이션을 만드는 것은 오늘날 데이터 중심 세계에서 매우 중요하며, 차트는 이를 위한 필수 도구입니다. Java를 사용하여 PowerPoint 내에서 box-and-whisker 차트를 생성하려는 경우 Aspose.Slides 라이브러리가 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용해 이러한 차트를 손쉽게 생성하고 구성하는 방법을 단계별로 안내합니다.

## 배울 내용

- Aspose.Slides for Java 환경 설정
- **add chart to slide** 단계와 Java를 사용하여 PowerPoint에서 box‑whisker 차트 생성
- Aspose.Slides 사용 시 성능 최적화를 위한 모범 사례
- box‑and‑whisker 차트의 실제 적용 사례

## 빠른 답변

- **What library creates a box plot in Java?** Aspose.Slides for Java.
- **Which chart type is used?** `ChartType.BoxAndWhisker`.
- **Do I need a license?** 평가용으로는 무료 체험판을 사용할 수 있으며, 제품 환경에서는 상용 라이선스가 필요합니다.
- **Can I add multiple series?** 예 – 각 데이터 세트마다 series‑creation 블록을 반복하면 됩니다.
- **What format is the final file?** PowerPoint PPTX (`SaveFormat.Pptx`).

## 사전 요구 사항

이 튜토리얼을 따라하려면 다음이 필요합니다:

- **Java Development Kit (JDK)**: JDK 8 이상이 설치되어 있어야 합니다.
- **Aspose.Slides for Java Library**: Java에서 PowerPoint 프레젠테이션을 처리하는 데 필수합니다.
- **IDE**: IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경으로 코드를 작성하고 실행합니다.

## Aspose.Slides for Java 설정

Aspose.Slides를 사용하려면 종속성으로 추가합니다. Maven, Gradle 또는 직접 다운로드를 통해 관리할 수 있습니다.

### Maven

`pom.xml`에 다음 종속성을 추가합니다:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

`build.gradle`에 다음을 포함합니다:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드

또는 최신 버전을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드합니다.

#### 라이선스 획득

- **Free Trial**: 기능을 살펴보기 위해 무료 체험판으로 시작합니다.  
- **Temporary License**: 평가용으로 임시 라이선스를 얻습니다.  
- **Purchase**: 전체 기능을 사용하려면 라이선스 구매를 고려하십시오.

Aspose.Slides를 초기화하려면 클래스패스에 라이브러리를 포함하고 필요에 따라 라이선스 설정을 수행하십시오.

## 구현 가이드

이제 단계별 코드를 살펴보겠습니다. 각 블록은 코드 스니펫 전에 설명되어 있어 정확히 무엇을 하는지 알 수 있습니다.

### 박스 플롯이란 무엇이며 Java에서 사용하는 이유는?

Box‑and‑whisker 차트(일반적으로 *box plot*이라고도 함)는 데이터 분포—중앙값, 사분위수 및 이상치—를 간결하게 시각화합니다. Java에서 프로그래밍 방식으로 이 차트를 생성하면 통계적 인사이트를 PowerPoint 프레젠테이션에 직접 삽입할 수 있어 수동 차트 작성을 없앨 수 있습니다.

### Aspose.Slides로 슬라이드에 차트를 추가하는 이유는?

Aspose.Slides는 저수준 OpenXML 세부 정보를 추상화하여 차트를 생성, 스타일링 및 내보내기 위한 유창한 API를 제공합니다. 이를 통해 보고서 생성을 자동화하고 일관된 브랜드를 유지하며 차트를 더 큰 Java 워크플로에 통합할 수 있습니다.

### 단계 1: 프레젠테이션 만들기 또는 열기

먼저 기존 PPTX 파일을 열거나 새 프레젠테이션을 시작합니다:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** 파일이 존재하지 않으면 Aspose.Slides가 새 빈 프레젠테이션을 생성합니다.

### 단계 2: 슬라이드에 Box‑and‑Whisker 차트 추가

차트의 위치와 크기(포인트 단위)를 지정하여 원하는 위치에 배치합니다:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### 단계 3: 기존 데이터 지우기

새 데이터를 입력하기 전에 자리표시자 카테고리나 시리즈를 모두 삭제합니다:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### 단계 4: 카테고리 구성

각 박스 아래에 표시될 카테고리(X축 레이블)를 추가합니다:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Note:** 레이블 텍스트를 데이터 도메인에 맞게 조정하세요(예: “Q1”, “Product A”).

### 단계 5: 시리즈 생성 및 사용자 정의

이제 시리즈를 생성하고 시각 옵션을 설정한 뒤 숫자 데이터 포인트를 입력합니다:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

`int[] data` 배열을 데이터베이스, CSV 파일 또는 기타 소스에서 읽은 값으로 교체할 수 있습니다.

### 단계 6: 프레젠테이션 저장

변경 내용을 새 PPTX 파일에 저장합니다:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### 단계 7: 리소스 정리

항상 `Presentation` 객체를 dispose하여 네이티브 리소스를 해제합니다:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## 실용적인 적용 사례

Box‑and‑whisker 차트는 통계 분석 및 데이터 프레젠테이션에서 매우 유용합니다. 다음은 차트가 특히 효과적인 몇 가지 시나리오입니다:

1. **Financial Analysis** – 지역별 매출 분포를 시각화합니다.  
2. **Quality Control** – 제조 측정값에서 이상치를 찾아냅니다.  
3. **Academic Research** – 실험 결과 변동성을 보여줍니다.  
4. **Market Research** – 인구통계별 제품 성능을 비교합니다.

이 차트를 PowerPoint 프레젠테이션에 통합하면 이해관계자가 복잡한 데이터를 한눈에 파악할 수 있습니다.

## 성능 고려 사항

Java에서 Aspose.Slides를 사용할 때 다음 팁을 기억하세요:

- **Memory Management** – `Presentation` 객체를 즉시 dispose합니다.  
- **Data Handling** – 필요한 데이터만 로드하고, 대용량 데이터를 차트 워크북에 직접 입력하는 것을 피합니다.  
- **Lazy Loading** – 많은 슬라이드를 생성할 경우, 표시될 슬라이드에만 차트를 생성하는 것을 고려합니다.

## 일반적인 문제와 해결책

| Issue | Cause | Solution |
|-------|-------|----------|
| **Chart appears blank** | 데이터 셀에 올바르게 값이 채워지지 않음 | `wb.getCell`이 올바른 행/열을 참조하고 값이 `null`이 아닌지 확인합니다. |
| **Outliers not shown** | `setShowOutlierPoints`가 `false`로 설정됨 | `series.setShowOutlierPoints(true)`가 호출되었는지 확인합니다. |
| **Memory leak** | Presentation이 dispose되지 않음 | 사용을 try/finally 블록으로 감싸고 `dispose()`를 호출합니다. |
| **Incorrect quartiles** | 기본 `Inclusive` 방법 사용 | `setQuartileMethod(QuartileMethodType.Exclusive)`로 `Exclusive`로 전환합니다. |

## 자주 묻는 질문

**Q1: Box-and-whisker 차트란 무엇인가요?**  
Box-and-whisker 차트(또는 box plot)는 최소값, 1사분위수, 중앙값, 3사분위수, 최대값 및 이상치를 포함한 다섯 가지 요약 통계량을 기반으로 데이터 분포를 표시합니다.

**Q2: Box-and-whisker 차트의 외관을 사용자 정의할 수 있나요?**  
예. Aspose.Slides를 사용하면 차트 서식 API를 통해 색상, 선 스타일, 마커 모양을 변경하고 데이터 레이블을 추가할 수 있습니다.

**Q3: 하나의 차트에 여러 시리즈를 포함할 수 있나요?**  
물론입니다. 시각화하려는 각 데이터 세트마다 series‑creation 블록을 반복하면 됩니다.

**Q4: 데이터가 올바르게 표시되지 않을 때 어떻게 해결하나요?**  
데이터가 워크북 셀에 정확히 기록되었는지, `setShowMeanLine`과 같은 가시성 속성이 활성화되어 있는지 확인하십시오.

**Q5: 문제가 발생하면 어디에서 지원을 받을 수 있나요?**  
커뮤니티 도움을 위해 [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11)을 방문하거나 공식 문서를 참고하십시오.

**Q6: Aspose.Slides가 다른 차트 유형도 지원하나요?**  
예, 라인, 바, 파이, 스캐터, 레이더 등 다양한 차트 유형을 지원합니다.

**Q7: 헤드리스 서버 환경에서도 차트를 생성할 수 있나요?**  
이 라이브러리는 서버 측 시나리오에서도 완전히 작동하며 UI가 필요하지 않습니다.

## 리소스

- **Documentation**: 자세한 API 레퍼런스는 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)에서 확인하세요  
- **Download**: Aspose.Slides 릴리스를 [여기](https://releases.aspose.com/slides/java/)에서 다운로드하세요  
- **Purchase**: 전체 기능을 사용하려면 [Aspose Purchase](https://purchase.aspose.com/buy)에서 라이선스를 구매하세요  
- **Free Trial & Temporary License**: 무료 체험판으로 시작하거나 임시 라이선스를 요청하려면 [여기](https://releases.aspose.com/slides/java/)를 방문하세요

이 가이드를 따라하면 Java 애플리케이션에서 통찰력 있는 box‑and‑whisker 차트를 프로그래밍 방식으로 생성하고 PowerPoint 프레젠테이션에 직접 삽입할 수 있습니다. 즐거운 코딩 되세요!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-03-02  
**테스트 환경:** Aspose.Slides 25.4 (JDK 16 classifier)  
**작성자:** Aspose
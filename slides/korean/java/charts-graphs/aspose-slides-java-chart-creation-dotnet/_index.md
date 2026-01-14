---
date: '2026-01-14'
description: Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에 클러스터형 세로 막대 차트를 추가하고 슬라이드에
  차트를 삽입하는 방법을 배웁니다. 완전한 코드 예제가 포함된 단계별 가이드를 따라하세요.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: .NET 슬라이드에 클러스터형 열 차트 추가 Aspose.Slides Java
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용한 .NET 프레젠테이션에서 차트 만들기
## 소개
설득력 있는 프레젠테이션을 만들려면 차트와 같은 시각적 데이터 표현을 통합하여 청중의 이해와 참여를 높이는 경우가 많습니다. Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에 동적이고 사용자 정의 가능한 차트를 추가하고자 하는 개발자를 위해 이 튜토리얼을 준비했습니다. 프레젠테이션 초기화, 다양한 차트 유형 추가, 차트 데이터 관리, 시리즈 데이터 서식 지정 방법을 자세히 살펴보겠습니다.

**배우게 될 내용:**
- .NET 환경에서 Aspose.Slides for Java를 설정하고 사용하는 방법
- Aspose.Slides를 사용한 새 프레젠테이션 초기화
- 슬라이드에 차트 추가 및 사용자 정의
- 차트 데이터 워크북 관리
- 특히 음수 값을 처리하는 시리즈 데이터 서식 지정

전제 조건 섹션으로 이동하면 순조롭게 따라올 수 있는 준비가 됩니다.

## 빠른 답변
- **주요 목표는 무엇인가요?** .NET 슬라이드에 클러스터형 열 차트를 추가하는 것입니다.
- **필요한 라이브러리는?** Aspose.Slides for Java (v25.4 이상).
- **.NET 프로젝트에서 사용할 수 있나요?** 예 – Java 라이브러리는 Java‑to‑.NET 브리지를 통해 작동합니다.
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.
- **구현 소요 시간은?** 기본 차트는 약 10‑15분이면 완성됩니다.

## 클러스터형 열 차트란?
클러스터형 열 차트는 각 카테고리마다 여러 데이터 시리즈를 나란히 표시하여 그룹 간 값을 쉽게 비교할 수 있게 해줍니다. 비즈니스 대시보드, 성과 보고서, 여러 지표를 대비해야 하는 모든 상황에 적합한 시각화 방식입니다.

## Aspose.Slides for Java로 슬라이드에 차트를 추가하는 이유
Aspose.Slides를 사용하면 Microsoft PowerPoint가 설치되지 않은 환경에서도 프레젠테이션을 생성·수정·저장할 수 있습니다. 차트 유형, 데이터, 스타일을 완벽히 제어할 수 있어 .NET 애플리케이션에서 직접 보고서 생성을 자동화할 수 있습니다.

## 전제 조건
Aspose.Slides for Java로 차트를 만들기 전에 필요한 사항을 정리해 보겠습니다.

### 필요 라이브러리 및 버전
- **Aspose.Slides for Java**: 버전 25.4 이상.

### 환경 설정 요구 사항
- .NET 애플리케이션을 지원하는 개발 환경.
- Java 프로그래밍 기본 개념에 대한 이해.

### 지식 전제 조건
- .NET 애플리케이션 컨텍스트에서 프레젠테이션을 만드는 경험.
- Maven/Gradle과 같은 Java 의존성 관리 도구에 대한 이해.

## Aspose.Slides for Java 설정
Aspose.Slides를 사용하려면 프로젝트에 종속성을 추가해야 합니다. 아래 방법을 참고하세요.

### Maven
`pom.xml` 파일에 다음 종속성을 추가합니다:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` 파일에 다음을 포함합니다:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 최신 버전을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드할 수 있습니다.

#### 라이선스 획득 단계
- **무료 체험**: 기능을 살펴볼 수 있는 임시 라이선스로 시작합니다.
- **구매**: 광범위한 사용을 위해 정식 라이선스를 구매합니다.

#### 기본 초기화 및 설정
코드에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
이 설정은 리소스 관리를 효과적으로 처리하도록 보장합니다.

## 구현 가이드
다음 단계별로 기능을 구현하는 방법을 안내합니다.

### 프레젠테이션 초기화
**개요:**  
프레젠테이션 인스턴스를 생성하면 이후 모든 작업의 기반이 마련됩니다. 이 섹션에서는 Aspose.Slides를 사용해 처음부터 시작하는 방법을 보여줍니다.

#### 단계 1: 필요한 패키지 가져오기
```java
import com.aspose.slides.Presentation;
```

#### 단계 2: 새 프레젠테이션 객체 생성
다음과 같이 수행합니다:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*이렇게 하면 사용 후 프레젠테이션 객체가 적절히 해제되어 메모리 누수를 방지합니다.*

### 슬라이드에 차트 추가
**개요:**  
슬라이드에 차트를 추가하면 데이터 시각화가 더욱 효과적이고 흥미롭게 됩니다.

#### 단계 1: 필요한 패키지 가져오기
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 단계 2: 프레젠테이션 초기화 및 차트 추가
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*여기서는 지정된 좌표와 크기로 첫 번째 슬라이드에 클러스터형 열 차트를 추가합니다.*

### 차트 데이터 워크북 관리
**개요:**  
차트의 데이터 워크북을 효율적으로 관리하면 시리즈와 카테고리를 손쉽게 조작할 수 있습니다.

#### 단계 1: 필요한 패키지 가져오기
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 단계 2: 데이터 워크북에 접근하고 초기화
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*새로운 시리즈와 카테고리를 추가하기 전에 워크북을 초기화하는 것이 중요합니다.*

### 차트에 시리즈 및 카테고리 추가
**개요:**  
시리즈와 카테고리를 추가하여 의미 있는 데이터 포인트를 구성할 수 있습니다.

#### 단계 1: 시리즈 및 카테고리 추가
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*시리즈와 카테고리를 추가하면 데이터가 보다 체계적으로 표시됩니다.*

### 시리즈 데이터 채우기 및 서식 지정
**개요:**  
차트에 데이터 포인트를 채우고 서식을 지정하여 가독성을 높이며, 특히 음수 값을 처리할 때 유용합니다.

#### 단계 1: 시리즈 데이터 채우기
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*이 섹션에서는 데이터를 채우고 색상 서식을 적용해 시각화를 개선하는 방법을 보여줍니다.*

## 일반적인 문제 및 해결책
- **메모리 누수:** `Presentation` 객체를 `finally` 블록에서 반드시 `dispose()` 호출하세요.
- **잘못된 차트 유형:** 클러스터형 열 차트를 원한다면 `ChartType.ClusteredColumn`을 사용해야 합니다. 다른 유형은 다른 시각적 결과를 생성합니다.
- **음수 값 색상이 적용되지 않음:** `IDataPoint` 값을 `Number`로 올바르게 캐스팅한 후 비교하고 있는지 확인하세요.

## 자주 묻는 질문

**Q: 순수 .NET 프로젝트에서 Java 없이 Aspose.Slides for Java를 사용할 수 있나요?**  
A: 예. 라이브러리는 Java‑to‑.NET 브리지를 통해 작동하므로 .NET 언어에서 Java API를 호출할 수 있습니다.

**Q: 무료 체험판으로 차트 생성이 가능한가요?**  
A: 체험판은 전체 차트 기능을 제공하지만, 생성된 파일에 작은 평가용 워터마크가 삽입됩니다.

**Q: 어떤 .NET 버전과 호환되나요?**  
A: Java 16+와 상호 운용 가능한 모든 .NET 버전, 예를 들어 .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7 등과 호환됩니다.

**Q: 차트가 많은 대용량 프레젠테이션을 어떻게 처리하나요?**  
A: 가능한 경우 동일한 `IChartDataWorkbook` 인스턴스를 재사용하고, 각 `Presentation`을 즉시 `dispose()`하여 메모리를 해제합니다.

**Q: 차트를 이미지로 내보낼 수 있나요?**  
A: 예. `chart.getImage()` 또는 `chart.exportChartImage()` 메서드를 사용해 PNG/JPEG 형식의 이미지를 얻을 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-01-14  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose  

---
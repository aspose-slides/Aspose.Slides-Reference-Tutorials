---
date: '2026-06-03'
description: Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에서 차트를 만들고 슬라이드에 차트를 추가하는 방법을
  배웁니다. 데이터 시각화를 위한 단계별 가이드를 따라보세요.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: .NET에서 Aspose.Slides for Java를 사용하여 차트 만들기
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET에서 Aspose.Slides for Java를 사용하여 차트 만들기

## 소개
매력적인 프레젠테이션을 만들려면 청중의 이해와 참여를 높이기 위해 차트와 같은 시각적 데이터 표현을 통합하는 경우가 많습니다. **.NET에서 차트를 만들고 싶다면**, Aspose.Slides for Java는 .NET 애플리케이션 내에서 원활하게 작동하는 강력하고 언어에 구애받지 않는 API를 제공합니다. 이 튜토리얼에서는 프레젠테이션을 초기화하고, 다양한 차트 유형을 추가하며, 차트 데이터 워크북을 관리하고, 시리즈 데이터를 포맷하는 방법(음수 값 처리 포함)을 배웁니다. 마지막에는 프로그래밍 방식으로 프레젠테이션 파일에 차트를 생성하고 몇 줄의 코드만으로 슬라이드에 차트를 추가할 수 있게 됩니다.

## 빠른 답변
- **주요 목표는 무엇인가요?** .NET 프레젠테이션에서 Aspose.Slides for Java를 사용하여 차트를 만들기.  
- **필요한 라이브러리 버전은?** Aspose.Slides for Java 25.4 이상.  
- **라이선스가 필요합니까?** 개발용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **Maven 또는 Gradle을 사용할 수 있나요?** 예—두 빌드 시스템 모두 지원됩니다.  
- **어떤 차트 유형을 사용할 수 있나요?** 클러스터형 컬럼, 라인, 파이, 바, 영역 등 다양한 차트.

## Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에 차트를 만드는 방법?
`Presentation` 클래스는 PowerPoint 파일을 나타내며 슬라이드를 조작하는 메서드를 제공합니다. 새로운 `Presentation` 객체를 로드하고, `slides.addEmptySlide()`를 호출하여 슬라이드를 얻은 다음, `slide.getShapes().addChart()`를 사용해 지정한 좌표에 원하는 차트 유형을 삽입합니다. 차트를 추가한 후에는 시리즈와 카테고리로 데이터 워크북을 채우고, 음수 값에 대한 색상과 같은 서식을 적용한 뒤, 프레젠테이션을 .pptx 파일로 저장합니다. 이 흐름을 통해 **.NET에서 차트를 만들 수** 있는 간결한 API 호출 세트를 사용할 수 있습니다.

## Aspose.Slides for Java란?
Aspose.Slides for Java는 Microsoft Office 없이도 개발자가 PowerPoint 파일을 생성, 수정 및 렌더링할 수 있게 해 주는 크로스‑플랫폼 API입니다. **50개 이상의 입력 및 출력 형식**을 지원하며, 메모리 사용량을 200 MB 이하로 유지하면서 수천 장의 슬라이드가 포함된 프레젠테이션을 처리할 수 있습니다.

## .NET 프로젝트에서 Aspose.Slides for Java를 사용하는 이유는?
Aspose.Slides for Java는 Java Virtual Machine에서 실행되며 네이티브 래퍼를 통해 .NET에서 호출할 수 있어, .NET 개발자에게 성숙한 차트 엔진, 대용량 데이터 세트의 고성능 처리, 기존 Java 코드와의 완전한 호환성을 제공하며 로직을 다시 작성할 필요가 없습니다.

## 전제 조건
Aspose.Slides for Java로 차트를 만들기 전에 필요한 사항을 정리해 보겠습니다:

### 필요한 라이브러리 및 버전
- **Aspose.Slides for Java**: 버전 25.4 이상.

### 환경 설정 요구 사항
- .NET 애플리케이션을 지원하는 개발 환경.  
- Java 프로그래밍 개념에 대한 기본 이해.

### 지식 전제 조건
- .NET 애플리케이션 환경에서 프레젠테이션을 만드는 데 익숙함.  
- Java 의존성 및 관리 방법(Maven/Gradle)에 대한 이해.

## Aspose.Slides for Java 설정
Aspose.Slides를 사용하려면 프로젝트에 종속성으로 포함해야 합니다. 다음은 그 방법입니다:

### Maven
Maven 의존성 스니펫은 Aspose.Slides for Java를 프로젝트에 추가합니다.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` 파일에 이 줄을 포함하여 Maven Central에서 라이브러리를 가져옵니다.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 최신 버전을 다운로드할 수 있습니다.

#### 라이선스 획득 단계
- **Free Trial**: 기능을 살펴보기 위해 임시 라이선스로 시작합니다.  
- **Purchase**: 제한 없는 프로덕션 사용을 위해 라이선스를 구매합니다.

#### 기본 초기화 및 설정
`Slides` 초기화에는 라이선스를 설정하고 `Presentation` 인스턴스를 생성하는 것이 필요합니다.

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
기능 구현을 단계별로 안내합니다.

### 프레젠테이션 초기화
**Overview:**  
프레젠테이션 인스턴스를 생성하면 이후 모든 작업의 기반이 마련됩니다. 이 기능은 Aspose.Slides를 사용하여 처음부터 시작하는 방법을 보여줍니다.

#### 단계 1: 필요한 패키지 가져오기
`Presentation` 및 관련 클래스는 `com.aspose.slides` 네임스페이스에 포함됩니다.

```java
import com.aspose.slides.Presentation;
```

#### 단계 2: 새로운 Presentation 객체 생성
`Presentation` 객체를 인스턴스화하고 try‑with‑resources 블록으로 감싸서 자동으로 해제되도록 합니다.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*이렇게 하면 사용 후 프레젠테이션 객체가 적절히 해제되어 메모리 누수를 방지할 수 있습니다.*

### 슬라이드에 차트 추가
**Overview:**  
슬라이드에 차트를 추가하면 데이터 시각화를 보다 효과적이고 흥미롭게 만들 수 있습니다.

#### 단계 1: 필요한 패키지 가져오기
`Chart` 클래스는 슬라이드에 배치하고 사용자 지정할 수 있는 차트 도형을 나타냅니다.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 단계 2: 프레젠테이션 초기화 및 차트 추가
슬라이드를 만든 다음, `ChartType.ClusteredColumn`과 원하는 위치 및 크기를 지정하여 `addChart`를 호출합니다.

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

*여기서는 지정된 좌표와 크기로 첫 번째 슬라이드에 클러스터형 컬럼 차트를 추가합니다.*

### 차트 데이터 워크북 관리
**Overview:**  
차트의 데이터 워크북을 효율적으로 관리하면 시리즈와 카테고리를 원활하게 조작할 수 있습니다.

#### 단계 1: 필요한 패키지 가져오기
`IChartDataWorkbook`은 차트에서 사용하는 기본 Excel 유사 워크북에 대한 접근을 제공합니다.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 단계 2: 데이터 워크북에 접근하고 초기화
차트에서 워크북을 가져와 기존 데이터를 모두 지워 새로 시작합니다.

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

*새로운 시리즈와 카테고리를 추가할 때 깨끗한 상태로 시작하려면 워크북을 초기화하는 것이 중요합니다.*

### 차트에 시리즈 및 카테고리 추가
**Overview:**  
이 기능은 시리즈와 카테고리를 관리하여 의미 있는 데이터 포인트를 추가하는 방법을 보여줍니다.

#### 단계 1: 시리즈 및 카테고리 추가
`chart.getChartData().getSeries().add()`와 `chart.getChartData().getCategories().add()`를 사용하여 구조를 정의합니다.

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

*시리즈와 카테고리를 추가하면 데이터 프레젠테이션을 보다 체계적으로 구성할 수 있습니다.*

### 시리즈 데이터 채우기 및 포맷
**Overview:**  
차트에 데이터 포인트를 채우고 외관을 포맷하여 가독성을 높이며, 특히 음수 값을 다룰 때 유용합니다.

#### 단계 1: 시리즈 데이터 채우기
워크북의 각 셀에 숫자 값을 할당하고 음수에 대해서는 빨간색 채우기를 적용합니다.

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

*이 섹션은 데이터를 채우고 시각화를 개선하기 위해 색상 포맷을 적용하는 방법을 보여줍니다.*

## 일반적인 문제 및 해결책
- **LicenseNotFoundException** – 라이선스 파일 경로가 올바르고 런타임에 파일에 접근할 수 있는지 확인하십시오.  
- **NullPointerException on chart data** – 새로운 시리즈를 추가하기 전에 항상 워크북을 초기화하여 잔여 데이터를 방지하십시오.  
- **Chart not rendering in .NET** – .NET 호환 버전의 Aspose.Slides JAR를 사용하고 Java 런타임이 .NET 프로젝트에 올바르게 구성되었는지 확인하십시오.

## 자주 묻는 질문

**Q: GUI 없이 프레젠테이션 파일에 차트를 생성할 수 있나요?**  
A: 예, Aspose.Slides for Java는 완전 무헤드 모드이며 그래픽 구성 요소가 없는 서버에서도 작동합니다.

**Q: 지원되는 .NET 버전은 무엇인가요?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 모두 지원됩니다.

**Q: 추가할 수 있는 차트 유형은 몇 개인가요?**  
A: 컬럼, 라인, 파이, 영역, 레이더 차트를 포함해 20가지가 넘는 차트 유형을 사용할 수 있습니다.

**Q: 개별 데이터 포인트를 스타일링할 수 있나요?**  
A: 물론입니다 – `IDataPoint` API를 통해 각 데이터 포인트에 채우기 색상, 테두리, 마커 등을 설정할 수 있습니다.

**Q: Java 객체를 .NET 타입으로 수동 변환해야 하나요?**  
A: 아니요, Aspose.Slides for Java .NET 래퍼가 타입 변환을 자동으로 처리합니다.

---

**마지막 업데이트:** 2026-06-03  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides를 사용하여 .NET 프레젠테이션에 차트 삽입 및 효과적인 데이터 시각화 방법](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Aspose.Slides for .NET을 사용하여 차트 데이터 소스 유형 가져오기 - 차트 및 그래프](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Aspose.Slides .NET으로 차트 시리즈 생성 및 조작 마스터 - 효과적인 데이터 시각화](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
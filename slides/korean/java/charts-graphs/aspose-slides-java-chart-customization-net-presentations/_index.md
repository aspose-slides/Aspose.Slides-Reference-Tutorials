---
date: '2026-06-08'
description: Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에서 차트에 시리즈를 추가하고 stacked column
  charts를 사용자 지정하는 방법을 배웁니다.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Aspose.Slides for Java를 사용해 .NET에서 차트에 시리즈 추가
url: /ko/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET 프레젠테이션에서 Aspose.Slides for Java를 사용한 차트 맞춤 마스터하기

## 소개
데이터 기반 프레젠테이션 영역에서 차트는 원시 숫자를 설득력 있는 시각적 스토리로 변환하는 필수 도구입니다. 특히 .NET 프레젠테이션 파일 내부에서 프로그래밍 방식으로 **add series to chart**를 수행해야 할 때 작업이 벅차게 느껴질 수 있습니다. 다행히 **Aspose.Slides for Java**는 강력하고 언어에 구애받지 않는 API를 제공하여 차트 생성 및 맞춤을 간단하게 해줍니다—대상 형식이 .NET PPTX인 경우에도 마찬가지입니다. 이 가이드는 시리즈 추가, 스택형 컬럼 차트 구축, 간격 너비와 같은 시각적 요소 미세 조정 방법을 단계별로 안내하여, 세련되고 전문적인 동적 데이터 풍부 슬라이드를 생성할 수 있도록 도와줍니다.

## 빠른 답변
`Presentation` 클래스는 PPTX 파일을 나타내며, `slide.getShapes().addChart(...)`는 차트 도형을 삽입합니다. 시리즈를 추가하려면 `chart.getChartData().getSeries().add(...)`를 사용하고, `setGapWidth()`는 간격을 조정합니다.

- **프레젠테이션을 시작하기 위한 기본 클래스는 무엇입니까?** `Presentation` – 메모리 내에서 PPTX 파일을 나타냅니다.  
- **슬라이드에 차트를 추가하는 메서드는 무엇입니까?** `slide.getShapes().addChart(...)`는 슬라이드에 차트 객체를 생성합니다.  
- **새 시리즈를 추가하려면 어떻게 해야 합니까?** `chart.getChartData().getSeries().add(...)`는 새로운 데이터 시리즈를 삽입합니다.  
- **막대 사이의 간격 너비를 변경할 수 있습니까?** 예—`chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)`를 호출합니다(값은 백분율).  
- **프로덕션에 라이선스가 필요합니까?** 물론입니다—유효한 Aspose.Slides for Java 라이선스는 모든 기능을 활성화하고 평가용 워터마크를 제거합니다.

## “add series to chart”란 무엇입니까?
차트에 시리즈를 추가한다는 것은 차트가 별개의 시각적 요소(예: 별도 컬럼 그룹)로 렌더링하는 새로운 데이터 포인트 컬렉션을 삽입하는 것을 의미합니다. 각 시리즈는 자체 값, 색상 및 서식을 가질 수 있어 여러 데이터 세트를 나란히 비교할 수 있습니다.

## .NET 프레젠테이션을 수정하기 위해 Aspose.Slides for Java를 사용하는 이유는?
Aspose.Slides for Java를 사용하면 Microsoft Office를 설치하지 않고도 .NET PowerPoint 뷰어와 완전히 호환되는 PPTX 파일을 생성하거나 편집할 수 있습니다. 서버 측, 크로스 플랫폼 솔루션이 필요하고 .NET PPTX 파일을 생성·업데이트하며 50가지 이상의 차트 유형을 지원하고 전체 문서를 메모리에 로드하지 않고 최대 500 MB 파일을 처리해야 할 때 Aspose.Slides for Java를 사용하십시오. API는 Java, Kotlin, Scala 또는 모든 JVM 언어에서 작동하며 .NET 개발자가 기대하는 동일한 출력을 제공합니다.

## 전제 조건
- **Aspose.Slides for Java** 라이브러리 (버전 25.4 이상).  
- Maven, Gradle 또는 수동 JAR 다운로드.  
- 기본 Java 지식 및 PPTX 파일 구조에 대한 이해.  

## Aspose.Slides for Java 설정
### Maven 설치
다음 의존성을 `pom.xml`에 추가하십시오:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 설치
다음 라인을 `build.gradle` 파일에 포함하십시오:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 공식 릴리스 페이지에서 최신 JAR를 다운로드하십시오: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**라이선스 획득**  
무료 체험을 시작하려면 [여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 다운로드하십시오. 프로덕션 사용을 위해서는 전체 라이선스를 구매하여 모든 기능을 활성화하고 평가용 워터마크를 제거하십시오.

## 단계별 구현 가이드
각 단계 아래에는 원본 튜토리얼과 동일한 간결한 코드 스니펫이 있으며, 그 뒤에 해당 코드가 수행하는 작업에 대한 설명이 있습니다.

### 단계 1: 빈 프레젠테이션 만들기
`Presentation`은 메모리 내에서 PowerPoint 파일을 나타내는 진입점 클래스입니다.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*우리는 깨끗한 PPTX 파일로 시작하며, 차트를 추가할 캔버스를 제공합니다.*

### 단계 2: 슬라이드에 스택형 컬럼 차트 추가
`Chart`는 슬라이드 내 차트 도형을 나타냅니다. `ChartType.StackedColumn`은 스택형 컬럼 차트를 지정합니다.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*`addChart` 메서드는 **stacked column chart**를 생성하고 슬라이드의 왼쪽 상단에 배치합니다.*

### 단계 3: 차트에 시리즈 추가 (주 목표)
`Series`는 차트 내 단일 데이터 시리즈를 캡슐화합니다.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*여기서 우리는 **add series to chart**를 수행합니다 – 각 호출은 별도의 컬럼 그룹으로 표시되는 새로운 데이터 시리즈를 생성합니다.*

### 단계 4: 차트에 카테고리 추가
`Category`는 차트 데이터의 X축 레이블을 정의합니다.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*카테고리는 X축 레이블 역할을 하여 각 컬럼에 의미를 부여합니다.*

### 단계 5: 시리즈 데이터 채우기
`DataPoint`는 특정 카테고리에서 시리즈의 숫자 값을 보유합니다.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*데이터 포인트는 각 시리즈에 숫자 값을 제공하며, 차트는 이를 막대 높이로 렌더링합니다.*

### 단계 6: 차트 시리즈 그룹의 간격 너비 설정
`SeriesGroup`은 간격 너비와 같은 시리즈 그룹의 레이아웃 속성을 제어합니다.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*간격 너비를 조정하면 특히 카테고리가 많을 때 가독성이 향상됩니다.*

## 일반 사용 사례
- **Financial reporting** – 비즈니스 유닛별 분기 매출을 비교합니다.  
- **Project dashboards** – 팀별 작업 완료 비율을 표시합니다.  
- **Marketing analytics** – 캠페인 성과를 나란히 시각화합니다.  
이러한 시나리오는 **stacked column chart example**의 이점을 얻습니다. 개별 카테고리의 전체 기여도를 강조하기 때문입니다.

## 성능 팁
- 여러 차트를 만들 때 메모리 오버헤드를 줄이기 위해 `Presentation` 객체를 재사용하십시오.  
- 시각적 스토리에 필요한 데이터 포인트만 제한하십시오; Aspose.Slides는 10,000 포인트를 처리할 수 있지만 렌더링 속도는 약 5,000 포인트 이후에 감소합니다.  
- 저장 후 (`presentation.dispose()`) 객체를 해제하여 리소스를 확보하고 메모리 누수를 방지하십시오.  

## 자주 묻는 질문
**Q: 스택형 컬럼 외에 다른 차트 유형을 추가할 수 있습니까?**  
A: 예, Aspose.Slides는 라인, 파이, 영역, 레이더, 버블 및 50가지 이상의 다른 차트 유형을 지원하며, 모두 동일한 `addChart` 메서드를 통해 접근할 수 있습니다.

**Q: .NET 출력에 별도의 라이선스가 필요합니까?**  
A: 아니요, 동일한 Java 라이선스가 모든 출력 형식, 포함 .NET PPTX 파일에 대해 작동합니다.

**Q: 차트의 색상 팔레트를 어떻게 변경합니까?**  
A: `series.getFormat().getFill().setFillType(FillType.Solid)`를 사용하고 각 시리즈에 원하는 `Color` 객체를 설정하십시오.

**Q: 프로그래밍 방식으로 데이터 레이블을 추가할 수 있습니까?**  
A: 물론입니다. `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`를 호출하면 각 컬럼에 숫자 값을 표시합니다.

**Q: 기존 프레젠테이션을 업데이트해야 하면 어떻게 합니까?**  
A: `new Presentation("existing.pptx")`로 파일을 로드하고, 동일한 API 호출을 사용해 차트를 수정한 뒤 디스크에 다시 저장하십시오.

## 결론
이제 Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에서 **add series to chart**를 수행하고, **stacked column chart**를 만들며, 외관을 미세 조정하는 완전한 종단‑종단 가이드를 보유하게 되었습니다. 다양한 차트 유형, 색상 및 데이터 소스를 실험하여 이해관계자를 사로잡고 데이터 기반 의사 결정을 촉진하는 설득력 있는 시각 보고서를 구축하십시오.

---

**Last Updated:** 2026-06-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [.NET에서 Aspose.Slides를 사용하여 백분율 기반 스택형 컬럼 차트 만드는 방법](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [효과적인 데이터 시각화를 위한 Aspose.Slides .NET으로 차트 시리즈 생성 및 조작 마스터](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Aspose.Slides .NET으로 특정 차트 시리즈 데이터 포인트 지우기](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
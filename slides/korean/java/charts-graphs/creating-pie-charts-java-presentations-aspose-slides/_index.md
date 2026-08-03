---
date: '2026-08-01'
description: Aspose Slides 라이선스를 사용하여 Java 프레젠테이션에서 pie charts를 만들고 사용자 지정하는 방법을 배웁니다.
  단계별 지침을 따라 pie chart 데이터를 구성하고 차트 슬라이드를 효율적으로 추가하세요.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Aspose Slides 라이선스를 사용하여 Java 프레젠테이션에서 pie charts를 만들고 사용자 지정하는 방법을
  배웁니다. 단계별 지침을 따라 pie chart 데이터를 구성하고 차트 슬라이드를 효율적으로 추가하세요.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Aspose Slides 라이선스를 사용하여 Java에서 pie charts 만들기
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Aspose Slides 라이선스를 사용하여 Java에서 pie charts 만들기
url: /ko/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java 프레젠테이션에서 파이 차트 만들기

## 소개

전문적인 프레젠테이션을 만들고 싶다면 **Aspose Slides 라이선스**를 통해 차트를 프로그래밍 방식으로 생성하고 스타일링할 수 있습니다. 이 가이드에서는 파이 차트를 만드는 방법, 데이터를 구성하는 방법, 그리고 Java 슬라이드 데크에 삽입하는 방법을 배웁니다—Microsoft PowerPoint에 의존하지 않고. 설정 과정, 코드 흐름, 그리고 모범 사례 팁을 단계별로 안내하여 몇 분 안에 깔끔한 시각 보고서를 제공할 수 있습니다.

**배우게 될 내용:**
- 유효한 라이선스로 Aspose.Slides for Java 설정하기
- 파이 차트를 만들고 사용자 정의하는 단계
- 파이 차트 데이터를 구성하고 차트 슬라이드를 추가하는 방법
- 일반적인 함정 및 성능 팁

환경이 준비되었는지 확인해 봅시다.

## 빠른 답변
- **Aspose Slides 라이선스로 무엇을 할 수 있나요?** 전체 기능 차트 생성, PDF/HTML로 내보내기, 워터마크 제거.
- **필요한 Java 버전은 무엇인가요?** JDK 16 이상.
- **Maven 또는 Gradle이 필요합니까?** 둘 중 하나면 됩니다; 라이브러리는 두 방식 모두 제공됩니다.
- **파이 차트가 보유할 수 있는 데이터 포인트 수는?** 메모리 문제 없이 최대 10 000 포인트.
- **슬라이드를 이미지로 내보낼 수 있나요?** 예 – PNG, JPEG, SVG 등 다양한 형식을 지원합니다.

## 사전 요구 사항
- **필수 라이브러리:** Aspose.Slides for Java (버전 25.4 이상) – 이 버전은 최신 파일 형식 및 성능 최적화를 지원합니다.
- **환경 설정:** IDE 또는 빌드 시스템에 JDK 16+가 설치되고 구성되어 있어야 합니다.
- **기본 지식:** Java, Maven 또는 Gradle, 객체 지향 프로그래밍 개념에 익숙해야 합니다.

## Aspose.Slides for Java 설정

To use Aspose.Slides for Java, include it in your project. Here’s how to add the dependency with the most common build tools:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Direct Download:** 최신 JAR 파일은 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드할 수 있습니다.

### 라이선스 획득

Aspose는 모든 기능을 사용할 수 있는 무료 체험을 제공하지만, **유효한 Aspose Slides 라이선스**가 평가용 워터마크를 제거하고 성능 이점을 얻기 위해 프로덕션 사용에 필요합니다. 구매 옵션은 [purchase page](https://purchase.aspose.com/buy) 에 나와 있습니다. 라이선스 파일을 획득한 후, 애플리케이션 시작 시 한 번 로드합니다:

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## 구현 가이드

### 프레젠테이션에 파이 차트 만들기 및 추가

#### 개요
이 섹션에서는 파이 차트를 만들고, 데이터 시리즈를 구성하며, 차트를 슬라이드에 삽입하는 방법을 설명합니다. 프레젠테이션 객체 초기화부터 최종 파일 저장까지 전체 흐름을 확인할 수 있습니다.

#### 1단계: 프레젠테이션 초기화  
`Presentation`은 Aspose.Slides의 최상위 객체로 메모리 내에서 PowerPoint 파일을 나타냅니다. 인스턴스를 생성하면 수정할 준비가 된 빈 슬라이드 데크가 제공됩니다.

```java
demo.Presentation pres = new demo.Presentation();
```  
이 라인은 이후 모든 변경 사항이 적용될 새 프레젠테이션을 생성합니다.

#### 2단계: 슬라이드에 파이 차트 추가  
`Chart`는 파이 차트를 포함한 차트 객체를 캡슐화하는 클래스입니다. 차트를 슬라이드에 추가하는 것은 위치와 크기를 지정하는 단일 메서드 호출입니다.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` 및 `yPosition`은 차트의 좌상단 모서를 설정합니다.  
- `width`와 `height`는 슬라이드에서 차트의 시각적 크기를 정의합니다.

#### 3단계: 파이 차트 데이터 구성  
`ChartData`는 차트의 데이터 시리즈를 보관합니다.  
**파이 차트 데이터를 어떻게 구성하나요?**  
먼저 간결한 답변을 제공합니다: `ChartData` 컬렉션에 시리즈를 추가하고, `ChartDataPoint` 객체에 숫자 값과 카테고리 이름을 채워 넣습니다. 이 방법을 사용하면 라벨 서식을 유지하면서 최대 10 000개의 슬라이스를 표시할 수 있습니다. 데이터를 설정한 후에는 색상, 범례 및 데이터 라벨을 기업 스타일 가이드에 맞게 사용자 정의할 수 있습니다.

이제 두 개의 카테고리를 추가하고 라벨을 표시하는 코드를 소개합니다:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
이 스니펫은 데이터 시리즈를 생성하고 두 개의 포인트를 삽입하며 차트에 카테고리 라벨을 활성화합니다.

#### 4단계: 프레젠테이션 저장  
마지막으로 원하는 파일 형식(PPTX, PDF, PNG 등)으로 프레젠테이션을 저장합니다. `save` 메서드는 활성 라이선스를 준수하여 평가용 워터마크가 나타나지 않도록 합니다.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### 일반적인 문제 및 해결책
- **라이선스 누락 오류:** 라이선스 파일 경로가 올바른지 확인하고 Aspose.Slides 호출 전에 `License` 객체를 인스턴스화하십시오.
- **빈 차트:** `ChartData` 시리즈에 최소 하나의 `ChartDataPoint`가 포함되어 있는지 확인하십시오. 빈 시리즈는 차트 영역이 비게 됩니다.
- **대용량 데이터 세트에서 성능 지연:** 사용되지 않는 슬라이드를 `presentation.getSlides().removeAt(index)` 로 제거하고, 무거운 처리 후 `System.gc()` 를 호출하십시오.

## 실용적인 적용 사례
1. **비즈니스 보고서:** 단일 파이 차트로 지역별 시장 점유율 또는 매출 분포를 시각화합니다.
2. **학술 프레젠테이션:** 설문 결과나 실험 결과를 명확하고 이해하기 쉬운 형식으로 보여줍니다.
3. **프로젝트 대시보드:** 작업 완료 비율이나 자원 할당을 슬라이드에 즉시 표시합니다.

또한 Aspose.Slides를 JDBC와 결합하여 데이터베이스에서 실시간 데이터를 가져와 주간 임원 브리핑용 최신 차트를 생성할 수 있습니다.

## 성능 고려 사항
많은 고해상도 이미지 또는 대용량 데이터 세트를 포함하는 프레젠테이션을 다룰 때:
- `try‑with‑resources` 또는 명시적 `dispose()` 호출을 사용하여 객체를 즉시 해제하십시오.
- 메모리 사용량을 낮게 유지하기 위해 슬라이드 리소스의 지연 로딩을 활성화하십시오.
- 배치 처리 시 가능한 경우 단일 `Presentation` 인스턴스를 재사용하여 JVM 오버헤드를 줄이십시오.

## 결론
이제 **Aspose Slides 라이선스**를 사용하여 Java에서 파이 차트를 만들기 위한 완전한 프로덕션 워크플로우를 갖추었습니다. 추가 차트 유형(막대, 선, 도넛 등)을 실험하여 슬라이드를 더욱 풍부하게 만들 수 있습니다. 다음 단계로 API의 내보내기 기능을 탐색하여 PDF 보고서나 PNG 이미지를 자동으로 생성해 보세요.

## 자주 묻는 질문

**Q: 단일 슬라이드에 여러 차트를 어떻게 추가하나요?**  
A: 각 차트마다 `slide.getShapes().addChart()` 를 호출하고, 각 인스턴스에 고유한 좌표와 크기를 지정합니다.

**Q: Java용 Aspose.Slides의 대안은 무엇인가요?**  
A: Apache POI와 JFreeChart가 일반적인 대안이지만, 포괄적인 내보내기 옵션과 Aspose의 라이선스 모델을 제공하지 않습니다.

**Q: Aspose.Slides를 사용해 프레젠테이션을 다른 형식으로 변환할 수 있나요?**  
A: 예—단일 `save` 호출로 PDF, XPS, HTML, PNG, JPEG, SVG 등 다양한 형식으로 내보낼 수 있습니다.

**Q: 대규모 개발 팀을 위한 라이선스 관리는 어떻게 하나요?**  
A: 여러 개발자와 서버를 포괄하는 엔터프라이즈 라이선스를 구매하십시오; 볼륨 할인은 Aspose 영업팀에 문의하세요.

**Q: 차트 데이터가 자주 업데이트되면 어떻게 해야 하나요?**  
A: Aspose.Slides를 데이터 소스(예: SQL 쿼리)와 통합하고 런타임에 차트를 재구성하십시오; API는 동적 데이터 바인딩을 지원합니다.

## 리소스
- **문서:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **다운로드:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **구매:** [Buy a License](https://purchase.aspose.com/buy)
- **무료 체험:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **임시 라이선스:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **지원:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**마지막 업데이트:** 2026-08-01  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용하여 프레젠테이션에 차트 추가 및 구성 방법](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Aspose.Slides를 사용하여 Java 프레젠테이션에서 차트 만들기 및 사용자 정의](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Aspose.Slides Java로 프레젠테이션 만들기 및 구성 방법: 단계별 가이드](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-07-17'
description: Aspose.Slides for Java를 사용하여 Pie of Pie Chart를 만들면서 PowerPoint에 chart를
  추가하는 방법을 배웁니다. setup, code, customization, saving을 포함하고 PPTX로 저장합니다.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java를 사용하여 PowerPoint에 chart를 추가합니다. 이 가이드는 몇 분
  안에 Pie of Pie chart를 만들고, customize하고, PPTX로 save하는 방법을 보여줍니다.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: PowerPoint에 Chart 추가 – Java에서 Pie of Pie Chart 만들기
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: PowerPoint에 Chart 추가 – Java와 Aspose.Slides를 사용하여 Pie of Pie Chart 만들기
url: /ko/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint에 차트 추가 – Aspose.Slides for Java로 파이 오브 파이 차트 만들기

## 차트 및 그래프

### 소개

현대의 데이터 기반 프레젠테이션에서 **PowerPoint에 차트 추가**는 원시 데이터를 시각적 인사이트로 전환하는 가장 빠른 방법 중 하나입니다. 일반 파이 차트는 몇 개의 카테고리에는 잘 맞지만, 일부 슬라이스가 매우 작으면 읽기 어려워집니다. *파이 오브 파이* 차트는 이러한 작은 슬라이스를 보조 파이로 분리하여 메인 차트를 깔끔하게 유지하고 세부 정보를 쉽게 확인할 수 있게 합니다.

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 파이 오브 파이 차트를 만들면서 **PowerPoint에 차트 추가** 방법을 배웁니다. 환경 설정, 차트 생성, 레이블 사용자 정의, 분할 위치 조정, 그리고 최종적으로 프레젠테이션을 PPTX 파일로 저장하는 과정을 단계별로 안내합니다. 끝까지 진행하면 어떤 슬라이드 데크에도 정교한 차트를 삽입할 준비가 됩니다.

## 빠른 답변
Aspose.Slides에서 `Presentation`은 PPTX 파일을 나타내고, `ChartType.PieOfPie`는 파이 오브 파이 차트를 선택하며, `setShowValue(true)`는 레이블에 값을 표시하고, `save`는 파일을 저장합니다.

- **PowerPoint 조작을 위한 기본 클래스는 무엇입니까?** `Presentation` – 메모리 내 전체 PPTX 파일을 나타냅니다.  
- **작은 슬라이스를 위한 보조 파이를 생성하는 차트 유형은?** `ChartType.PieOfPie`.  
- **각 슬라이스에 값을 표시하려면 어떻게 합니까?** `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`를 설정합니다.  
- **파일을 직접 PPTX로 저장할 수 있나요?** 예 – `presentation.save("output.pptx", SaveFormat.Pptx)`를 호출합니다.  
- **개발에 라이선스가 필요합니까?** 무료 30일 체험판으로 테스트가 가능하며, 영구 라이선스는 평가 워터마크를 제거합니다.

## 파이 오브 파이 차트란?
**파이 오브 파이 차트**는 두 단계의 파이 시각화로, 하나 이상의 작은 슬라이스를 별도의 연결된 파이로 분리하여 읽기 쉽게 합니다. Aspose.Slides는 이 차트 유형을 기본적으로 지원하며, 분할 크기, 위치 및 레이블 형식을 제어할 수 있습니다.

## 왜 Aspose.Slides로 PowerPoint에 차트를 추가하나요?
Aspose.Slides는 Microsoft Office 없이도 PowerPoint 파일을 생성, 편집 및 렌더링할 수 있습니다. **50개 이상의 입력 및 출력 형식**을 지원하고, 일반 서버 하드웨어에서 **최대 500슬라이드** 프레젠테이션을 1초 미만에 처리하며, 차트 스타일링, 데이터 레이블 및 레이아웃에 대한 **전체 API 제어**를 제공하므로 자동화된 보고 파이프라인에 이상적입니다.

## 전제 조건

시작하기 전에 다음이 설치되어 있는지 확인하십시오:

- **Java Development Kit (JDK) 16+**가 설치되어 있어야 합니다.  
- **IntelliJ IDEA**, **Eclipse**, 또는 **NetBeans**와 같은 IDE.  
- 의존성 관리를 위한 Maven 또는 Gradle(아래 섹션 참조).  
- 기본적인 Java 지식 및 프로젝트 빌드에 대한 친숙함.

## Aspose.Slides for Java 설정

### 설치 정보

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

**Direct Download:** 최신 버전은 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드할 수 있습니다.

### 라이선스 획득 단계
- **Free Trial:** 모든 기능을 탐색하기 위해 30일 체험판으로 시작합니다.  
- **Temporary License:** 연장된 평가를 위해 임시 키를 요청합니다.  
- **Purchase:** 평가 워터마크를 제거하고 프로덕션에서 사용하기 위해 영구 라이선스를 획득합니다.

### 기본 초기화 및 설정
`Presentation`은 PowerPoint 파일을 생성하기 위한 주요 객체이며, `Chart`는 슬라이드 내 차트 도형을 나타냅니다.

```java
Presentation presentation = new Presentation();
```  

이 코드는 슬라이드와 차트를 추가할 수 있는 빈 프레젠테이션을 생성합니다.

## 구현 가이드

### Aspose.Slides for Java를 사용하여 PowerPoint에 차트를 추가하려면 어떻게 해야 하나요?
새 `Presentation`을 로드하고 슬라이드를 추가한 뒤 `PieOfPie` 유형의 `Chart`를 삽입합니다. API 호출 흐름은 간결합니다: 차트를 생성하고, 시리즈 데이터를 채우고, 레이블 가시성을 조정하고, 보조 파이 크기를 구성한 뒤 최종적으로 저장합니다. 전체 과정은 보통 20줄 이하의 코드로 구현 가능해 자동 보고서 생성에 이상적입니다.

### '파이 오브 파이' 차트 만들기

#### 개요
첫 번째 슬라이드에 파이 오브 파이 차트를 만들고, 가장 작은 슬라이스를 분리한 뒤 각 세그먼트에 값을 레이블로 표시합니다.

#### 단계 1: Presentation 클래스 인스턴스 생성
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
이 코드는 이후 슬라이드와 차트를 위한 컨테이너를 초기화합니다.

#### 단계 2: 첫 번째 슬라이드에 '파이 오브 파이' 차트 추가
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
여기서는 `ChartType.PieOfPie`를 지정하고 슬라이드 캔버스 상에서 차트의 위치(X, Y)와 크기(너비, 높이)를 정의합니다.

#### 단계 3: 시리즈에 대한 데이터 레이블을 값 표시로 설정
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
`showValue`를 활성화하면 각 슬라이스가 숫자 값을 표시하게 되며, 이는 빠른 데이터 해석에 필수적입니다.

#### 단계 4: 보조 파이 크기 및 백분율 기준 분할 설정
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
이 옵션을 통해 차트 중 보조 파이에 할당되는 비율과 백분율 임계값에 따라 이동할 슬라이스를 결정할 수 있습니다.

#### 단계 5: PPTX 형식으로 프레젠테이션을 디스크에 저장
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** 절대 경로나 Java의 `Paths.get()`을 사용하여 플랫폼별 구분자를 피하십시오.

## 일반적인 문제 및 해결책

`License` 클래스는 평가 제한을 제거하기 위해 라이선스 파일을 로드합니다.

- **Missing license warning:** 차트에 “Evaluation Only”가 표시되면 `License license = new License(); license.setLicense("Aspose.Slides.lic");`와 같이 유효한 라이선스 파일을 적용했는지 확인하십시오.  
- **Incorrect slice split:** `splitBy` 속성이 `SplitBy.Percentage`로 설정되어 있고 `secondPieSize`가 0~100 사이 값인지 확인하십시오.  
- **Data not displaying:** 차트 시리즈에 최소 하나의 데이터 포인트가 포함되어 있는지 확인하십시오. 그렇지 않으면 차트가 비어 있게 렌더링됩니다.

## 자주 묻는 질문

`IChart`는 슬라이드에 추가할 수 있는 차트 객체를 나타냅니다.

**Q: 하나의 프레젠테이션에 여러 차트를 생성할 수 있나요?**  
A: 예, 각 슬라이드 또는 위치마다 새로운 `IChart`를 인스턴스화하면 됩니다; API는 파일당 무제한 차트 객체를 허용합니다.

`SaveFormat.Pdf`는 저장을 위한 PDF 출력 형식을 지정합니다.

**Q: Aspose.Slides가 PDF 저장도 지원하나요?**  
A: 물론입니다 – `presentation.save("output.pdf", SaveFormat.Pdf)`를 호출하면 동일한 슬라이드 데크를 PDF로 내보낼 수 있습니다.

`IPortion`은 파이 차트의 개별 슬라이스를 나타냅니다.

**Q: 파이 오브 파이 차트가 처리할 수 있는 최대 데이터 포인트 수는 얼마인가요?**  
A: 라이브러리는 시리즈당 최대 **10,000**개의 데이터 포인트를 지원하며, 이는 사용 가능한 메모리에 의해 제한됩니다.

**Q: 개별 슬라이스의 색상을 사용자 정의할 수 있나요?**  
A: 예, `chart.getChartData().getSeries().get_Item(0).getPortions()`를 통해 각 `IPortion`에 접근하고 `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`를 설정하면 됩니다.

**Q: 생성된 PPTX를 웹 애플리케이션에 어떻게 삽입합니까?**  
A: 파일을 저장한 후 `HttpServletResponse`와 `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`을 사용하여 클라이언트에 직접 스트리밍합니다.

## 결론

이제 Aspose.Slides for Java를 사용하여 파이 오브 파이 차트를 만들면서 **PowerPoint에 차트 추가**를 위한 완전하고 프로덕션 준비된 레시피를 갖추었습니다. 다양한 분할 임계값, 레이블 형식 및 색상 스키마를 실험하여 브랜드 가이드라인에 맞추세요. 다음으로 스택형 막대 차트나 레이더 차트와 같은 다른 차트 유형을 탐색하여 자동화된 슬라이드 데크를 더욱 풍부하게 만들 수 있습니다.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## 관련 튜토리얼

- [동적 차트 Java 만들기 – Aspose.Slides용 PowerPoint 차트 튜토리얼](/slides/java/charts-graphs/)
- [Aspose.Slides for Java로 PowerPoint에 파이 차트 추가하는 방법](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
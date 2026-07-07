---
date: '2026-07-03'
description: Aspose.Slides를 사용하여 Java에서 Sunburst 차트를 단계별로 만드는 방법을 배우고, PowerPoint
  프레젠테이션에 대한 완전한 맞춤 설정 옵션을 제공합니다.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Aspose.Slides를 사용하여 Java에서 Sunburst 차트를 만드는 방법
url: /ko/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java에서 Aspose.Slides를 사용하여 Sunburst 차트 만들기

## 소개
오늘날 데이터 기반 프레젠테이션에서 **Sunburst 차트 만드는 방법**을 빠르게 구현하면 슬라이드가 돋보일 수 있습니다. 이 튜토리얼은 프로젝트 설정부터 최종 내보내기까지 Aspose.Slides for Java로 Sunburst 차트를 만드는 과정을 단계별로 안내하여 Java 환경을 떠나지 않고도 설득력 있는 계층형 데이터 그래픽을 제공할 수 있게 합니다.

## 빠른 답변
- **PowerPoint 파일의 주요 클래스는 무엇입니까?** `Presentation` – 메모리에서 전체 PPTX를 나타냅니다.  
- **기본 Sunburst에 필요한 코드 라인은 몇 줄입니까?** 라이브러리를 참조하면 일반적으로 5–7줄이면 됩니다.  
- **지원되는 출력 형식은 무엇입니까?** PPTX, PDF, PNG, SVG, and HTML.  
- **개별 세그먼트를 스타일링할 수 있나요?** Yes – fill colors, borders, and data labels are fully customizable.  
- **프로덕션에 라이선스가 필요합니까?** A free evaluation works for testing; a commercial license is required for deployment.

## Sunburst 차트란?
Sunburst 차트는 계층형 데이터를 동심원 형태로 시각화하며, 각 원은 계층의 수준을 나타냅니다. 이를 통해 관객은 한눈에 부모‑자식 관계를 파악할 수 있어 조직도, 분류 체계, 다중 수준 메트릭 등에 이상적입니다. 특히 제품 라인, 지리적 지역, 조직 구조와 같은 다중 수준 카테고리를 표시할 때 전체 분포와 각 세그먼트 내 상세 분해를 동시에 보여줄 수 있습니다.

## Sunburst 차트에 Aspose.Slides를 사용하는 이유
Aspose.Slides는 **30개 이상의 차트 유형**을 지원하고, **500 MB**까지 파일을 메모리 전체를 로드하지 않고 처리하며, **300 DPI**로 그래픽을 렌더링해 선명한 출력을 제공합니다. 이러한 정량적 기능은 대규모 프레젠테이션에서도 빠른 생성과 고품질 시각화를 보장합니다. 또한 라이브러리는 스레드 안전한 작업을 제공하고, 인기 있는 Java 빌드 도구와 원활히 통합되어 데스크톱 및 서버 측에서 대규모 프레젠테이션 생성을 지원합니다.

## 사전 요구 사항
- Java Development Kit (JDK) 8 이상.  
- Maven 또는 Gradle을 사용한 종속성 관리.  
- Aspose.Slides for Java (최신 버전).  
- 계층형 데이터 구조에 대한 기본 이해.

## Sunburst 차트를 단계별로 만드는 방법?
환경을 설정하고, 차트를 추가하고, 계층형 데이터를 입력하고, 스타일을 지정한 뒤 파일을 저장하면 됩니다. 아래 워크플로우는 추가적인 보일러플레이트 코드 없이 바로 따라 할 수 있는 정확한 절차를 제공합니다. 이 과정은 완전 자동화되어 있어 UI 조작 없이 배치 작업이나 웹 서비스에 통합해 필요 시 차트를 생성할 수 있습니다.

### 단계 1: 프로젝트 설정
`pom.xml`에 Aspose.Slides Maven 의존성을 추가합니다(또는 해당 Gradle 스니펫). 이렇게 하면 필요한 모든 바이너리와 전이 종속성이 자동으로 가져와집니다.

### 단계 2: 프레젠테이션 로드 또는 생성
`Presentation`은 Aspose.Slides의 최상위 객체로 메모리에서 단일 PowerPoint 파일을 나타냅니다. 새 프레젠테이션을 만들려면 `new Presentation()`을 사용하고, 기존 PPTX를 열려면 파일 경로를 전달합니다.

### 단계 3: Sunburst 차트 추가
`slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`를 사용해 슬라이드에 새로운 차트 도형을 삽입합니다. 이는 데이터 입력을 위한 Sunburst 자리표시자를 생성합니다. `ChartType.Sunburst`는 차트를 추가할 때 Sunburst 차트 유형을 지정합니다.

### 단계 4: 계층형 데이터 채우기
`ChartData`는 차트의 데이터 시리즈와 카테고리를 보관합니다. 차트의 `ChartData` 컬렉션에 접근해 계층을 반영하는 시리즈와 카테고리를 추가합니다. 각 수준마다 `ParentSeries` 속성을 통해 부모‑자식 관계를 지정하면 차트가 자동으로 동심원을 그립니다.

### 단계 5: 외관 사용자 정의
`ChartSeries`와 `ChartDataPoint` 객체를 통해 세그먼트 색상, 테두리 스타일, 데이터 레이블을 미세 조정합니다. `ChartSeries`는 차트 내 데이터 포인트 시리즈를, `ChartDataPoint`는 시리즈 내 개별 데이터 포인트를 나타냅니다. 또한 3‑D 회전을 활성화하거나 `Explode` 속성을 설정해 특정 슬라이스를 강조할 수 있습니다.

### 단계 6: 프레젠테이션 저장
`SaveFormat` 열거형은 저장 가능한 파일 형식을 정의합니다. `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)`를 호출해 파일을 디스크에 기록합니다. `SaveFormat` 값을 변경하면 PDF나 PNG 등으로도 내보낼 수 있습니다.

## Sunburst 차트 색상 사용자 정의 방법
각 `ChartDataPoint`에 대해 `point.getFillFormat().setFillType(FillType.Solid)`를 호출한 뒤 `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`로 채우기 색상을 지정합니다. 이 직접적인 접근 방식으로 기업 브랜드 색상에 맞추거나 핵심 데이터 포인트를 강조할 수 있습니다. 그라디언트 채우기, 투명도 조정, 테마 색상 적용 등으로 슬라이드 전체 디자인과 일관성을 유지할 수도 있습니다.

## 일반적인 문제와 해결책
- **Problem:** Hierarchy appears flat.  
  **Solution:** Ensure each child series correctly references its `ParentSeries`. Missing links cause the chart to treat all data as a single level.
- **Problem:** Exported PNG looks blurry.  
  **Solution:** Increase the export DPI by setting `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.
- **Problem:** Large PPTX files cause OutOfMemoryError.  
  **Solution:** Use `Presentation.setMemoryOptimization(true)` to stream data and keep memory usage low.

## 자주 묻는 질문

**Q: CSV 파일에서 Sunburst 차트를 생성할 수 있나요?**  
A: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s `ChartData` collection before saving.

**Q: Aspose.Slides가 Sunburst 차트에 대한 애니메이션 전환을 지원하나요?**  
A: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)` for chart‑level animation.

**Q: 차트를 SVG 벡터 그래픽으로 내보낼 수 있나요?**  
A: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable vector version of the Sunburst chart.

**Q: Sunburst 차트가 처리할 수 있는 최대 데이터 포인트 수는 얼마인가요?**  
A: Aspose.Slides reliably processes up to **10,000** data points in a single Sunburst chart without performance degradation.

**Q: 각 배포 환경마다 별도의 라이선스가 필요합니까?**  
A: A single commercial license covers all environments (development, staging, production) as long as the license terms are respected.

## 결론
이제 Aspose.Slides for Java를 사용해 **Sunburst 차트 만드는 방법**에 대한 완전한 단계별 가이드를 확보했습니다. 위 워크플로우를 따르면 어떤 PowerPoint 프레젠테이션에서도 고품질의 완전 맞춤형 계층형 시각화를 손쉽게 생성할 수 있습니다.

---

**마지막 업데이트:** 2026-07-03  
**테스트 환경:** Aspose.Slides for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가하는 방법: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [동적 프레젠테이션을 위한 Aspose.Slides Java를 활용한 PowerPoint 차트 맞춤 마스터](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Aspose.Slides for Java로 PowerPoint 차트 카테고리 애니메이션 적용 | 단계별 가이드](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
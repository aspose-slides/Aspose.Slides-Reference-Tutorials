---
date: '2026-09-02'
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 funnel chart를 만드는 방법을 배웁니다.
  이 단계별 가이드에서는 차트 데이터 설정, 색상 맞춤 및 프레젠테이션 내보내기를 다룹니다.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Aspose.Slides for Java를 사용하여 PowerPoint에서 funnel chart를 만드는 방법을 배웁니다.
  이 가이드는 데이터 설정, 색상 맞춤 및 최종 프레젠테이션 내보내기를 안내합니다.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Aspose.Slides for Java를 사용하여 PowerPoint에서 funnel chart 만들기
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Aspose.Slides for Java를 사용하여 PowerPoint에서 funnel chart 만들기
url: /ko/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 Aspose.Slides for Java로 퍼널 차트 만들기 마스터

## 소개
매력적인 프레젠테이션을 만드는 것은 데이터 시각화, 디자인, 스토리텔링이 결합된 예술입니다. 다단계 프로세스를 즉시 명확히 보여주는 강력한 시각 요소가 바로 퍼널 차트입니다. 영업 파이프라인, 전환 흐름, 생산 병목 현상을 설명해야 할 때, 잘 설계된 퍼널 차트는 원시 데이터를 직관적인 내러티브로 변환합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용해 **PowerPoint에서 프로그래밍 방식으로 퍼널 차트를 생성**하고, 데이터를 구성하며, 각 구간의 색상을 커스터마이징하고, 완성된 프레젠테이션을 내보내는 방법을 배웁니다.

**배우게 될 내용**
- Maven 또는 Gradle 프로젝트에 Aspose.Slides for Java를 추가하는 방법  
- `Presentation` 객체를 인스턴스화하고 슬라이드에 접근하는 방법  
- 퍼널 차트를 삽입하고 카테고리를 정의하며 시리즈 데이터를 채우는 방법  
- 각 퍼널 슬라이스를 단색 채우기 또는 브랜드 색상으로 스타일링하는 방법  
- 프레젠테이션을 PPTX 파일로 저장하거나 슬라이드를 이미지로 내보내는 방법  

## 빠른 답변
- **Java 데이터 시각화를 위한 주요 라이브러리는?** Aspose.Slides for Java.  
- **PowerPoint에서 퍼널 차트를 만들려면?** 대상 슬라이드에서 `slide.addChart(ChartType.Funnel, …)`를 호출합니다.  
- **차트 데이터 소스를 설정하는 API는?** `IChartDataWorkbook`과 `chart.getChartData()`를 함께 사용합니다.  
- **각 퍼널 구간의 색상을 커스터마이즈할 수 있나요?** 예—`FillFormat.setFillType(FillType.Solid)`를 설정하고 `java.awt.Color`를 지정합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 상업적 배포에는 구매한 Aspose.Slides 라이선스가 필요합니다.

## Java 데이터 시각화란?
Java 데이터 시각화는 Java 애플리케이션에서 원시 데이터를 차트, 그래프 또는 인터랙티브 그래픽으로 직접 변환하는 작업을 말합니다. Aspose.Slides for Java는 100가지가 넘는 차트 유형(퍼널 차트 포함)을 PowerPoint를 수동으로 실행하지 않고도 생성할 수 있게 해 주며, 최대 500장의 슬라이드를 지원하면서 메모리 사용량을 최소화합니다.

## PowerPoint에서 퍼널 차트를 사용하는 이유
퍼널 차트는 순차 단계별 이탈률을 즉시 드러내어 영업 파이프라인, 전환 분석, 프로세스 효율성 검토 등에 이상적입니다. Aspose.Slides는 레이아웃, 구간 색상, 데이터 레이블에 대한 픽셀 단위 제어를 제공하므로 브랜드 일관성을 유지하고 PowerPoint UI에서 차트를 수동으로 편집하는 번거로움을 피할 수 있습니다.

## 전제 조건 (H2)

### 필요한 라이브러리, 버전 및 종속성
Aspose.Slides for Java를 프로젝트에 적용하려면 적절한 Maven 또는 Gradle 좌표를 포함하십시오. 이 라이브러리는 Java 8‑21을 지원하며 외부 네이티브 종속성이 없습니다.

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

또한 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/)에서 JAR 파일을 직접 다운로드할 수 있습니다.

### 환경 설정 요구 사항
JDK 8 이상이 설치되어 있고 `JAVA_HOME`이 올바른 JDK 디렉터리를 가리키는지 확인하십시오. Aspose.Slides는 Windows, macOS, Linux 등 JDK를 지원하는 모든 OS에서 실행됩니다.

### 지식 전제 조건
Java 문법, 객체 지향 프로그래밍, 프레젠테이션 파일 개념에 대한 기본적인 이해가 있으면 도움이 되지만, 코드 스니펫은 모든 수준의 개발자를 위해 충분히 설명되어 있습니다.

## Aspose.Slides for Java 설정 (H2)

1. **종속성 추가** – 위의 Maven 또는 Gradle 스니펫을 사용합니다.  
2. **라이선스 획득** –  
   - **무료 체험** – 평가용 임시 라이선스를 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)에서 다운로드합니다.  
   - **정식 라이선스** – [구매 페이지](https://purchase.aspose.com/buy)에서 프로덕션 라이선스를 구매합니다.  
3. **기본 초기화** –  

`Presentation`은 메모리 내에서 PowerPoint 파일을 나타내는 Aspose.Slides의 핵심 클래스이며, 슬라이드, 도형, 차트 객체에 접근할 수 있게 해 줍니다.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

위 코드는 새로운 `Presentation` 인스턴스를 생성하여 슬라이드 조작을 준비하고, `dispose()`를 통해 리소스를 해제하도록 보장합니다.

## 구현 가이드

우리는 완전한 퍼널 차트를 만들기 위해 필요한 각 기능을 단계별로 살펴보며, 모든 코드 자리표시자 앞에 간단한 설명 텍스트를 추가합니다.

### 기능 1: 프레젠테이션 만들기 (H2)

#### 개요
`Presentation` 클래스를 인스턴스화합니다. 이 객체는 이후 모든 작업의 진입점이 됩니다.

`Presentation`은 슬라이드 컬렉션과 전역 문서 설정을 보유하는 Aspose.Slides의 최상위 객체입니다.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

위 스니펫은 빈 프레젠테이션을 열며, 이후 `.pptx` 파일로 저장할 수 있습니다.

### 기능 2: 슬라이드에 퍼널 차트 추가 (H2)

#### 개요
첫 번째 슬라이드에 퍼널 차트를 삽입하고 크기를 정의한 뒤 차트 유형을 설정합니다.

`ChartType.Funnel`은 Aspose.Slides에게 막대나 선 차트가 아니라 퍼널 스타일 시각화를 렌더링하도록 지시합니다.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

`addChart` 호출은 차트 도형을 생성하고, 위치를 `(50, 50)` 포인트로 지정하며, 너비 `500`, 높이 `400`을 부여합니다.

### 기능 3: 차트 데이터 초기화 (H2)

#### 개요
차트를 채우기 전에 템플릿에 포함될 수 있는 모든 플레이스홀더 카테고리와 시리즈를 제거합니다.

`chart.getChartData().getCategories().clear()`는 기존 카테고리 항목을 모두 삭제하고, `chart.getChartData().getSeries().clear()`는 사전 채워진 시리즈를 제거합니다.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

이렇게 하면 사용자 정의 데이터가 정확히 원하는 대로 표시됩니다.

### 기능 4: 차트 데이터 워크북 설정 (H2)

#### 개요
`IChartDataWorkbook` 객체는 차트를 구동하는 원시 값을 저장합니다. 이를 초기화하면 셀에 직접 데이터를 기록할 수 있습니다.

`IChartDataWorkbook`은 Aspose.Slides가 차트 시리즈와 카테고리에 데이터를 공급하기 위해 사용하는 가벼운 인‑메모리 스프레드시트입니다.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

코드는 기존 셀을 모두 비우고 새 항목을 위한 워크북을 준비합니다.

### 기능 5: 차트에 카테고리 추가 (H2)

#### 개요
퍼널 왼쪽에 표시될 텍스트 라벨을 정의합니다—각 단계가 프로세스의 어느 단계인지 나타냅니다.

`chart.getChartData().getCategories().add()`는 특정 워크북 셀에 연결된 새로운 카테고리 객체를 생성합니다.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

여기서는 “Prospects”, “Qualified Leads”, “Closed Deals” 세 단계를 추가합니다.

### 기능 6: 차트에 데이터 시리즈 추가 (H2)

#### 개요
숫자 값을 퍼널에 채우고, 필요에 따라 각 슬라이스에 고유 색상을 할당합니다.

`IDataPoint`는 차트 시리즈 내의 단일 데이터 포인트를 나타냅니다.  

`chart.getChartData().getSeries().add()`는 숫자 데이터 포인트를 보관하는 시리즈를 생성하며, 각 `IDataPoint`는 자체 채우기 색상을 가질 수 있습니다.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

루프는 각 포인트에 단색 채우기를 설정하는 방법을 보여 주며, 브랜드 전용 `java.awt.Color` 상수나 무작위 색상을 사용해 시각적 다양성을 제공합니다.

## 일반적인 사용 사례 및 팁 (H2)

- **영업 파이프라인 보고** – 각 단계별로 잠재고객이 어떻게 클로즈드‑원으로 이동하는지 보여줍니다.  
- **프로세스 효율성 분석** – 제조 단계별 재료 손실 또는 시간 지연을 시각화합니다.  
- **마케팅 퍼널 검토** – 캠페인 또는 트래픽 소스별 전환율을 비교합니다.  

**프로 팁:** 무작위 색상 대신 회사 브랜드 팔레트(예: `new Color(0, 112, 192)`)를 사용해 프레젠테이션을 다른 마케팅 자산과 일관되게 유지하세요.

## 자주 묻는 질문 (H2)

**Q: 퍼널 차트의 방향을 어떻게 변경하나요?**  
A: `IChart` 객체의 `ChartOrientation` 속성을 `ChartOrientation.Vertical` 또는 `ChartOrientation.Horizontal`로 설정합니다.

**Q: 차트를 추가한 뒤 슬라이드를 이미지로 내보낼 수 있나요?**  
A: 예—`pres.getSlides().get_Item(0).getThumbnail(1, 1)`을 호출하고 결과 `java.awt.image.BufferedImage`를 PNG 또는 JPEG 파일로 저장합니다.

**Q: 카테고리가 세 개 이상 필요하면 어떻게 하나요?**  
A: `chart.getChartData().getCategories().add(...)`를 사용해 추가 카테고리를 만들고, 각 새 카테고리에 맞는 데이터 포인트를 제공하면 됩니다.

**Q: 범례를 숨길 수 있나요?**  
A: `chart.getChartTitle().setVisible(false)`와 `chart.getLegend().setVisible(false)`를 사용해 제목과 범례를 모두 제거합니다.

**Q: 개발 빌드에 라이선스가 필요합니까?**  
A: 평가용 임시 라이선스로 충분하지만, 프로덕션 배포에는 정식 상용 라이선스가 필요합니다.

---

**Last updated:** 2026-09-02  
**Tested with:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용해 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java로 PowerPoint 차트 데이터 편집하기: 종합 가이드](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java를 사용해 PowerPoint 차트에 애니메이션 추가하기 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
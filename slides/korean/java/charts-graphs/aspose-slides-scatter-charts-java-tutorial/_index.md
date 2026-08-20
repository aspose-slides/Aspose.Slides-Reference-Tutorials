---
date: '2026-07-27'
description: Aspose.Slides for Java를 사용하여 차트를 사용자 지정하는 방법. PowerPoint 차트를 만들고, 산점도
  시리즈의 스타일을 지정하며, 프레젠테이션을 효율적으로 저장하는 방법을 배웁니다.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Aspose.Slides for Java로 차트를 사용자 지정하는 방법. 이 가이드는 PowerPoint 차트를 만들고,
  산점도 포인트의 스타일을 지정하며, 프레젠테이션을 내보내는 방법을 보여줍니다.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: '차트 사용자 지정 방법: Java용 Aspose 산점도 차트'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: '차트 사용자 지정 방법: Java용 Aspose 산점도 차트'
url: /ko/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java에서 Aspose를 사용한 산점도 차트 사용자 지정

이 튜토리얼에서는 **차트를 사용자 지정하는 방법** — 특히 산점도 차트 — 을 강력한 Aspose.Slides for Java 라이브러리를 사용해 알아봅니다. 프로젝트 설정, 산점도 차트 생성, 시리즈 유형 및 마커 조정, 최종 프레젠테이션 저장 과정을 단계별로 진행합니다. 끝까지 따라오면 프로그래밍으로 전문적인 산점도 차트를 생성하고 브랜드 또는 보고 요구에 맞게 모든 시각적 요소를 맞춤 설정할 수 있게 됩니다.

## 빠른 답변
- **어떤 라이브러리가 필요합니까?** Aspose.Slides for Java (v25.4+).  
- **지원되는 Java 버전은?** JDK 8 이상.  
- **마커 모양을 변경할 수 있나요?** 예 – `MarkerStyleType`을 사용해 별, 원 등 다양한 모양을 선택합니다.  
- **파일을 어떻게 저장하나요?** `pres.save("output.pptx", SaveFormat.Pptx)`를 호출합니다.  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 프로덕션에서는 상용 라이선스가 필요합니다.

## Aspose.Slides를 사용하여 Java에서 차트를 사용자 지정하는 방법은?
`Presentation`은 메모리 내 전체 PowerPoint 파일을 나타내는 Aspose.Slides 클래스입니다. 새 `Presentation`을 로드하고 첫 슬라이드에 산점도 차트를 추가한 뒤 시리즈와 마커 스타일을 구성하고 `save`를 호출합니다. 이 단일 워크플로우만으로 몇 줄의 Java 코드로 완전하게 스타일링된 차트를 만들 수 있어 어떤 PowerPoint 데크에도 쉽게 포함할 수 있습니다.

## “customize scatter chart aspose”란 무엇인가요?
Aspose를 사용해 산점도 차트를 사용자 지정한다는 것은 차트의 데이터, 외관 및 동작을 프로그래밍 방식으로 정의하는 것을 의미합니다—점 좌표부터 마커 기호까지—PowerPoint를 직접 열지 않고도 가능합니다. 이 접근 방식은 자동 보고, 데이터 기반 프레젠테이션, 또는 반복 가능한 고품질 시각화가 필요한 모든 시나리오에 이상적입니다.

## 왜 Aspose.Slides로 산점도 차트를 사용자 지정해야 할까요?
Aspose.Slides는 개발자에게 차트 외관에 대한 완전한 프로그래밍 제어를 제공하여 자동화된 고품질 시각화 생성, 보고 파이프라인과의 원활한 통합, PowerPoint를 직접 열지 않고도 모든 시각 요소를 맞춤 설정할 수 있게 해줍니다. 이는 시간 절약과 프레젠테이션 전반에 걸친 일관성을 보장합니다.

- **전체 제어** – Java 코드로 시리즈 유형, 마커 스타일, 색상 등을 수정합니다.  
- **자동화** – 대시보드나 배치 보고서를 위해 실시간으로 수십 개의 차트를 생성합니다.  
- **크로스‑플랫폼** – Java를 지원하는 모든 OS에서 동작하며 Office 설치가 필요 없습니다.  
- **성능** – **150개 이상의 차트 유형**을 처리하고 전체 파일을 메모리에 로드하지 않고도 수백 페이지 프레젠테이션을 다룰 수 있는 가벼운 API입니다.

## 전제 조건

다음 항목을 준비하십시오:

- **Aspose.Slides for Java** (v25.4 이상).  
- **Java Development Kit (JDK)** 8 + 설치.  
- Maven 또는 Gradle을 통한 종속성 관리 (또는 JAR 파일을 직접 다운로드).  
- 기본 Java 지식 및 선택한 빌드 도구에 대한 친숙함.

## Aspose.Slides for Java 설정

프로젝트에 라이브러리를 통합하려면 아래 방법 중 하나를 사용하십시오.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 최신 릴리스를 [Aspose Releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

#### 라이선스 획득
- **무료 체험** – 30일 평가.  
- **임시 라이선스** – 연장된 테스트 기간.  
- **정식 라이선스** – 프리미엄 지원이 포함된 프로덕션 사용.

## Aspose를 사용한 산점도 차트 사용자 지정 단계별 가이드

### 1️⃣ 프레젠테이션 파일을 저장할 폴더 준비
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*이것이 중요한 이유:* 출력 폴더가 존재하도록 하면 나중에 PPTX를 저장할 때 `FileNotFoundException`을 방지할 수 있습니다.

### 2️⃣ 새 프레젠테이션을 만들고 첫 슬라이드를 가져오기
`Presentation`은 PowerPoint 문서를 나타내며 슬라이드와 도형에 접근할 수 있게 해줍니다. `Presentation` 클래스는 메모리 내 전체 PowerPoint 파일을 나타냅니다.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ 부드러운 선이 있는 산점도 차트 추가
`ChartType.ScatterWithSmoothLines`는 점을 부드러운 선으로 연결하는 산점도 차트를 생성합니다.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ 기본 시리즈를 모두 지우고 사용자 정의 시리즈 추가
`IChartSeries`는 차트 내 데이터 시리즈를 나타냅니다.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ 첫 번째 시리즈에 데이터 포인트 채우기
`addDataPointForScatterSeries`는 산점도 시리즈에 단일 X‑Y 포인트를 추가합니다.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ 시리즈 유형 및 마커 모양 맞춤 설정
`Marker`는 차트 시리즈의 각 데이터 포인트에 사용되는 시각 기호를 제어합니다.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ 프레젠테이션 저장
`save`는 지정된 형식으로 프레젠테이션을 파일에 기록합니다.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 맞춤형 산점도 차트의 일반적인 사용 사례
- **재무 대시보드** – 주가와 거래량을 플롯.  
- **과학 연구** – 오류 마커가 있는 실험 측정값 표시.  
- **프로젝트 관리** – 작업별 계획 대비 실제 노력 비교.  

## 성능 팁
- 저장 후 `pres.dispose()`를 호출하여 네이티브 메모리를 해제합니다.  
- 대용량 데이터 세트의 경우 먼저 워크북을 채운 뒤 시리즈에 바인딩하여 UI 새로 고침을 반복하지 않도록 합니다.  
- 다수의 시리즈를 추가할 때는 단일 `IChartDataWorkbook` 인스턴스를 재사용해 메모리 사용량을 낮춥니다.

## 자주 묻는 질문

**Q: 마커 색상을 어떻게 변경하나요?**  
A: `series.getMarker().getFillFormat().setFillColor(Color)`를 사용합니다. 여기서 `Color`는 `java.awt.Color` 인스턴스로, 예를 들어 `Color.RED`와 같이 지정합니다.

**Q: 산점도 차트에 두 개 이상 시리즈를 추가할 수 있나요?**  
A: 예. 추가 시리즈마다 `chart.getChartData().getSeries().add(...)`를 호출하고 해당 포인트를 채워 넣으면 됩니다.

**Q: 각 시리즈에 사용자 정의 범례를 설정할 수 있나요?**  
A: 물론 가능합니다. 시리즈를 만든 후 `series.getLegend().setText("Your Legend Text")`를 호출해 기본 이름을 덮어씁니다.

**Q: 차트를 PPTX가 아니라 이미지로 내보내려면 어떻게 하나요?**  
A: 차트를 구성한 뒤 `chart.getImage().save("chart.png", ImageFormat.Png)`를 호출하면 독립적인 PNG 파일이 생성됩니다.

**Q: 산점도 포인트에 애니메이션을 적용하려면 어떻게 해야 하나요?**  
A: Aspose.Slides는 애니메이션 효과를 지원합니다. `chart.getTimeline().getMainSequence().addEffect(...)`를 사용해 차트 또는 개별 시리즈에 입장 또는 강조 애니메이션을 추가할 수 있습니다.

---

**Last Updated:** 2026-07-27  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides를 사용하여 Java에서 PowerPoint 차트 만들기 및 사용자 지정](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Aspose.Slides for Java를 사용해 PowerPoint에서 버블 차트 만드는 방법 (튜토리얼)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java에서 추세선이 포함된 차트 만들기 및 사용자 지정](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
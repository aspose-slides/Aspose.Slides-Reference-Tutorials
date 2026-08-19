---
date: '2026-07-17'
description: Aspose Slides for Java를 사용하여 PowerPoint에 Sunburst Charts를 추가하는 방법을 배웁니다.
  단계별 가이드에서는 설정, 차트 생성, 사용자 지정 및 실제 사용 사례를 다룹니다.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Aspose Slides for Java를 사용하여 PowerPoint에 Sunburst Charts를 추가하는 방법.
  이 튜토리얼을 따라 라이브러리를 설정하고, 차트를 만들며, 데이터 포인트를 사용자 지정하고, 실제 프로젝트에 적용하세요.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Aspose (Java)를 사용하여 PowerPoint에 Sunburst Charts 추가하는 방법
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Aspose (Java)를 사용하여 PowerPoint에 Sunburst Charts 추가하는 방법
url: /ko/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint에서 Aspose (Java)로 Sunburst 차트 추가 방법

## 소개

PowerPoint 프레젠테이션에 Sunburst 차트를 추가하면 평면 데이터 테이블을 즉시 매력적인 시각적 계층 구조로 변환할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint에 **sunburst 차트 추가 방법**을 환경 설정부터 색상 및 레이블 미세 조정까지 배웁니다. 영업 대시보드, 프로젝트 작업 분류, 교육용 슬라이드 데크를 만들든, 아래 단계는 프로덕션에 바로 사용할 수 있는 솔루션을 제공합니다.

**배울 내용**
- Maven 또는 Gradle 프로젝트에서 Aspose.Slides를 구성하는 방법  
- 새 프레젠테이션을 만들고 Sunburst 차트를 삽입하는 방법  
- 데이터 포인트, 레이블 및 채우기 색상을 사용자 정의하는 방법  
- Sunburst 차트가 빛을 발하는 실제 시나리오  

시작해 보겠습니다. 원시 계층 데이터를 세련된 PowerPoint 시각 자료로 변환하는 것이 얼마나 쉬운지 확인해 보세요.

## 빠른 답변
- **주요 라이브러리?** Aspose.Slides for Java  
- **지원 차트 유형?** Sunburst (방사형 계층형)  
- **최소 Java 버전?** JDK 16  
- **일반 구현 시간?** 기본 차트에 10‑15분  
- **프로덕션에 라이선스 필요?** 예, 유효한 Aspose 라이선스  

## Sunburst 차트란?
Sunburst 차트는 중심점에서 바깥쪽으로 링을 중첩시켜 계층 데이터를 시각화하는 방사형 다이어그램입니다. 조직 구조, 제품 카테고리, 파일 시스템 트리와 같은 다중 레벨 관계를 표시하는 데 적합합니다. 각 동심원 링은 계층의 레벨을 나타내며, 각 섹션의 크기는 정량적 값을 반영하여 구조와 규모를 한눈에 파악할 수 있게 합니다.

## 왜 Aspose.Slides for Java를 사용해야 할까요?
Aspose.Slides는 **50개 이상의 차트 유형**을 지원하고 전체 파일을 메모리에 로드하지 않고도 **10,000 슬라이드**까지 조작할 수 있어 엔터프라이즈 규모 보고에 높은 성능을 제공합니다. 크로스‑플랫폼으로 동작하며 광범위한 API 커버리지를 제공하고, 평가 제한을 제거하는 강력한 라이선스 옵션을 포함해 프로덕션 환경에 최적화되어 있습니다.

## 사전 요구 사항
- **Java Development Kit (JDK)** 16 이상  
- **IDE** – IntelliJ IDEA, Eclipse 또는 Java 호환 편집기  
- Java 구문 및 Maven/Gradle 빌드 도구에 대한 기본적인 이해  

## Aspose.Slides for Java 설정

### Maven 의존성
`pom.xml`에 Aspose.Slides Maven 아티팩트를 추가합니다:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 의존성
Gradle을 선호한다면 `build.gradle`에 다음 라인을 포함합니다:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
공식 릴리스 페이지에서 최신 JAR를 직접 다운로드할 수도 있습니다: [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/).

### 라이선스 획득
평가 제한 없이 실행하려면 라이선스를 획득하세요:
- **무료 체험** – 빠른 평가를 위한 임시 라이선스.  
- **임시 라이선스** – [Aspose 웹사이트](https://purchase.aspose.com/temporary-license)에서 요청하세요.  
- **정식 구매** – 무제한 프로덕션 사용을 위한 구독을 구매하세요.

### 기본 초기화
`Presentation` 클래스는 PowerPoint 파일을 생성하거나 여는 진입점입니다.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## 구현 가이드

### Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 Sunburst 차트를 추가하는 방법
새 `Presentation`을 로드하고, 슬라이드를 추가한 뒤, `ChartType.Sunburst` 유형의 `IChart`를 삽입하고 `save`를 호출합니다. 이 간결한 3단계 패턴은 추가 커스터마이징이 가능한 완전한 Sunburst 차트를 생성합니다.

#### 단계 1: 프레젠테이션 초기화
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### 단계 2: Sunburst 차트 추가
`IChart` 인터페이스는 슬라이드에 배치할 수 있는 차트 객체를 정의합니다. 여기서는 좌표 (100, 100)에 크기 450 × 400 포인트인 Sunburst 차트를 추가합니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### 단계 3: 프레젠테이션 저장
변경 사항은 반드시 `save`를 호출해 영구 저장합니다. PPTX, PDF 또는 50개 이상의 지원 출력 형식 중 선택할 수 있습니다.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 차트의 데이터 포인트 수정

#### 개요
차트의 데이터 포인트 컬렉션을 통해 Sunburst의 각 슬라이스—레이블, 색상, 가시성—를 맞춤 설정할 수 있습니다.

#### 단계 1: 데이터 포인트 컬렉션 접근
차트의 첫 번째 시리즈는 각 슬라이스를 나타내는 `IChartDataPoint` 객체 컬렉션을 보유합니다.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### 단계 2: 특정 데이터 포인트에 값 표시
원하는 데이터 포인트의 `IsValueShown`을 `true`로 설정하면 해당 슬라이스에 숫자 값이 직접 표시됩니다.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### 단계 3: 레이블 형식 수정
가독성을 높이기 위해 레이블 가시성, 글꼴 색상 및 배경을 조정합니다.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### 단계 4: 데이터 포인트 채우기 색상 설정
개별 슬라이스의 채우기 색상을 브랜드 팔레트에 맞추거나 핵심 세그먼트를 강조하도록 맞춤 설정합니다.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### 단계 5: 수정된 프레젠테이션 저장
프레젠테이션을 다시 저장하여 맞춤 차트를 영구 보관합니다.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 실용적인 적용 사례

1. **비즈니스 분석** – 지역 → 제품 라인 → SKU 순으로 매출을 단일 방사형 뷰에 시각화.  
2. **프로젝트 관리** – 단계 → 작업 → 하위 작업으로 작업 분류 구조를 표시.  
3. **교육** – 학과 → 강좌 → 모듈과 같은 커리큘럼 계층 구조를 매핑.  

## 성능 고려 사항

- **메모리 효율성:** Aspose.Slides는 데이터를 스트리밍하므로 여러 차트가 포함된 500페이지 프레젠테이션도 RAM 200 MB 이하로 유지됩니다.  
- **가비지 컬렉션:** 필요 없어진 슬라이드 객체(`slide.dispose()`)를 해제하여 메모리 누수를 방지하세요.  

## 자주 묻는 질문

**Q: Sunburst 차트란 무엇인가요?**  
A: Sunburst 차트는 동심원 형태의 링으로 계층 데이터를 시각화하는 차트이며, 각 링은 계층 레벨을 나타내고 섹션 크기는 정량적 값을 반영합니다.

**Q: Maven을 사용하여 Aspose.Slides for Java를 설치하려면 어떻게 해야 하나요?**  
A: “Maven 의존성” 섹션에 표시된 의존성을 `pom.xml`에 추가하고 `mvn clean install`을 실행하면 됩니다.

**Q: Aspose.Slides로 다른 차트 유형도 사용자 정의할 수 있나요?**  
A: 예, 라이브러리는 컬럼, 라인, 파이, 레이더 차트를 포함해 50개 이상의 차트 유형을 지원합니다.

**Q: 프레젠테이션이 저장되지 않아요—무엇을 확인해야 하나요?**  
A: 파일 경로가 올바른지, 디렉터리가 존재하는지, 쓰기 권한이 있는지 확인하십시오. 또한 `Presentation.save()` 메서드가 호출되었는지 확인하세요.

**Q: 추가 도움이나 예제를 어디서 얻을 수 있나요?**  
A: [Aspose 포럼](https://forum.aspose.com/c/slides/11)이나 공식 [Aspose.Slides 레퍼런스](https://reference.aspose.com/slides/java/)를 방문하십시오.

## 리소스
- **문서:** [Aspose.Slides 레퍼런스](https://reference.aspose.com/slides/java/)  
- **레퍼런스 (소문자):** [Aspose.Slides 레퍼런스](https://reference.aspose.com/slides/java/)  
- **커뮤니티 포럼:** [Aspose 포럼](https://forum.aspose.com/c/slides)  
- **다운로드:** [Aspose.Slides 다운로드](https://releases.aspose.com/slides/java)  

---

**마지막 업데이트:** 2026-07-17  
**테스트 환경:** Aspose.Slides for Java 24.12  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java로 PowerPoint 차트 애니메이션 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Java에서 Aspose.Slides로 차트 만들기 – 차트 추가 및 검증](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
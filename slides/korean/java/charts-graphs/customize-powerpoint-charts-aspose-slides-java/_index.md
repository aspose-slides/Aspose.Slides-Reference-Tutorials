---
date: '2026-09-07'
description: Java를 사용하여 Aspose Slides 차트에 사용자 정의 선을 추가하는 방법을 배웁니다. 단계별 가이드를 통해 PowerPoint
  차트를 향상시켜 데이터 시각화를 보다 명확하게 합니다.
keywords:
- aspose slides chart
- customize PowerPoint charts
- add custom lines to charts Java
lastmod: '2026-09-07'
og_description: Java를 사용하여 Aspose Slides 차트에 사용자 정의 선을 추가하는 방법을 배웁니다. 이 가이드는 단계별 맞춤
  설정을 통해 데이터 시각화를 보다 명확하게 보여줍니다.
og_image_alt: Developer guide showing custom line addition to an Aspose Slides chart
  in Java
og_title: Java에서 Aspose Slides 차트에 사용자 정의 선을 추가하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  headline: How to add custom lines to an Aspose Slides chart in Java
  type: TechArticle
- description: Learn how to add custom lines to an Aspose Slides chart using Java.
    Step‑by‑step guide enhances PowerPoint charts for clearer data visualization.
  name: How to add custom lines to an Aspose Slides chart in Java
  steps:
  - name: create a presentation object
    text: The `Presentation` class is Aspose.Slides' top‑level object that represents
      a single PowerPoint file in memory.
  - name: add a clustered column chart
    text: Insert a clustered column chart on the first slide at coordinates (100,
      100) with a width of 500 px and a height of 400 px.
  - name: add an auto‑shape line to the chart
    text: Add a line shape to the chart’s `userShapes` collection, which stores custom
      drawing objects. `userShapes` is a collection that holds custom shapes drawn
      directly on a chart, allowing you to overlay lines, arrows, or other annotations.
  - name: customize line properties
    text: Set the line’s fill type to solid, change its color to red, and optionally
      adjust thickness or dash style.
  - name: save the presentation
    text: Persist the modified presentation to disk.
  type: HowTo
- questions:
  - answer: '`Presentation` represents a PowerPoint file in memory.'
    question: What is the main class for creating a presentation?
  - answer: '`slide.getShapes().addChart(...)` creates a chart object.'
    question: Which method adds a chart to a slide?
  - answer: Use `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`.
    question: How do you draw a line on a chart?
  - answer: Yes—set the line’s fill to a solid red `Color.RED`.
    question: Can I set the line color to red?
  - answer: A full license removes evaluation limits; a trial works for testing.
    question: Do I need a license for production use?
  type: FAQPage
tags:
- aspose slides
- chart customization
- java presentation
title: Java에서 Aspose Slides 차트에 사용자 정의 선을 추가하는 방법
url: /ko/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Aspose Slides 차트에 사용자 정의 선을 추가하는 방법

## 소개

이 튜토리얼에서는 Java를 사용하여 **aspose slides chart**에 사용자 정의 선을 추가하는 방법을 알아봅니다. 사용자 정의 선은 임계값, 추세 또는 핵심 데이터 포인트를 강조하여 일반 차트를 강력한 시각적 스토리로 변환합니다. 가이드를 마치면 Aspose.Slides를 프로젝트에 통합하고, 차트에 선을 그리며, 최대 효과를 위해 외관을 세밀하게 조정할 수 있게 됩니다.

**배우게 될 내용**
- Aspose.Slides for Java 설치 및 라이선스 방법
- 차트에 사용자 정의 선을 그리는 정확한 단계
- 선 스타일링 방법(색상, 두께, 대시 스타일)
- 사용자 정의 선이 데이터 전달을 개선하는 실제 시나리오

## 빠른 답변
- **프레젠테이션을 만들기 위한 주요 클래스는 무엇인가요?** `Presentation`은 메모리 내의 PowerPoint 파일을 나타냅니다.  
- **슬라이드에 차트를 추가하는 메서드는 무엇인가요?** `slide.getShapes().addChart(...)`는 차트 객체를 생성합니다.  
- **차트에 선을 그리려면 어떻게 하나요?** `chart.getUserShapes().addAutoShape(ShapeType.Line, ...)`를 사용합니다.  
- **선 색상을 빨간색으로 설정할 수 있나요?** 예—선의 채우기를 고정 빨간색 `Color.RED`로 설정합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 전체 라이선스는 평가 제한을 제거합니다; 평가판은 테스트에 사용할 수 있습니다.  

`ShapeType.Line`은 Aspose.Slides에 선 모양 자동 도형을 생성하도록 지시하는 열거형 값입니다.

## Aspose Slides 차트란?

**Aspose Slides chart**는 PowerPoint 슬라이드 내부에 존재하는 프로그래밍 가능한 차트 객체로, Java 코드만으로 차트를 생성, 수정 및 스타일링할 수 있습니다. 컬럼, 바, 라인, 파이 등 다양한 차트 유형을 지원하며, 시리즈, 축, 범례에 대한 완전한 제어를 제공하고 이미지 및 사용자 정의 도형과 같은 다른 슬라이드 요소와 결합할 수 있어 자동화된 보고서 및 동적 프레젠테이션에 적합합니다.

## Aspose Slides 차트에 사용자 정의 선을 추가하는 이유

사용자 정의 선은 차트에 정확한 시각적 힌트를 추가하여 주석을 달 수 있게 합니다. Aspose.Slides는 **50+ 입력 및 출력 형식**을 지원하고 **수백 개의 슬라이드**를 처리하면서 일반 개발 머신에서 **150 MB 이하의 RAM**만 사용하므로 대규모 보고에 이상적입니다.

## 전제 조건

- **Aspose.Slides for Java** – 버전 25.4(이상)  
- **JDK 16+** – 최신 Java 런타임 중 하나  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE  
- 기본 Java 지식 및 PowerPoint 개념에 대한 이해  

### 필수 라이브러리
- Aspose.Slides for Java (Version 25.4)

### 환경 설정
- JDK 16 이상 설치  
- Maven 또는 Gradle을 사용하여 종속성 관리(아래 예시 참고)  

## Aspose.Slides for Java 설정

다음 빌드 도구 중 하나를 사용하여 라이브러리를 프로젝트에 추가합니다.

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

수동 다운로드는 최신 패키지를 위해 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)를 방문하십시오.

### 라이선스 획득
- **무료 체험:** 구매 없이 테스트 시작.  
- **임시 라이선스:** 워터마크 없이 확장 평가에 사용.  
- **전체 라이선스:** 프로덕션 작업에 모든 기능 잠금 해제.  

코드 예시와 같이 라이선스를 초기화합니다:
```java
License license = new License();
license.setLicense("path_to_license.lic");
```  

`License`는 Aspose.Slides 라이선스 파일을 로드하고 적용하는 데 사용되는 클래스입니다.

## Aspose Slides 차트에 사용자 정의 선을 추가하려면 어떻게 하나요?

프레젠테이션을 로드하거나 생성하고, 차트를 삽입한 다음 차트의 사용자 도형 컬렉션에 선 도형을 추가합니다. 선은 위치, 크기 및 스타일을 조정하여 보고 요구에 맞출 수 있습니다. 이 방법은 클러스터형 컬럼, 바, 라인 및 영역 차트 모두에 적용됩니다.

## 구현 가이드

### 차트에 사용자 정의 선 추가

#### 개요
사용자 정의 선은 예산 한도나 목표선과 같은 특정 값을 강조하여 차트를 보다 통찰력 있게 만듭니다.

#### 단계 1: 프레젠테이션 객체 생성
`Presentation` 클래스는 Aspose.Slides의 최상위 객체로, 메모리 내의 단일 PowerPoint 파일을 나타냅니다.  
```java
Presentation pres = new Presentation();
```  

#### 단계 2: 클러스터형 컬럼 차트 추가
첫 번째 슬라이드에 좌표 (100, 100)에서 너비 500 px, 높이 400 px인 클러스터형 컬럼 차트를 삽입합니다.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 500, 400);
```  

#### 단계 3: 차트에 자동 도형 선 추가
차트의 `userShapes` 컬렉션에 선 도형을 추가합니다. 이 컬렉션은 사용자 정의 그리기 객체를 저장합니다.  
```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(
    ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```  

`userShapes`는 차트에 직접 그린 사용자 정의 도형을 보관하는 컬렉션으로, 선, 화살표 또는 기타 주석을 겹쳐 놓을 수 있게 합니다.

#### 단계 4: 선 속성 사용자 정의
선의 채우기 유형을 고정으로 설정하고 색상을 빨간색으로 변경하며, 필요에 따라 두께나 대시 스타일을 조정합니다.  
```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```  

#### 단계 5: 프레젠테이션 저장
수정된 프레젠테이션을 디스크에 저장합니다.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/" + "AddCustomLines.pptx", SaveFormat.Pptx);
```  

### Presentation 클래스 사용
`Presentation` 클래스는 PowerPoint 파일을 로드, 생성 및 저장하는 메서드와 개별 슬라이드 및 도형에 접근하는 기능을 제공합니다.

### 문제 해결 팁
- `save`에 사용된 파일 경로가 쓰기 가능한지 확인하고, 신뢰성을 위해 절대 경로를 사용하십시오.  
- 차트가 표시되지 않으면 X/Y 좌표를 다시 확인하고 슬라이드 인덱스가 올바른지 확인하십시오.  

## 실용적인 적용 사례

사용자 정의 선은 특히 다음 분야에서 유용합니다.
1. **재무 보고** – 예산 상한선이나 이익 목표 강조.  
2. **영업 대시보드** – 분기별 매출 목표 선 그리기.  
3. **헬스케어 분석** – 환자 바이탈 사인 추세에서 중요한 임계값 표시.  

데이터베이스나 API에서 임계값을 가져와 선 배치를 자동화하면 실시간 보고가 가능합니다.

## 성능 고려 사항

- 작업이 끝난 후 `presentation.dispose()`로 `Presentation` 객체를 해제하여 네이티브 메모리를 확보하십시오.  
- 파일 크기 관리를 위해 적당한 이미지 및 차트 해상도(예: 150 dpi)를 사용하십시오.  
- 개발 중에는 임시 라이선스를 사용하면 평가 워터마크를 피하면서 전체 API 접근이 가능합니다.

## 결론

이제 Java에서 **aspose slides chart**에 사용자 정의 선을 추가하는 방법을 알게 되었으며, 차트 주석 및 시각적 강조를 완벽히 제어할 수 있습니다. 다양한 선 스타일, 위치 및 차트 유형을 실험하여 데이터를 즉시 전달하는 보고서를 만들어 보세요.

## FAQ 섹션

**Q1: 사용자 정의 선의 색상을 변경할 수 있나요?**  
A1: 예, `SolidFillColor` 속성을 원하는 `java.awt.Color`로 설정하여 선 색상을 맞춤화할 수 있습니다.

**Q2: Aspose.Slides가 모든 Java IDE와 호환되나요?**  
A2: 예, IDE가 Maven 또는 Gradle을 지원하기만 하면 Aspose.Slides를 문제 없이 통합할 수 있습니다.

**Q3: 사용자 정의 선 추가를 지원하는 차트 유형은 무엇인가요?**  
A3: 클러스터형 컬럼, 바, 라인, 영역 및 파이 차트 등 다양한 차트에 사용자 정의 선을 추가할 수 있습니다.

**Q4: 프레젠테이션 저장 문제를 어떻게 해결하나요?**  
A4: 출력 디렉터리가 존재하는지, 파일 경로가 정확한지, 애플리케이션에 쓰기 권한이 있는지 확인하십시오.

**Q5: 평가판 라이선스를 사용할 때 제한 사항이 있나요?**  
A5: 평가판은 워터마크를 추가하고 일부 프리미엄 기능을 제한할 수 있으며, 임시 또는 전체 라이선스를 사용하면 이러한 제약이 해제됩니다.

## 리소스
- **Documentation**: [Aspose.Slides Java Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides for Java Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [Get a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-09-07  
**Tested with:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## 관련 튜토리얼

- [Create Customize Charts Trend Lines Aspose Slides Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [How to Rotate Chart Axis Titles in PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/rotate-chart-axis-titles-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
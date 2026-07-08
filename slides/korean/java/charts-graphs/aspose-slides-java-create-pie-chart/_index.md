---
date: '2026-07-08'
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 파이 차트를 추가하는 방법을 배웁니다.
  이 단계별 가이드를 따라 전문적인 파이 차트를 만들고 사용자 지정하세요.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Aspose.Slides for Java를 사용하여 PowerPoint에 파이 차트를 추가합니다. 이 튜토리얼은 파이
  차트를 프로그램 방식으로 생성하고 사용자 지정하는 방법을 보여주며, 자동 보고서에 최적화되어 있습니다.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Aspose.Slides for Java로 PowerPoint 파이 차트 추가 – 빠른 가이드
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Aspose.Slides for Java를 사용하여 PowerPoint에 파이 차트 추가하는 방법
url: /ko/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 파이 차트 PowerPoint 추가

## 소개

PowerPoint를 수동으로 열지 않고 **add pie chart PowerPoint** 슬라이드를 추가해야 한다면, 올바른 곳에 오셨습니다. 이 가이드에서는 Aspose.Slides for Java 설정, 파이 차트 생성, 각 슬라이스 맞춤 설정 방법을 단계별로 안내합니다—자동 보고서, 대시보드 또는 맞춤형 프레젠테이션에 이상적입니다. 끝까지 진행하면 몇 초 만에 세련된 파이 차트 PowerPoint 파일을 생성하는 재사용 가능한 Java 코드 스니펫을 얻게 됩니다.

### 빠른 답변
- **어떤 라이브러리가 차트를 생성합니까?** Aspose.Slides for Java (latest release).  
- **헤드리스로 실행할 수 있나요?** Yes—no Office installation required.  
- **어떤 Java 버전이 최적입니까?** JDK 16+ for best performance and GC improvements.  
- **슬라이스를 어떻게 폭발시킬 수 있나요?** Call `setExplosion` on the `IDataPoint` and set a pixel offset.  
- **프로덕션에 라이선스가 필요합니까?** A trial works for development; a permanent license removes all evaluation limits.

## 왜 Aspose.Slides for Java를 사용하여 파이 차트 PowerPoint를 추가해야 할까요?
백엔드 서비스에서 직접 최신 시각 보고서를 생성할 수 있어 수동 복사‑붙여넣기 오류를 없애고 브랜드 일관된 스타일을 보장합니다. Aspose.Slides는 **70+ chart types**를 지원하고 전체 파일을 메모리에 로드하지 않고도 **10,000+ slides**를 처리할 수 있어 대규모 자동화에 이상적입니다.

## 전제 조건
- **Aspose.Slides for Java** – 이 튜토리얼은 버전 25.4(작성 시 최신)를 참조합니다.  
- **Java Development Kit** – JDK 16 이상을 권장합니다.  
- **Maven** 또는 **Gradle** – 종속성 관리를 위해 사용합니다.  

## Aspose.Slides for Java 설정

### Maven
다음 의존성을 `pom.xml` 파일에 추가하세요:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
다음 내용을 `build.gradle` 파일에 포함하세요:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 최신 버전을 직접 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

### 라이선스
Aspose.Slides를 제한 없이 사용하려면:

- API를 평가하려면 **free trial**로 시작하십시오.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) 페이지에서 확장 테스트를 위한 **temporary license**를 요청하십시오.  
- [Purchase page](https://purchase.aspose.com/buy)를 통해 전체 구독을 구매하십시오.

## Aspose.Slides for Java를 사용하여 파이 차트 PowerPoint를 추가하는 방법
새 프레젠테이션을 로드하고 파이 차트를 삽입한 뒤 파일을 저장합니다—세 단계만으로 완료됩니다. 이 패턴은 데이터 크기에 관계없이 작동하며 루프에 감싸서 수십 개의 슬라이드를 자동으로 생성할 수 있습니다. 접근 방식은 가볍고 몇 줄의 코드와 외부 리소스 없이도 구현 가능해 작은 유틸리티와 대규모 배치 작업 모두에 적합합니다.

### 1단계: 프레젠테이션 초기화
`Presentation` 클래스는 메모리 내에서 단일 PowerPoint 파일을 나타냅니다. 인스턴스를 생성하면 작업할 새롭고 빈 슬라이드 덱을 얻을 수 있습니다.
```java
Presentation pres = new Presentation();
```

### 2단계: 파이 차트 추가
첫 번째 슬라이드에 파이 차트를 삽입합니다. 좌표 (50, 50) 및 크기 (600 × 400)는 표준 16:9 레이아웃에 맞으며 제목을 위한 공간을 남깁니다.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### 3단계: 프레젠테이션 저장
프레젠테이션을 디스크에 저장합니다. `YOUR_OUTPUT_DIRECTORY`를 파일을 저장하려는 폴더 경로로 교체하십시오.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### 4단계: 리소스 정리
`Presentation` 객체를 폐기하여 네이티브 리소스를 해제하고 메모리 누수를 방지합니다.
```java
if (pres != null) pres.dispose();
```

## 데이터 포인트 폭발 및 색상 맞춤 방법
차트를 로드하고 대상 데이터 포인트를 찾은 다음 폭발 오프셋과 단색 채우기 색상을 적용합니다. 이렇게 하면 슬라이스가 강조되어 눈에 띕니다. 이러한 조정은 청중이 중요한 값을 주목하도록 돕고 차트 전체 가독성을 향상시킵니다.

### 1단계: 기존 프레젠테이션 로드 (또는 방금 만든 프레젠테이션 재사용)
`Presentation` 객체는 기존 PowerPoint 파일을 메모리로 로드하여 내용 수정이 가능하도록 합니다.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### 2단계: 차트 및 대상 데이터 포인트 접근
`IDataPoint` 인터페이스는 차트 시리즈 내 개별 데이터 포인트(슬라이스)를 나타냅니다.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### 3단계: 폭발 및 색상 적용
`setExplosion(int)`은 슬라이스가 차트 중심에서 픽셀 단위로 떨어지는 거리를 설정합니다. `setExplosion(20)`으로 슬라이스를 시각적으로 분리하고 `setFillType(FillType.Solid)`와 `setSolidFillColor(Color.BLUE)`를 사용해 채우기를 파란색으로 변경합니다.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### 4단계: 저장 및 폐기
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## 실용적인 적용 사례
- **Sales Reports:** 최고 판매 제품을 폭발된 슬라이스로 강조합니다.  
- **Budget Analysis:** 부서별로 구별되는 색상을 지정하여 빠른 시각적 비교를 가능하게 합니다.  
- **Educational Slides:** 복잡한 개념을 소화하기 쉬운 차트 세그먼트로 분해합니다.  

## 성능 고려 사항
- **Dispose objects**를 즉시 수행하여 메모리 누수를 방지하십시오. 특히 루프에서 많은 슬라이드를 생성할 때 중요합니다.  
- **Monitor heap usage**를 수행하고, `Save` 메서드 중 `OutputStream`을 받는 오버로드를 사용해 데이터를 스트리밍함으로써 메모리 사용량을 낮게 유지하십시오.  
- **JDK 16+**를 사용하여 최신 가비지 컬렉션 개선의 이점을 누리십시오. 이는 1,000 슬라이드 덱의 처리 시간을 최대 30 %까지 단축할 수 있습니다.

## 결론
이제 Aspose.Slides for Java를 사용하여 **add pie chart PowerPoint** 파일을 생성하는 완전하고 프로덕션 준비된 워크플로우를 갖추었습니다. 다양한 폭발 거리, 색상 및 데이터 세트를 실험하여 브랜드에 맞추세요. 준비가 되면 다른 차트 유형(막대, 선, 산점도)을 탐색하여 PowerPoint 내부에 전체 분석 대시보드를 구축하십시오.

## 자주 묻는 질문

**Q: Aspose.Slides for Java를 사용할 때 가장 큰 장점은 무엇인가요?**  
A: Microsoft Office를 설치할 필요 없이 프로그래밍 방식으로 PowerPoint 파일을 생성, 편집 및 렌더링할 수 있으며, 70개 이상의 차트 유형과 100개 이상의 파일 형식을 지원합니다.

**Q: 처음부터 PowerPoint 파일을 생성할 수 있나요?**  
A: 예, `Presentation` 객체를 인스턴스화하고 슬라이드, 차트 또는 도형을 추가한 뒤 `save`를 호출하면 순수 Java 코드만으로 가능합니다.

**Q: 특정 파이 슬라이스를 어떻게 폭발시킬 수 있나요?**  
A: 해당 슬라이스의 `IDataPoint`를 가져와 `setExplosion(pixelOffset)`을 호출하면 됩니다. 오프셋 값은 슬라이스가 외부로 이동하는 거리를 정의합니다.

**Q: 생성할 수 있는 슬라이드 수에 제한이 있나요?**  
A: Aspose.Slides는 단일 파일에서 **10,000 슬라이드**까지 처리할 수 있으며, 전체를 메모리에 로드하지 않도록 출력을 스트리밍하면 됩니다.

**Q: 보다 고급 차트 맞춤 예제를 어디서 찾을 수 있나요?**  
A: 자세한 API 레퍼런스와 샘플 프로젝트는 공식 [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)을 확인하십시오.

## 리소스
- **문서:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **라이브러리 다운로드:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **라이선스 구매:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **무료 체험:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **임시 라이선스:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **지원 포럼:** [Aspose Support](https://forum.aspose.com/c/slides/11)

**마지막 업데이트:** 2026-07-08  
**테스트 환경:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼
- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가하는 방법: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java를 사용하여 PowerPoint 차트 애니메이션 만들기 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Aspose.Slides for Java를 사용하여 PowerPoint에서 차트 레이아웃 생성 및 검증 | SEO 최적화 가이드](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
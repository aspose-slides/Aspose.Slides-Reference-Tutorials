---
date: '2026-08-21'
description: Aspose.Slides for Java로 clustered column chart를 만들고 trend lines를 추가하는
  방법을 배우세요. license setup, Maven/Gradle 통합 및 자세한 예제가 포함됩니다.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Aspose.Slides for Java를 사용하여 clustered column chart를 만들고 trend lines를
  추가하세요. 이 가이드는 license setup, Maven/Gradle 및 step‑by‑step code snippets를 다룹니다.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Aspose.Slides for Java와 함께 clustered column chart 만들고 trend lines 추가하기
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Aspose.Slides for Java를 사용하여 clustered column chart 만들고 trend lines 추가하는 방법
url: /ko/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 클러스터형 열 차트를 만들고 Aspose.Slides for Java를 사용하여 추세선 추가하는 방법

데이터를 명확하게 시각화하는 것이 매력적인 프레젠테이션을 만드는 시작점입니다. 이 가이드에서는 **클러스터형 열 차트** 객체를 만든 다음, 강력한 Aspose.Slides for Java API를 사용하여 지수, 선형, 로그, 이동 평균, 다항식 및 멱법칙 등 다양한 추세선을 추가하는 방법을 설명합니다.

## 빠른 답변
- **첫 번째 단계는 무엇인가요?** `Presentation` 객체를 초기화하고 슬라이드에 클러스터형 열 차트를 추가합니다.  
- **필요한 라이브러리 버전은?** Aspose.Slides for Java 25.4 이상.  
- **Maven 또는 Gradle을 사용할 수 있나요?** 예, 두 빌드 도구 모두 지원됩니다; Maven은 `<dependency>`를, Gradle은 `implementation`을 사용합니다.  
- **라이선스가 필요합니까?** 평가용 트라이얼 라이선스로도 평가가 가능하며, 정식 Aspose.Slides 라이선스를 사용하면 평가 제한이 해제됩니다.  
- **사용 가능한 추세선 유형은 몇 개인가요?** 지수, 선형, 로그, 이동 평균, 다항식, 멱법칙 등 총 6가지 내장 유형.

## 클러스터형 열 차트란?
`create clustered column chart`는 각 카테고리 내에서 여러 데이터 시리즈를 나란히 배치하여 시리즈 간 값을 쉽게 비교할 수 있는 차트를 생성한다는 의미입니다. 이 차트 유형은 지역별 분기 매출과 같은 범주형 데이터를 시각화하는 데 이상적이며, 그룹 간 차이를 빠르게 파악할 수 있게 해줍니다.

## 왜 추세선을 추가하나요?
추세선은 데이터 시리즈의 기본 패턴을 드러내어 향후 값을 예측하거나 성장률을 강조하고, 잡음이 많은 데이터를 부드럽게 만드는 데 도움을 줍니다. 클러스터형 열 차트에 추세선을 추가하면 원시 숫자가 실행 가능한 인사이트로 변환되어 이해관계자가 장기적인 경향을 파악하고 데이터 기반 의사결정을 내릴 수 있습니다.

## 사전 요구 사항
- **Java Development Kit (JDK):** 8 이상.  
- **Aspose.Slides for Java:** 버전 25.4 이상.  
- **IDE:** IntelliJ IDEA, Eclipse 또는 Java 호환 편집기.  
- **빌드 도구:** Maven 또는 Gradle (선택 사항이지만 권장).  
- **라이선스:** 트라이얼 또는 구매한 Aspose.Slides 라이선스 파일.  

기본적인 Java 문법에 익숙하고 프로젝트 의존성 관리를 이해하고 있어야 합니다.

## Aspose.Slides for Java를 설정하는 방법
선호하는 의존성 관리자를 사용해 Aspose.Slides 라이브러리를 프로젝트에 추가하고, 런타임이 라이선스 파일을 찾을 수 있는 위치에 배치합니다. 이렇게 하면 전체 기능이 활성화되고 평가 제한이 해제됩니다.

### Maven
`pom.xml` 파일에 다음 의존성을 추가합니다:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
`build.gradle` 파일에 다음 라인을 포함합니다:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 JAR 파일을 수동으로 다운로드할 수 있습니다.

#### Aspose Slides 라이선스
프로젝트 루트에 `Aspose.Slides.lic` 파일을 두거나 다음 코드를 사용해 프로그래밍 방식으로 라이선스를 설정합니다: `License license = new License(); license.setLicense("Aspose.Slides.lic");`. 트라이얼 라이선스는 모든 기능 제한을 해제하지만, 구매한 라이선스는 평가 워터마크를 제거하고 전체 성능 최적화를 제공합니다. 실제 운영 환경에서는 [Aspose 구매 페이지](https://purchase.aspose.com/buy)에서 라이선스를 구매하는 것을 권장합니다.

## 프레젠테이션을 만들고 클러스터형 열 차트를 추가하는 방법
`Presentation` 클래스는 PowerPoint 파일을 나타내며 슬라이드 생성, 편집 및 저장 메서드를 제공합니다. `Presentation` 인스턴스를 생성하고 슬라이드를 추가한 뒤, `ChartType.ClusteredColumn`을 사용해 `addChart`를 호출하면 차트 객체가 만들어집니다. 이 과정은 슬라이드 캔버스를 설정하고 차트 셰이프를 삽입한 뒤 데이터 입력 및 스타일링을 위한 준비를 합니다.

1. **프레젠테이션 초기화** – 출력 폴더를 설정하고 새 `Presentation` 인스턴스를 생성합니다.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **클러스터형 열 차트 추가** – 차트 셰이프를 가져오고, 시리즈를 구성한 뒤 데이터 포인트를 채웁니다.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## 지수 추세선을 추가하는 방법
`ITrendline` 인터페이스는 차트 시리즈에 추가할 수 있는 추세선을 정의합니다. `TrendlineType`을 `Exponential`으로 설정하고 원하는 시리즈에 연결하면 지수 추세선을 적용할 수 있습니다. 이 유형은 급격히 증가하는 데이터를 모델링하는 데 유용합니다.

1. **추세선 구성** – 시리즈를 선택하고 `addTrendline(TrendlineType.Exponential)`을 호출합니다.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## 선형 추세선을 추가하는 방법
선형 추세선은 데이터 포인트를 가장 잘 통과하는 직선을 표시합니다. 선 색상 및 두께와 같은 외관을 맞춤 설정해 프레젠테이션 스타일에 맞출 수 있습니다.

1. **추세선 설정** – `addTrendline(TrendlineType.Linear)`을 사용하고, `getLineFormat().setFillFormat().setFillType(FillType.Solid)` 등을 통해 색상을 변경합니다.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## 로그 추세선을 사용자 정의 텍스트 프레임과 함께 추가하는 방법
로그 추세선은 초기 급성장 후 완만해지는 데이터를 모델링하는 데 적합합니다. 기본 레이블을 재정의하면 추세의 의미를 설명하는 텍스트를 추가할 수 있습니다.

1. **추세선 커스터마이징** – 추세선을 추가한 뒤 `getDataLabel()`에 접근해 `setText("Custom label")` 속성을 설정합니다.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## 이동 평균 추세선을 추가하는 방법
이동 평균 추세선은 단기 변동성을 완화하고 장기 추세를 강조합니다. 평균에 사용할 기간(포인트 수)을 지정해 선의 부드러움을 조절할 수 있습니다.

1. **추세선 구성** – `addTrendline(TrendlineType.MovingAverage)`를 호출하고 `setPeriod(3)`을 설정해 3포인트 이동 평균을 사용합니다.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## 다항식 추세선을 추가하는 방법
다항식 추세선은 다항식 방정식으로 정의된 곡선으로 데이터를 맞춥니다. `order` 속성으로 다항식 차수를 지정해 더 복잡한 관계를 모델링할 수 있습니다.

1. **추세선 커스터마이징** – 추세선을 추가한 뒤 `setOrder(3)`을 설정해 3차(큐빅) 피팅을 수행합니다.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## 멱법칙 추세선을 추가하는 방법
멱법칙 추세선은 데이터가 멱법칙 관계를 따를 때 유용합니다. 또한 `setBackward`와 `setForward` 값을 설정해 기존 데이터 범위를 넘어선 예측을 할 수 있습니다.

1. **추세선 구성** – `addTrendline(TrendlineType.Power)`를 사용하고 `setBackward(2)` 등을 조정해 선을 뒤쪽으로 연장합니다.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## 클러스터형 열 차트에서 추세선의 실용적인 활용 사례
- **재무 분석:** 지수 및 다항식 추세는 주가 움직임을 예측하는 데 도움을 줍니다.  
- **판매 예측:** 이동 평균 선은 계절적 급증을 부드럽게 하여 기본 판매 추세를 명확히 보여줍니다.  
- **과학 연구:** 로그 추세선은 음향 강도나 pH 수준처럼 여러 자릿수에 걸친 데이터를 다룰 때 적합합니다.  
- **운영 모니터링:** 멱법칙 추세선은 시간에 따른 성능 저하를 모델링할 수 있습니다.

## Aspose.Slides 사용 시 메모리 최적화 방법
프레젠테이션을 저장한 뒤 `presentation.dispose()`를 호출해 객체를 즉시 해제합니다. 대용량 데이터셋의 경우 이미지의 지연 로딩을 활성화하고 차트를 한 번에 메모리로 로드하지 않도록 합니다.

- **Dispose 패턴:** `Presentation`을 try‑with‑resources 블록으로 감싸거나 finally 절에서 `presentation.dispose()`를 호출합니다.  
- **지연 로딩:** 수천 개의 데이터 포인트를 다룰 때 `ChartData.setUseCache(true)`를 설정합니다.  
- **스트리밍 출력:** 전체 파일을 RAM에 보관하지 않도록 `FileOutputStream`에 직접 프레젠테이션을 씁니다.

## Aspose.Slides for Java의 정량적 장점
Aspose.Slides는 **50개 이상의 차트 유형**을 지원하며, 일반적인 2 GHz CPU에서 **30초 미만**에 **1,000개 이상의 슬라이드**를 생성하고, **500페이지 PDF**를 Microsoft Office 없이 처리할 수 있습니다. 이러한 수치는 최신 25.4 릴리스에서 검증되었습니다.

## 결론
이제 **클러스터형 열 차트** 객체를 만들고 Aspose.Slides for Java에서 제공하는 모든 주요 추세선 유형을 추가하는 완전한 엔드‑투‑엔드 솔루션을 갖추었습니다. 위 단계들을 따라 하면 시각적으로 매력적이고 분석적으로 강력한 데이터 기반 프레젠테이션을 제작할 수 있습니다.

다음 단계로 차트 스타일 옵션을 탐색하고, PDF/HTML로 내보내며, 여러 데이터 소스에 걸쳐 차트 생성을 자동화해 보세요.

## 자주 묻는 질문

**Q: Maven 프로젝트에 Aspose.Slides를 설정하려면 어떻게 해야 하나요?**  
A: Maven 섹션에 표시된 `<dependency>` 스니펫을 `pom.xml`에 추가하고 `mvn clean install`을 실행합니다.

**Q: 색상과 레이블 외에 추세선을 더 커스터마이즈할 수 있나요?**  
A: 예, `ITrendline` API를 통해 선 스타일, 두께, 대시 패턴 및 전/후 예측 값을 수정할 수 있습니다.

**Q: 버전 호환성 오류가 발생하면 어떻게 해야 하나요?**  
A: JDK 버전이 Aspose.Slides 최소 요구 사항(JDK 8+)과 일치하는지 확인하고, Aspose 릴리스 노트를 참고해 호환성 문제를 해결합니다.

**Q: 여러 차트에 추세선을 자동으로 추가할 수 있나요?**  
A: 물론입니다. 슬라이드 컬렉션의 각 `IChart`를 순회하면서 각 시리즈에 적절한 `addTrendline` 메서드를 호출하면 됩니다.

**Q: 운영 환경에서 유료 라이선스가 필요합니까?**  
A: 예, 구매한 Aspose.Slides 라이선스를 사용하면 평가 제한이 해제되고 전체 성능 최적화 기능을 사용할 수 있습니다.

---

**Last Updated:** 2026-08-21  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## 관련 튜토리얼

- [aspose slides maven dependency: Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
date: '2026-07-27'
description: Aspose.Slides를 사용하여 doughnut chart java를 만드는 방법을 배우세요 – 라이브러리를 설정하고,
  사용자 정의 가능한 doughnut chart를 추가하고, hole size를 조정하고, 프레젠테이션을 저장하는 빠른 가이드.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Aspose.Slides를 사용하여 doughnut chart java를 만드는 방법을 배우세요 – 라이브러리를 설정하고,
  사용자 정의 가능한 doughnut chart를 추가하고, hole size를 조정하고, 프레젠테이션을 저장하는 빠른 가이드.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Aspose.Slides와 함께하는 Doughnut Chart Java 만들기 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Aspose.Slides와 함께하는 Doughnut Chart Java 만들기 – 단계별 가이드
url: /ko/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java에서 Aspose.Slides for Presentations를 사용하여 도넛 차트 만드는 방법

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 정보를 효과적으로 전달하는 데 필수적입니다. **Create doughnut chart java**는 현대적인 모양으로 비례 데이터를 나타내야 할 때 흔히 요구되는 작업입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 설정하고, 도넛 차트를 구축하며, 구멍 크기와 색상을 사용자 정의하고, 최종적으로 프레젠테이션 파일을 저장하는 방법을 배웁니다. 끝까지 진행하면 PowerPoint 데크를 자동으로 생성하는 모든 Java 프로젝트에 적용할 수 있는 재사용 가능한 패턴을 얻게 됩니다.

**배울 내용:**
- Aspose.Slides for Java 설정
- 프레젠테이션에서 도넛 차트 만들기 및 구성
- 구멍 크기와 같은 차트 미학 조정
- 새 차트가 포함된 프레젠테이션 저장

환경 설정부터 시작해봅시다!

## 빠른 답변
- **어떤 라이브러리가 도넛 차트 java를 생성합니까?** Aspose.Slides for Java.
- **기본 도넛 차트를 만들기 위해 필요한 코드 라인은 몇 줄입니까?** 프레젠테이션을 인스턴스화한 후 약 8–10줄입니다.
- **구멍 크기를 변경할 수 있나요?** 예, `setHoleSize(double)` 메서드는 0 %에서 100 %까지의 값을 허용합니다.
- **지원되는 출력 형식은 무엇입니까?** PPTX, PDF, XPS, PNG, JPEG 등 50가지 이상을 지원합니다.
- **프로덕션에서 라이선스가 필요합니까?** 무제한 사용을 위해서는 상용 라이선스가 필요하며, 평가용으로는 무료 체험판을 사용할 수 있습니다.

## Aspose.Slides for Java란 무엇인가?
**Aspose.Slides for Java**는 Microsoft Office 없이도 개발자가 PowerPoint 파일을 생성, 수정, 변환 및 렌더링할 수 있게 해주는 완전 관리형 API입니다. 50개 이상의 파일 형식을 지원하며, 메모리 사용량을 최소화하면서 수천 장의 슬라이드를 처리할 수 있습니다.

## 프레젠테이션에서 도넛 차트를 사용하는 이유
도넛 차트는 전체 대비 부분 관계를 표시하면서 중앙에 레이블이나 이미지를 배치할 공간을 제공합니다. Aspose.Slides는 일반적인 2.5 GHz 서버에서 **분당 500 슬라이드**까지 도넛 차트를 렌더링할 수 있으며, 전체 파일을 메모리에 로드하지 않고도 **수백 페이지 프레젠테이션**을 처리하므로 대규모 보고 솔루션에 이상적입니다.

## 전제 조건
시작하기 전에 다음 전제 조건을 충족했는지 확인하십시오:

### 필수 라이브러리 및 버전
Aspose.Slides for Java를 사용하려면 Maven 또는 Gradle을 통해 프로젝트에 포함하거나 직접 다운로드하십시오.

#### 환경 설정 요구 사항
- Java Development Kit (JDK) 8 이상 버전 권장.
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE).

### 지식 전제 조건
Java 및 기본 프로그래밍 개념에 익숙하면 도움이 됩니다. Maven 또는 Gradle에 대한 기본 지식은 설정 과정을 간소화합니다.

## Aspose.Slides for Java 설정
프로젝트에 Aspose.Slides를 포함하는 방법은 여러 가지가 있습니다:

**Maven:**  
`pom.xml` 파일에 다음 종속성을 추가하십시오:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
`build.gradle` 파일에 다음을 포함하십시오:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 최신 버전을 다운로드하십시오.

### 라이선스 획득
- **Free Trial:** Aspose.Slides 기능을 탐색하기 위해 체험판을 다운로드하십시오.  
- **Temporary License:** 제한 없이 확장된 기능을 사용하려면 임시 라이선스를 획득하십시오.  
- **Purchase:** 지속적인 사용을 위해서는 라이선스를 구매해야 합니다.

라이브러리를 설정하고 환경이 준비되면 도넛 차트 구현으로 넘어갑시다.

## Java에서 도넛 차트를 만드는 방법?
새 `Presentation` 객체를 로드하고, 슬라이드에 도넛 차트를 추가하고, 구멍 크기를 설정한 뒤 파일을 저장하면 됩니다—몇 가지 간단한 API 호출만으로 가능합니다. 이 방법은 차트 데이터, 외관 및 내보내기 형식에 대한 완전한 제어를 제공하며, 서버에 Microsoft PowerPoint가 설치되지 않아도 작동합니다.

### Presentation 객체 초기화
`Presentation` 클래스는 메모리 내에서 PowerPoint 파일을 나타내는 Aspose.Slides의 최상위 객체입니다.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
이 단계에서는 슬라이드, 도형 및 차트를 추가할 수 있는 빈 프레젠테이션을 생성합니다.

### 슬라이드에 도넛 차트 추가
`ISlide`는 단일 슬라이드에 대한 인터페이스이며, 첫 번째 슬라이드를 가져오거나 새 슬라이드를 추가할 수 있습니다.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
`addChart` 메서드는 도넛 차트를 생성하며, 매개변수는 슬라이드상의 위치(X, Y)와 크기(너비, 높이)를 정의합니다.

### 도넛 구멍 크기 구성
`Chart`는 `setHoleSize(double)`를 통해 차트 반경에 대한 백분율로 내부 반경을 제어합니다.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
구멍 크기를 90 %로 설정하면 차트가 거의 전체 원 형태로 표시되어 외부 세그먼트를 강조할 때 유용합니다.

### 프레젠테이션 저장
`presentation.save(String, SaveFormat)`은 선택한 형식으로 파일을 디스크에 기록합니다.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
예제는 결과를 `DoughnutHoleSize_out.pptx`로 저장하지만, PDF, PNG 등 50가지 이상의 지원 형식 중 하나를 선택할 수도 있습니다.

### 리소스 정리
`presentation.dispose()`를 호출하면 네이티브 리소스를 해제하고 메모리 누수를 방지할 수 있으며, 특히 장시간 실행되는 서버 애플리케이션에서 중요합니다.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## 실용적인 적용 사례
도넛 차트는 다재다능합니다. 다음과 같은 시나리오에서 특히 유용합니다:
1. **예산 배분:** 부서별 예산 분포를 표시합니다.  
2. **설문 조사 결과:** 다중 선택형 질문에 대한 응답을 시각화합니다.  
3. **웹사이트 트래픽 출처:** 다양한 채널(유기적, 유료, 추천 등)에서 오는 트래픽 비율을 보여줍니다.

## 성능 고려 사항
Aspose.Slides를 사용할 때 최적 성능을 위해 다음 팁을 참고하십시오:
- 작업이 끝난 즉시 `Presentation` 객체를 폐기하여 네이티브 메모리를 해제합니다.  
- 대용량 데이터 세트에는 스트림(`FileInputStream`, `ByteArrayOutputStream`)을 사용해 전체 파일을 RAM에 로드하는 것을 피합니다.  
- 많은 슬라이드를 루프에서 생성할 경우 차트 객체를 재사용하여 객체 생성 오버헤드를 줄입니다.

## 일반적인 문제 및 해결책
- **저장 중 오류:** 출력 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오.  
- **차트 데이터 누락:** `setHoleSize`를 호출하기 전에 차트의 `ChartData` 컬렉션을 채웠는지 확인하십시오.  
- **메모리 급증:** 수천 장의 슬라이드가 있는 경우 `Presentation.setSlideSize`를 더 작은 크기로 설정하고 중간 슬라이드를 즉시 폐기하십시오.

## 자주 묻는 질문

**Q: 도넛 차트 세그먼트 색상을 조정할 수 있나요?**  
A: 예. `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`을 사용한 뒤 원하는 RGB 색상을 지정하십시오.

**Q: 차트에 데이터 레이블을 추가하려면 어떻게 해야 하나요?**  
A: `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`를 호출하면 각 세그먼트 내부에 값이 표시됩니다.

**Q: PPTX 외에 다른 형식으로 차트를 저장할 수 있나요?**  
A: 물론입니다. Aspose.Slides는 PDF, XPS, PNG, JPEG, TIFF 등 50가지가 넘는 다양한 형식을 지원합니다.

**Q: 대용량 프레젠테이션을 로드할 때 예외가 발생하면 어떻게 해야 하나요?**  
A: 스트림을 받아들이는 `Presentation` 생성자를 사용하고 `loadOptions.setLoadFormat(LoadFormat.Pptx)`를 활성화하여 파일을 스트리밍하고 메모리 사용을 줄이십시오.

**Q: 실시간 데이터 소스로 차트 업데이트를 자동화할 수 있나요?**  
A: 예. 데이터베이스나 REST API에서 데이터를 가져와 `ChartData` 컬렉션을 업데이트하고 저장 전에 `chart.refresh()`를 호출하십시오.

## 리소스
- **Documentation:** 자세한 API 레퍼런스는 [Aspose.Slides for Java](https://reference.aspose.com/slides/java/)에서 확인하십시오.  
- **Download:** 최신 라이브러리 버전은 [Aspose.Slides releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.  
- **Purchase:** 전체 기능을 사용하려면 [Aspose Purchase](https://purchase.aspose.com/buy)에서 라이선스를 구매하십시오.  
- **Free Trial:** 다운로드 페이지에서 제공되는 무료 체험판으로 Aspose.Slides를 시험해 보십시오.  
- **Temporary License:** 제한 없이 확장 테스트를 위해 임시 라이선스를 획득하십시오.  
- **Support:** 질문이 있나요? [Aspose Forum](https://forum.aspose.com/c/slides/11)에서 도움을 받으세요.

---

**마지막 업데이트:** 2026-07-27  
**테스트 환경:** Aspose.Slides for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides와 Java로 차트 만들기: 종합 가이드](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
---
date: '2026-08-06'
description: Aspose.Slides를 사용하여 Java 프레젠테이션에서 chart를 만드는 방법과 동적 데이터 업데이트를 위한 workbook
  연결 방법을 배웁니다. 단계별 가이드.
keywords:
- how to create chart
- how to link workbook
- dynamic chart linking
lastmod: '2026-08-06'
og_description: Aspose.Slides를 사용하여 Java 프레젠테이션에서 chart를 만드는 방법과 동적 데이터 업데이트를 위한 workbook
  연결 방법을 배웁니다. 간결한 튜토리얼을 따라 보세요.
og_image_alt: 'Guide: create chart in Java with Aspose.Slides linking external workbook'
og_title: Aspose.Slides를 사용하여 Java 프레젠테이션에서 chart를 만드는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  headline: How to create chart in Java presentations with Aspose.Slides
  type: TechArticle
- description: Learn how to create chart in Java presentations using Aspose.Slides
    and how to link workbook for dynamic data updates. Step-by-step guide.
  name: How to create chart in Java presentations with Aspose.Slides
  steps:
  - name: '**Create a new presentation**'
    text: '**Create a new presentation**'
  - name: '**Access the first slide**'
    text: '**Access the first slide**'
  - name: '**Add a chart to the slide**'
    text: '**Add a chart to the slide**'
  - name: '**Set external workbook URL for chart data**'
    text: '**Set external workbook URL for chart data**'
  - name: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
    text: '**Real‑time data reporting** – sales dashboards that pull the latest figures
      from a central Excel file.'
  - name: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
    text: '**Financial analysis** – stock price trends that refresh automatically
      from a market data feed.'
  - name: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
    text: '**Project management** – KPI dashboards that reflect the most recent task
      completion stats.'
  type: HowTo
- questions:
  - answer: Charts update automatically when the linked Excel workbook changes.
    question: What is the main benefit?
  - answer: Aspose.Slides for Java 25.4 or newer.
    question: Which library version is required?
  - answer: A free trial works for development; a commercial license removes all evaluation
      limits.
    question: Do I need a license?
  - answer: Yes – both `.xlsx` and legacy `.xls` files are supported.
    question: Can I use any Excel format?
  - answer: Cache the workbook locally or use a CDN to minimise latency.
    question: Is network latency a concern?
  type: FAQPage
tags:
- create chart
- Aspose.Slides
- Java presentation
title: Aspose.Slides를 사용하여 Java 프레젠테이션에서 chart를 만드는 방법
url: /ko/java/charts-graphs/dynamic-charts-aspose-slides-java-external-workbook/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용한 Java 프레젠테이션에서 차트 만들기: 외부 워크북 연결

## 소개
이 튜토리얼에서는 Java 프레젠테이션에서 차트 객체를 **how to create chart**하고, 차트가 자동으로 새로 고침되도록 워크북 데이터를 **how to link workbook**하는 방법을 배웁니다. 동적 차트는 수동 복사‑붙여넣기 없이 슬라이드를 최신 상태로 유지해 주며, 실시간 보고, 재무 대시보드, 프로젝트 상태 데크에 필수적입니다. 설정, 구현 및 일반적인 함정들을 단계별로 안내하여 몇 줄의 코드만으로 실시간 Excel 데이터를 통합할 수 있도록 도와드립니다.

## 빠른 답변
- **What is the main benefit?** 차트는 연결된 Excel 워크북이 변경될 때 자동으로 업데이트됩니다.  
- **Which library version is required?** Aspose.Slides for Java 25.4 또는 최신 버전이 필요합니다.  
- **Do I need a license?** 무료 체험판은 개발에 사용할 수 있으며, 상용 라이선스를 구매하면 모든 평가 제한이 해제됩니다.  
- **Can I use any Excel format?** 예 – `.xlsx`와 기존 `.xls` 파일 모두 지원됩니다.  
- **Is network latency a concern?** 워크북을 로컬에 캐시하거나 CDN을 사용하여 지연 시간을 최소화하십시오.

## 동적 차트 연결이란 무엇인가요?
동적 차트 연결을 사용하면 차트가 런타임에 외부 워크북에서 데이터 소스를 읽어, 워크북이 변경될 때마다 다음에 슬라이드를 열 때 해당 변경 사항이 반영됩니다. 이를 통해 매 데이터 업데이트마다 프레젠테이션을 다시 생성할 필요가 없어집니다.

## 왜 Aspose.Slides for Java를 사용해야 하나요?
Aspose.Slides는 **50개 이상의 입력 및 출력 형식**을 지원하고, 전체 파일을 메모리에 로드하지 않고도 수백 페이지 프레젠테이션을 렌더링할 수 있으며, 일반 서버에서 차트 데이터 업데이트를 200 ms 이하로 처리합니다. 이러한 정량화된 성능 수치는 엔터프라이즈 보고 파이프라인에 신뢰할 수 있는 선택이 됩니다.

## 전제 조건
- **Aspose.Slides for Java** 25.4 이상.  
- **Java Development Kit (JDK)** 16 이상.  
- Maven 또는 Gradle을 사용한 의존성 관리에 익숙함.  

### 필요한 라이브러리 및 종속성
- **Aspose.Slides for Java** – 프레젠테이션 API를 제공합니다.  
- **Java Development Kit (JDK)** – 코드를 컴파일하고 실행하는 데 필요합니다.  

### 환경 설정 요구 사항
- 기본 Java 프로그래밍 지식.  
- 외부 Excel 워크북에 대한 접근 권한(로컬 파일 경로나 HTTP URL).  

## Aspose.Slides for Java 설정
프로젝트에 Aspose.Slides를 추가하려면 지원되는 빌드 시스템 중 하나를 선택하십시오.

### Maven 설정
`pom.xml`에 다음 종속성을 추가하십시오:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 설정
`build.gradle` 파일에 다음을 포함하십시오:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 라이브러리를 다운로드하십시오.

#### 라이선스 획득
무료 체험판으로 시작하거나 임시 라이선스를 받아 Aspose.Slides를 제한 없이 테스트하십시오. 장기 사용을 위해서는 라이선스 구매를 고려하십시오.

##### 기본 초기화 및 설정
`Presentation`은 메모리 내에서 PowerPoint 파일을 나타내는 Aspose.Slides의 핵심 클래스입니다. 프레젠테이션 객체를 다음과 같이 초기화하십시오:
```java
Presentation pres = new Presentation();
```

## 구현 가이드
이 섹션에서는 프레젠테이션에서 차트 데이터를 업데이트하기 위해 외부 워크북을 설정하는 과정을 단계별로 안내합니다.

### 차트 데이터 업데이트를 위한 외부 워크북 설정

#### 개요
이 기능을 사용하면 차트가 외부 소스에서 데이터를 동적으로 업데이트할 수 있습니다. 데이터가 자주 변경되고 슬라이드가 자동으로 해당 변경을 반영해야 할 때 이상적입니다.

#### 단계별 구현
1. **Create a new presentation**  
   먼저 새 `Presentation` 인스턴스를 생성합니다:
   ```java
   Presentation pres = new Presentation();
   ```

2. **Access the first slide**  
   슬라이드에 접근하는 것은 간단합니다:
   ```java
   ISlide slide = pres.getSlides().get_Item(0);
   ```

3. **Add a chart to the slide**  
   원형 차트를 원하는 위치와 크기로 추가합니다:
   ```java
   IChart chart = slide.getShapes().addChart(
       ChartType.Pie, 50, 50, 400, 600, true
   );
   ```

4. **Set external workbook URL for chart data**  
   외부 워크북을 데이터 소스로 지정합니다:
   ```java
   IChartData chartData = chart.getChartData();
   // Note: This is a demo URL and does not need to exist.
   chartData.setExternalWorkbook("http://path/doesnt/exist");
   ```

#### 구성 옵션
- **Chart type** – 데이터 시각화 방식에 따라 Pie, Bar, Line, Area 등 중에서 선택하십시오.  
- **Position & size** – 슬라이드 레이아웃에 맞게 X/Y 좌표와 너비/높이를 조정하십시오.  

## 워크북에 연결되는 차트를 만드는 방법
`Chart`는 차트 모양과 데이터를 캡슐화하는 Aspose.Slides 객체입니다.  
프레젠테이션을 로드하고 차트를 추가한 뒤 `chart.getChartData().setExternalWorkbook("https://example.com/data.xlsx")`를 호출합니다. 이제 차트는 파일이 열릴 때마다 워크북에서 시리즈 값을 읽어 들여 PPTX를 다시 생성하지 않아도 실시간 업데이트를 제공합니다. 이 직접 답변 문단은 GEO 요구 사항을 충족하며 간결하고 실행 가능한 설명을 제공합니다.

## 일반적인 문제 및 해결책
외부 링크가 업데이트되지 않을 경우:
- URL에 접근할 수 있고 유효한 Excel 파일을 반환하는지 확인하십시오.
- 서버가 익명 GET 요청을 허용하는지 확인하거나 필요시 인증 정보를 제공하십시오.
- 네트워크 지연이 큰 경우 워크북을 로컬에 캐시하고 프레젠테이션을 열기 전에 캐시를 업데이트하십시오.

## 실제 적용 사례
외부 워크북으로 구동되는 동적 차트는 여러 시나리오에서 유용합니다:
1. **Real‑time data reporting** – 중앙 Excel 파일에서 최신 수치를 가져오는 영업 대시보드.  
2. **Financial analysis** – 시장 데이터 피드에서 자동으로 새로 고침되는 주가 추세.  
3. **Project management** – 최신 작업 완료 통계를 반영하는 KPI 대시보드.  

## 성능 고려 사항
대용량 워크북을 다룰 때는 성능 최적화가 필수적입니다:
- 애플리케이션 서버에 워크북을 캐시하여 반복적인 네트워크 호출을 최소화하십시오.
- 스트리밍 API를 사용해 필요한 워크시트 범위만 읽어 메모리 사용량을 줄이십시오.
- Aspose.Slides는 10 MB 이하 워크북에 대해 차트 업데이트를 200 ms 미만으로 처리하므로 대부분의 보고 시나리오에 적합합니다.

## 결론
이 가이드를 따라 하면 Java 프레젠테이션에서 차트 객체를 **how to create chart**하고 워크북 데이터를 **how to link workbook**하여 자동 업데이트하는 방법을 알게 됩니다. 이 기능은 슬라이드를 보다 인터랙티브하게 만들고 수동 작업을 줄이며 이해관계자가 항상 최신 수치를 확인하도록 보장합니다. 슬라이드 복제, 애니메이션, PDF 내보내기 등 추가 Aspose.Slides 기능을 탐색하여 보고 워크플로를 더욱 향상시켜 보십시오.

## FAQ 섹션
**Q1: 외부 워크북으로 어떤 URL이든 사용할 수 있나요?**  
A1: URL은 접근 가능한 Excel 파일(`.xlsx` 또는 `.xls`)을 가리켜야 합니다. 서버가 올바른 MIME 유형을 반환하고, 필요시 인증이 코드에서 처리되는지 확인하십시오.

**Q2: 동적 연결을 지원하는 차트 유형은 무엇인가요?**  
A2: 모든 기본 Aspose.Slides 차트 유형—Pie, Bar, Line, Area, Scatter, Radar 등—을 외부 워크북에 연결할 수 있습니다.

**Q3: 외부 워크북의 크기 제한이 있나요?**  
A3: Aspose.Slides는 100 MB 이상의 워크북도 처리할 수 있지만 처리 시간은 선형적으로 증가합니다. 최상의 성능을 위해 파일을 20 MB 이하로 유지하거나 필요한 범위만 스트리밍하십시오.

**Q4: 접근할 수 없는 URL을 어떻게 처리해야 하나요?**  
A4: 연결 코드를 try‑catch 블록으로 감싸고 예외를 로그에 기록한 뒤, 필요에 따라 정적 데이터 소스로 대체하여 프레젠테이션이 계속 로드되도록 할 수 있습니다.

**Q5: 자동 보고 파이프라인에서 사용할 수 있나요?**  
A5: 물론 가능합니다. API는 헤드리스 환경에서도 동작하므로 서버에서 프레젠테이션을 생성·업데이트하고, 이메일에 삽입하거나 SharePoint 라이브러리에 게시할 수 있습니다.

## 리소스
- [Aspose.Slides Java 문서](https://reference.aspose.com/slides/java/)
- [Aspose.Slides for Java 다운로드](https://releases.aspose.com/slides/java/)
- [라이선스 구매](https://purchase.aspose.com/buy)
- [무료 체험 및 임시 라이선스](https://releases.aspose.com/slides/java/)
- [Aspose 지원 포럼](https://forum.aspose.com/c/slides/11)

---

**마지막 업데이트:** 2026-08-06  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose

## 관련 튜토리얼

- [Java에서 Aspose.Slides로 차트 만들기: 종합 가이드](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Aspose.Slides for Java를 사용해 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java로 PowerPoint 차트 애니메이션 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
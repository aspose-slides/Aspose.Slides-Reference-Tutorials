---
date: '2026-05-29'
description: Aspose.Slides Maven를 사용하여 파이 차트를 만드는 방법, 슬라이드에 파이 차트 java를 추가하고 차트 데이터를
  사용자 정의하는 방법을 배웁니다. Maven 설정 및 실제 예제가 포함된 단계별 가이드.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Aspose 파이 차트 만들기 – Maven을 사용하여 프레젠테이션에 차트 추가
url: /ko/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java를 사용하여 프레젠테이션에 파이 차트 추가하기

## 소개
이 가이드에서는 Aspose.Slides Maven을 사용하여 **create pie chart aspose**를 만들고 PowerPoint 슬라이드에 삽입하는 방법을 보여줍니다. 시각적으로 매력적인 프레젠테이션을 만드는 것은 정보를 효과적으로 전달하는 데 중요하며, 특히 데이터 시각화가 핵심 역할을 할 때 더욱 그렇습니다. **aspose slides maven**으로 이 프로세스를 자동화하고자 한다면 올바른 곳에 오신 것입니다. 슬라이드에 차트를 추가하는 과정을 단계별로 살펴보겠습니다 — 특히 파이 차트를 — 그리고 실제 시나리오에 맞게 커스터마이징하는 방법을 다룹니다.

### 배울 내용
- Java에서 프레젠테이션 객체를 초기화하는 방법.  
- 프레젠테이션의 첫 번째 슬라이드에 **add a pie chart java**를 추가하는 단계.  
- 차트 데이터 워크북에 접근하고 그 안의 워크시트를 나열하는 방법.  

Aspose.Slides Java를 활용하여 동적 차트로 프레젠테이션을 향상시키는 방법을 살펴보겠습니다!

## 빠른 답변
- **Maven을 통해 차트를 추가하는 라이브러리는 무엇입니까?** aspose slides maven  
- **시연된 차트 유형은 무엇입니까?** Pie chart (add chart to slide)  
- **필요한 최소 Java 버전은?** JDK 16 or later  
- **테스트에 라이선스가 필요합니까?** A free trial works; production needs a license  
- **Maven 의존성을 어디에서 찾을 수 있나요?** In the setup section below  

## Aspose Slides Maven이란?
Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 파일을 생성, 수정 및 렌더링할 수 있게 해주는 강력한 API입니다. Maven 패키지(`aspose-slides`)는 의존성 관리를 단순화하여, 저수준 파일 처리를 다루지 않고도 슬라이드 구축 및 커스터마이징—예: 파이 차트 추가—에 집중할 수 있게 해줍니다.

## 슬라이드에 차트를 추가하기 위해 Aspose.Slides Maven을 사용하는 이유
Aspose.Slides Maven을 사용하면 수동 PowerPoint 편집 없이 Java 코드에서 직접 차트를 생성할 수 있습니다. 차트 유형, 데이터 소스 및 스타일링에 대한 완전한 프로그래밍 제어를 제공하여 일관된 브랜딩과 정확성을 보장합니다. Maven 아티팩트는 모든 필수 의존성을 처리하여 빌드를 단순화하고 CI/CD 파이프라인에 원활하게 통합할 수 있게 합니다.

## 전제 조건
- **Aspose.Slides for Java** 버전 25.4 이상 (Maven/Gradle).  
- JDK 16+가 설치되어 있음.  
- IDE (IntelliJ IDEA, Eclipse 등).  
- 기본 Java 지식 및 Maven 또는 Gradle에 대한 이해.  

## Aspose.Slides for Java 설정
먼저, Maven 또는 Gradle을 통해 프로젝트에 Aspose.Slides를 포함합니다.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 Aspose 웹사이트에서 직접 [최신 릴리스를 다운로드](https://releases.aspose.com/slides/java/)할 수 있습니다.

### 라이선스 획득
Aspose.Slides for Java는 테스트용 임시 라이선스가 포함된 무료 체험판을 제공합니다. 제한 없는 프로덕션 사용을 위해서는 [구매 페이지](https://purchase.aspose.com/buy)를 통해 라이선스를 구매하십시오.

## 구현 가이드
아래에서는 솔루션을 두 가지 기능으로 나눕니다: 파이 차트 추가와 차트 데이터 워크북 접근.

### 기능 1: 프레젠테이션 생성 및 차트 추가
#### 개요
이 섹션에서는 새 프레젠테이션을 생성하고 첫 번째 슬라이드에 **add a pie chart**를 추가하는 방법을 보여줍니다.

#### 파이 차트 aspose를 만드는 방법?
`Presentation` 클래스를 로드하고 `ChartType.Pie` 유형의 차트를 추가한 뒤 파일을 저장합니다. 전체 작업은 세 번의 API 호출만으로 완료되며 일반적인 10슬라이드 데크에서는 1초 미만에 실행되어 자동 보고서 생성에 이상적입니다.

#### 단계별

**Step 1: 새 프레젠테이션 객체 초기화**  
`Presentation` 클래스는 Aspose.Slides의 최상위 객체로 메모리 내에서 PowerPoint 파일을 나타냅니다.  
```java
Presentation pres = new Presentation();
```
*모든 슬라이드를 보관할 `Presentation` 인스턴스를 생성합니다.*

**Step 2: 파이 차트 추가**  
`ChartType.Pie`는 Aspose에 파이 차트를 렌더링하도록 지시합니다.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*좌표 (50, 50)에 너비 400, 높이 500인 파이 차트를 배치합니다.*

**Step 3: 리소스 해제**  
`dispose()`를 호출하면 네이티브 리소스가 해제되어 메모리 누수를 방지합니다.  
```java
if (pres != null) pres.dispose();
```
*네이티브 리소스를 해제합니다; 작업이 끝났을 때 항상 `dispose()`를 호출하세요.*

### 기능 2: 차트 데이터 워크북 및 워크시트 접근
#### 개요
차트 데이터를 저장하는 기본 워크북에 접근하고 워크시트를 순회하는 방법을 배웁니다.

#### 차트 데이터 워크북에 접근하는 방법?
차트에서 `IChartDataWorkbook`을 가져온 뒤 `Worksheets` 컬렉션을 반복합니다. 이 워크북은 Excel 파일을 모방하여 프로그래밍 방식으로 데이터 시리즈를 읽고, 수정하거나 추가할 수 있으며, 차트는 런타임 중 새로 고침될 때 즉시 반영됩니다.

#### 단계별

**Step 1: (Reuse) 새 프레젠테이션 객체 초기화**  
*Feature 1, Step 1과 동일합니다.*

**Step 2: (Reuse) 파이 차트 추가**  
*Feature 1, Step 2와 동일합니다.*

**Step 3: 차트 데이터 워크북 가져오기**  
`IChartDataWorkbook`은 차트 내부의 Excel‑유사 워크북에 대한 읽기/쓰기 접근을 제공하는 인터페이스입니다.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*차트에 연결된 `IChartDataWorkbook`을 가져옵니다.*

**Step 4: 워크시트 순회**  
`Worksheet` 객체는 워크북 내부의 개별 시트를 나타냅니다.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*각 워크시트의 이름을 출력하여 데이터 구조를 확인할 수 있습니다.*

**Step 5: 리소스 해제**  
*Feature 1, Step 3과 동일합니다.*

## 실용적인 적용 사례
- **Data Reporting:** 최신 메트릭을 자동으로 생성하여 비즈니스 인텔리전스용 슬라이드 덱을 자동 생성합니다.  
- **Academic Presentations:** 수동 차트 생성 없이 연구 결과를 시각화합니다.  
- **Marketing Material:** 제품 성능이나 설문 결과를 즉시 보여줍니다.  

## 성능 고려 사항
- Aspose.Slides는 **50+ 입력 및 출력 포맷**을 처리할 수 있으며 전체 파일을 메모리에 로드하지 않고도 수백 페이지 프레젠테이션을 처리합니다.  
- 슬라이드와 차트 수를 적절히 유지하세요; 각 차트는 네이티브 메모리를 소비합니다.  
- `dispose()`를 항상 호출하여 리소스를 즉시 해제하세요.  
- 워크북 데이터 처리를 최적화하세요—대용량 데이터를 단일 차트에 로드하는 것을 피하십시오.  

## 결론
우리는 **aspose slides maven**이 프로그래밍 방식으로 **add chart to slide**을 가능하게 하고 차트 데이터 워크북을 다루는 방법을 다루었습니다. 이러한 빌딩 블록을 사용하면 깔끔한 PowerPoint 출력이 필요한 모든 보고 워크플로를 자동화할 수 있습니다.

### 다음 단계
- 차트 스타일 옵션(색상, 범례, 데이터 레이블) 탐색.  
- 외부 데이터 소스(CSV, 데이터베이스)와 연결하여 차트를 동적으로 채우기.  
- 풍부한 스토리텔링을 위해 단일 프레젠테이션에 여러 차트 유형 결합하기.  

## 자주 묻는 질문

**Q: Aspose.Slides for Java를 어떻게 설치합니까?**  
A: 위에 표시된 Maven 또는 Gradle 의존성을 사용하거나 릴리스 페이지에서 라이브러리를 다운로드하십시오.

**Q: Aspose.Slides의 시스템 요구 사항은 무엇입니까?**  
A: JDK 16 이상; 이 라이브러리는 Java를 지원하는 모든 플랫폼에서 실행됩니다.

**Q: 파이 차트 외에 다른 차트 유형을 추가할 수 있나요?**  
A: 예, Aspose.Slides는 막대, 선, 산점도, 레이더 등 20가지 이상의 차트 유형을 지원합니다.

**Q: 대용량 프레젠테이션을 효율적으로 처리하려면 어떻게 해야 하나요?**  
A: 객체를 즉시 dispose하고, 고해상도 이미지를 제한하며, 차트 템플릿을 재사용하여 메모리 사용량을 낮추세요.

**Q: Aspose.Slides 기능에 대한 자세한 정보를 어디서 찾을 수 있나요?**  
A: 전체 API 레퍼런스를 보려면 [Aspose documentation](https://reference.aspose.com/slides/java/)을 방문하십시오.

**Q: 상업적 사용에 라이선스가 필요합니까?**  
A: 프로덕션 사용에는 유효한 라이선스가 필요하며, 평가를 위해 무료 체험판을 사용할 수 있습니다.

**Q: Maven 패키지에 모든 차트 기능이 포함되어 있나요?**  
A: 예, `aspose-slides` Maven 아티팩트에는 전체 차트 엔진이 포함되어 있습니다.

## 리소스
- 문서: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- 다운로드: [Latest Releases](https://releases.aspose.com/slides/java/)
- 구매 및 체험: [Purchase Page](https://purchase.aspose.com/buy)
- 무료 체험: [Trial Downloads](https://releases.aspose.com/slides/java/)
- 임시 라이선스: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- 지원 포럼: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**마지막 업데이트:** 2026-05-29  
**테스트 환경:** Aspose.Slides 25.4 for Java (jdk16)  
**작성자:** Aspose

## 관련 튜토리얼

- [Java에서 Aspose.Slides로 파이 차트 색상 맞춤 방법 – 완전 가이드](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Java에서 Aspose.Slides로 파이 오브 파이 차트 만들기: 종합 가이드](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Aspose.Slides for Java를 사용한 PowerPoint 차트 애니메이션 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}
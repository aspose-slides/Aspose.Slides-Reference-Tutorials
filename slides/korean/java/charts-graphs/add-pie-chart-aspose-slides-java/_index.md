---
date: '2026-01-09'
description: aspose slides maven을 사용하여 슬라이드에 차트를 추가하고 Java 프레젠테이션에서 파이 차트를 맞춤 설정하는
  방법을 알아보세요. 단계별 설정, 코드 및 실제 예제.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven: 프레젠테이션에 파이 차트 추가'
url: /ko/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java를 사용하여 프레젠테이션에 파이 차트 추가하기

## Introduction
시각적으로 매력적인 프레젠테이션을 만드는 것은 정보를 효과적으로 전달하는 데 필수적이며, 특히 데이터 시각화가 중요한 역할을 할 때 더욱 그렇습니다. **aspose slides maven**을 사용해 이 과정을 자동화하고 싶다면, 여기가 바로 정답입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 이용해 **add chart to slide** — 특히 파이 차트 — 를 추가하는 방법을 배우고, 실제 시나리오에 맞게 커스터마이징하는 방법을 확인해 보세요.

### What You'll Learn
- Java에서 프레젠테이션 객체를 초기화하는 방법.  
- 프레젠테이션 첫 슬라이드에 **add a pie chart java**를 추가하는 단계.  
- 차트 데이터 워크북에 접근하고 워크시트를 열거하는 방법.  

Aspose.Slides Java를 활용해 동적 차트로 프레젠테이션을 강화하는 방법을 지금 바로 살펴보세요!

## Quick Answers
- **What library adds charts via Maven?** aspose slides maven  
- **Which chart type is demonstrated?** Pie chart (add chart to slide)  
- **Minimum Java version required?** JDK 16 or later  
- **Do I need a license for testing?** A free trial works; production needs a license  
- **Where can I find the Maven dependency?** In the setup section below  

## What is Aspose Slides Maven?
Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 파일을 생성, 수정 및 렌더링할 수 있게 해 주는 강력한 API입니다. Maven 패키지(`aspose-slides`)는 의존성 관리를 간소화하여, 파이 차트 추가와 같은 슬라이드 구축 및 커스터마이징에 집중할 수 있게 해 줍니다.

## Why Use Aspose.Slides Maven to Add a Chart to a Slide?
- **Automation:** 보고서와 대시보드를 자동으로 생성합니다.  
- **Precision:** 차트 유형, 데이터 및 스타일을 완벽히 제어합니다.  
- **Cross‑Platform:** Java 호환 환경 어디서든 동작합니다.  

## Prerequisites
- **Aspose.Slides for Java** 버전 25.4 이상 (Maven/Gradle).  
- JDK 16+ 설치.  
- IDE (IntelliJ IDEA, Eclipse 등).  
- 기본 Java 지식 및 Maven 또는 Gradle 사용 경험.

## Setting Up Aspose.Slides for Java
먼저 Maven 또는 Gradle을 통해 프로젝트에 Aspose.Slides를 포함합니다.

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

또는 Aspose 공식 웹사이트에서 직접 [download the latest release](https://releases.aspose.com/slides/java/)를 받을 수 있습니다.

### License Acquisition
Aspose.Slides for Java는 테스트용 임시 라이선스를 제공하는 무료 체험판을 제공합니다. 무제한 프로덕션 사용을 위해서는 [purchase page](https://purchase.aspose.com/buy)에서 라이선스를 구매하세요.

## Implementation Guide
아래에서는 두 가지 기능으로 솔루션을 나눕니다: 파이 차트 추가와 차트 데이터 워크북 접근.

### Feature 1: Creating a Presentation and Adding a Chart
#### Overview
새 프레젠테이션을 만들고 첫 슬라이드에 **add a pie chart**를 추가하는 방법을 보여줍니다.

#### Step‑by‑Step

**Step 1: Initialize a New Presentation Object**  
```java
Presentation pres = new Presentation();
```
*프레젠테이션에 포함될 모든 슬라이드를 보관할 `Presentation` 인스턴스를 생성합니다.*

**Step 2: Add a Pie Chart**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*좌표 (50, 50) 위치에 너비 400, 높이 500인 파이 차트를 배치합니다. `ChartType.Pie` 열거형이 Aspose에 파이 차트를 렌더링하도록 지시합니다.*

**Step 3: Dispose of Resources**  
```java
if (pres != null) pres.dispose();
```
*네이티브 리소스를 해제합니다; 작업이 끝났을 때 항상 `dispose()`를 호출하세요.*

### Feature 2: Accessing Chart Data Workbook and Worksheets
#### Overview
차트 데이터를 저장하는 기본 워크북에 접근하고 워크시트를 순회하는 방법을 배웁니다.

#### Step‑by‑Step

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Feature 1, Step 1과 동일합니다.*

**Step 2: (Reuse) Add a Pie Chart**  
*Feature 1, Step 2와 동일합니다.*

**Step 3: Get the Chart Data Workbook**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*차트와 연결된 `IChartDataWorkbook`을 가져옵니다.*

**Step 4: Iterate Through Worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*각 워크시트의 이름을 출력하여 데이터 구조를 확인합니다.*

**Step 5: Dispose of Resources**  
*Feature 1, Step 3과 동일합니다.*

## Practical Applications
- **Data Reporting:** 비즈니스 인텔리전스를 위한 최신 메트릭을 자동으로 슬라이드 덱에 생성합니다.  
- **Academic Presentations:** 연구 결과를 수동 차트 생성 없이 시각화합니다.  
- **Marketing Material:** 제품 성과나 설문 결과를 즉시 보여줄 수 있습니다.

## Performance Considerations
- 슬라이드와 차트 수를 적절히 유지하세요; 각각 메모리를 차지합니다.  
- 항상 `dispose()`를 호출해 네이티브 리소스를 해제합니다.  
- 워크북 데이터 처리를 최적화하고, 하나의 차트에 대용량 데이터를 로드하는 것을 피하세요.

## Conclusion
**aspose slides maven**을 사용해 프로그래밍 방식으로 **add chart to slide**를 수행하고 차트 데이터 워크북을 다루는 방법을 살펴보았습니다. 이 기본 블록들을 활용하면 깔끔한 PowerPoint 출력이 필요한 모든 보고 워크플로를 자동화할 수 있습니다.

### Next Steps
- 차트 스타일 옵션(색상, 범례, 데이터 레이블) 탐색하기.  
- 외부 데이터 소스(CSV, 데이터베이스)와 연결해 차트를 동적으로 채우기.  
- 풍부한 스토리텔링을 위해 하나의 프레젠테이션에 여러 차트 유형 결합하기.

## Frequently Asked Questions

**Q: How do I install Aspose.Slides for Java?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.

**Q: What are the system requirements for Aspose.Slides?**  
A: JDK 16 or later; the library is platform‑independent.

**Q: Can I add other chart types besides pie charts?**  
A: Yes, Aspose.Slides supports bar, line, scatter, and many more chart types.

**Q: How should I handle large presentations efficiently?**  
A: Dispose of objects promptly, limit the number of high‑resolution images, and reuse chart templates when possible.

**Q: Where can I find more details about Aspose.Slides features?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.

**Q: Is a license required for commercial use?**  
A: A valid license is required for production; a free trial is available for evaluation.

**Q: Does the Maven package include all chart capabilities?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.

---  

**Last Updated:** 2026-01-09  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## Resources
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)
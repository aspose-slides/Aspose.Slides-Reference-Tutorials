---
date: '2026-03-20'
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 클러스터형 열 차트를 추가하고, PowerPoint
  차트를 사용자 지정하며, 데이터 시리즈 차트를 삽입하는 방법을 배웁니다.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Aspose.Slides for Java를 사용하여 PowerPoint에 클러스터형 열 차트를 추가하는 방법
url: /ko/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint에서 Aspose.Slides for Java를 사용하여 클러스터형 열 차트 추가하는 방법

## 소개

PowerPoint 프레젠테이션에 **클러스터형 열 차트**를 추가해야 할 때, 명확한 용도는 원시 데이터를 인스턴트 데이터로 이해할 수 있는 게임이므로. PowerPoint에서 문서를 작성하는 데에는 시간이 많이 소요되며, 특히 프로그래밍으로 많은 슬라이드를 작성해야 하는 경우도 마찬가지입니다. **Aspose.Slides for Java**는 이러한 독립을 제거하고, 몇 줄의 PowerPoint 코드 차트를 생성·맞춤화하고 데이터 시리즈 차트를 삽입할 수 있게 됐습니다.

이 튜토리얼에서는 다음을 배웁니다:
- Aspose.Slides for Java를 사용하여 새 PowerPoint 프레젠테이션을 업로드합니다.
- **슬라이드에 차트 추가**를 수행하고 클러스터형 열 차트로 구성합니다.
- 카테고리의 그룹화 개념을 정의하여 **그룹화된 세로 막대형 차트를 생성**합니다.
- **데이터 계열 차트 삽입**을 삽입하여 데이터를 표시하도록 합니다.
- 완성된 프레젠테이션을 PPTX 파일로 저장합니다.

코드에 있기 위해 필요한 준비물이 함께 하였음을 알게 되었습니다.

## 빠른 답변
- **주요 클래스는 무엇입니까?** `com.aspose.slides`의 `Presentation`입니다.
- **사용되는 차트 유형은?** `ChartType.ClusteredColumn`.
- **테스트에 클러스터가 필요합니까?** 무료로 동작하지만, 클러스터를 사용하면 평가를 제한할 수 있습니다.
- **지원되는 Java 버전은?** JDK16 이상(예제는 JDK16 사용)입니다.
- **샘플을 실행하려면?** Maven/Gradle 의존성을 추가하고 추가로 `main` 방법을 실행합니다.

## '군집형 세로 막대형 차트 추가'란 무엇인가요?

*클러스터형 열 차트*(*그룹형 열 차트* 존재함)는 각 카테고리마다 여러 데이터 시리즈를 표시하여 그룹 간 값을 쉽게 쉽게 표시할 수 있습니다. PowerPoint에서 이 차트 유형은 분기별, 소비 결과 또는 동일한 카테고리 내 여러 데이터를 비교해야 하는 모든 상황에 있는 것입니다.

## 클러스터형 세로 막대형 차트를 추가하기 위해 Aspose.Slides를 사용하는 이유는 무엇입니까?

- **전체적으로** – 사용자가 백업 없이 슬라이드를 생성합니다.
- **세밀한 맞춤화** – 색상, 라벨, 그룹화 수준 등을 제어합니다.
- **크로스플랫폼** – Java를 지원하는 모든 OS에서 동작합니다.
- **Office 추가 필요** – 서버나 CI 파이프라인에서 PPTX 파일을 생성할 수 있습니다.

## 전제 조건

- **Aspose.Slides for Java** 라이브러리(최신 버전 추천).
- JDK16 이상.
- Maven 또는 Gradle 빌드 도구(또는 JAR를 직접 추가 가능).
- Java 코드를 편집하는 IDE 또는 텍스트 편집기.

## Java용 Aspose.Slides 설정

프로젝트에 라이브러리를 추가하려면 다음 빌드 스크립트 중 하나를 사용하십시오.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 최신 릴리스를 직접 다운로드할 수 있습니다.

### 라이선스 취득

운영에 배포하기 위한 권한을 부여합니다:
- **무료 체험** – 구매 없이 모든 기능을 탐색할 수 있습니다.
- **임시권** – 짧은 기간 동안 확장된 기능을 평가합니다.
- **정식 권위** – 사용이 가능해집니다. [Aspose 구매 페이지](https://purchase.aspose.com/buy)에서 예약하세요.

## 구현 가이드

각 단계를 진행하면서 **차트 추가 방법**과 **PowerPoint 차트를 맞춤화**하는 것에 대해 설명하겠습니다.

### 프레젠테이션 초기화

먼저 새 `Presentation` 객체를 생성하고 기본 슬라이드를 가져옵니다.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 슬라이드에 차트 추가

이제 `ClusteredColumn` 유형을 사용하여 **add chart to slide**를 수행하고 기본 데이터를 모두 지웁니다.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### 차트 데이터 통합 ​​문서 준비

차트는 데이터를 내부 워크북에 저장합니다. 새로 시작하기 위해 이를 초기화합니다.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### 그룹화 수준을 포함한 범주 추가

카테고리를 그룹화하면 **grouped column chart** 효과가 나타납니다. 각 카테고리는 논리적 그룹에 속할 수 있습니다.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### 차트에 데이터 계열 추가

여기서는 별도의 열로 시각화될 **insert data series chart** 항목을 추가합니다.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### 차트가 포함된 프레젠테이션 저장

마지막으로 PPTX 파일을 디스크에 기록합니다.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## 실제 적용

- **비즈니스 보고서** – 지역별 분기를 비교합니다.
- **학술 연구** – 실험 조건 변경 그룹화 실험 결과를 표시합니다.
- **프로젝트 관리** – 하나의 슬라이드에서 여러 팀의 작업을 편하게 하기를 바랍니다.

## 성능 고려 사항

- **메모리 관리** – 사용 후 큰 워크북을 해제합니다.
- **배치 작업** – 강제로 차트를 자주 업데이트하지 말고, 데이터를 먼저 수집한 뒤 적용합니다.
- **내장 최적화** – 주최 파일을 위해 `Presentation.optimize()`와 동일한 메서드를 Aspose.Slides가 제공합니다.

## 일반적인 함정 및 팁

- **함정:** 기존 시리즈/카테고리를 분류하는 데이터가 있습니다. 
**팁:** 새 데이터를 등록하기 전에 `clear()`를 호출하세요.
- **함정:** 잘못된 셀 주소 사용(예: `"c2"` 대신 `"C2"`). 
**팁:** 셀 참조는 대칭을 구분하지 않기 위해 독성을 위해 일관적으로 유지하세요.
- **팁:** `setGroupingItem`을 사용하여 의미 있는 그룹 레이블을 만들면 차트 범례에 자동으로 표시됩니다.

## 자주 묻는 질문

**Q1: ​​차트에 여러 시리즈를 어떻게 추가할 수 있나요?**
A1: `ch.getChartData().getSeries().add()`를 호출하여 각 시리즈에 고유 이름과 데이터 포인트를 제공합니다.

**Q2: Aspose.Slides 차트에서 흔히 발생하는 문제는 무엇입니까?**
A2: 문제는 주로 소수의 사람들이 찾는 문제에서 발생합니다. 모든 카테고리와 데이터 포인트에 해당 셀이 있는지 확인하세요.

**Q3: Aspose.Slides를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**
A3: 예, Aspose는 .NET, C++, Python 외에 추가적인 존재를 제공합니다.

**Q4: 프레젠테이션에서 기존 차트를 어떻게 업데이트하나요?**
A4: 프레젠테이션을 로드하고 `slide.getShapes().get_Item(index)`를 통해 차트를 찾은 뒤, 필요에 따라 시리즈나 서식을 수정합니다.

**Q5: Aspose.Slides 차트 유형에 제한이 있나요?**
A5: 라이브러리는 다양한 차트 유형을 지원하지만, 최신 문서에서 추가로 폐기된 형태를 확인하세요.

## 자원

- **문서**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **다운로드**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **구매**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **무료 체험**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **임시 라이선스**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **지원 포럼**: [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**마지막 업데이트:** 2026-03-20  
**테스트 환경:** Aspose.Slides for Java 25.4 (JDK 16)  
**작성자:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

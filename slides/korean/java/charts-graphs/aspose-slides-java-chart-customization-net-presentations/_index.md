---
date: '2026-01-17'
description: Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에서 차트에 시리즈를 추가하고 누적 세로 막대 차트를
  맞춤 설정하는 방법을 배워보세요.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Aspose.Slides for Java를 사용하여 .NET에서 차트에 시리즈 추가
url: /ko/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용한 .NET 프레젠테이션 차트 맞춤 설정 마스터하기

## 소개
데이터 기반 프레젠테이션 분야에서 차트는 원시 데이터를 매력적인 시각 스토리로 변환하는 필수 도구입니다. 특히 .NET 프레젠테이션 파일 안에서 프로그래밍으로 **add series to chart**를 해야 할 때 작업이 벅차게 느껴질 수 있습니다. 다행히 **Aspose.Slides for Java**는 강력하고 언어에 구애받지 않는 API를 제공하여 차트 생성 및 맞춤 설정을 간단하게 해줍니다—대상 형식이 .NET PPTX일지라도 말이죠.

이 튜토리얼에서는 **add series to chart** 방법, **add stacked column chart**를 슬라이드에 추가하는 방법, 그리고 간격 너비와 같은 시각적 요소를 미세 조정하는 방법을 배웁니다. 끝까지 진행하면 다채롭고 전문적인 슬라이드를 동적으로 생성할 수 있게 됩니다.

**배우게 될 내용**
- Aspose.Slides를 사용하여 빈 프레젠테이션을 만드는 방법
- **add stacked column chart**를 슬라이드에 추가하는 방법
- **add series to chart** 및 카테고리 정의 방법
- 데이터 포인트를 채우고 시각 설정을 조정하는 방법

개발 환경을 준비해 봅시다.

## 빠른 답변
- **프레젠테이션을 시작하기 위한 기본 클래스는 무엇인가요?** `Presentation`  
- **슬라이드에 차트를 추가하는 메서드는?** `slide.getShapes().addChart(...)`  
- **새 시리즈를 추가하려면 어떻게 하나요?** `chart.getChartData().getSeries().add(...)`  
- **막대 사이의 간격 너비를 변경할 수 있나요?** 예, 시리즈 그룹에서 `setGapWidth()`를 사용합니다  
- **프로덕션에 라이선스가 필요합니까?** 예, 유효한 Aspose.Slides for Java 라이선스가 필요합니다  

## “add series to chart”란 무엇인가요?
차트에 시리즈를 추가한다는 것은 차트가 별개의 시각 요소(예: 새로운 막대, 선, 혹은 조각)로 렌더링할 새로운 데이터 컬렉션을 삽입하는 것을 의미합니다. 각 시리즈는 자체 값, 색상 및 서식을 가질 수 있어 여러 데이터 세트를 나란히 비교할 수 있습니다.

## .NET 프레젠테이션을 수정할 때 Aspose.Slides for Java를 사용하는 이유는?
- **크로스 플랫폼**: Java 코드를 한 번 작성하면 .NET 애플리케이션에서 사용하는 PPTX 파일을 대상으로 할 수 있습니다.  
- **COM 또는 Office 의존성 없음**: 서버, CI 파이프라인 및 컨테이너에서 작동합니다.  
- **풍부한 차트 API**: 누적 세로 막대 차트를 포함해 50가지 이상의 차트 유형을 지원합니다.  

## 전제 조건
1. **Aspose.Slides for Java** 라이브러리 (버전 25.4 이상).  
2. Maven 또는 Gradle 빌드 도구, 혹은 수동 JAR 다운로드.  
3. 기본 Java 지식 및 PPTX 구조에 대한 이해.  

## Aspose.Slides for Java 설정
### Maven 설치
`pom.xml`에 다음 의존성을 추가하세요:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 설치
`build.gradle` 파일에 다음 라인을 포함하세요:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 공식 릴리스 페이지에서 최신 JAR를 다운로드하세요: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**라이선스 획득**  
무료 체험을 위해 [여기](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 다운로드하세요. 프로덕션 사용을 위해서는 전체 라이선스를 구매하여 모든 기능을 활성화하십시오.

## 단계별 구현 가이드
각 단계 아래에 원본 튜토리얼과 동일한 간결한 코드 스니펫이 있으며, 그 뒤에 해당 코드가 수행하는 작업에 대한 설명이 있습니다.

### Step 1: 빈 프레젠테이션 만들기
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*우리는 차트를 추가할 캔버스를 제공하는 깨끗한 PPTX 파일로 시작합니다.*

### Step 2: 슬라이드에 누적 세로 막대 차트 추가
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*`addChart` 메서드는 **add stacked column chart**를 생성하고 슬라이드의 좌상단에 배치합니다.*

### Step 3: 차트에 시리즈 추가 (주 목표)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*여기서 우리는 **add series to chart**를 수행합니다 – 각 호출은 별도의 열 그룹으로 표시되는 새로운 데이터 시리즈를 생성합니다.*

### Step 4: 차트에 카테고리 추가
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*카테고리는 X축 레이블 역할을 하여 각 열에 의미를 부여합니다.*

### Step 5: 시리즈 데이터 채우기
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*데이터 포인트는 각 시리즈에 숫자 값을 제공하며, 차트는 이를 막대 높이로 렌더링합니다.*

### Step 6: 차트 시리즈 그룹의 간격 너비 설정
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*간격 너비를 조정하면 특히 카테고리가 많을 때 가독성이 향상됩니다.*

## 일반적인 사용 사례
- **재무 보고** – 사업 부문별 분기 매출을 비교합니다.  
- **프로젝트 대시보드** – 팀별 작업 완료 비율을 표시합니다.  
- **마케팅 분석** – 캠페인 성과를 나란히 시각화합니다.  

## 성능 팁
- 여러 차트를 만들 때 **`Presentation` 객체를 재사용**하여 메모리 오버헤드를 줄이세요.  
- 시각 스토리에 필요한 데이터 포인트만 **제한**하세요.  
- 저장 후 **객체를 해제** (`presentation.dispose()`)하여 리소스를 해제하세요.  

## 자주 묻는 질문
**Q: 누적 세로 막대 외에 다른 차트 유형을 추가할 수 있나요?**  
A: 예, Aspose.Slides는 선, 원형, 영역 등 다양한 차트 유형을 지원합니다.

**Q: .NET 출력에 별도의 라이선스가 필요합니까?**  
A: 아니요, 동일한 Java 라이선스가 모든 출력 형식, 포함 .NET PPTX 파일에 적용됩니다.

**Q: 차트의 색상 팔레트를 어떻게 변경하나요?**  
A: `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)`를 사용하고 원하는 `Color`를 설정하세요.

**Q: 프로그래밍으로 데이터 레이블을 추가할 수 있나요?**  
A: 물론입니다. `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`를 호출하면 값이 표시됩니다.

**Q: 기존 프레젠테이션을 업데이트해야 하면 어떻게 하나요?**  
A: `new Presentation("existing.pptx")`로 파일을 로드하고 차트를 수정한 뒤 다시 저장하세요.

## 결론
이제 Aspose.Slides for Java를 사용하여 .NET 프레젠테이션에서 **add series to chart** 방법, **stacked column chart** 생성 및 외관을 미세 조정하는 전체적인 가이드를 갖추었습니다. 다양한 차트 유형, 색상 및 데이터 소스를 실험하여 이해관계자를 감동시킬 매력적인 시각 보고서를 만들어 보세요.

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

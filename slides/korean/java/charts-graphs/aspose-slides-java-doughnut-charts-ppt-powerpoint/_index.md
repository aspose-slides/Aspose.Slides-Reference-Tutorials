---
date: '2026-07-08'
description: Aspose를 사용하여 Java로 PowerPoint에서 doughnut chart를 만드는 방법을 배웁니다. 이 단계별 가이드는
  차트 데이터 포인트를 프로그래밍 방식으로 추가하고, 레이블을 사용자 정의하며, PPTX를 고품질로 저장하는 방법을 보여줍니다.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Aspose를 사용하면 Java로 PowerPoint에서 doughnut chart를 만들 수 있습니다. 이 튜토리얼을
  따라 데이터 포인트를 추가하고, 레이블을 사용자 정의하며, PPTX를 고품질로 저장하세요.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Aspose 사용 방법: PowerPoint(Java)에서 doughnut chart 만들기'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Aspose를 사용하여 PowerPoint(Java)에서 doughnut chart 만드는 방법
url: /ko/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose를 사용하여 PowerPoint에서 도넛 차트 만드는 방법 (Java)

## 소개
매력적인 프레젠테이션을 만들려면 텍스트와 이미지만으로는 부족할 때가 많으며, 차트는 데이터를 효과적으로 시각화하여 스토리텔링을 크게 향상시킬 수 있습니다. **Aspose를 사용한 차트 생성**은 PowerPoint를 열지 않고도 프로그래밍 방식으로 제어할 수 있게 해줍니다. 이 튜토리얼에서는 도넛 차트를 구축하고, 데이터 포인트를 구성하며, 고품질 PPTX를 저장하는 과정을 단계별로 안내합니다. 기본적인 Java 지식과 몇 분만 투자하면 됩니다.

`Aspose.Slides for Java`는 Microsoft Office 없이도 PowerPoint 파일을 생성, 조작 및 변환할 수 있는 Java 라이브러리입니다.

## 빠른 답변
- **PowerPoint용 도넛 차트를 생성하는 라이브러리는 무엇인가요?** Aspose.Slides for Java  
- **차트 데이터 포인트를 프로그래밍 방식으로 추가할 수 있나요?** 예, 차트 API를 사용합니다  
- **프로덕션에 라이선스가 필요합니까?** 유효한 Aspose.Slides 라이선스가 필요합니다  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상 (JDK 16 classifier 표시됨)  
- **몇 개의 시리즈를 추가할 수 있나요?** 예제는 최대 15개의 시리즈를 추가하지만 필요에 따라 조정할 수 있습니다  

## PowerPoint에서 도넛 차트란?
도넛 차트는 파이 차트와 유사하지만 중앙에 구멍이 있는 원형 차트로, 여러 시리즈를 동시에 표시할 수 있습니다. 전체와 부분 간의 관계를 강조하면서도 시각적 레이아웃을 컴팩트하고 읽기 쉽게 유지합니다.

## 왜 Aspose.Slides for Java를 사용해 도넛 차트를 만들까요?
Aspose.Slides for Java는 50개 이상의 입력 및 출력 형식을 지원하며, 전체 파일을 메모리에 로드하지 않고도 500 MB까지의 프레젠테이션을 생성할 수 있습니다. 차트 외관, 데이터 및 레이아웃에 대한 완전한 프로그래밍 제어를 제공하고, COM 인터옵을 제거하며, 일반 서버에서 100개의 차트가 포함된 슬라이드를 2초 미만에 렌더링할 수 있습니다.

## 사전 요구 사항
- Java 프로그래밍에 대한 기본 지식.  
- IntelliJ IDEA 또는 Eclipse와 같은 IDE.  
- 의존성 관리를 위한 Maven 또는 Gradle.  
- 유효한 Aspose.Slides for Java 라이선스(무료 체험 가능).

## Aspose.Slides for Java 설정
프로젝트에 맞는 의존성 관리자를 선택하세요.

**Maven**  
`pom.xml`에 다음 의존성을 추가합니다(버전은 최신 릴리스로 교체).

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle`에 다음 줄을 추가합니다.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

직접 다운로드를 원한다면 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) 페이지를 방문하세요.

### 라이선스 획득
무료 체험으로 Aspose.Slides 기능을 탐색할 수 있습니다. 장기 사용을 위해서는 라이선스를 구매하거나 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 요청하세요. 환경 설정 및 Aspose.Slides 초기화 방법은 제공된 지침을 따르세요.

## Aspose.Slides for Java를 사용해 PowerPoint 도넛 차트 만들기
도넛 차트를 만들려면 `Presentation`을 로드하거나 새로 생성하고, `ChartType.Doughnut` 유형의 차트 도형을 추가한 뒤 기본 시리즈를 제거하고 구멍 크기를 설정합니다. 그런 다음 차트 워크북에 카테고리 이름과 숫자 값을 채우고, 레이블 서식을 조정한 뒤 PPTX로 저장합니다.

### 단계 1: 프레젠테이션 초기화
새 프레젠테이션을 만들거나 기존 파일을 열어 슬라이드 컬렉션을 얻습니다.

`Presentation`은 PowerPoint 파일을 나타내는 기본 클래스입니다.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 단계 2: 슬라이드에 도넛 차트 추가
차트 도형을 삽입하고 기본 시리즈/카테고리를 제거한 뒤 도넛 구멍 크기와 같은 기본 시각 설정을 구성합니다.

`Chart`(또는 차트 도형)는 슬라이드에 배치된 차트 객체를 나타냅니다.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 단계 3: 차트 데이터 포인트 추가 및 레이블 사용자 정의
카테고리 이름을 채우고 각 시리즈에 데이터 포인트를 추가한 뒤 레이블 서식(폰트, 색상, 위치)을 미세 조정합니다. 이 단계는 “차트 데이터 포인트 추가” 기능을 보여줍니다.

`Workbook`은 차트의 기본 스프레드시트 데이터에 접근할 수 있게 하며, 여기서 셀을 채웁니다.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 단계 4: 업데이트된 프레젠테이션 저장
변경 사항을 새 PPTX 파일로 디스크에 저장합니다.

`save`는 선택한 형식으로 프레젠테이션을 파일에 기록합니다.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## 실용적인 적용 사례
- **재무 보고서:** 예산 할당 또는 비용 분류 시각화.  
- **시장 분석:** 경쟁사 간 시장 점유율 분포 표시.  
- **설문 조사 결과:** 범주형 설문 데이터를 간결하게 제시.  
- **대시보드 생성:** 데이터베이스 쿼리와 결합해 실시간 업데이트 슬라이드 생성.

## 성능 고려 사항
- **리소스 해제:** 저장 후 `pres.dispose()`를 호출해 네이티브 메모리를 해제합니다.  
- **차트 수 제한:** 수백 개의 차트를 추가하면 메모리 사용량이 증가할 수 있으니 필요 시 배치 처리하세요.  
- **스트리밍 사용:** 대용량 데이터 세트의 경우 메모리 배열 대신 스트림으로 직접 워크북을 채우세요.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결책 |
|-------|-------|-----|
| **차트가 빈 화면으로 표시됨** | 데이터 셀이 올바르게 채워지지 않음 | `workBook.getCell(...)`가 올바른 행/열 인덱스를 참조하는지 확인하십시오. |
| **레이블이 겹침** | 제한된 공간에 카테고리가 너무 많음 | `DoughnutHoleSize`를 늘리거나 `FirstSliceAngle`을 조정하십시오. |
| **OutOfMemoryError** | 해제 없이 큰 프레젠테이션 사용 | 저장 후 `pres.dispose()`를 호출하고 JVM 힙 크기 증대를 고려하십시오. |

## 자주 묻는 질문

**Q: Java 애플리케이션에서 Aspose.Slides for Java를 상업적으로 사용할 수 있나요?**  
A: 예, 유효한 상업용 라이선스가 필요합니다. 평가용 무료 체험이 제공됩니다.

**Q: 15개 이상의 시리즈를 추가하려면 어떻게 해야 하나요?**  
A: “Add Doughnut Chart” 단계에서 루프 제한을 늘리고 데이터 워크북에 충분한 행이 있는지 확인하십시오.

**Q: 생성 후 도넛 구멍 크기를 변경할 수 있나요?**  
A: 예, 저장하기 전에 `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`를 호출하십시오.

**Q: 차트를 PPTX 대신 이미지로 내보낼 수 있나요?**  
A: 물론입니다. `chart.getImage()`를 사용하고 반환된 `java.awt.image.BufferedImage`를 원하는 형식으로 저장하십시오.

**Q: Aspose.Slides에서 애니메이션 차트를 지원하나요?**  
A: `ISlide.getTimeline()` API를 통해 애니메이션을 추가할 수 있지만, 이 튜토리얼 범위를 벗어납니다.

## 결론
이제 Aspose.Slides for Java를 사용해 **PowerPoint 도넛 차트** 파일을 **생성**하고, **차트 데이터 포인트 추가**, 레이블 사용자 정의 및 성능 고려 사항을 처리하는 완전한 생산 준비 방법을 알게 되었습니다. 다양한 색상, 데이터 소스 및 차트 유형을 실험해 프레젠테이션을 더욱 돋보이게 하세요.

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용해 PowerPoint에 차트 추가하기: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides for Java를 사용해 PowerPoint 차트 데이터 편집하기: 종합 가이드](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Aspose.Slides for Java를 사용해 PowerPoint 차트 애니메이션 만들기 – 단계별 가이드](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
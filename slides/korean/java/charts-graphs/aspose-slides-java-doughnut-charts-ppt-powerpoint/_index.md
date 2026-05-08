---
date: '2026-02-17'
description: Aspose.Slides for Java를 사용하여 도넛 차트 PowerPoint를 만드는 방법을 배우고 차트 데이터 포인트를
  프로그래밍 방식으로 추가하세요. 쉬운 단계와 코드 예제를 따라해 보세요.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Aspose.Slides for Java로 도넛 차트 PowerPoint 만들기
url: /ko/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

Point** 파일을 만들기 위한 완전하고 프로덕션 준비된 방법을 갖추었습니다. 여기에는 **차트 데이터 포인트 추가**, 레이블 사용자 정의 및 성능 고려 사항 처리 방법이 포함됩니다. 다양한 색상, 데이터 소스 및 차트 유형을 실험하여 프레젠테이션을 더욱 돋보이게 해 보세요."

--- separator stays.

**Last Updated:** 2026-02-17 => same.

**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier) => same.

**Author:** Aspose => same.

Then closing shortcodes.

Also need to translate "Last Updated" and "Tested With" and "Author"? These are labels; we should translate them? The instruction says translate all text content. So yes translate.

**Last Updated:** => "**마지막 업데이트:**"

**Tested With:** => "**테스트 환경:**"

**Author:** => "**작성자:**"

Now ensure we keep markdown bold formatting.

Now produce final output with all content.

Let's assemble.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java로 도넛 차트 PowerPoint 만들기

## 소개
매력적인 프레젠테이션을 만들려면 텍스트와 이미지만으로는 부족한 경우가 많으며, 차트는 데이터를 효과적으로 시각화하여 스토리텔링을 크게 향상시킬 수 있습니다. 하지만 많은 개발자들이 프로그래밍 방식으로 PowerPoint 파일에 동적 차트 기능을 통합하는 데 어려움을 겪습니다. 이 튜토리얼에서는 유연성과 사용 편의성을 겸비한 강력한 도구인 Aspose.Slides for Java를 사용하여 **도넛 차트 PowerPoint**를 만드는 방법을 보여줍니다.

**배우게 될 내용:**
- Aspose.Slides for Java를 사용하여 프레젠테이션 초기화하는 방법
- 슬라이드에 도넛 차트를 추가하는 단계별 가이드
- 데이터 포인트 구성 및 레이블 속성 사용자 정의
- 수정된 프레젠테이션을 고품질로 저장하기

이러한 기능을 활용하여 프레젠테이션을 향상시키는 방법을 살펴보겠습니다. 시작하기 전에 기본 Java 프로그래밍 개념에 익숙한지 확인하세요.

## 빠른 답변
- **도넛 차트 PowerPoint를 생성하는 라이브러리는?** Aspose.Slides for Java
- **프로그래밍 방식으로 차트 데이터 포인트를 추가할 수 있나요?** 예, 차트 API를 사용합니다
- **프로덕션에 라이선스가 필요합니까?** 유효한 Aspose.Slides 라이선스가 필요합니다
- **지원되는 Java 버전은?** Java 8 이상 (JDK 16 classifier 표시)
- **몇 개의 시리즈를 추가할 수 있나요?** 예제에서는 최대 15개의 시리즈를 추가하지만 필요에 따라 조정할 수 있습니다

## PowerPoint에서 도넛 차트란?
도넛 차트는 중앙에 구멍이 있는 파이 차트의 변형으로, 여러 데이터 시리즈를 컴팩트하고 시각적으로 매력적인 방식으로 표시할 수 있습니다. 전체 대비 부분 관계를 보여주면서 디자인을 깔끔하게 유지하는 데 이상적입니다.

## 왜 Aspose.Slides for Java를 사용하여 도넛 차트를 만들까요?
- **전체 제어** PowerPoint를 열지 않고 차트 외관, 데이터 및 레이아웃을 제어
- **COM 인터옵 없음** – Java를 지원하는 모든 플랫폼에서 작동
- **고성능** 대용량 프레젠테이션 생성 또는 웹 서비스와 통합
- **풍부한 사용자 정의** 폭발 효과, 구멍 크기, 슬라이스 각도, 레이블 서식 등

## 사전 요구 사항
- Java 프로그래밍 기본 지식
- IntelliJ IDEA 또는 Eclipse와 같은 IDE
- 의존성 관리를 위한 Maven 또는 Gradle
- 유효한 Aspose.Slides for Java 라이선스(무료 체험 가능)

## Aspose.Slides for Java 설정
프로젝트에 맞는 의존성 관리자를 선택하세요.

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

직접 다운로드를 선호한다면 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/) 페이지를 방문하세요.

### 라이선스 획득
Aspose.Slides 기능을 탐색하려면 무료 체험으로 시작할 수 있습니다. 장기 사용을 위해서는 라이선스를 구매하거나 [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 요청하세요. 환경 설정 및 애플리케이션에서 Aspose.Slides를 초기화하는 방법에 대한 지침을 따라 주세요.

## Aspose.Slides for Java를 사용하여 도넛 차트 PowerPoint 만드는 방법
아래는 완전한 단계별 가이드입니다. 각 코드 블록은 바로 앞에서 설명되므로 어떤 작업이 수행되는지 정확히 알 수 있습니다.

### 단계 1: 프레젠테이션 초기화
먼저 기존 PPTX 파일을 로드하거나 새 파일을 생성합니다. 이렇게 하면 슬라이드 컬렉션을 추가 수정할 준비가 됩니다.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 단계 2: 슬라이드에 도넛 차트 추가
차트 모양을 추가하고 기본 시리즈/카테고리를 제거한 뒤 기본 시각 속성을 설정합니다.

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

### 단계 3: 차트 데이터 포인트 추가 및 레이블 사용자 정의
여기서는 카테고리를 채우고 각 시리즈에 대한 데이터 포인트를 추가하며 레이블 모양을 세밀하게 조정합니다. 바로 이 부분에서 **add chart data points** 키워드가 사용됩니다.

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

### 단계 4: 업데이트된 프레젠테이션 저장
마지막으로 변경 내용을 새로운 PPTX 파일에 저장합니다.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 실용적인 적용 사례
- **재무 보고서:** 예산 할당 또는 비용 분류를 시각화
- **시장 분석:** 경쟁사 간 시장 점유율 분포 표시
- **설문 조사 결과:** 범주형 설문 데이터를 컴팩트하게 표시
- **대시보드 생성:** 데이터베이스 쿼리와 결합하여 실시간 업데이트 슬라이드 생성

## 성능 고려 사항
- **리소스 해제**: 작업이 끝나면 `pres.dispose()`를 호출하여 네이티브 메모리를 해제합니다.
- **차트 수 제한**: 수백 개의 차트를 추가하면 메모리 사용량이 증가할 수 있으니 필요 시 배치 처리하세요.
- **스트리밍 사용**: 대용량 데이터 세트의 경우 메모리 배열 대신 스트림에서 직접 워크북을 채우세요.

## 일반적인 문제 및 해결책
| Issue | Cause | Fix |
|-------|-------|-----|
| **차트가 비어 있음** | 데이터 셀이 올바르게 채워지지 않음 | `workBook.getCell(...)`가 올바른 행/열 인덱스를 참조하는지 확인하십시오. |
| **레이블 겹침** | 제한된 공간에 카테고리가 너무 많음 | `DoughnutHoleSize`를 늘리거나 `FirstSliceAngle`을 조정하십시오. |
| **OutOfMemoryError** | 해제 없이 큰 프레젠테이션 사용 | 저장 후 `pres.dispose()`를 호출하고 JVM 힙 크기 증가를 고려하십시오. |

## 자주 묻는 질문

**Q: Aspose.Slides for Java를 상업용 애플리케이션에서 사용할 수 있나요?**  
A: 예, 유효한 상업용 라이선스가 필요합니다. 평가용 무료 체험이 제공됩니다.

**Q: 15개 이상의 시리즈를 추가하려면 어떻게 해야 하나요?**  
A: “Add Doughnut Chart” 단계에서 루프 제한을 늘리고 데이터 워크북에 충분한 행이 있는지 확인하십시오.

**Q: 생성 후에 도넛 구멍 크기를 변경할 수 있나요?**  
A: 예, 저장하기 전 언제든지 `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`를 호출하십시오.

**Q: 차트를 PPTX 대신 이미지로 내보낼 수 있나요?**  
A: 물론입니다. `chart.getImage()`를 사용하고 반환된 `java.awt.image.BufferedImage`를 원하는 형식으로 저장하십시오.

**Q: Aspose.Slides가 애니메이션 차트를 지원하나요?**  
A: `ISlide.getTimeline()` API를 통해 애니메이션을 추가할 수 있지만, 이 튜토리얼의 범위를 벗어납니다.

## 결론
이제 Aspose.Slides for Java를 사용하여 **도넛 차트 PowerPoint** 파일을 만들기 위한 완전하고 프로덕션 준비된 방법을 갖추었습니다. 여기에는 **차트 데이터 포인트 추가**, 레이블 사용자 정의 및 성능 고려 사항 처리 방법이 포함됩니다. 다양한 색상, 데이터 소스 및 차트 유형을 실험하여 프레젠테이션을 더욱 돋보이게 해 보세요.

---

**마지막 업데이트:** 2026-02-17  
**테스트 환경:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
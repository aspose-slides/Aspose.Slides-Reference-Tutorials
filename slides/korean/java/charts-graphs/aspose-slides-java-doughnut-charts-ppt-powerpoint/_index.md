---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 PowerPoint에서 역동적인 도넛형 차트를 만드는 방법을 알아보세요. 따라 하기 쉬운 단계와 코드 예제를 통해 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"title": "Java용 Aspose.Slides를 사용하여 PowerPoint에서 동적 도넛형 차트 만들기"
"url": "/ko/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java용 Aspose.Slides를 사용하여 PowerPoint에서 동적 도넛 차트 만들기

## 소개
매력적인 프레젠테이션을 만들려면 텍스트와 이미지만으로는 부족할 때가 많습니다. 차트는 데이터를 효과적으로 시각화하여 스토리텔링을 크게 향상시킬 수 있습니다. 하지만 많은 개발자들이 PowerPoint 파일에 동적 차트 기능을 프로그래밍 방식으로 통합하는 데 어려움을 겪습니다. 이 튜토리얼에서는 Java용 Aspose.Slides를 사용하여 PowerPoint에서 도넛형 차트를 만드는 방법을 보여줍니다. 도넛형 차트는 유연성과 사용 편의성을 모두 갖춘 강력한 도구입니다.

**배울 내용:**
- Java용 Aspose.Slides를 사용하여 프레젠테이션을 초기화하는 방법
- 슬라이드에 도넛형 차트를 추가하는 단계별 가이드
- 데이터 포인트 구성 및 레이블 속성 사용자 정의
- 수정된 프레젠테이션을 높은 충실도로 저장

이러한 기능을 활용하여 프레젠테이션을 더욱 효과적으로 만드는 방법을 살펴보겠습니다. 시작하기 전에 기본적인 Java 프로그래밍 개념을 숙지하시기 바랍니다.

## 필수 조건
이 튜토리얼을 효과적으로 따르려면 다음 사항이 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- IntelliJ IDEA나 Eclipse와 같은 통합 개발 환경(IDE).
- 종속성 관리를 위해 Maven 또는 Gradle을 설치했습니다.
- 유효한 Aspose.Slides for Java 라이선스가 필요합니다. 무료 평가판을 통해 기능을 테스트해 보세요.

## Java용 Aspose.Slides 설정
먼저 Aspose.Slides를 프로젝트에 통합하세요. Maven과 Gradle 중 원하는 것을 선택하세요.

**메이븐**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

직접 다운로드를 원하시면 다음을 방문하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/) 페이지.

### 라이센스 취득
Aspose.Slides의 기능을 체험해 보려면 무료 체험판을 시작하세요. 장기간 사용하려면 라이선스를 구매하거나 임시 라이선스를 요청하세요. [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)제공된 지침에 따라 애플리케이션에서 환경을 설정하고 Aspose.Slides를 초기화하세요.

## 구현 가이드
Aspose.Slides for Java를 사용하여 PowerPoint에서 도넛형 차트를 만드는 데 필요한 단계를 자세히 살펴보겠습니다. 각 섹션은 특정 기능에 중점을 두고 있어 명확성과 집중도를 높였습니다.

### 프레젠테이션 초기화
먼저 새 PowerPoint 파일을 로드하거나 만들어 보세요. 이 단계에서는 프레젠테이션 환경을 설정합니다.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// 초기 프레젠테이션을 저장하여 성공적인 로딩을 확인하세요.
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 도넛 차트 추가
슬라이드에 도넛형 차트를 추가하고 크기와 모양을 사용자 지정합니다.

```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// 시리즈 속성 구성
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 데이터 포인트 및 레이블 구성
각 데이터 포인트의 모양을 사용자 지정하고 가독성을 향상시키도록 레이블을 구성합니다.

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
        
        // 데이터 포인트 포맷
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // 각 카테고리의 마지막 시리즈에 대한 레이블 속성을 사용자 정의합니다.
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

### 프레젠테이션 저장
차트를 구성한 후, 변경 사항을 유지하려면 프레젠테이션을 저장하세요.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## 실제 응용 프로그램
도넛형 차트는 다양한 시나리오에서 사용될 수 있습니다.
- **재무 보고서:** 예산 배분이나 재무 지표를 시각화합니다.
- **시장 분석:** 경쟁사들 간의 시장점유율 분포를 보여줍니다.
- **설문조사 결과:** 설문조사 응답에서 범주형 데이터를 효과적으로 제시합니다.

데이터베이스 및 웹 애플리케이션과 같은 다른 시스템과 통합하면 실시간 데이터를 기반으로 동적 차트를 생성할 수 있습니다.

## 성능 고려 사항
최적의 성능을 위해:
- 리소스를 신속하게 처리하여 메모리 사용을 관리합니다.
- 필요하지 않다면 처리 능력을 보존하기 위해 차트나 슬라이드의 수를 제한하세요.
- 대용량 데이터 세트를 처리하려면 효율적인 데이터 구조를 사용하세요.

모범 사례를 준수하면, 특히 복잡한 프레젠테이션을 처리할 때 애플리케이션이 원활하게 실행됩니다.

## 결론
핵심 단계만 이해하면 Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 도넛형 차트를 만드는 것은 매우 간단합니다. 이 가이드를 통해 시각적으로 매력적인 차트를 통합하여 데이터 인사이트를 효과적으로 전달하고 프레젠테이션을 더욱 풍성하게 만들 수 있습니다.

Aspose.Slides의 기능을 더욱 자세히 알아보고 그 성능을 심층적으로 이해하려면 다양한 차트 유형이나 애니메이션, 전환과 같은 고급 기능을 실험해 보세요.

## FAQ 섹션
**질문: Aspose.Slides for Java를 상업용 애플리케이션에서 사용할 수 있나요?**
A: 네, 하지만 라이선스를 구매해야 합니다. 무료 체험판을 통해 기능을 체험해 보실 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
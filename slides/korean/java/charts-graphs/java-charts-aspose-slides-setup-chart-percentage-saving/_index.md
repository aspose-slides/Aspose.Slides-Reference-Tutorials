---
"date": "2025-04-17"
"description": "Aspose.Slides를 사용하여 Java 프레젠테이션에서 백분율 레이블이 있는 차트를 만들고, 사용자 지정하고, 저장하는 방법을 알아보세요. 오늘 바로 프레젠테이션 실력을 향상시켜 보세요!"
"title": "Aspose.Slides를 사용하여 Java 프레젠테이션에서 차트 만들기 및 사용자 지정"
"url": "/ko/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java 프레젠테이션에서 차트 만들기 및 사용자 지정

## 소개
매력적인 프레젠테이션을 만들려면 단순히 텍스트만으로는 부족합니다. 정보를 효과적으로 전달하는 역동적인 차트가 필요하죠. Aspose.Slides를 사용하여 정교한 차트 기능으로 Java 기반 프레젠테이션을 더욱 향상시키고 싶다면 이 튜토리얼이 도움이 될 것입니다. 프레젠테이션 만들기, 차트 추가 및 구성, 합계 계산, 백분율 레이블 표시, 작업 저장까지 몇 가지 간단한 단계만으로 모든 과정을 안내해 드립니다.

**배울 내용:**
- Java용 Aspose.Slides를 사용하여 차트가 포함된 프레젠테이션을 만들고 사용자 지정하는 방법
- 차트에서 카테고리 총계 계산
- 차트에 데이터를 백분율 레이블로 표시
- 향상된 차트 기능으로 프레젠테이션 저장

시작하기 전에 필요한 전제 조건을 살펴보겠습니다.

## 필수 조건
이 튜토리얼을 따르려면 다음 사항이 있는지 확인하세요.

- **자바 개발 키트(JDK)**: 버전 8 이상.
- **IDE**: IntelliJ IDEA, Eclipse 또는 Java를 지원하는 IDE 등.
- **Java용 Aspose.Slides 라이브러리**: 이는 프레젠테이션 기능을 처리하는 데 중요합니다.

### 필수 라이브러리 및 버전
Java용 Aspose.Slides가 필요합니다. 프로젝트에 포함하는 방법은 다음과 같습니다.

**메이븐:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 최신 버전을 다음에서 직접 다운로드할 수 있습니다. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 환경 설정
개발 환경이 JDK 8 이상을 사용하도록 구성되어 있는지 확인하고, IDE가 Maven이나 Gradle을 사용하여 종속성을 관리하도록 설정되어 있는지 확인하세요.

**라이센스 취득:**
- **무료 체험**: 테스트 목적으로 기본 기능에 접근합니다.
- **임시 면허**: 평가 제한 없이 고급 기능을 테스트합니다.
- **구입**: 장기간 상업적으로 이용하려면 라이선스 구매를 고려하세요.

## Java용 Aspose.Slides 설정
먼저 Java 프로젝트에 Aspose.Slides 라이브러리를 설정하세요. 초기화 및 설정 방법은 다음과 같습니다.

1. 위에 표시된 대로 Maven이나 Gradle을 통해 종속성을 추가합니다.
2. 필요한 Aspose.Slides 패키지를 가져옵니다.
   ```java
   import com.aspose.slides.*;
   ```

3. 새로운 것을 초기화합니다 `Presentation` 사례:
   ```java
   Presentation presentation = new Presentation();
   ```

이 설정을 사용하면 프로그래밍 방식으로 프레젠테이션을 만들 수 있습니다.

## 구현 가이드

### 프레젠테이션에서 차트 만들기 및 사용자 지정

#### 개요
차트를 만들려면 프레젠테이션을 초기화하고, 슬라이드에 액세스하고, 차트 유형, 위치, 크기와 같은 특정 속성을 추가하는 작업이 필요합니다.

**단계:**
1. **프레젠테이션 인스턴스 생성**: 인스턴스를 생성하여 시작합니다. `Presentation` 수업.
2. **슬라이드 접근**: 첫 번째 슬라이드를 검색합니다. `get_Item(0)`.
3. **차트 추가**: 사용 `addChart()` 정의된 차원을 사용하여 지정된 좌표에 쌓인 막대형 차트를 추가합니다.

```java
// 기능: 차트를 사용하여 프레젠테이션 만들기
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### 카테고리별 총계 계산

#### 개요
범주별 합계를 계산하려면 차트의 각 시리즈를 반복하여 범주별 값을 합산해야 합니다.

**단계:**
1. **배열 초기화**: 전체 값을 저장할 배열을 만듭니다.
2. **카테고리와 시리즈 반복**: 중첩 루프를 사용하여 모든 시리즈의 각 범주에 대한 합계를 누적합니다.

```java
// 기능: 차트의 범주별 합계 계산
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### 차트에 백분율 레이블로 데이터 표시

#### 개요
이 기능은 데이터 레이블을 구성하여 값을 백분율로 표시하고 시각화의 명확성을 제공하는 데 중점을 둡니다.

**단계:**
1. **시리즈 레이블 구성**: 글꼴 크기 및 범례 키의 표시 여부와 같은 레이블 속성을 설정합니다.
2. **백분율 계산**: 전체 범주 값을 기준으로 각 데이터 포인트의 백분율을 계산합니다.
3. **레이블 텍스트 설정**: 소수점 두 자리까지 백분율을 표시하도록 레이블 형식을 지정합니다.

```java
// 기능: 차트에 데이터를 백분율 레이블로 표시
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### 차트와 함께 프레젠테이션 저장

#### 개요
마지막으로, 프레젠테이션을 PPTX 형식으로 지정된 경로에 저장합니다.

**단계:**
1. **저장 방법**: 사용하세요 `save()` 방법에 대한 `Presentation` 사례.
2. **자원 폐기**: 저장 후 리소스가 해제되는지 확인하세요.

```java
// 기능: 차트와 함께 프레젠테이션 저장
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 실제 응용 프로그램

1. **재무 보고**: 차트를 사용하여 부서별 매출 성장률을 표시합니다.
2. **판매 데이터 분석**: 지역별 판매 데이터를 백분율 레이블과 함께 시각화하여 더욱 명확한 통찰력을 제공합니다.
3. **교육 프레젠테이션**: 시각적 통계를 활용해 학술적 프레젠테이션을 강화하세요.
4. **마케팅 캠페인**: 캠페인 성과 지표를 매력적인 시각적 자료로 표시합니다.
5. **사업 전략 회의**: 전략적 계획 논의에서 복잡한 데이터를 전달하기 위해 차트를 활용하세요.

## 성능 고려 사항
- **메모리 관리**: 폐기하다 `Presentation` 객체를 신속하게 처리하여 리소스를 확보합니다.
- **차트 로딩 최적화**: 가능하면 필수적인 차트 요소만 메모리에 로드합니다.
- **일괄 처리**: 여러 프레젠테이션을 처리할 때 리소스 소비를 효과적으로 관리하기 위해 일괄 처리로 처리하는 것을 고려하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
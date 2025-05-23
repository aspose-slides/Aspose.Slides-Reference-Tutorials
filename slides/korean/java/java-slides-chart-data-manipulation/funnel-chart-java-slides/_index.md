---
"description": "Aspose.Slides for Java를 사용하여 파워포인트 프레젠테이션에서 퍼널 차트를 만드는 방법을 배워보세요. 효과적인 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java 슬라이드의 퍼널 차트"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 퍼널 차트"
"url": "/ko/java/chart-data-manipulation/funnel-chart-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 퍼널 차트


## Java용 Aspose.Slides에서 깔때기형 차트 만들기 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 퍼널 차트를 만드는 과정을 안내합니다. 퍼널 차트는 여러 단계 또는 범주로 점진적으로 좁혀지거나 "퍼널"처럼 이동하는 데이터를 시각화하는 데 유용합니다. 이를 위한 단계별 지침과 소스 코드를 제공합니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- 프로젝트에 Java 라이브러리용 Aspose.Slides를 설치하고 설정했습니다.
- 깔때기형 차트를 삽입할 PowerPoint 프레젠테이션(PPTX) 파일입니다.

## 1단계: Java용 Aspose.Slides 가져오기

먼저, Aspose.Slides for Java 라이브러리를 Java 프로젝트로 가져와야 합니다. 빌드 구성에 필요한 종속성을 추가했는지 확인하세요.

```java
import com.aspose.slides.*;
```

## 2단계: 프레젠테이션 및 차트 초기화

이 단계에서는 프레젠테이션을 초기화하고 슬라이드에 깔때기형 차트를 추가합니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
    // 첫 번째 슬라이드에 좌표 (50, 50)과 크기 (500, 400)의 깔때기형 차트를 추가합니다.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
}
finally
{
    if (pres != null) pres.dispose();
}
```

## 3단계: 차트 데이터 정의

다음으로, 퍼널 차트의 데이터를 정의합니다. 필요에 따라 카테고리와 데이터 포인트를 맞춤 설정할 수 있습니다.

```java
// 기존 차트 데이터를 지웁니다.
wb.clear(0);

// 차트의 범주를 정의합니다.
chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));

// 퍼널 차트 시리즈에 대한 데이터 포인트를 추가합니다.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## 4단계: 프레젠테이션 저장

마지막으로, 퍼널 차트가 포함된 프레젠테이션을 지정된 파일에 저장합니다.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

이제 끝났습니다! Aspose.Slides for Java를 사용하여 퍼널 차트를 성공적으로 만들어 PowerPoint 프레젠테이션에 삽입했습니다.

## Java Slides의 Funnel Chart에 대한 완전한 소스 코드

```java
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "test.pptx");
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0);
            chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
            chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
            series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
            pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 결론

이 단계별 가이드에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 퍼널 차트를 만드는 방법을 살펴보았습니다. 퍼널 차트는 진행 또는 축소 패턴을 따르는 데이터를 시각화하는 데 유용한 도구로, 정보를 효과적으로 전달하기 쉽게 해줍니다. 

## 자주 묻는 질문

### 퍼널 차트의 모양을 어떻게 사용자 지정할 수 있나요?

색상, 레이블, 스타일 등 다양한 차트 속성을 수정하여 깔때기형 차트의 모양을 사용자 지정할 수 있습니다. 차트 사용자 지정 옵션에 대한 자세한 내용은 Aspose.Slides 설명서를 참조하세요.

### 퍼널 차트에 더 많은 데이터 포인트나 카테고리를 추가할 수 있나요?

네, 3단계에서 제공된 코드를 확장하여 퍼널 차트에 추가 데이터 포인트와 카테고리를 추가할 수 있습니다. 필요에 따라 카테고리 레이블과 데이터 포인트를 더 추가하기만 하면 됩니다.

### 슬라이드에서 깔때기형 차트의 위치와 크기를 어떻게 변경할 수 있나요?

2단계에서 슬라이드에 차트를 추가할 때 제공된 좌표와 치수를 수정하여 깔때기형 차트의 위치와 크기를 조정할 수 있습니다. 값(50, 50, 500, 400)을 적절히 업데이트합니다.

### 차트를 PDF나 이미지 등 다른 형식으로 내보낼 수 있나요?

네, Aspose.Slides for Java를 사용하면 Funnel Chart가 포함된 프레젠테이션을 PDF, 이미지 형식 등 다양한 형식으로 내보낼 수 있습니다. `SaveFormat` 프레젠테이션을 저장할 때 원하는 출력 형식을 지정하는 옵션입니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
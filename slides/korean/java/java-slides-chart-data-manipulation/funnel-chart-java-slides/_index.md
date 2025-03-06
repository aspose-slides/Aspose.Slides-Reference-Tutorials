---
title: Java 슬라이드의 깔때기형 차트
linktitle: Java 슬라이드의 깔때기형 차트
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 깔때기형 차트를 만드는 방법을 알아보세요. 효과적인 데이터 시각화를 위한 소스 코드가 포함된 단계별 가이드입니다.
weight: 18
url: /ko/java/chart-data-manipulation/funnel-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Aspose.Slides for Java에서 깔때기형 차트 만들기 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 깔때기형 차트를 만드는 과정을 안내합니다. 깔때기형 차트는 다양한 단계나 범주를 통해 점진적으로 범위를 좁히거나 "깔때기형"으로 만드는 데이터를 시각화하는 데 유용합니다. 이를 달성하는 데 도움이 되는 소스 코드와 함께 단계별 지침을 제공할 것입니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java 라이브러리용 Aspose.Slides가 프로젝트에 설치 및 설정됩니다.
- 깔때기형 차트를 삽입하려는 PowerPoint 프레젠테이션(PPTX) 파일.

## 1단계: Java용 Aspose.Slides 가져오기

먼저 Aspose.Slides for Java 라이브러리를 Java 프로젝트로 가져와야 합니다. 빌드 구성에 필요한 종속성을 추가했는지 확인하세요.

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
    //차원(500, 400)이 있는 좌표(50, 50)의 첫 번째 슬라이드에 깔때기형 차트를 추가합니다.
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

다음으로 깔때기형 차트의 데이터를 정의합니다. 요구 사항에 따라 범주와 데이터 요소를 사용자 정의할 수 있습니다.

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

// 깔때기형 차트 시리즈에 대한 데이터 포인트를 추가합니다.
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

## 4단계: 프레젠테이션 저장

마지막으로 깔때기형 차트가 포함된 프레젠테이션을 지정된 파일에 저장합니다.

```java
pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
```

그게 다야! Aspose.Slides for Java를 사용하여 깔때기형 차트를 성공적으로 만들고 이를 PowerPoint 프레젠테이션에 삽입했습니다.

## Java 슬라이드의 깔때기형 차트에 대한 전체 소스 코드

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

이 단계별 가이드에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 깔때기형 차트를 만드는 방법을 시연했습니다. 깔때기형 차트는 진행 또는 축소 패턴을 따르는 데이터를 시각화하여 정보를 효과적으로 전달하기 위한 유용한 도구입니다. 

## FAQ

### 깔때기형 차트의 모양을 어떻게 사용자 정의할 수 있나요?

색상, 레이블, 스타일 등 다양한 차트 속성을 수정하여 깔때기형 차트의 모양을 사용자 정의할 수 있습니다. 차트 사용자 정의 옵션에 대한 자세한 내용은 Aspose.Slides 설명서를 참조하세요.

### 깔때기형 차트에 더 많은 데이터 요소나 범주를 추가할 수 있습니까?

예, 3단계에서 제공된 코드를 확장하여 깔때기형 차트에 추가 데이터 포인트와 카테고리를 추가할 수 있습니다. 필요에 따라 카테고리 라벨과 데이터 포인트를 더 추가하기만 하면 됩니다.

### 슬라이드에서 깔때기형 차트의 위치와 크기를 어떻게 변경할 수 있나요?

2단계에서 슬라이드에 차트를 추가할 때 제공된 좌표와 크기를 수정하여 깔때기형 차트의 위치와 크기를 조정할 수 있습니다. 이에 따라 값(50, 50, 500, 400)을 업데이트하세요.

### 차트를 PDF나 이미지 등 다른 형식으로 내보낼 수 있나요?

예, Aspose.Slides for Java를 사용하면 깔때기형 차트가 포함된 프레젠테이션을 PDF, 이미지 형식 등을 포함한 다양한 형식으로 내보낼 수 있습니다. 당신은 사용할 수 있습니다`SaveFormat` 프레젠테이션을 저장할 때 원하는 출력 형식을 지정하는 옵션입니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Java 슬라이드의 개별 시리즈에 대해 음수인 경우 반전
linktitle: Java 슬라이드의 개별 시리즈에 대해 음수인 경우 반전
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java의 음수인 경우 반전 기능을 사용하여 PowerPoint 프레젠테이션의 차트 시각적 효과를 향상시키는 방법을 알아보세요.
weight: 11
url: /ko/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드의 개별 시리즈에 대한 음수 반전 소개

Aspose.Slides for Java는 프레젠테이션 작업을 위한 강력한 도구를 제공하며 흥미로운 기능 중 하나는 데이터 시리즈가 차트에 표시되는 방식을 제어하는 기능입니다. 이 기사에서는 Java 슬라이드의 개별 시리즈에 대해 "음수인 경우 반전" 기능을 사용하는 방법을 살펴보겠습니다. 이 기능을 사용하면 차트에서 부정적인 데이터 포인트를 시각적으로 구분하여 프레젠테이션을 더욱 유익하고 매력적으로 만들 수 있습니다.

## 전제 조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 프로젝트 설정

시작하려면 선호하는 IDE(통합 개발 환경)에서 새 Java 프로젝트를 생성하세요. 프로젝트가 설정되면 다음 단계에 따라 Java 슬라이드의 개별 시리즈에 대해 "음수인 경우 반전" 기능을 구현하십시오.

## 1단계: Aspose.Slides 라이브러리 포함

먼저 프로젝트에 Aspose.Slides 라이브러리를 포함해야 합니다. 프로젝트의 클래스 경로에 라이브러리 JAR 파일을 추가하면 됩니다. 이 단계를 통해 PowerPoint 프레젠테이션 작업에 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

```java
import com.aspose.slides.*;
```

## 2단계: 프레젠테이션 만들기

 이제 Aspose.Slides를 사용하여 새로운 PowerPoint 프레젠테이션을 만들어 보겠습니다. 다음을 사용하여 프레젠테이션을 저장할 디렉터리를 정의할 수 있습니다.`dataDir` 변하기 쉬운.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3단계: 차트 추가

이 단계에서는 프레젠테이션에 차트를 추가하겠습니다. 클러스터형 세로 막대형 차트를 예로 사용하겠습니다. 요구 사항에 따라 다양한 차트 유형을 선택할 수 있습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## 4단계: 차트 데이터 시리즈 구성

다음으로 차트의 데이터 시리즈를 구성하겠습니다. "음수인 경우 반전" 기능을 시연하기 위해 양수 값과 음수 값이 모두 포함된 샘플 데이터 세트를 생성하겠습니다.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// 계열에 데이터 포인트 추가
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## 5단계: "음수인 경우 반전" 적용

이제 데이터 포인트 중 하나에 "음수인 경우 반전" 기능을 적용하겠습니다. 그러면 특정 데이터 포인트가 음수인 경우 색상이 시각적으로 반전됩니다.

```java
series.get_Item(0).setInvertIfNegative(false); // 기본적으로 반전하지 않음
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // 세 번째 데이터 포인트의 색상 반전
```

## 6단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 지정된 디렉터리에 저장합니다.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 개별 시리즈에 대해 음수인 경우 반전을 위한 완전한 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드의 개별 시리즈에 대해 "음수인 경우 반전" 기능을 사용하는 방법을 배웠습니다. 이 기능을 사용하면 차트에서 부정적인 데이터 요소를 강조 표시하여 프레젠테이션을 시각적으로 더욱 매력적이고 유익하게 만들 수 있습니다.

## FAQ

### Aspose.Slides for Java의 "음수인 경우 반전" 기능의 목적은 무엇입니까?

Aspose.Slides for Java의 "음수인 경우 반전" 기능을 사용하면 차트에서 음수 데이터 포인트를 시각적으로 구분할 수 있습니다. 특정 데이터 포인트를 강조하여 프레젠테이션을 더욱 유익하고 흥미롭게 만드는 데 도움이 됩니다.

### Java 프로젝트에 Aspose.Slides 라이브러리를 어떻게 포함할 수 있나요?

Java 프로젝트에 Aspose.Slides 라이브러리를 포함하려면 프로젝트의 클래스 경로에 라이브러리 JAR 파일을 추가해야 합니다. 이를 통해 PowerPoint 프레젠테이션 작업에 필요한 모든 클래스와 메서드에 액세스할 수 있습니다.

### "음수인 경우 반전" 기능으로 다른 차트 유형을 사용할 수 있습니까?

예, "음수인 경우 반전" 기능을 사용하면 다양한 차트 유형을 사용할 수 있습니다. 본 튜토리얼에서는 클러스터형 세로 막대형 차트를 예로 들어 설명했지만, 요구 사항에 따라 다양한 차트 유형에 이 기능을 적용할 수 있습니다.

### 반전된 데이터 포인트의 모양을 사용자 정의할 수 있습니까?

예, 반전된 데이터 포인트의 모양을 사용자 정의할 수 있습니다. Aspose.Slides for Java는 "음수인 경우 반전" 설정으로 인해 데이터 포인트가 반전될 때 데이터 포인트의 색상과 스타일을 제어하는 옵션을 제공합니다.

### Java 설명서용 Aspose.Slides에 어디서 액세스할 수 있나요?

Java용 Aspose.Slides 문서에 액세스할 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

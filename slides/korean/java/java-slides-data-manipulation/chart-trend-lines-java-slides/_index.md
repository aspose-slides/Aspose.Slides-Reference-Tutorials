---
title: Java 슬라이드의 차트 추세선
linktitle: Java 슬라이드의 차트 추세선
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에 다양한 추세선을 추가하는 방법을 알아보세요. 효과적인 데이터 시각화를 위한 코드 예제가 포함된 단계별 가이드입니다.
weight: 15
url: /ko/java/data-manipulation/chart-trend-lines-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드의 차트 추세선 소개: 단계별 가이드

이 종합 가이드에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 차트 추세선을 만드는 방법을 살펴보겠습니다. 차트 추세선은 프레젠테이션에 유용한 추가 기능으로 데이터 추세를 효과적으로 시각화하고 분석하는 데 도움이 됩니다. 명확한 설명과 코드 예제를 통해 프로세스를 안내해 드리겠습니다.

## 전제 조건

차트 추세선 생성을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 자바 개발 환경
- Java 라이브러리용 Aspose.Slides
- 당신이 선택한 코드 편집기

## 1단계: 시작하기

필요한 환경을 설정하고 새 프레젠테이션을 만드는 것부터 시작해 보겠습니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// 빈 프레젠테이션 만들기
Presentation pres = new Presentation();
```

프레젠테이션을 초기화했으며 이제 묶은 세로 막대형 차트를 추가할 준비가 되었습니다.

```java
// 묶은 세로 막대형 차트 만들기
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## 2단계: 지수 추세선 추가

차트 시리즈에 지수 추세선을 추가하는 것부터 시작해 보겠습니다.

```java
// 차트 시리즈 1에 지수 추세선 추가
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## 3단계: 선형 추세선 추가

다음으로 차트 시리즈에 선형 추세선을 추가하겠습니다.

```java
// 차트 시리즈 1에 선형 추세선 추가
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 4단계: 로그 추세선 추가

이제 다른 차트 시리즈에 로그 추세선을 추가해 보겠습니다.

```java
// 차트 시리즈 2에 로그 추세선 추가
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## 5단계: 이동 평균 추세선 추가

이동 평균 추세선을 추가할 수도 있습니다.

```java
// 차트 시리즈 2에 이동 평균 추세선 추가
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## 6단계: 다항식 추세선 추가

다항식 추세선 추가:

```java
// 차트 시리즈 3에 다항식 추세선 추가
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## 7단계: 전력 추세선 추가

마지막으로 전력 추세선을 추가해 보겠습니다.

```java
// 차트 시리즈 3에 대한 전력 추세선 추가
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## 8단계: 프레젠테이션 저장

이제 차트에 다양한 추세선을 추가했으므로 프레젠테이션을 저장해 보겠습니다.

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

축하해요! Aspose.Slides for Java를 사용하여 Java 슬라이드에 다양한 유형의 추세선이 포함된 프레젠테이션을 성공적으로 만들었습니다.

## Java 슬라이드의 차트 추세선에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// 빈 프레젠테이션 만들기
Presentation pres = new Presentation();
// 묶은 세로 막대형 차트 만들기
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// 차트 시리즈 1에 대한 잠재적 추세선 추가
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// 차트 시리즈 1에 선형 추세선 추가
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// 차트 시리즈 2에 대한 로그 추세선 추가
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// 차트 시리즈 2에 MovingAverage 추세선 추가
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// 차트 시리즈 3에 다항식 추세선 추가
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// 차트 시리즈 3에 대한 전력 추세선 추가
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// 프레젠테이션 저장 중
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 Java 슬라이드의 차트에 다양한 유형의 추세선을 추가하는 방법을 배웠습니다. 데이터 분석 작업을 하거나 유익한 프레젠테이션을 만들 때 추세를 시각화하는 기능은 강력한 도구가 될 수 있습니다.

## FAQ

### Aspose.Slides for Java에서 추세선 색상을 어떻게 변경합니까?

 추세선의 색상을 변경하려면`getSolidFillColor().setColor(Color)` 선형 추세선을 추가하는 예에 표시된 대로 방법을 사용합니다.

### 단일 차트 시리즈에 여러 추세선을 추가할 수 있나요?

예, 단일 차트 시리즈에 여러 추세선을 추가할 수 있습니다. 간단히 전화하세요.`getTrendLines().add()` 추가하려는 각 추세선에 대한 방법입니다.

### Aspose.Slides for Java의 차트에서 추세선을 어떻게 제거합니까?

 차트에서 추세선을 제거하려면`removeAt(int index)` 제거하려는 추세선의 인덱스를 지정하는 방법입니다.

### 추세선 방정식 표시를 사용자 정의할 수 있습니까?

 예, 다음을 사용하여 추세선 방정식 표시를 사용자 정의할 수 있습니다.`setDisplayEquation(boolean)` 예제에 설명된 대로 방법을 사용합니다.

### Aspose.Slides for Java에 대한 더 많은 리소스와 예제에 어떻게 액세스할 수 있나요?

 Aspose.Slides for Java에 대한 추가 리소스, 문서 및 예제에 액세스할 수 있습니다.[Aspose 웹사이트](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: Java 슬라이드에서 자동 시리즈 채우기 색상 설정
linktitle: Java 슬라이드에서 자동 시리즈 채우기 색상 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 자동 시리즈 채우기 색상을 설정하는 방법을 알아보세요. 동적 프레젠테이션을 위한 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 14
url: /ko/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

## Java 슬라이드에서 자동 계열 채우기 색상 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드에서 자동 시리즈 채우기 색상을 설정하는 방법을 살펴보겠습니다. Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 생성, 조작 및 관리할 수 있는 강력한 라이브러리입니다. 이 가이드가 끝나면 쉽게 차트를 만들고 자동 계열 채우기 색상을 설정할 수 있습니다.

## 전제조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  프로젝트에 Java 라이브러리용 Aspose.Slides가 추가되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

이제 개요가 준비되었으므로 단계별 가이드부터 시작하겠습니다.

## 1단계: Java용 Aspose.Slides 소개

Aspose.Slides for Java는 개발자가 PowerPoint 프레젠테이션 작업을 할 수 있도록 하는 Java API입니다. 슬라이드, 차트, 도형 등을 생성, 편집, 조작하는 등 다양한 기능을 제공합니다.

## 2단계: Java 프로젝트 설정

코딩을 시작하기 전에 선호하는 IDE(통합 개발 환경)에서 Java 프로젝트를 설정했는지 확인하세요. 프로젝트에 Aspose.Slides for Java 라이브러리를 추가했는지 확인하세요.

## 3단계: PowerPoint 프레젠테이션 만들기

시작하려면 다음 코드 조각을 사용하여 새 PowerPoint 프레젠테이션을 만드세요.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 바꾸다`"Your Document Directory"` 프레젠테이션을 저장하려는 경로를 사용하세요.

## 4단계: 프레젠테이션에 차트 추가

다음으로 프레젠테이션에 묶은 세로 막대형 차트를 추가해 보겠습니다. 이를 달성하기 위해 다음 코드를 사용합니다.

```java
// 묶은 세로 막대형 차트 만들기
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

이 코드는 프레젠테이션의 첫 번째 슬라이드에 묶은 세로 막대형 차트를 만듭니다.

## 5단계: 자동 시리즈 채우기 색상 설정

이제 자동 시리즈 채우기 색상 설정의 핵심 부분이 나옵니다. 차트 시리즈를 반복하고 채우기 형식을 자동으로 설정합니다.

```java
// 시리즈 채우기 형식을 자동으로 설정
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

이 코드는 계열 채우기 색상이 자동으로 설정되도록 합니다.

## 6단계: 프레젠테이션 저장

프레젠테이션을 저장하려면 다음 코드를 사용하십시오.

```java
//프리젠테이션 파일을 디스크에 쓰기
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 바꾸다`"AutoFillSeries_out.pptx"` 원하는 파일 이름으로

## Java 슬라이드의 자동 시리즈 채우기 색상 설정에 대한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// 묶은 세로 막대형 차트 만들기
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// 시리즈 채우기 형식을 자동으로 설정
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	//프리젠테이션 파일을 디스크에 쓰기
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

축하해요! Aspose.Slides for Java를 사용하여 Java 슬라이드에서 자동 시리즈 채우기 색상을 성공적으로 설정했습니다. 이제 이 지식을 사용하여 Java 응용 프로그램에서 동적이고 시각적으로 매력적인 PowerPoint 프레젠테이션을 만들 수 있습니다.

## FAQ

### 차트 유형을 다른 스타일로 어떻게 변경할 수 있나요?

 대체하여 차트 유형을 변경할 수 있습니다.`ChartType.ClusteredColumn` 다음과 같은 원하는 차트 유형으로`ChartType.Line` 또는`ChartType.Pie`.

### 차트 모양을 추가로 사용자 정의할 수 있나요?

예, 색상, 글꼴, 레이블 등 차트의 다양한 속성을 수정하여 차트 모양을 맞춤설정할 수 있습니다.

### Aspose.Slides for Java는 상업용으로 적합합니까?

예, Aspose.Slides for Java는 개인 및 상업용 프로젝트 모두에 사용할 수 있습니다. 자세한 내용은 해당 라이선스 약관을 참조하세요.

### Aspose.Slides for Java에서 제공하는 다른 기능이 있습니까?

예, Aspose.Slides for Java는 슬라이드 조작, 텍스트 서식 지정, 애니메이션 지원을 포함한 광범위한 기능을 제공합니다.

### 더 많은 리소스와 문서는 어디에서 찾을 수 있나요?

 Aspose.Slides for Java에 대한 포괄적인 문서에 액세스할 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
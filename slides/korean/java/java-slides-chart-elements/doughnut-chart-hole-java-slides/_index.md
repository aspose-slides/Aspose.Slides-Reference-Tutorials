---
"description": "Aspose.Slides for Java를 사용하여 Java 슬라이드에서 사용자 정의 구멍 크기가 적용된 도넛형 차트를 만들어 보세요. 차트 사용자 정의를 위한 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "자바 슬라이드의 도넛 차트 구멍"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "자바 슬라이드의 도넛 차트 구멍"
"url": "/ko/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 자바 슬라이드의 도넛 차트 구멍


## Java 슬라이드에 구멍이 있는 도넛형 차트 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 구멍이 있는 도넛형 차트를 만드는 방법을 안내합니다. 이 단계별 가이드는 소스 코드 예제를 통해 과정을 안내합니다.

## 필수 조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).

## 1단계: 필요한 라이브러리 가져오기

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2단계: 프레젠테이션 초기화

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";

// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
```

## 3단계: 도넛 차트 만들기

```java
try {
    // 첫 번째 슬라이드에 도넛형 차트를 만듭니다.
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // 도넛 차트의 구멍 크기 설정(백분율)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // 프레젠테이션을 디스크에 저장
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // 프레젠테이션 객체를 폐기합니다
    if (presentation != null) presentation.dispose();
}
```

## 4단계: 코드 실행

IDE 또는 텍스트 편집기에서 Java 코드를 실행하여 지정된 구멍 크기의 도넛형 차트를 만듭니다. `"Your Document Directory"` 프레젠테이션을 저장하려는 실제 경로를 입력합니다.

## Java 슬라이드의 도넛 차트 홀에 대한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// 디스크에 프레젠테이션 쓰기
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 구멍이 있는 도넛형 차트를 만드는 방법을 알아보았습니다. `setDoughnutHoleSize` 메서드 매개변수.

## 자주 묻는 질문

### 차트 세그먼트의 색상을 어떻게 변경할 수 있나요?

차트 세그먼트의 색상을 변경하려면 다음을 사용할 수 있습니다. `setDataPointsInLegend` 방법에 대한 `IChart` 객체를 선택하고 각 데이터 포인트에 대해 원하는 색상을 설정합니다.

### 도넛형 차트 세그먼트에 라벨을 추가할 수 있나요?

예, 도넛 차트 세그먼트에 레이블을 추가할 수 있습니다. `setDataPointsLabelValue` 방법에 대한 `IChart` 물체.

### 차트에 제목을 추가할 수 있나요?

물론입니다! 차트에 제목을 추가할 수 있습니다. `setTitle` 방법에 대한 `IChart` 객체를 선택하고 원하는 제목 텍스트를 제공합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
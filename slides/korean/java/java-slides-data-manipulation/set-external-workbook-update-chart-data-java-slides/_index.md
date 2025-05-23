---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 외부 통합 문서를 설정하고 차트 데이터를 업데이트하는 방법을 알아보세요. PowerPoint 자동화 기술을 향상시켜 보세요."
"linktitle": "Java 슬라이드에서 업데이트 차트 데이터로 외부 통합 문서 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 업데이트 차트 데이터로 외부 통합 문서 설정"
"url": "/ko/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 업데이트 차트 데이터로 외부 통합 문서 설정


## Java 슬라이드에서 업데이트 차트 데이터를 사용하여 외부 통합 문서 설정 소개

이 포괄적인 가이드에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 업데이트된 차트 데이터가 포함된 외부 통합 문서를 설정하는 과정을 안내합니다. 이 강력한 라이브러리를 사용하면 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작할 수 있으므로 외부 소스에서 차트 데이터를 업데이트하는 등의 작업을 쉽게 자동화할 수 있습니다. 이 튜토리얼을 마치면 단계별 지침과 함께 제공되는 Java 코드를 통해 이 작업을 수행하는 방법을 명확하게 이해하게 될 것입니다.

## 필수 조건

구현에 들어가기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.

1. Java용 Aspose.Slides: Java용 Aspose.Slides 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

2. Java 개발 환경: 시스템에 Java 개발 환경이 설정되어 있는지 확인하세요.

## 1단계: 새 프레젠테이션 만들기

시작하기 위해 Aspose.Slides for Java를 사용하여 새 PowerPoint 프레젠테이션을 만들어 보겠습니다. Java 코드는 다음과 같습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 차트 추가

이제 프레젠테이션에 차트를 추가해 보겠습니다. 이 예제에서는 원형 차트를 만들어 보겠습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## 3단계: 외부 통합 문서 설정

여기서 외부 통합 문서를 차트의 데이터 원본으로 설정합니다. 외부 통합 문서가 아직 없더라도 URL을 입력해야 합니다.

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://경로가 존재하지 않습니다", false);
```

## 4단계: 프레젠테이션 저장

마지막으로 업데이트된 차트 데이터로 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에서 업데이트 차트 데이터를 사용하여 외부 통합 문서 설정에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://경로가 존재하지 않습니다", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

축하합니다! Aspose.Slides for Java를 사용하여 Java Slides에서 업데이트된 차트 데이터가 포함된 외부 통합 문서를 설정하는 방법을 알아보았습니다. 이 기능은 외부 데이터 소스에서 PowerPoint 프레젠테이션의 차트를 동적으로 업데이트하는 데 매우 유용합니다.

## 자주 묻는 질문

### 차트의 외부 통합 문서 데이터를 어떻게 업데이트할 수 있나요?

차트의 외부 통합 문서 데이터를 업데이트하려면 지정된 URL에서 외부 통합 문서의 데이터를 수정하기만 하면 됩니다. 다음에 프레젠테이션을 열면 Aspose.Slides for Java가 외부 통합 문서에서 업데이트된 데이터를 가져와 차트를 업데이트합니다.

### 로컬 파일을 외부 통합 문서로 사용할 수 있나요?

네, URL 대신 파일 경로를 제공하면 로컬 파일을 외부 통합 문서로 사용할 수 있습니다. 단, 파일 경로가 정확하고 Java 애플리케이션에서 액세스할 수 있는지 확인하세요.

### Aspose.Slides for Java에서 외부 통합 문서를 사용하는 데 제한이 있습니까?

외부 통합 문서를 사용하는 것은 강력한 기능이지만, 외부 통합 문서 데이터의 가용성은 제공된 URL 또는 파일 경로에서의 접근성에 따라 달라진다는 점을 명심하세요. 데이터 검색 문제를 방지하려면 프레젠테이션을 열 때 외부 데이터 원본을 사용할 수 있는지 확인하세요.

### 외부 통합 문서를 설정한 후 차트 모양을 사용자 지정할 수 있나요?

네, 외부 통합 문서를 설정한 후에도 제목, 레이블, 색상 등 차트 모양을 사용자 지정할 수 있습니다. Aspose.Slides for Java는 사용자의 요구에 맞는 다양한 차트 서식 옵션을 제공합니다.

### Aspose.Slides for Java에 대한 추가 문서와 리소스는 어디에서 찾을 수 있나요?

자세한 설명서 및 추가 리소스는 Aspose.Slides for Java 설명서를 참조하세요. [여기](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
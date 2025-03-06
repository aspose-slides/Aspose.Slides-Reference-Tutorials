---
title: Java 슬라이드의 외부 통합 문서에서 차트 데이터 편집
linktitle: Java 슬라이드의 외부 통합 문서에서 차트 데이터 편집
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 외부 통합 문서에서 차트 데이터를 편집하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다.
weight: 17
url: /ko/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드의 외부 통합 문서에서 차트 데이터 편집 소개

이 가이드에서는 Aspose.Slides for Java를 사용하여 외부 통합 문서에서 차트 데이터를 편집하는 방법을 보여줍니다. 프로그래밍 방식으로 PowerPoint 프레젠테이션 내의 차트 데이터를 수정하는 방법을 알아봅니다. 프로젝트에 Java용 Aspose.Slides 라이브러리가 설치 및 구성되어 있는지 확인하세요.

## 전제 조건

- Java용 Aspose.Slides
- 자바 개발 환경

## 1단계: 프레젠테이션 로드

 먼저, 편집하려는 데이터가 포함된 차트가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 사용하세요.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 2단계: 차트에 액세스

프레젠테이션이 로드되면 프레젠테이션 내의 차트에 액세스해야 합니다. 이 예에서는 차트가 첫 번째 슬라이드에 있고 해당 슬라이드의 첫 번째 셰이프라고 가정합니다.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 3단계: 차트 데이터 수정

이제 차트 데이터를 수정해 보겠습니다. 차트의 특정 데이터 포인트를 변경하는 데 중점을 둘 것입니다. 이 예에서는 첫 번째 계열의 첫 번째 데이터 요소 값을 100으로 설정합니다. 필요에 따라 이 값을 조정할 수 있습니다.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 4단계: 프레젠테이션 저장

차트 데이터에 필요한 사항을 변경한 후 수정된 프레젠테이션을 새 파일에 저장합니다. 요구 사항에 따라 출력 파일 경로와 형식을 지정할 수 있습니다.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 5단계: 정리

리소스를 해제하려면 프레젠테이션 개체를 삭제하는 것을 잊지 마세요.

```java
if (pres != null) pres.dispose();
```

이제 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 내 외부 통합 문서의 차트 데이터를 성공적으로 편집했습니다. 특정 요구 사항에 맞게 이 코드를 사용자 정의하고 Java 애플리케이션에 통합할 수 있습니다.

## 완전한 소스 코드

```java
        // 외부 통합 문서의 경로는 프레젠테이션에 거의 저장되지 않습니다.
        // 따라서 예제를 실행하기 전에 Data/Chart 디렉터리 D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\에서 externalWorkbook.xlsx 파일을 복사하세요.
        // 문서 디렉터리의 경로입니다.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## 결론

이 종합 가이드에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 내 외부 통합 문서의 차트 데이터를 편집하는 방법을 살펴보았습니다. 단계별 지침과 소스 코드 예제를 따르면 차트 데이터를 프로그래밍 방식으로 쉽게 수정할 수 있는 지식과 기술을 습득하게 됩니다.

## FAQ

### 다른 차트나 슬라이드를 지정하려면 어떻게 해야 합니까?

 다른 차트나 슬라이드에 액세스하려면`getSlides().get_Item()` 그리고`getShapes().get_Item()`행동 양식. 인덱싱은 0부터 시작한다는 점을 기억하세요.

### 동일한 프레젠테이션 내에서 여러 차트의 데이터를 편집할 수 있나요?

예, 각 차트에 대해 차트 데이터 수정 단계를 반복하여 동일한 프레젠테이션 내의 여러 차트에 있는 데이터를 편집할 수 있습니다.

### 외부 통합 문서의 데이터를 다른 형식으로 편집하려면 어떻게 해야 합니까?

적절한 Aspose.Cells 클래스와 해당 형식의 데이터를 읽고 쓰는 메서드를 사용하여 다양한 외부 통합 문서 형식을 처리하도록 코드를 조정할 수 있습니다.

### 여러 프레젠테이션에 대해 이 프로세스를 자동화하려면 어떻게 해야 합니까?

여러 프레젠테이션을 처리하고, 각 프레젠테이션을 로드하고, 원하는 대로 변경하고, 수정된 프레젠테이션을 하나씩 저장하는 루프를 만들 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

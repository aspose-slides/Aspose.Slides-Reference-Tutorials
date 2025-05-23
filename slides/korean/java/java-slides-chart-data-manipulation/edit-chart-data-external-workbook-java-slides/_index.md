---
"description": "Aspose.Slides for Java를 사용하여 외부 통합 문서의 차트 데이터를 편집하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java Slides에서 외부 통합 문서의 차트 데이터 편집"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 외부 통합 문서의 차트 데이터 편집"
"url": "/ko/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 외부 통합 문서의 차트 데이터 편집


## Java Slides에서 외부 통합 문서의 차트 데이터 편집 소개

이 가이드에서는 Aspose.Slides for Java를 사용하여 외부 통합 문서의 차트 데이터를 편집하는 방법을 보여줍니다. PowerPoint 프레젠테이션 내에서 차트 데이터를 프로그래밍 방식으로 수정하는 방법도 배우게 됩니다. 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 구성되어 있는지 확인하세요.

## 필수 조건

- Java용 Aspose.Slides
- 자바 개발 환경

## 1단계: 프레젠테이션 로드

먼저, 편집하려는 차트 데이터가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. `"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 포함합니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 2단계: 차트에 액세스

프레젠테이션이 로드되면 프레젠테이션 내의 차트에 접근해야 합니다. 이 예시에서는 차트가 첫 번째 슬라이드에 있고 해당 슬라이드의 첫 번째 도형이라고 가정합니다.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 3단계: 차트 데이터 수정

이제 차트 데이터를 수정해 보겠습니다. 차트의 특정 데이터 요소를 변경하는 데 중점을 두겠습니다. 이 예에서는 첫 번째 계열의 첫 번째 데이터 요소의 값을 100으로 설정했습니다. 필요에 따라 이 값을 조정할 수 있습니다.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 4단계: 프레젠테이션 저장

차트 데이터를 필요에 따라 변경한 후 수정된 프레젠테이션을 새 파일로 저장합니다. 필요에 따라 출력 파일 경로와 형식을 지정할 수 있습니다.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 5단계: 정리

리소스를 해제하려면 프레젠테이션 객체를 삭제하는 것을 잊지 마세요.

```java
if (pres != null) pres.dispose();
```

이제 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 내의 외부 통합 문서에 있는 차트 데이터를 성공적으로 편집했습니다. 이 코드를 특정 요구 사항에 맞게 사용자 정의하고 Java 애플리케이션에 통합할 수 있습니다.

## 완전한 소스 코드

```java
        // 외부 통합 문서 경로가 프레젠테이션에 거의 저장되지 않는다는 점에 주의하세요.
        // 따라서 예제를 실행하기 전에 Data/Chart 디렉토리 D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\에서 externalWorkbook.xlsx 파일을 복사해 주세요.
        // 문서 디렉토리의 경로입니다.
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

이 종합 가이드에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 내 외부 통합 문서의 차트 데이터를 편집하는 방법을 살펴보았습니다. 단계별 지침과 소스 코드 예제를 따라가다 보면 차트 데이터를 프로그래밍 방식으로 쉽게 수정할 수 있는 지식과 기술을 습득하게 될 것입니다.

## 자주 묻는 질문

### 다른 차트나 슬라이드를 지정하려면 어떻게 해야 하나요?

다른 차트나 슬라이드에 액세스하려면 해당 인덱스를 수정하세요. `getSlides().get_Item()` 그리고 `getShapes().get_Item()` 메서드. 인덱싱은 0부터 시작한다는 점을 기억하세요.

### 동일한 프레젠테이션 내에서 여러 차트의 데이터를 편집할 수 있나요?

네, 각 차트에 대해 차트 데이터 수정 단계를 반복하여 동일한 프레젠테이션 내의 여러 차트에 있는 데이터를 편집할 수 있습니다.

### 다른 형식으로 외부 통합 문서의 데이터를 편집하려면 어떻게 해야 하나요?

적절한 Aspose.Cells 클래스와 메서드를 사용하여 해당 형식의 데이터를 읽고 쓰면 다양한 외부 통합 문서 형식을 처리하도록 코드를 조정할 수 있습니다.

### 여러 프레젠테이션에 대해 이 프로세스를 어떻게 자동화할 수 있나요?

여러 프레젠테이션을 처리하는 루프를 만들어서 각각을 로드하고, 원하는 변경 사항을 적용하고, 수정된 프레젠테이션을 하나씩 저장할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
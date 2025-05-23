---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 사용자 지정 범례 옵션을 설정하는 방법을 알아보세요. PowerPoint 차트에서 범례 위치와 크기를 사용자 지정하세요."
"linktitle": "Java 슬라이드에서 범례 사용자 정의 옵션 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드에서 범례 사용자 정의 옵션 설정"
"url": "/ko/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 범례 사용자 정의 옵션 설정


## Java Slides에서 범례 사용자 정의 옵션 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 차트의 범례 속성을 사용자 지정하는 방법을 보여드립니다. 프레젠테이션의 필요에 맞게 범례의 위치, 크기 및 기타 속성을 수정할 수 있습니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java API용 Aspose.Slides가 설치되었습니다.
- Java 개발 환경 설정.

## 1단계: 필요한 클래스 가져오기:

```java
// Java 클래스용 Aspose.Slides 가져오기
import com.aspose.slides.*;
```

## 2단계: 문서 디렉토리 경로를 지정하세요.

```java
String dataDir = "Your Document Directory";
```

## 3단계: 인스턴스 생성 `Presentation` 수업:

```java
Presentation presentation = new Presentation();
```

## 4단계: 프레젠테이션에 슬라이드 추가:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## 5단계: 슬라이드에 클러스터형 막대형 차트를 추가합니다.

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## 6단계. 범례 속성 설정:

- 범례의 X 위치를 설정합니다(차트 너비에 상대적):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- 범례의 Y 위치를 설정합니다(차트 높이를 기준으로):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- 범례의 너비를 설정합니다(차트 너비에 상대적):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- 범례의 높이를 설정합니다(차트 높이에 상대적):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## 7단계: 프레젠테이션을 디스크에 저장합니다.

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

이제 끝났습니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 차트의 범례 속성을 성공적으로 사용자 지정했습니다.

## Java Slides의 Set Legend 사용자 정의 옵션에 대한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
try
{
	// 슬라이드 참조를 얻으세요
	ISlide slide = presentation.getSlides().get_Item(0);
	// 슬라이드에 클러스터형 막대형 차트 추가
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// 범례 속성 설정
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// 디스크에 프레젠테이션 쓰기
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 차트의 범례 속성을 사용자 지정하는 방법을 알아보았습니다. 범례의 위치, 크기 및 기타 속성을 수정하여 시각적으로 매력적이고 유익한 프레젠테이션을 만들 수 있습니다.

## 자주 묻는 질문

## 범례의 위치를 어떻게 변경할 수 있나요?

범례의 위치를 변경하려면 다음을 사용하세요. `setX` 그리고 `setY` legend 객체의 메서드입니다. 값은 차트의 너비와 높이를 기준으로 지정됩니다.

## 범례의 크기를 어떻게 조정할 수 있나요?

다음을 사용하여 범례의 크기를 조정할 수 있습니다. `setWidth` 그리고 `setHeight` legend 객체의 메서드입니다. 이 값은 차트의 너비와 높이를 기준으로 합니다.

## 다른 범례 속성을 사용자 정의할 수 있나요?

네, 글꼴 스타일, 테두리, 배경색 등 다양한 범례 속성을 사용자 지정할 수 있습니다. 범례 사용자 지정에 대한 자세한 내용은 Aspose.Slides 문서를 참조하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
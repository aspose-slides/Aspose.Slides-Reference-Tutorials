---
title: Java 슬라이드에서 범례 사용자 정의 옵션 설정
linktitle: Java 슬라이드에서 범례 사용자 정의 옵션 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 사용자 정의 범례 옵션을 설정하는 방법을 알아보세요. PowerPoint 차트에서 범례 위치와 크기를 사용자 정의하세요.
weight: 14
url: /ko/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드에서 범례 사용자 정의 옵션 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 차트의 범례 속성을 사용자 정의하는 방법을 보여줍니다. 프레젠테이션 요구 사항에 맞게 범례의 위치, 크기 및 기타 속성을 수정할 수 있습니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java API용 Aspose.Slides가 설치되었습니다.
- Java 개발 환경이 설정되었습니다.

## 1단계: 필요한 클래스 가져오기:

```java
// Java 클래스용 Aspose.Slides 가져오기
import com.aspose.slides.*;
```

## 2단계: 문서 디렉터리 경로를 지정합니다.

```java
String dataDir = "Your Document Directory";
```

##  3단계: 인스턴스 생성`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## 4단계: 프레젠테이션에 슬라이드를 추가합니다.

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## 5단계: 묶은 세로 막대형 차트를 슬라이드에 추가합니다.

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## 6단계. 범례 속성 설정:

- 범례의 X 위치를 설정합니다(차트 너비를 기준으로).

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- 범례의 Y 위치를 설정합니다(차트 높이를 기준으로).

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- 범례 너비를 설정합니다(차트 너비 기준).

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- 범례의 높이를 설정합니다(차트 높이를 기준으로).

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

그게 다야! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 차트의 범례 속성을 성공적으로 사용자 정의했습니다.

## Java 슬라이드의 범례 사용자 정의 옵션 설정을 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
try
{
	// 슬라이드 참조 얻기
	ISlide slide = presentation.getSlides().get_Item(0);
	// 슬라이드에 묶은 세로 막대형 차트 추가
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// 범례 속성 설정
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// 프레젠테이션을 디스크에 쓰기
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 차트의 범례 속성을 사용자 정의하는 방법을 배웠습니다. 범례의 위치, 크기 및 기타 속성을 수정하여 시각적으로 매력적이고 유익한 프레젠테이션을 만들 수 있습니다.

## FAQ

## 범례의 위치를 어떻게 변경할 수 있나요?

 범례의 위치를 변경하려면`setX` 그리고`setY` 범례 객체의 메소드. 값은 차트의 너비와 높이를 기준으로 지정됩니다.

## 범례의 크기를 어떻게 조정할 수 있나요?

 다음을 사용하여 범례의 크기를 조정할 수 있습니다.`setWidth` 그리고`setHeight` 범례 객체의 메소드. 이 값은 차트의 너비와 높이에도 상대적입니다.

## 다른 범례 속성을 사용자 정의할 수 있나요?

예, 글꼴 스타일, 테두리, 배경색 등과 같은 범례의 다양한 속성을 사용자 정의할 수 있습니다. 범례 사용자 정의에 대한 자세한 내용은 Aspose.Slides 문서를 살펴보세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

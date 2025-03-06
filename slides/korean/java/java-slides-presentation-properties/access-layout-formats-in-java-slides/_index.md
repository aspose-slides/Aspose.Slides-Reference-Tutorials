---
title: Java 슬라이드의 레이아웃 형식에 액세스
linktitle: Java 슬라이드의 레이아웃 형식에 액세스
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드의 레이아웃 형식에 액세스하고 조작하는 방법을 알아보세요. PowerPoint 프레젠테이션에서 모양과 선 스타일을 손쉽게 사용자 정의하세요.
weight: 10
url: /ko/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 레이아웃 형식에 액세스


## Java 슬라이드의 레이아웃 형식 액세스 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드의 레이아웃 형식에 액세스하고 작업하는 방법을 살펴보겠습니다. 레이아웃 형식을 사용하면 프레젠테이션의 레이아웃 슬라이드 내에서 모양과 선의 모양을 제어할 수 있습니다. 레이아웃 슬라이드의 도형에 대한 채우기 형식과 선 형식을 검색하는 방법을 다룹니다.

## 전제 조건

1. Aspose.Slides for Java 라이브러리.
2. 레이아웃 슬라이드가 포함된 PowerPoint 프레젠테이션(PPTX 형식)입니다.

## 1단계: 프레젠테이션 로드

 먼저 레이아웃 슬라이드가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## 2단계: 레이아웃 형식에 액세스

이제 프레젠테이션의 레이아웃 슬라이드를 반복하면서 각 레이아웃 슬라이드에 있는 도형의 채우기 형식과 선 형식에 액세스해 보겠습니다.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // 도형의 채우기 형식에 액세스
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // 도형의 선 형식에 액세스
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

위의 코드에서:

- 우리는`for` 고리.
- 각 레이아웃 슬라이드에 대해 해당 슬라이드의 모양에 대한 채우기 형식과 선 형식을 저장하는 배열을 만듭니다.
-  우리는 중첩을 사용합니다`for` 루프를 사용하여 레이아웃 슬라이드의 모양을 반복하고 채우기 및 선 형식을 검색합니다.

## 3단계: 레이아웃 형식 작업

이제 레이아웃 슬라이드의 도형에 대한 채우기 형식과 선 형식에 액세스했으므로 필요에 따라 다양한 작업을 수행할 수 있습니다. 예를 들어 채우기 색상, 선 스타일 또는 도형의 기타 속성을 변경할 수 있습니다.

## Java 슬라이드의 액세스 레이아웃 형식에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java 슬라이드의 레이아웃 형식에 액세스하고 조작하는 방법을 살펴보았습니다. 레이아웃 형식은 PowerPoint 프레젠테이션의 레이아웃 슬라이드 내에서 모양과 선의 모양을 제어하는 데 필수적입니다.

## FAQ

### 도형의 채우기 색상을 어떻게 변경합니까?

 도형의 채우기 색상을 변경하려면`IFillFormat`객체의 메소드. 예는 다음과 같습니다.

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // 채우기 유형을 단색으로 설정
fillFormat.getSolidFillColor().setColor(Color.RED); // 채우기 색상을 빨간색으로 설정
```

### 도형의 선 스타일을 어떻게 변경합니까?

 도형의 선 스타일을 변경하려면`ILineFormat`객체의 메소드. 예는 다음과 같습니다.

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // 선 스타일을 단일로 설정
lineFormat.setWidth(2.0); // 선 너비를 2.0포인트로 설정
lineFormat.getSolidFillColor().setColor(Color.BLUE); // 선 색상을 파란색으로 설정
```

### 레이아웃 슬라이드의 도형에 이러한 변경 사항을 어떻게 적용합니까?

이러한 변경 사항을 레이아웃 슬라이드의 특정 도형에 적용하려면 레이아웃 슬라이드의 도형 컬렉션에 있는 해당 색인을 사용하여 도형에 액세스하면 됩니다. 예를 들어:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // 레이아웃 슬라이드의 첫 번째 도형에 액세스
```

 그런 다음`IFillFormat` 그리고`ILineFormat` 이전 답변에 표시된 방법을 사용하여 모양의 채우기 및 선 형식을 수정합니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

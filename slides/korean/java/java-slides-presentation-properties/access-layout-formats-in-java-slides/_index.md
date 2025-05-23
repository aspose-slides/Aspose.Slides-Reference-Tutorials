---
"description": "Aspose.Slides for Java를 사용하여 Java Slides의 레이아웃 형식에 접근하고 조작하는 방법을 알아보세요. PowerPoint 프레젠테이션에서 모양과 선 스타일을 손쉽게 사용자 지정할 수 있습니다."
"linktitle": "Java Slides에서 레이아웃 형식 액세스"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 레이아웃 형식 액세스"
"url": "/ko/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 레이아웃 형식 액세스


## Java Slides의 Access 레이아웃 형식 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 레이아웃 서식에 액세스하고 작업하는 방법을 살펴봅니다. 레이아웃 서식을 사용하면 프레젠테이션 레이아웃 슬라이드에서 도형과 선의 모양을 제어할 수 있습니다. 레이아웃 슬라이드에서 도형의 채우기 서식과 선 서식을 가져오는 방법도 다룹니다.

## 필수 조건

1. Java 라이브러리용 Aspose.Slides.
2. 레이아웃 슬라이드가 포함된 PowerPoint 프레젠테이션(PPTX 형식)입니다.

## 1단계: 프레젠테이션 로드

먼저 레이아웃 슬라이드가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. `"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용합니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## 2단계: 레이아웃 형식 액세스

이제 프레젠테이션의 레이아웃 슬라이드를 반복하면서 각 레이아웃 슬라이드에 있는 도형의 채우기 서식과 선 서식에 접근해 보겠습니다.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // 도형의 채우기 형식에 접근
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // 모양의 접근선 형식
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

- 우리는 다음을 사용하여 각 레이아웃 슬라이드를 반복합니다. `for` 고리.
- 각 레이아웃 슬라이드에 대해 해당 슬라이드의 모양에 대한 채우기 형식과 선 형식을 저장하기 위한 배열을 만듭니다.
- 우리는 중첩을 사용합니다 `for` 레이아웃 슬라이드의 모양을 반복하고 채우기 및 선 서식을 검색하는 루프입니다.

## 3단계: 레이아웃 형식 작업

이제 레이아웃 슬라이드의 도형에 대한 채우기 서식과 선 서식을 살펴보았으니, 필요에 따라 다양한 작업을 수행할 수 있습니다. 예를 들어, 도형의 채우기 색, 선 스타일 또는 기타 속성을 변경할 수 있습니다.

## Java Slides의 Access 레이아웃 형식에 대한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
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

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides의 레이아웃 형식에 접근하고 조작하는 방법을 살펴보았습니다. 레이아웃 형식은 PowerPoint 프레젠테이션의 레이아웃 슬라이드에서 도형과 선의 모양을 제어하는 데 필수적입니다.

## 자주 묻는 질문

### 도형의 채우기 색상을 어떻게 바꾸나요?

모양의 채우기 색상을 변경하려면 다음을 사용할 수 있습니다. `IFillFormat` 객체의 메서드입니다. 예를 들어 다음과 같습니다.

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // 채우기 유형을 단색으로 설정
fillFormat.getSolidFillColor().setColor(Color.RED); // 채우기 색상을 빨간색으로 설정하세요
```

### 도형의 선 스타일을 어떻게 변경합니까?

도형의 선 스타일을 변경하려면 다음을 사용할 수 있습니다. `ILineFormat` 객체의 메서드입니다. 예를 들어 다음과 같습니다.

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // 선 스타일을 단일로 설정
lineFormat.setWidth(2.0); // 선 너비를 2.0포인트로 설정하세요
lineFormat.getSolidFillColor().setColor(Color.BLUE); // 선 색상을 파란색으로 설정
```

### 레이아웃 슬라이드의 도형에 이러한 변경 사항을 적용하려면 어떻게 해야 하나요?

레이아웃 슬라이드의 특정 도형에 이러한 변경 사항을 적용하려면 레이아웃 슬라이드의 도형 컬렉션에서 해당 도형의 인덱스를 사용하여 도형에 액세스할 수 있습니다. 예:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // 레이아웃 슬라이드의 첫 번째 모양에 접근합니다.
```

그런 다음 다음을 사용할 수 있습니다. `IFillFormat` 그리고 `ILineFormat` 이전 답변에서 보여준 것과 같은 방법을 사용하여 도형의 채우기와 선 서식을 수정합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
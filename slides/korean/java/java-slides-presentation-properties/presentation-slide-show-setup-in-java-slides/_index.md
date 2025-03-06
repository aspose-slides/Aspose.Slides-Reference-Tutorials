---
title: Java 슬라이드의 프레젠테이션 슬라이드 쇼 설정
linktitle: Java 슬라이드의 프레젠테이션 슬라이드 쇼 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides로 Java 슬라이드 쇼를 최적화하세요. 맞춤형 설정으로 매력적인 프레젠테이션을 만드세요. 단계별 가이드와 FAQ를 살펴보세요.
weight: 16
url: /ko/java/presentation-properties/presentation-slide-show-setup-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드의 프레젠테이션 슬라이드 쇼 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프레젠테이션 슬라이드 쇼를 설정하는 방법을 살펴보겠습니다. PowerPoint 프레젠테이션을 만들고 다양한 슬라이드 쇼 설정을 구성하는 과정을 단계별로 살펴보겠습니다.

## 전제 조건

 시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 추가되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose 웹사이트](https://releases.aspose.com/slides/java/).

## 1단계: PowerPoint 프레젠테이션 만들기

먼저 새로운 PowerPoint 프레젠테이션을 만들어야 합니다. Java에서 이를 수행하는 방법은 다음과 같습니다.

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

 위 코드에서는 프레젠테이션의 출력 파일 경로를 지정하고 새 파일을 만듭니다.`Presentation` 물체.

## 2단계: 슬라이드 쇼 설정 구성

다음으로 프레젠테이션에 대한 다양한 슬라이드 쇼 설정을 구성하겠습니다. 

### 타이밍 매개변수 사용

"타이밍 사용" 매개변수를 설정하여 슬라이드 쇼 중에 슬라이드를 자동으로 진행할지 수동으로 진행할지 제어할 수 있습니다.

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // 수동으로 진행하려면 false로 설정하세요.
```

 이 예에서는 다음과 같이 설정했습니다.`false` 슬라이드를 수동으로 진행할 수 있습니다.

### 펜 색상 설정

슬라이드 쇼 중에 사용되는 펜 색상을 사용자 정의할 수도 있습니다. 이 예에서는 펜 색상을 녹색으로 설정하겠습니다.

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### 슬라이드 추가

프레젠테이션에 슬라이드를 몇 개 추가해 보겠습니다. 작업을 단순하게 유지하기 위해 기존 슬라이드를 복제하겠습니다.

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

이 코드에서는 첫 번째 슬라이드를 4번 복제합니다. 이 부분을 수정하여 자신만의 콘텐츠를 추가할 수 있습니다.

## 3단계: 슬라이드 쇼의 슬라이드 범위 정의

슬라이드 쇼에 포함할 슬라이드를 지정할 수 있습니다. 이 예에서는 두 번째 슬라이드부터 다섯 번째 슬라이드까지 슬라이드 범위를 설정해 보겠습니다.

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

시작 및 끝 슬라이드 번호를 설정하면 슬라이드 쇼에 포함될 슬라이드를 제어할 수 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 구성된 프레젠테이션을 파일에 저장하겠습니다.

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

원하는 출력 파일 경로를 제공해야 합니다.

## Java 슬라이드에서 프리젠테이션 슬라이드 쇼 설정을 위한 전체 소스 코드

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// 슬라이드쇼 설정을 가져옵니다.
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// "타이밍 사용" 매개변수 설정
	slideShow.setUseTimings(false);
	// 펜 색상 설정
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// 다음에 대한 슬라이드를 추가합니다.
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// 슬라이드 표시 매개변수 설정
	SlidesRange slidesRange = new SlidesRange();
	slidesRange.setStart(2);
	slidesRange.setEnd(5);
	slideShow.setSlides(slidesRange);
	// 프레젠테이션 저장
	pres.save(outPptxPath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java로 프레젠테이션 슬라이드 쇼를 설정하는 방법을 배웠습니다. 타이밍, 펜 색상, 슬라이드 범위 등 다양한 슬라이드 쇼 설정을 사용자 정의하여 대화형의 매력적인 프레젠테이션을 만들 수 있습니다.

## FAQ

### 슬라이드 전환 타이밍을 어떻게 변경합니까?

 슬라이드 전환 타이밍을 변경하려면 슬라이드 쇼 설정에서 "타이밍 사용" 매개변수를 수정할 수 있습니다. 다음으로 설정하세요`true` 사전 정의된 타이밍으로 자동 진행을 위해 또는`false`슬라이드 쇼 도중 수동으로 진행합니다.

### 슬라이드 쇼 중에 사용되는 펜 색상을 어떻게 사용자 정의할 수 있나요?

 슬라이드 쇼 설정의 펜 색상 설정에 액세스하여 펜 색상을 사용자 정의할 수 있습니다. 사용`setColor` 원하는 색상을 설정하는 방법입니다. 예를 들어 펜 색상을 녹색으로 설정하려면`penColor.setColor(Color.GREEN)`.

### 슬라이드 쇼에 특정 슬라이드를 어떻게 추가합니까?

 슬라이드 쇼에 특정 슬라이드를 포함하려면`SlidesRange` 개체를 사용하여 시작 및 끝 슬라이드 번호를 설정합니다.`setStart` 그리고`setEnd` 행동 양식. 그런 다음 다음을 사용하여 이 범위를 슬라이드 쇼 설정에 할당합니다.`slideShow.setSlides(slidesRange)`.

### 프레젠테이션에 슬라이드를 더 추가할 수 있나요?

 예, 프레젠테이션에 슬라이드를 추가할 수 있습니다. 사용`pres.getSlides().addClone()` 필요에 따라 기존 슬라이드를 복제하거나 새 슬라이드를 만드는 방법입니다. 귀하의 요구 사항에 따라 이러한 슬라이드의 내용을 사용자 정의하십시오.

### 구성된 프레젠테이션을 파일에 어떻게 저장합니까?

 구성된 프리젠테이션을 파일에 저장하려면`pres.save()`방법을 선택하고 출력 파일 경로와 원하는 형식을 지정합니다. 예를 들어 다음을 사용하여 PPTX 형식으로 저장할 수 있습니다.`pres.save(outPptxPath, SaveFormat.Pptx)`.

### 슬라이드 쇼 설정을 추가로 사용자 정의하려면 어떻게 해야 합니까?

 Aspose.Slides for Java에서 제공하는 추가 슬라이드 쇼 설정을 탐색하여 슬라이드 쇼 경험을 필요에 맞게 조정할 수 있습니다. 다음 문서를 참조하세요.[여기](https://reference.aspose.com/slides/java/) 사용 가능한 옵션 및 구성에 대한 자세한 내용은
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

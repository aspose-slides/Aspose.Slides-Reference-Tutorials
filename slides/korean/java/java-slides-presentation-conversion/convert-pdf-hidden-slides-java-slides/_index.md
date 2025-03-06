---
title: Java 슬라이드의 숨겨진 슬라이드를 사용하여 PDF로 변환
linktitle: Java 슬라이드의 숨겨진 슬라이드를 사용하여 PDF로 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 숨겨진 슬라이드가 있는 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 알아보세요. 원활한 PDF 생성을 위한 소스 코드가 포함된 단계별 가이드를 따르세요.
weight: 27
url: /ko/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Aspose.Slides for Java를 사용하여 숨겨진 슬라이드가 있는 PowerPoint 프레젠테이션을 PDF로 변환하는 방법 소개

이 단계별 가이드에서는 Aspose.Slides for Java를 사용하여 숨겨진 슬라이드를 유지하면서 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 알아봅니다. 숨겨진 슬라이드는 일반 프레젠테이션 중에는 표시되지 않지만 PDF 출력에는 포함될 수 있는 슬라이드입니다. 우리는 이 작업을 달성하기 위한 소스 코드와 자세한 지침을 제공할 것입니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  Aspose.Slides for Java 라이브러리: Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설정되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/).

2. Java 개발 환경: 시스템에 Java 개발 환경이 설치되어 있어야 합니다.

## 1단계: Java용 Aspose.Slides 가져오기

먼저 Aspose.Slides 라이브러리를 Java 프로젝트로 가져와야 합니다. 프로젝트의 빌드 경로에 라이브러리를 추가했는지 확인하세요.

```java
import com.aspose.slides.*;
```

## 2단계: PowerPoint 프레젠테이션 로드

 PDF로 변환하려는 PowerPoint 프레젠테이션을 로드하는 것부터 시작합니다. 바꾸다`"Your Document Directory"` 그리고`"HiddingSlides.pptx"` 적절한 파일 경로로.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## 3단계: PDF 옵션 구성

PDF 출력에 숨겨진 슬라이드를 포함하도록 PDF 옵션을 구성합니다. 이 작업은 다음을 설정하여 수행할 수 있습니다.`setShowHiddenSlides` 의 재산`PdfOptions` 수업`true`.

```java
// PdfOptions 클래스를 인스턴스화합니다.
PdfOptions pdfOptions = new PdfOptions();
// 생성된 문서에 숨겨진 슬라이드가 포함되도록 지정
pdfOptions.setShowHiddenSlides(true);
```

## 4단계: 프레젠테이션을 PDF로 저장

 이제 지정된 옵션을 사용하여 프레젠테이션을 PDF 파일로 저장합니다. 바꾸다`"PDFWithHiddenSlides_out.pdf"` 원하는 출력 파일 이름으로.

```java
// 지정된 옵션을 사용하여 프레젠테이션을 PDF로 저장
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 5단계: 리소스 정리

프레젠테이션이 끝나면 프레젠테이션에 사용된 리소스를 해제해야 합니다.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java 슬라이드의 숨겨진 슬라이드가 있는 PDF로 변환하기 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// PdfOptions 클래스를 인스턴스화합니다.
	PdfOptions pdfOptions = new PdfOptions();
	// 생성된 문서에 숨겨진 슬라이드가 포함되도록 지정
	pdfOptions.setShowHiddenSlides(true);
	// 지정된 옵션을 사용하여 프레젠테이션을 PDF로 저장
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 종합 가이드에서는 Aspose.Slides for Java를 사용하여 숨겨진 슬라이드를 유지하면서 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 배웠습니다. 우리는 이 작업을 원활하게 수행하는 데 필요한 소스 코드와 함께 단계별 튜토리얼을 제공했습니다.

## FAQ

### PowerPoint 프레젠테이션에서 슬라이드를 숨기려면 어떻게 해야 하나요?

PowerPoint 프레젠테이션에서 슬라이드를 숨기려면 다음 단계를 따르세요.
1. 여러 슬라이드 보기에서 숨기려는 슬라이드를 선택하세요.
2. 선택한 슬라이드를 마우스 오른쪽 버튼으로 클릭하세요.
3. 상황에 맞는 메뉴에서 "슬라이드 숨기기"를 선택하십시오.

### Aspose.Slides for Java에서 프로그래밍 방식으로 숨겨진 슬라이드를 숨김 해제할 수 있나요?

 예, Aspose.Slides for Java에서 프로그래밍 방식으로 숨겨진 슬라이드 숨기기를 해제할 수 있습니다.`Hidden` 의 재산`Slide` 수업`false`. 예는 다음과 같습니다.

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // SlideIndex를 숨겨진 슬라이드의 인덱스로 교체
slide.setHidden(false);
```

### Java용 Aspose.Slides를 어떻게 다운로드하나요?

 Aspose 웹사이트에서 Java용 Aspose.Slides를 다운로드할 수 있습니다. 방문하다[Aspose.Slides for Java 다운로드 페이지](https://releases.aspose.com/slides/java/) 최신 버전을 얻으려면.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

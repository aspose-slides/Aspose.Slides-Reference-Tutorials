---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 숨겨진 슬라이드가 있는 PDF로 변환하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드를 따라 PDF를 원활하게 생성하세요."
"linktitle": "Java Slides에서 숨겨진 슬라이드를 PDF로 변환"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 숨겨진 슬라이드를 PDF로 변환"
"url": "/ko/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 숨겨진 슬라이드를 PDF로 변환


## Java용 Aspose.Slides를 사용하여 숨겨진 슬라이드가 있는 PowerPoint 프레젠테이션을 PDF로 변환하는 방법 소개

이 단계별 가이드에서는 Aspose.Slides for Java를 사용하여 숨겨진 슬라이드를 유지하면서 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 알아봅니다. 숨겨진 슬라이드는 일반 프레젠테이션에서는 표시되지 않지만 PDF 출력에는 포함될 수 있는 슬라이드입니다. 이 작업을 수행하기 위한 소스 코드와 자세한 지침을 제공합니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Aspose.Slides for Java 라이브러리: Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).

2. Java 개발 환경: 시스템에 Java 개발 환경이 설치되어 있어야 합니다.

## 1단계: Java용 Aspose.Slides 가져오기

먼저 Aspose.Slides 라이브러리를 Java 프로젝트로 가져와야 합니다. 프로젝트의 빌드 경로에 라이브러리를 추가했는지 확인하세요.

```java
import com.aspose.slides.*;
```

## 2단계: PowerPoint 프레젠테이션 로드

PDF로 변환하려는 PowerPoint 프레젠테이션을 로드하여 시작합니다. 바꾸기 `"Your Document Directory"` 그리고 `"HiddingSlides.pptx"` 적절한 파일 경로를 사용하여.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## 3단계: PDF 옵션 구성

PDF 출력에 숨겨진 슬라이드를 포함하도록 PDF 옵션을 구성하세요. 다음을 설정하여 이를 수행할 수 있습니다. `setShowHiddenSlides` 의 재산 `PdfOptions` 수업에 `true`.

```java
// PdfOptions 클래스를 인스턴스화합니다.
PdfOptions pdfOptions = new PdfOptions();
// 생성된 문서에 숨겨진 슬라이드를 포함하도록 지정합니다.
pdfOptions.setShowHiddenSlides(true);
```

## 4단계: 프레젠테이션을 PDF로 저장

이제 지정된 옵션을 사용하여 프레젠테이션을 PDF 파일로 저장합니다. 바꾸기 `"PDFWithHiddenSlides_out.pdf"` 원하는 출력 파일 이름을 입력하세요.

```java
// 지정된 옵션을 사용하여 프레젠테이션을 PDF로 저장합니다.
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 5단계: 자원 정리

프레젠테이션을 마친 후에는 사용된 리소스를 반드시 반환하세요.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Java Slides에서 숨겨진 슬라이드를 PDF로 변환하기 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// PdfOptions 클래스를 인스턴스화합니다.
	PdfOptions pdfOptions = new PdfOptions();
	// 생성된 문서에 숨겨진 슬라이드를 포함하도록 지정합니다.
	pdfOptions.setShowHiddenSlides(true);
	// 지정된 옵션을 사용하여 프레젠테이션을 PDF로 저장합니다.
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 종합 가이드에서는 Aspose.Slides for Java를 사용하여 숨겨진 슬라이드를 유지하면서 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 알아보았습니다. 이 작업을 원활하게 수행하는 데 필요한 소스 코드와 함께 단계별 튜토리얼을 제공합니다.

## 자주 묻는 질문

### PowerPoint 프레젠테이션에서 슬라이드를 숨기려면 어떻게 해야 하나요?

PowerPoint 프레젠테이션에서 슬라이드를 숨기려면 다음 단계를 따르세요.
1. 슬라이드 정렬 보기에서 숨기려는 슬라이드를 선택합니다.
2. 선택한 슬라이드를 마우스 오른쪽 버튼으로 클릭합니다.
3. 상황에 맞는 메뉴에서 "슬라이드 숨기기"를 선택합니다.

### Java용 Aspose.Slides에서 숨겨진 슬라이드를 프로그래밍 방식으로 표시하도록 설정할 수 있나요?

예, Aspose.Slides for Java에서 숨겨진 슬라이드를 프로그래밍 방식으로 표시하려면 다음을 설정하세요. `Hidden` 의 재산 `Slide` 수업에 `false`. 예를 들면 다음과 같습니다.

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // slideIndex를 숨겨진 슬라이드의 인덱스로 바꾸세요
slide.setHidden(false);
```

### Java용 Aspose.Slides를 어떻게 다운로드하나요?

Aspose.Slides for Java는 Aspose 웹사이트에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/) 최신 버전을 받으려면.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
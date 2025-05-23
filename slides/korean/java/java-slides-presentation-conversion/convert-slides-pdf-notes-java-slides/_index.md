---
"description": "Aspose.Slides for Java를 사용하여 Java에서 PowerPoint 슬라이드를 노트가 포함된 PDF로 변환하는 방법을 알아보세요. Java 개발자를 위한 단계별 가이드입니다. 프레젠테이션 공유를 더욱 효과적으로 만들어 보세요."
"linktitle": "Java Slides에서 노트를 사용하여 슬라이드를 PDF로 변환"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 노트를 사용하여 슬라이드를 PDF로 변환"
"url": "/ko/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 노트를 사용하여 슬라이드를 PDF로 변환


## Java에서 슬라이드를 노트와 함께 PDF로 변환하는 방법 소개

디지털 프레젠테이션 분야에서 슬라이드를 노트와 함께 PDF로 변환하는 기능은 매우 유용합니다. Java 개발자는 Aspose.Slides for Java 라이브러리를 사용하여 이를 구현할 수 있습니다. 이 라이브러리는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있는 강력한 도구 세트를 제공합니다. 이 단계별 가이드에서는 Java와 Aspose.Slides for Java를 사용하여 슬라이드를 노트와 함께 PDF로 변환하는 방법을 살펴보겠습니다.

## 필수 조건

코드를 살펴보기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Java용 Aspose.Slides 라이브러리입니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

이제 개요를 살펴보았으니, 구현 단계를 하나씩 살펴보겠습니다.
## 1단계: 프로젝트 설정

먼저 Java 프로젝트를 만들고 프로젝트의 종속성에 Java용 Aspose.Slides 라이브러리를 추가합니다.

## 2단계: 프레젠테이션 로딩

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 3단계: 새 프레젠테이션 만들기

```java
Presentation auxPresentation = new Presentation();
```

## 4단계: 슬라이드 복사

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## 5단계: 슬라이드 크기 조정

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6단계: PDF 옵션 구성

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## 7단계: PDF로 저장

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Java Slides에서 노트를 포함한 슬라이드를 PDF로 변환하기 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다. 
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// 슬라이드 유형 및 크기 설정
		//auxPresentation.getSlideSize().setSize(프레젠테이션.getSlideSize().getSize().getWidth(), 프레젠테이션.getSlideSize().getSize().getHeight(),슬라이드사이즈스케일유형.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java에서 슬라이드를 노트가 포함된 PDF로 변환하는 방법을 알아보았습니다. 프로젝트 설정, 프레젠테이션 로드, 새 프레젠테이션 생성, 슬라이드 복사, 슬라이드 크기 조정, PDF 옵션 구성, 마지막으로 프레젠테이션을 노트가 포함된 PDF로 저장하는 방법을 다루었습니다.

## 자주 묻는 질문

### Java용 Aspose.Slides를 어떻게 설치합니까?

Java용 Aspose.Slides를 설치하려면 다음 단계를 따르세요.
1. 라이브러리를 다운로드하세요 [여기](https://releases.aspose.com/slides/java/).
2. JAR 파일을 Java 프로젝트의 클래스 경로에 추가합니다.

### 생성된 PDF에서 메모 위치를 사용자 지정할 수 있나요?

예, 메모 위치를 수정하여 사용자 정의할 수 있습니다. `NotesPositions` PDF 옵션의 열거형입니다. 이 튜토리얼에서는 이를 다음과 같이 설정합니다. `BottomFull`하지만 다른 옵션도 살펴볼 수 있습니다.

### Java에서 Aspose.Slides를 사용하는 데 라이선스 요구 사항이 있습니까?

네, Aspose.Slides for Java는 상용 라이브러리이므로 프로덕션 환경에서 사용하려면 라이선스를 구매해야 할 수 있습니다. 라이선스에 대한 자세한 내용은 Aspose 웹사이트를 참조하세요.

### 여러 슬라이드를 한 번에 변환할 수 있나요?

물론입니다! 프레젠테이션의 슬라이드를 반복해서 살펴보고 새 프레젠테이션에 복제하면 여러 슬라이드를 노트가 포함된 PDF로 한 번에 변환할 수 있습니다.

### Java용 Aspose.Slides에 대한 추가 문서는 어디에서 찾을 수 있나요?

다음 사이트에서 Aspose.Slides for Java에 대한 자세한 문서를 찾을 수 있습니다. [Java용 Aspose.Slides API 참조](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
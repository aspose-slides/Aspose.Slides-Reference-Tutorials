---
title: Java 슬라이드의 메모를 사용하여 슬라이드를 PDF로 변환
linktitle: Java 슬라이드의 메모를 사용하여 슬라이드를 PDF로 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java에서 메모가 포함된 PowerPoint 슬라이드를 PDF로 변환하는 방법을 알아보세요. Java 개발자를 위한 단계별 가이드입니다. 프레젠테이션 공유 기능을 향상하세요.
weight: 19
url: /ko/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 메모를 사용하여 슬라이드를 PDF로 변환


## Java의 Notes를 사용하여 슬라이드를 PDF로 변환하는 방법 소개

디지털 프리젠테이션 세계에서 슬라이드를 메모와 함께 PDF로 변환하는 기능은 중요한 기능입니다. Java 개발자는 프로그래밍 방식으로 PowerPoint 프레젠테이션 작업을 위한 강력한 도구 세트를 제공하는 Aspose.Slides for Java 라이브러리를 사용하여 이를 달성할 수 있습니다. 이 단계별 가이드에서는 Java 및 Aspose.Slides for Java를 사용하여 메모가 포함된 슬라이드를 PDF로 변환하는 방법을 살펴보겠습니다.

## 전제 조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

이제 개요가 완성되었으므로 구현을 단계별로 살펴보겠습니다.
## 1단계: 프로젝트 설정

먼저 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 프로젝트 종속성에 추가합니다.

## 2단계: 프레젠테이션 로드

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 3단계: 새 프레젠테이션 만들기

```java
Presentation auxPresentation = new Presentation();
```

## 4단계: 슬라이드 복사하기

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

## Java 슬라이드의 메모가 포함된 슬라이드를 PDF로 변환하기 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프리젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// 슬라이드 유형 및 크기 설정
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), Presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
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

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java에서 메모가 포함된 슬라이드를 PDF로 변환하는 방법을 배웠습니다. 프로젝트 설정, 프레젠테이션 로드, 새 프레젠테이션 만들기, 슬라이드 복사, 슬라이드 크기 조정, PDF 옵션 구성, 마지막으로 프레젠테이션을 메모와 함께 PDF로 저장하는 과정을 다루었습니다.

## FAQ

### Java용 Aspose.Slides를 어떻게 설치하나요?

Java용 Aspose.Slides를 설치하려면 다음 단계를 따르세요.
1.  다음에서 라이브러리를 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
2. Java 프로젝트의 클래스 경로에 JAR 파일을 추가합니다.

### 생성된 PDF에서 메모 위치를 사용자 정의할 수 있나요?

 예, 메모 위치를 수정하여 사용자 정의할 수 있습니다.`NotesPositions` PDF 옵션에 열거되어 있습니다. 이 튜토리얼에서는 다음과 같이 설정했습니다.`BottomFull`이지만 다른 옵션도 탐색할 수 있습니다.

### Aspose.Slides for Java를 사용하기 위한 라이선스 요구 사항이 있나요?

예, Aspose.Slides for Java는 상용 라이브러리이므로 프로덕션에서 사용하려면 라이선스를 취득해야 할 수도 있습니다. 라이선스 세부정보를 보려면 Aspose 웹사이트를 방문하세요.

### 여러 슬라이드를 한 번에 변환할 수 있나요?

틀림없이! 프레젠테이션의 슬라이드를 반복하여 새 프레젠테이션에 복제할 수 있으므로 한 번에 여러 슬라이드를 메모가 포함된 PDF로 변환할 수 있습니다.

### Aspose.Slides for Java에 대한 추가 문서는 어디서 찾을 수 있나요?

 다음 사이트에서 Aspose.Slides for Java에 대한 자세한 문서를 찾을 수 있습니다.[Java API 참조용 Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

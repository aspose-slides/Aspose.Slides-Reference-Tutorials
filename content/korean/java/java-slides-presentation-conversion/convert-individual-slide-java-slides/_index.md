---
title: Java 슬라이드에서 개별 슬라이드 변환
linktitle: Java 슬라이드에서 개별 슬라이드 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 코드 예제를 통해 개별 PowerPoint 슬라이드를 HTML로 단계별로 변환하는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/java/presentation-conversion/convert-individual-slide-java-slides/
---

## Java 슬라이드의 개별 슬라이드 변환 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 개별 슬라이드를 HTML로 변환하는 과정을 안내합니다. 이 단계별 가이드에서는 이 작업을 수행하는 데 도움이 되는 소스 코드와 설명을 제공합니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java 라이브러리용 Aspose.Slides가 설치되었습니다.
- PowerPoint 프리젠테이션 파일(`Individual-Slide.pptx`) 변환하려는 항목입니다.
- Java 개발 환경이 설정되었습니다.

## 1단계: 프로젝트 설정

1. 원하는 개발 환경에서 Java 프로젝트를 만듭니다.
2. 프로젝트에 Aspose.Slides for Java 라이브러리를 추가하세요.

## 2단계: 필요한 클래스 가져오기

Java 클래스에서 필수 클래스를 가져오고 초기 구성을 설정합니다.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## 3단계: 주요 변환 방법 정의

 개별 슬라이드의 변환을 수행하는 방법을 만듭니다. 꼭 교체하세요`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // 파일 저장 중
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 4단계: CustomFormattingController 구현

 생성`CustomFormattingController` 변환 중에 사용자 정의 형식을 처리하는 클래스입니다.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## 5단계: 변환 실행

 마지막으로`convertIndividualSlides` 변환 프로세스를 실행하는 방법.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Java 슬라이드의 개별 슬라이드 변환을 위한 완전한 소스 코드

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// 파일 저장 중
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## 결론

Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 개별 슬라이드를 HTML로 성공적으로 변환했습니다. 이 튜토리얼에서는 이 작업을 수행하는 데 필요한 코드와 단계를 제공했습니다. 특정 요구 사항에 따라 필요에 따라 출력 및 형식을 자유롭게 사용자 정의할 수 있습니다.

## FAQ

### HTML 출력을 추가로 사용자 정의하려면 어떻게 해야 합니까?

 다음을 수정하여 HTML 출력을 사용자 정의할 수 있습니다.`CustomFormattingController` 수업. 조정하다`writeSlideStart` 그리고`writeSlideEnd` 슬라이드 HTML 구조와 스타일을 변경하는 방법입니다.

### 여러 PowerPoint 프레젠테이션을 한 번에 변환할 수 있나요?

 예, 여러 프리젠테이션 파일을 반복하고 호출하여 개별적으로 변환하도록 코드를 수정할 수 있습니다.`convertIndividualSlides` 각 프레젠테이션의 방법.

### 슬라이드 내의 도형 및 텍스트에 대한 추가 서식을 어떻게 처리합니까?

 연장할 수 있습니다.`CustomFormattingController` 클래스를 구현하여 모양별 서식을 처리합니다.`writeShapeStart` 그리고`writeShapeEnd` 메소드와 그 안에 사용자 정의 형식 논리를 적용합니다.
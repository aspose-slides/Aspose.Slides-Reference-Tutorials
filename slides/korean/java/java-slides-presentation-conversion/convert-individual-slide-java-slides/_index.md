---
"description": "Aspose.Slides for Java를 사용하여 코드 예제를 통해 개별 PowerPoint 슬라이드를 HTML로 단계별로 변환하는 방법을 알아보세요."
"linktitle": "개별 슬라이드를 Java 슬라이드로 변환"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "개별 슬라이드를 Java 슬라이드로 변환"
"url": "/ko/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 개별 슬라이드를 Java 슬라이드로 변환


## Java 슬라이드에서 개별 슬라이드 변환 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 개별 슬라이드를 HTML로 변환하는 과정을 살펴보겠습니다. 이 단계별 가이드는 이 작업을 수행하는 데 도움이 되는 소스 코드와 설명을 제공합니다.

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

- Java 라이브러리용 Aspose.Slides가 설치되었습니다.
- PowerPoint 프레젠테이션 파일(`Individual-Slide.pptx`) 변환하려는 항목입니다.
- Java 개발 환경 설정.

## 1단계: 프로젝트 설정

1. 원하는 개발 환경에서 Java 프로젝트를 만듭니다.
2. 프로젝트에 Java용 Aspose.Slides 라이브러리를 추가합니다.

## 2단계: 필요한 클래스 가져오기

Java 클래스에서 필요한 클래스를 가져오고 초기 구성을 설정합니다.

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

개별 슬라이드를 변환하는 메서드를 만듭니다. 다음을 반드시 교체하세요. `"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용합니다.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // 파일 저장
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## 4단계: CustomFormattingController 구현

생성하다 `CustomFormattingController` 변환 중에 사용자 정의 형식을 처리하는 클래스입니다.

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

마지막으로 전화하세요 `convertIndividualSlides` 변환 과정을 실행하는 방법입니다.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Java 슬라이드에서 개별 슬라이드를 변환하기 위한 완전한 소스 코드

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// 파일 저장              
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

Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 개별 슬라이드를 HTML로 성공적으로 변환했습니다. 이 튜토리얼에서는 이 작업을 수행하는 데 필요한 코드와 단계를 제공했습니다. 특정 요구 사항에 맞게 출력 및 서식을 자유롭게 사용자 지정할 수 있습니다.

## 자주 묻는 질문

### HTML 출력을 더욱 세부적으로 사용자 지정하려면 어떻게 해야 합니까?

HTML 출력을 사용자 정의하려면 다음을 수정하세요. `CustomFormattingController` 클래스. 조정 `writeSlideStart` 그리고 `writeSlideEnd` 슬라이드 HTML 구조와 스타일을 변경하는 방법.

### 여러 개의 PowerPoint 프레젠테이션을 한 번에 변환할 수 있나요?

예, 여러 프레젠테이션 파일을 반복하고 개별적으로 변환하도록 코드를 수정할 수 있습니다. `convertIndividualSlides` 각 프레젠테이션에 대한 방법.

### 슬라이드 내의 도형과 텍스트에 대한 추가 서식을 어떻게 처리합니까?

확장할 수 있습니다 `CustomFormattingController` 모양별 서식을 처리하기 위한 클래스를 구현합니다. `writeShapeStart` 그리고 `writeShapeEnd` 방법을 사용하고 그 안에서 사용자 정의 서식 논리를 적용합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
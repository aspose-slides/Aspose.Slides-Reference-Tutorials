---
title: Java 슬라이드에서 원본 글꼴을 유지하면서 프레젠테이션을 HTML로 변환
linktitle: Java 슬라이드에서 원본 글꼴을 유지하면서 프레젠테이션을 HTML로 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 원본 글꼴을 유지하면서 PowerPoint 프레젠테이션을 HTML로 변환하세요.
weight: 14
url: /ko/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드에서 원본 글꼴을 유지하면서 프레젠테이션을 HTML로 변환하는 방법 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 원본 글꼴을 유지하면서 PowerPoint 프레젠테이션(PPTX)을 HTML로 변환하는 방법을 살펴보겠습니다. 이렇게 하면 결과 HTML이 원본 프레젠테이션의 모양과 매우 유사해집니다.

## 1단계: 프로젝트 설정
코드를 살펴보기 전에 필요한 설정이 제대로 되어 있는지 확인하세요.

1. Java용 Aspose.Slides 다운로드: 아직 다운로드하지 않은 경우 Java용 Aspose.Slides 라이브러리를 다운로드하여 프로젝트에 포함하세요.

2. Java 프로젝트 만들기: 자주 사용하는 IDE에서 Java 프로젝트를 설정하고 Aspose.Slides JAR 파일을 저장할 수 있는 "lib" 폴더가 있는지 확인하세요.

3. 필수 클래스 가져오기: Java 파일 시작 부분에서 필요한 클래스를 가져옵니다.

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2단계: 원본 글꼴을 사용하여 프레젠테이션을 HTML로 변환

이제 원본 글꼴을 유지하면서 PowerPoint 프레젠테이션을 HTML로 변환해 보겠습니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// 프레젠테이션 로드
Presentation pres = new Presentation("input.pptx");

try {
    // Calibri 및 Arial과 같은 기본 프레젠테이션 글꼴 제외
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML 옵션 생성 및 사용자 정의 HTML 포맷터 설정
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // 프레젠테이션을 HTML로 저장
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // 프레젠테이션 개체 삭제
    if (pres != null) pres.dispose();
}
```

이 코드 조각에서:

-  다음을 사용하여 입력 PowerPoint 프레젠테이션을 로드합니다.`Presentation`.

- 우리는 글꼴 목록을 정의합니다(`fontNameExcludeList`HTML에 삽입하지 않으려는 항목입니다. 이는 Calibri 및 Arial과 같은 일반적인 글꼴을 제외하여 파일 크기를 줄이는 데 유용합니다.

-  우리는`EmbedAllFontsHtmlController` 글꼴 제외 목록을 전달합니다.

-  우리는 창조한다`HtmlOptions` 다음을 사용하여 사용자 정의 HTML 포맷터를 설정합니다.`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- 마지막으로 지정된 옵션을 사용하여 프레젠테이션을 HTML로 저장합니다.

## Java 슬라이드의 원본 글꼴을 유지하면서 프레젠테이션을 HTML로 변환하기 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// 기본 프레젠테이션 글꼴 제외
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 원본 글꼴을 유지하면서 PowerPoint 프레젠테이션을 HTML로 변환하는 방법을 배웠습니다. 이는 웹에서 프레젠테이션을 공유할 때 프레젠테이션의 시각적 충실도를 유지하려는 경우에 유용합니다.

## FAQ

### Java용 Aspose.Slides를 어떻게 다운로드하나요?

 Aspose 웹사이트에서 Java용 Aspose.Slides를 다운로드할 수 있습니다. 방문하다[여기](https://downloads.aspose.com/slides/java/) 최신 버전을 얻으려면.

### 제외된 글꼴 목록을 사용자 정의할 수 있나요?

 예, 맞춤설정할 수 있습니다.`fontNameExcludeList` 요구 사항에 따라 특정 글꼴을 포함하거나 제외하도록 배열합니다.

### 이 방법이 PPT와 같은 이전 PowerPoint 형식에 작동합니까?

이 코드 예제는 PPTX 파일용으로 설계되었습니다. 이전 PPT 파일을 변환해야 하는 경우 코드를 조정해야 할 수도 있습니다.

### HTML 출력을 추가로 사용자 정의하려면 어떻게 해야 합니까?

 당신은 탐색 할 수 있습니다`HtmlOptions` 슬라이드 크기, 이미지 품질 등과 같은 HTML 출력의 다양한 측면을 사용자 정의하는 클래스입니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

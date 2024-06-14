---
title: Java를 사용하여 기본 일반 글꼴로 PowerPoint 저장
linktitle: Java를 사용하여 기본 일반 글꼴로 PowerPoint 저장
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하는 방법을 알아보세요. 단계별 튜토리얼을 통해 Java PowerPoint 처리를 마스터하세요.
type: docs
weight: 12
url: /ko/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## 소개
Java 개발 영역에서 프로그래밍 방식으로 PowerPoint 프레젠테이션을 만들고 조작하면 생산성과 사용자 정의 옵션이 크게 향상될 수 있습니다. Aspose.Slides for Java는 개발자가 PowerPoint 파일을 효율적으로 처리할 수 있도록 지원하는 강력한 라이브러리로, 간단한 수정부터 복잡한 프레젠테이션까지 포괄적인 기능 세트를 제공합니다.
## 전제 조건
Aspose.Slides for Java를 사용하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): Java용 Aspose.Slides가 올바르게 작동하려면 JDK 1.8 이상이 필요합니다.
2. Java JAR용 Aspose.Slides: 다음에서 Java용 Aspose.Slides의 최신 버전을 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 원하는 다른 Java IDE를 사용하세요.
4. Java에 대한 기본 이해: Java 프로그래밍 언어 기본 사항에 대한 지식이 필요합니다.

## 패키지 가져오기
Aspose.Slides for Java 사용을 시작하려면 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
이렇게 하면 Aspose.Slides for Java에서 제공하는 모든 클래스와 메서드에 액세스할 수 있습니다.
## 1단계: 프로젝트 설정
먼저 IDE에서 새 Java 프로젝트를 만들고 프로젝트 빌드 경로에 Aspose.Slides for Java JAR 파일을 포함합니다.
## 2단계: 프레젠테이션 개체 초기화
 인스턴스화`Presentation` 로컬 디렉터리에서 기존 PowerPoint 파일(.pptx)을 로드하여 개체를 만듭니다.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// 프레젠테이션 로드
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 바꾸다`"Your Document Directory"` 그리고`"Your Output Directory"` 실제 파일 경로로.
## 3단계: 기본 일반 글꼴로 프레젠테이션 저장
 다음을 사용하여 출력 형식(HTML 및 PDF)에 대한 기본 일반 글꼴을 지정합니다.`HtmlOptions` 그리고`PdfOptions` 각기.
```java
try {
    // HTML 저장 옵션
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF 저장 옵션
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 반드시 교체하세요`"Arial Black"` 그리고`"Lucida Console"` 원하는 기본 일반 글꼴로.

## 결론
다음 단계를 수행함으로써 Aspose.Slides for Java를 효과적으로 사용하여 PowerPoint 프레젠테이션을 조작하는 방법을 배웠습니다. 이 기능을 사용하면 작업을 자동화하고, 프레젠테이션을 사용자 정의하고, 고급 PowerPoint 처리 기능으로 Java 애플리케이션을 향상시킬 수 있습니다.
## FAQ
### Java용 Aspose.Slides가 이전 버전의 JDK와 작동할 수 있나요?
Aspose.Slides for Java에는 호환성을 위해 JDK 1.8 이상이 필요합니다.
### Aspose.Slides for Java에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득하실 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 포괄적인 문서 살펴보기[여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides에 대한 커뮤니티 지원이 있습니까?
 예, 커뮤니티 지원을 받을 수 있습니다[여기](https://forum.aspose.com/c/slides/11).
### Java용 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 무료 평가판을 다운로드하세요[여기](https://releases.aspose.com/).
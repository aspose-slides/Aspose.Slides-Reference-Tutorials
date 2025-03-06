---
title: Java용 Aspose.Slides를 사용하여 HTML에 글꼴 포함
linktitle: Java용 Aspose.Slides를 사용하여 HTML에 글꼴 포함
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 다양한 플랫폼과 장치에서 일관된 타이포그래피를 보장하기 위해 Java용 Aspose.Slides를 사용하여 HTML에 글꼴을 포함하는 방법을 알아보세요.
weight: 13
url: /ko/java/java-powerpoint-font-management/embed-fonts-in-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java용 Aspose.Slides를 사용하여 HTML에 글꼴 포함

## 소개
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하려는 Java 개발자를 위한 강력한 도구입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 HTML에 글꼴을 삽입하는 과정을 자세히 살펴보겠습니다. 글꼴을 포함하면 필요한 글꼴이 로컬에 설치되지 않은 경우에도 프레젠테이션이 다양한 플랫폼과 장치에서 의도한 모양을 유지할 수 있습니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Slides: 다음 사이트에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).
3. IDE(통합 개발 환경): IntelliJ IDEA 또는 Eclipse 등 Java 개발에 선호하는 IDE를 선택하세요.

## 패키지 가져오기
먼저, Aspose.Slides for Java를 사용하여 HTML에 글꼴 포함을 시작하려면 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.*;
```
## 1단계: 문서 및 출력 디렉터리 정의
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
 꼭 교체하세요`"Your Document Directory"` 그리고`"Your Output Directory"` 입력 PowerPoint 프레젠테이션 및 원하는 출력 디렉터리에 대한 경로를 각각 지정합니다.
## 2단계: 프레젠테이션 로드
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
이 단계에서는 PowerPoint 프레젠테이션을 메모리에 로드하여 다양한 작업을 수행할 수 있습니다.
## 3단계: 기본 글꼴 제외
```java
String[] fontNameExcludeList = { "Arial" };
```
포함에서 제외할 글꼴을 지정합니다. 이 예에서는 Arial을 제외합니다.
## 4단계: HTML에 글꼴 포함
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
 이 단계에서는 다음의 인스턴스를 생성합니다.`EmbedAllFontsHtmlController` 제외 목록에 지정된 글꼴을 제외한 모든 글꼴을 포함합니다. 그런 다음 우리는 정의합니다.`HtmlOptions`글꼴을 포함하도록 사용자 정의 HTML 포맷터를 설정합니다. 마지막으로 프레젠테이션을 글꼴이 포함된 HTML로 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 HTML에 글꼴을 포함하는 방법을 살펴보았습니다. 제공된 단계를 따르면 프레젠테이션이 다양한 플랫폼과 장치에서 일관된 타이포그래피를 유지하여 전반적인 보기 경험을 향상시킬 수 있습니다.
## FAQ
### 특정 글꼴을 제외하는 대신 포함할 수 있나요?
 예, 다음을 수정하여 포함하려는 글꼴을 지정할 수 있습니다.`fontNameExcludeList` 그에 따라 배열하십시오.
### Aspose.Slides for Java는 HTML 외에 다른 형식의 글꼴 삽입을 지원합니까?
예, Aspose.Slides는 PDF 및 이미지를 포함한 다양한 출력 형식에 글꼴 포함을 지원합니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Slides for Java에 대한 추가 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 지원을 원하거나 Aspose 지원에 문의하여 전문적인 지원을 받으십시오.
### Aspose.Slides for Java의 임시 라이선스를 구매할 수 있나요?
예, 임시 라이센스를 취득할 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에 단락 들여쓰기를 프로그래밍 방식으로 설정하는 방법을 알아보세요. 프레젠테이션 서식을 손쉽게 개선해 보세요."
"linktitle": "Java PowerPoint에서 단락 들여쓰기 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java PowerPoint에서 단락 들여쓰기 설정"
"url": "/ko/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 단락 들여쓰기 설정

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작하는 방법을 알아봅니다. 특히 슬라이드 내 단락 들여쓰기 설정에 중점을 둡니다. Aspose.Slides for Java는 개발자가 Microsoft Office Automation에 의존하지 않고도 PowerPoint 프레젠테이션을 제작, 수정, 변환 및 관리할 수 있도록 하는 강력한 API 세트를 제공합니다.
## 필수 조건
시작하기 전에 다음 사항이 설정되어 있는지 확인하세요.
- 컴퓨터에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Aspose.Slides for Java 라이브러리가 다운로드되었습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).
- Java 프로그래밍 언어에 대한 기본적인 이해.
## 패키지 가져오기
먼저 Aspose.Slides 기능에 액세스하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
import java.io.File;
```
Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에서 문단 들여쓰기를 설정하는 단계별 프로세스를 살펴보겠습니다.
## 1단계: 프레젠테이션 개체 만들기
인스턴스화 `Presentation` 새로운 PowerPoint 프레젠테이션 작업을 시작하는 수업입니다.
```java
// 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 2단계: 슬라이드에 액세스
프레젠테이션에서 첫 번째 슬라이드를 가져옵니다. 필요에 따라 색인별로 다른 슬라이드를 조작할 수 있습니다.
```java
// 첫 번째 슬라이드를 받으세요
ISlide slide = pres.getSlides().get_Item(0);
```
## 3단계: 사각형 모양 추가
슬라이드에 직사각형 모양을 추가하면 들여쓰기된 문단이 포함된 텍스트가 들어갑니다.
```java
// 사각형 모양 추가
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## 4단계: 사각형에 텍스트 추가
사각형 모양 내에 텍스트 프레임을 만들고 텍스트 내용을 설정합니다.
```java
// 사각형에 TextFrame 추가
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## 5단계: 텍스트 자동 맞춤 설정
텍스트 자동 맞춤을 도형 경계에 맞게 설정합니다.
```java
// 모양에 맞게 텍스트를 설정하세요
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## 6단계: 문단 들여쓰기 조정
텍스트 프레임 내에서 각 문단에 접근하여 들여쓰기를 설정합니다.
```java
// TextFrame에서 첫 번째 문단을 가져와 들여쓰기를 설정합니다.
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// TextFrame에서 두 번째 문단을 가져와 들여쓰기를 설정합니다.
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
// TextFrame에서 세 번째 문단을 가져와 들여쓰기를 설정합니다.
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## 7단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.
```java
// 프레젠테이션을 디스크에 기록하세요
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## 결론
다음 단계를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에 단락 들여쓰기를 쉽게 설정할 수 있습니다. 이 기능을 사용하면 슬라이드 내 텍스트의 서식과 표현을 프로그래밍 방식으로 정밀하게 제어할 수 있습니다.

## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업하기 위한 강력한 라이브러리입니다.
### Java용 Aspose.Slides에 대한 문서는 어디에서 찾을 수 있나요?
문서를 찾을 수 있습니다 [여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides를 어떻게 다운로드할 수 있나요?
여기에서 다운로드할 수 있습니다 [여기](https://releases.aspose.com/slides/java/).
### Aspose.Slides for Java에 대한 무료 평가판이 있나요?
네, 무료 체험판을 받으실 수 있습니다. [여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디에서 받을 수 있나요?
커뮤니티 포럼에서 지원을 받을 수 있습니다. [여기](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
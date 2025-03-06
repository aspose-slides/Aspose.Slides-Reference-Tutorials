---
title: Java PowerPoint에서 단락 들여쓰기 설정
linktitle: Java PowerPoint에서 단락 들여쓰기 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 PowerPoint 슬라이드에서 단락 들여쓰기를 설정하는 방법을 알아보세요. 손쉽게 프레젠테이션 형식을 향상하세요.
weight: 16
url: /ko/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 단락 들여쓰기 설정

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하는 방법을 배웁니다. 특히 슬라이드 내 단락 들여쓰기 설정에 중점을 둘 것입니다. Aspose.Slides for Java는 개발자가 Microsoft Office 자동화에 의존하지 않고도 PowerPoint 프레젠테이션을 생성, 수정, 변환 및 관리할 수 있는 강력한 API 세트를 제공합니다.
## 전제 조건
시작하기 전에 다음이 설정되어 있는지 확인하세요.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Slides가 다운로드되었습니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/slides/java/).
- Java 프로그래밍 언어에 대한 기본 이해.
## 패키지 가져오기
먼저 Aspose.Slides 기능에 액세스하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
import java.io.File;
```
Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에서 단락 들여쓰기를 설정하는 단계별 프로세스를 살펴보겠습니다.
## 1단계: 프리젠테이션 개체 만들기
 인스턴스화`Presentation` 새로운 PowerPoint 프레젠테이션 작업을 시작하는 수업입니다.
```java
// 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 2단계: 슬라이드에 액세스
프레젠테이션에서 첫 번째 슬라이드를 검색합니다. 필요에 따라 색인별로 다양한 슬라이드를 조작할 수 있습니다.
```java
// 첫 번째 슬라이드 가져오기
ISlide slide = pres.getSlides().get_Item(0);
```
## 3단계: 직사각형 모양 추가
들여쓰기된 단락이 있는 텍스트를 포함하는 직사각형 모양을 슬라이드에 추가합니다.
```java
// 직사각형 모양 추가
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## 4단계: 직사각형에 텍스트 추가
직사각형 모양 안에 텍스트 프레임을 만들고 텍스트 내용을 설정합니다.
```java
// 직사각형에 TextFrame 추가
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## 5단계: 텍스트 자동 맞춤 설정
모양 경계 내에 맞게 텍스트 자동 맞춤을 설정합니다.
```java
// 도형에 맞게 텍스트 설정
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## 6단계: 단락 들여쓰기 조정
텍스트 프레임 내의 각 단락에 액세스하고 들여쓰기를 설정합니다.
```java
// TextFrame의 첫 번째 단락을 가져오고 들여쓰기를 설정합니다.
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// TextFrame에서 두 번째 단락을 가져오고 들여쓰기를 설정합니다.
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
//TextFrame에서 세 번째 단락을 가져오고 들여쓰기를 설정합니다.
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## 7단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.
```java
// 프리젠테이션을 디스크에 쓰기
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## 결론
다음 단계를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에서 단락 들여쓰기를 쉽게 설정할 수 있습니다. 이 기능을 사용하면 슬라이드 내 텍스트의 서식 및 표시를 프로그래밍 방식으로 정밀하게 제어할 수 있습니다.

## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션 작업을 위한 강력한 라이브러리입니다.
### Java용 Aspose.Slides에 대한 문서는 어디서 찾을 수 있나요?
 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides를 어떻게 다운로드할 수 있나요?
 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 커뮤니티 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

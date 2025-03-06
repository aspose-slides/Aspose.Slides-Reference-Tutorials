---
title: Java PowerPoint에서 위 첨자 및 아래 첨자 텍스트 추가
linktitle: Java PowerPoint에서 위 첨자 및 아래 첨자 텍스트 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에 위 첨자와 아래 첨자 텍스트를 추가하는 방법을 알아보세요. 슬라이드를 향상시키는 데 적합합니다.
weight: 13
url: /ko/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
매력적이고 유익한 PowerPoint 프레젠테이션을 만들려면 위 첨자 및 아래 첨자 텍스트와 같은 서식 지정 기능을 사용해야 하는 경우가 많습니다. 이 튜토리얼은 Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에 위 첨자와 아래 첨자 텍스트를 통합하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- Java 개발을 위해 설정된 IntelliJ IDEA 또는 Eclipse와 같은 IDE(통합 개발 환경)입니다.
- Java 프로그래밍 및 PowerPoint 프레젠테이션에 대한 기본적인 지식.

## 패키지 가져오기
먼저 Aspose.Slides for Java에서 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2단계: 슬라이드에 액세스
```java
// 첫 번째 슬라이드 가져오기
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3단계: 텍스트 상자 만들기
```java
// 텍스트 상자로 사용할 도형 만들기
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## 4단계: 위 첨자 텍스트 추가
```java
// 본문에 대한 단락 만들기
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// 위 첨자 텍스트 부분 만들기
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // 위 첨자에 대한 이스케이프 설정
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//텍스트 상자에 위 첨자와 함께 기본 단락을 추가합니다.
textFrame.getParagraphs().add(mainParagraph);
```
## 5단계: 아래 첨자 텍스트 추가
```java
// 아래 첨자 텍스트에 대한 다른 단락 만들기
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// 아래 첨자 텍스트 부분 만들기
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // 아래 첨자에 대한 이스케이프 설정
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// 텍스트 상자에 아래 첨자 단락 추가
textFrame.getParagraphs().add(subscriptParagraph);
```
## 6단계: 프레젠테이션 저장
```java
// 프레젠테이션 저장
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 위 첨자 및 아래 첨자 텍스트로 Java PowerPoint 프레젠테이션을 향상시키는 방법을 살펴보았습니다. 다음 단계를 따르면 콘텐츠를 효과적으로 전달하는 시각적으로 더욱 매력적이고 유익한 슬라이드를 만들 수 있습니다.

## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다.
### Aspose.Slides for Java에 대한 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 지원 및 토론을 원하시면 다음 사이트를 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

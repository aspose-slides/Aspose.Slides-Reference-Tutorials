---
"description": "Aspose.Slides를 사용하여 Java로 PowerPoint 프레젠테이션의 글꼴 높이를 조정하는 방법을 알아보세요. 슬라이드의 텍스트 서식을 손쉽게 개선해 보세요."
"linktitle": "Java를 사용하여 PowerPoint에서 로컬 글꼴 높이 값 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java를 사용하여 PowerPoint에서 로컬 글꼴 높이 값 설정"
"url": "/ko/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 PowerPoint에서 로컬 글꼴 높이 값 설정

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 다양한 레벨의 글꼴 높이를 조정하는 방법을 알아봅니다. 글꼴 크기 조절은 시각적으로 매력적이고 구조화된 프레젠테이션을 만드는 데 매우 중요합니다. 다양한 텍스트 요소의 글꼴 높이를 설정하는 방법을 단계별 예제를 통해 살펴보겠습니다.
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 Java Development Kit(JDK)가 설치되어 있습니다.
- Aspose.Slides for Java 라이브러리를 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).
- Java 프로그래밍과 PowerPoint 프레젠테이션에 대한 기본적인 이해
## 패키지 가져오기
Java 파일에 필요한 Aspose.Slides 패키지를 포함해야 합니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 개체 초기화
먼저, 새로운 PowerPoint 프레젠테이션 개체를 만듭니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 모양과 텍스트 프레임 추가
첫 번째 슬라이드에 텍스트 프레임이 있는 자동 모양을 추가합니다.
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 3단계: 텍스트 부분 만들기
다양한 글꼴 높이로 텍스트 부분 정의:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## 4단계: 글꼴 높이 설정
다양한 레벨에서 글꼴 높이를 설정합니다.
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## 5단계: 프레젠테이션 저장
수정된 프레젠테이션을 파일에 저장합니다.
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 글꼴 높이를 프로그래밍 방식으로 조정하는 방법을 보여주었습니다. 다양한 수준(프레젠테이션 전체, 단락, 부분)에서 글꼴 크기를 조정하여 프레젠테이션의 텍스트 서식을 정밀하게 제어할 수 있습니다.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작하기 위한 강력한 API입니다.
### Java용 Aspose.Slides에 대한 문서는 어디에서 찾을 수 있나요?
문서를 찾을 수 있습니다 [여기](https://reference.aspose.com/slides/java/).
### 구매하기 전에 Aspose.Slides for Java를 사용해 볼 수 있나요?
네, 무료 체험판을 받으실 수 있습니다. [여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어떻게 받을 수 있나요?
지원을 받으려면 다음을 방문하세요. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java 라이선스는 어디에서 구매할 수 있나요?
라이센스를 구매할 수 있습니다 [여기](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
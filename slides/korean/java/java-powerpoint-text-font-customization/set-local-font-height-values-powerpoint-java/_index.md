---
title: Java를 사용하여 PowerPoint에서 로컬 글꼴 높이 값 설정
linktitle: Java를 사용하여 PowerPoint에서 로컬 글꼴 높이 값 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 PowerPoint 프레젠테이션에서 글꼴 높이를 조정하는 방법을 알아보세요. 슬라이드의 텍스트 서식을 손쉽게 향상하세요.
weight: 17
url: /ko/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 PowerPoint에서 로컬 글꼴 높이 값 설정

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 내의 다양한 수준에서 글꼴 높이를 조작하는 방법을 배웁니다. 시각적으로 매력적이고 구조화된 프레젠테이션을 만들려면 글꼴 크기를 제어하는 것이 중요합니다. 다양한 텍스트 요소에 대해 글꼴 높이를 설정하는 방법을 설명하기 위해 단계별 예제를 살펴보겠습니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 설치된 JDK(Java Development Kit)
-  Aspose.Slides for Java 라이브러리. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/slides/java/).
- Java 프로그래밍 및 PowerPoint 프레젠테이션에 대한 기본 이해
## 패키지 가져오기
Java 파일에 필요한 Aspose.Slides 패키지를 포함했는지 확인하세요.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 개체 초기화
먼저 새 PowerPoint 프리젠테이션 개체를 만듭니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 도형 및 텍스트 프레임 추가
첫 번째 슬라이드에 텍스트 프레임이 있는 자동 모양을 추가합니다.
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 3단계: 텍스트 부분 만들기
다양한 글꼴 높이로 텍스트 부분을 정의합니다.
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## 4단계: 글꼴 높이 설정
다양한 수준에서 글꼴 높이를 설정합니다.
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
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 PowerPoint 슬라이드 내에서 글꼴 높이를 조정하는 방법을 보여주었습니다. 다양한 수준(프레젠테이션 전체, 단락 및 부분)에서 글꼴 크기를 조작하면 프레젠테이션의 텍스트 서식을 정밀하게 제어할 수 있습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하기 위한 강력한 API입니다.
### Java용 Aspose.Slides에 대한 문서는 어디서 찾을 수 있나요?
 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/slides/java/).
### 구매하기 전에 Java용 Aspose.Slides를 사용해 볼 수 있나요?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 지원을 받으려면 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java 라이선스는 어디서 구매할 수 있나요?
 라이센스를 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Java를 사용하여 PowerPoint에서 텍스트 프레임의 앵커 설정
linktitle: Java를 사용하여 PowerPoint에서 텍스트 프레임의 앵커 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 PowerPoint에서 텍스트 프레임 앵커를 설정하는 방법을 알아보세요. 프레젠테이션을 향상시키세요.
weight: 13
url: /ko/java/java-powerpoint-text-font-customization/set-anchor-text-frame-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Aspose.Slides의 도움으로 Java를 사용하여 PowerPoint 프레젠테이션에서 텍스트 프레임의 앵커를 설정하는 방법을 배웁니다. 텍스트 프레임을 고정하면 모양 내에서 텍스트의 위치와 동작을 정밀하게 제어할 수 있어 슬라이드가 시각적으로 매력적이고 효율적으로 구성됩니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 JDK(Java Development Kit)
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/)
- Java 프로그래밍 언어 및 객체지향 개념에 대한 기본 이해
## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 Aspose.Slides 라이브러리를 포함하세요.
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 1단계: 프로젝트 설정
선호하는 IDE(통합 개발 환경)에 Java 프로젝트가 설정되어 있는지 확인하세요. Aspose.Slides JAR 파일이 프로젝트의 빌드 경로에 추가되었는지 확인하세요.
## 2단계: 프리젠테이션 개체 만들기
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
그러면 새 PowerPoint 프리젠테이션 개체가 초기화됩니다.
## 3단계: 슬라이드에 액세스하고 도형 추가
```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
여기에서는 특정 좌표와 치수로 슬라이드에 직사각형 모양이 추가됩니다.
## 4단계: 도형에 텍스트 프레임 추가
```java
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAnchoringType(TextAnchorType.Bottom);
```
 직사각형 모양에 텍스트 프레임이 추가되고 고정 유형이 다음으로 설정됩니다.`Bottom`, 텍스트가 도형의 아래쪽에 고정되도록 합니다.
## 5단계: 텍스트 프레임에 텍스트 삽입
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
이렇게 하면 텍스트 프레임에 텍스트 내용이 추가되고 텍스트 색상을 검은색으로 설정하는 등의 서식이 적용됩니다.
## 6단계: 프레젠테이션 저장
```java
presentation.save(dataDir + "AnchorText_out.pptx", SaveFormat.Pptx);
```
마지막으로 수정된 프레젠테이션을 디스크의 지정된 위치에 저장합니다.

## 결론
Java를 사용하여 PowerPoint에서 텍스트 프레임의 앵커를 설정하는 것은 잘 구성된 프레젠테이션을 만드는 데 필수적입니다. 다음 단계를 따르고 Aspose.Slides for Java를 활용하면 모양 내 텍스트 위치 지정을 효율적으로 관리하여 슬라이드의 시각적 매력과 명확성을 향상시킬 수 있습니다.

## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java 개발자가 PowerPoint 프레젠테이션을 생성, 읽기, 조작 및 변환할 수 있는 강력한 라이브러리입니다.
### Java용 Aspose.Slides에 대한 설명서는 어디에서 찾을 수 있나요?
 문서에 액세스할 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 무료 평가판을 다운로드할 수 있습니다[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 지원 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/slides/11) 문의사항이나 도움이 필요하시면
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

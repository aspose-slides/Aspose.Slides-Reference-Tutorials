---
title: Java PowerPoint에서 텍스트 프레임 자동 맞춤 설정
linktitle: Java PowerPoint에서 텍스트 프레임 자동 맞춤 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java PowerPoint에서 텍스트 프레임 자동 맞춤을 설정하는 방법을 알아보세요. 손쉽게 동적 프레젠테이션을 만들어 보세요.
weight: 14
url: /ko/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
Java 애플리케이션 개발에서는 프로그래밍 방식으로 동적이고 시각적으로 매력적인 PowerPoint 프레젠테이션을 만드는 것이 일반적인 요구 사항입니다. Aspose.Slides for Java는 이를 손쉽게 달성할 수 있는 강력한 API 세트를 제공합니다. 한 가지 필수 기능은 텍스트 프레임의 자동 맞춤을 설정하여 수동으로 조정하지 않고도 텍스트가 모양 내에서 깔끔하게 조정되도록 하는 것입니다. 이 튜토리얼에서는 Java용 Aspose.Slides를 활용하여 PowerPoint 슬라이드의 텍스트 맞춤을 자동화하는 프로세스를 단계별로 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
- 시스템에 설치된 JDK(Java Development Kit)
- Java 프로젝트에서 다운로드 및 참조되는 Java 라이브러리용 Aspose.Slides
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE)
### 패키지 가져오기
먼저 Java 프로젝트에서 필요한 Aspose.Slides 클래스를 가져와야 합니다.
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 1단계: 새 프레젠테이션 만들기
슬라이드와 도형을 추가할 새 PowerPoint 프레젠테이션 인스턴스를 만드는 것부터 시작하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
```
## 2단계: 슬라이드에 액세스하여 도형 추가
자동 맞춤 텍스트가 포함된 도형을 추가하려는 프레젠테이션의 첫 번째 슬라이드에 액세스합니다.
```java
// 첫 번째 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3단계: 도형(직사각형) 추가
슬라이드의 특정 좌표 및 치수에 도형(사각형)을 추가합니다.
```java
// 직사각형 유형의 도형 추가
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## 4단계: 직사각형에 TextFrame 추가
직사각형 모양에 텍스트 프레임을 추가합니다.
```java
// 직사각형에 TextFrame 추가
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## 5단계: 텍스트 프레임 자동 맞춤 설정
모양 크기에 따라 텍스트를 조정하려면 텍스트 프레임의 자동 맞춤 속성을 설정합니다.
```java
// 텍스트 프레임에 액세스하기
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## 6단계: 텍스트 프레임에 텍스트 추가
모양 내의 텍스트 프레임에 텍스트 내용을 추가합니다.
```java
// 텍스트 프레임용 단락 개체 만들기
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// 단락에 대한 부분 개체 만들기
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## 7단계: 프레젠테이션 저장
자동 맞춤 텍스트 프레임을 사용하여 수정된 프레젠테이션을 저장합니다.
```java
// 프레젠테이션 저장
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션의 텍스트 프레임 자동 맞춤을 설정하는 방법을 배웠습니다. 다음 단계를 수행하면 도형 내의 텍스트 맞춤을 자동화하여 프로그래밍 방식으로 프레젠테이션의 가독성과 미적 특성을 향상시킬 수 있습니다.

## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 PowerPoint 프레젠테이션을 생성, 읽기, 조작 및 변환할 수 있는 강력한 Java API입니다.
### Java용 Aspose.Slides를 어떻게 다운로드하나요?
 Java용 Aspose.Slides를 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
### Java용 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 다음에서 Aspose.Slides for Java의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 문서는 어디서 찾을 수 있나요?
 Aspose.Slides for Java에 대한 자세한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 Aspose.Slides for Java에 대한 커뮤니티 및 전문 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

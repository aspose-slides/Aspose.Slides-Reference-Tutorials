---
title: Java를 사용하여 SmartArt에서 글머리 기호 채우기 형식 설정
linktitle: Java를 사용하여 SmartArt에서 글머리 기호 채우기 형식 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 SmartArt에서 글머리 기호 채우기 형식을 설정하는 방법을 알아보세요. 효율적인 프레젠테이션 조작을 위한 단계별 가이드입니다.
weight: 18
url: /ko/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
Java 프로그래밍 영역에서는 특히 SmartArt 요소를 다룰 때 프레젠테이션을 효율적으로 조작하는 것이 일반적인 요구 사항입니다. Aspose.Slides for Java는 프로그래밍 방식으로 프레젠테이션을 처리할 수 있는 다양한 기능을 제공하여 이러한 작업을 위한 강력한 도구로 등장합니다. 이 튜토리얼에서는 Aspose.Slides와 함께 Java를 사용하여 SmartArt에서 글머리 기호 채우기 형식을 설정하는 프로세스를 단계별로 살펴보겠습니다.
## 전제 조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
### JDK(자바 개발 키트)
 시스템에 JDK가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 설치 지침을 따르십시오.
### Java용 Aspose.Slides
 다음에서 Java용 Aspose.Slides를 다운로드하여 설치하세요.[다운로드 링크](https://releases.aspose.com/slides/java/). 특정 운영 체제에 대한 설명서에 제공된 설치 지침을 따르십시오.

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Aspose.Slides와 함께 Java를 사용하여 SmartArt에서 글머리 기호 채우기 형식을 설정하는 방법을 명확하게 이해하기 위해 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프리젠테이션 개체 만들기
```java
Presentation presentation = new Presentation();
```
먼저 PowerPoint 프레젠테이션을 나타내는 Presentation 클래스의 새 인스턴스를 만듭니다.
## 2단계: SmartArt 추가
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
다음으로 슬라이드에 SmartArt 도형을 추가합니다. 이 코드 줄은 지정된 크기와 레이아웃을 사용하여 새 SmartArt 모양을 초기화합니다.
## 3단계: SmartArt 노드에 액세스
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
이제 SmartArt 모양 내의 첫 번째 노드(또는 원하는 노드)에 액세스하여 해당 속성을 수정합니다.
## 4단계: 글머리 기호 채우기 형식 설정
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
여기서는 글머리 기호 채우기 형식이 지원되는지 확인합니다. 그렇다면 이미지 파일을 로드하고 이를 SmartArt 노드의 글머리 기호 채우기로 설정합니다.
## 5단계: 프레젠테이션 저장
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
마지막으로 수정된 프레젠테이션을 지정된 위치에 저장합니다.

## 결론
축하해요! Aspose.Slides와 함께 Java를 사용하여 SmartArt에서 글머리 기호 채우기 형식을 설정하는 방법을 성공적으로 배웠습니다. 이 기능은 Java 애플리케이션에서 역동적이고 시각적으로 매력적인 프레젠테이션의 가능성을 열어줍니다.
## FAQ
### Aspose.Slides for Java를 사용하여 처음부터 프레젠테이션을 만들 수 있나요?
전적으로! Aspose.Slides는 코드를 통해 프레젠테이션을 완전히 생성, 수정 및 조작할 수 있는 포괄적인 API를 제공합니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
예, Aspose.Slides는 다양한 버전의 Microsoft PowerPoint와의 호환성을 보장하여 작업 흐름에 원활하게 통합할 수 있습니다.
### 글머리 기호 채우기 형식 외에 SmartArt 요소를 사용자 지정할 수 있나요?
실제로 Aspose.Slides를 사용하면 레이아웃, 스타일, 콘텐츠 등을 포함하여 SmartArt 모양의 모든 측면을 사용자 지정할 수 있습니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 무료 평가판을 통해 Aspose.Slides의 기능을 탐색할 수 있습니다. 간단히 다운로드하세요.[웹사이트](https://releases.aspose.com/slides/java/) 탐색을 시작하세요.
### Java용 Aspose.Slides에 대한 지원은 어디서 찾을 수 있나요?
 질문이나 도움이 필요하면 Aspose.Slides 포럼을 방문하세요.[이 링크](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

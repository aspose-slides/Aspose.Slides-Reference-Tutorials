---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 상대적 크기 조절이 가능한 사진 프레임을 추가하는 방법을 배우고 시각적 콘텐츠를 향상시켜 보세요."
"linktitle": "PowerPoint에서 상대적 크기 조절 높이 그림 프레임 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 상대적 크기 조절 높이 그림 프레임 추가"
"url": "/ko/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 상대적 크기 조절 높이 그림 프레임 추가

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 상대적 크기 조절 높이가 적용된 사진 프레임을 추가하는 방법을 알아봅니다.
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
2. Java 라이브러리용 Aspose.Slides를 다운로드하여 Java 프로젝트에 추가했습니다.

## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 프로젝트 설정
먼저, 프로젝트에 대한 디렉토리가 설정되어 있고 Java 환경이 올바르게 구성되어 있는지 확인하세요.
## 2단계: 프레젠테이션 객체 인스턴스화
Aspose.Slides를 사용하여 새로운 프레젠테이션 객체를 만듭니다.
```java
Presentation presentation = new Presentation();
```
## 3단계: 추가할 이미지 로드
프레젠테이션에 추가할 이미지를 로드하세요.
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## 4단계: 슬라이드에 그림 프레임 추가
프레젠테이션의 슬라이드에 그림 프레임을 추가합니다.
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## 5단계: 상대적 크기 조정 너비 및 높이 설정
그림 프레임의 상대적 크기 조절 너비와 높이를 설정합니다.
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## 6단계: 프레젠테이션 저장
추가된 사진 프레임으로 프레젠테이션을 저장합니다.
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## 결론
다음 단계를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 상대적인 크기 조절 높이를 가진 그림 프레임을 쉽게 추가할 수 있습니다. 원하는 이미지 모양을 얻으려면 다양한 크기 조절 값을 적용해 보세요.

## 자주 묻는 질문
### 이 방법을 사용하여 하나의 슬라이드에 여러 개의 사진 프레임을 추가할 수 있나요?
네, 각 이미지에 대해 이 과정을 반복하면 슬라이드에 여러 개의 사진 프레임을 추가할 수 있습니다.
### Aspose.Slides for Java는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for Java는 다양한 버전의 PowerPoint와 호환되므로 프레젠테이션을 만들 때 유연성이 보장됩니다.
### 사진 프레임의 위치와 크기를 사용자 지정할 수 있나요?
물론입니다. 위치 및 크기 매개변수를 조정할 수 있습니다. `addPictureFrame` 귀하의 요구 사항에 맞는 방법을 선택하세요.
### Aspose.Slides for Java는 JPEG 외에 다른 이미지 형식을 지원합니까?
네, Aspose.Slides for Java는 PNG, GIF, BMP 등 다양한 이미지 형식을 지원합니다.
### Aspose.Slides 사용자를 위한 커뮤니티 포럼이나 지원 채널이 있나요?
네, 라이브러리에 관한 질문, 토론 또는 지원이 있으면 Aspose.Slides 포럼을 방문하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
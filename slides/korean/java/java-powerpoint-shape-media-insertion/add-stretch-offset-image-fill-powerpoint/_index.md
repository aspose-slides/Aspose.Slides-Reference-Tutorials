---
title: PowerPoint에서 이미지 채우기를 위한 스트레치 오프셋 추가
linktitle: PowerPoint에서 이미지 채우기를 위한 스트레치 오프셋 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 이미지 채우기를 위한 스트레치 오프셋을 추가하는 방법을 알아보세요. 단계별 튜토리얼이 포함되어 있습니다.
type: docs
weight: 16
url: /ko/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---
## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 이미지 채우기를 위한 스트레치 오프셋을 추가하는 방법을 배웁니다. 이 기능을 사용하면 슬라이드 내의 이미지를 조작하여 이미지 모양을 더 효과적으로 제어할 수 있습니다.
## 전제 조건
시작하기 전에 다음 사항을 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2. Java 라이브러리용 Aspose.Slides가 Java 프로젝트에 다운로드되어 설정되었습니다.
## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 문서 디렉토리 설정
PowerPoint 문서가 있는 디렉터리를 정의합니다.
```java
String dataDir = "Your Document Directory";
```
## 2단계: 프리젠테이션 개체 만들기
PowerPoint 파일을 나타내기 위해 Presentation 클래스를 인스턴스화합니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드에 이미지 추가
첫 번째 슬라이드를 검색하고 여기에 이미지를 추가합니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## 4단계: 액자 추가
이미지와 동일한 크기의 사진 프레임을 만듭니다.
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## 5단계: 프레젠테이션 저장
수정된 PowerPoint 파일을 저장합니다.
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint에서 이미지 채우기를 위한 스트레치 오프셋을 추가하는 방법을 성공적으로 배웠습니다. 이 기능은 사용자 정의 이미지로 프레젠테이션을 향상시킬 수 있는 가능성의 세계를 열어줍니다.
## FAQ
### 이 방법을 사용하여 프레젠테이션의 특정 슬라이드에 이미지를 추가할 수 있나요?
예, 특정 슬라이드를 대상으로 슬라이드 개체를 검색할 때 슬라이드 인덱스를 지정할 수 있습니다.
### Aspose.Slides for Java는 JPEG 외에 다른 이미지 형식을 지원합니까?
예, Aspose.Slides for Java는 PNG, GIF, BMP 등 다양한 이미지 형식을 지원합니다.
### 이 방법을 사용하여 추가할 수 있는 이미지 크기에 제한이 있나요?
Aspose.Slides for Java는 다양한 크기의 이미지를 처리할 수 있지만 프레젠테이션 성능을 향상하려면 이미지를 최적화하는 것이 좋습니다.
### 슬라이드에 이미지를 추가한 후 이미지에 추가 효과나 변형을 적용할 수 있나요?
예, Aspose.Slides for Java의 광범위한 API를 사용하여 이미지에 광범위한 효과와 변형을 적용할 수 있습니다.
### Aspose.Slides for Java에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) 자세한 가이드를 확인하고[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지역 사회 지원을 위해.
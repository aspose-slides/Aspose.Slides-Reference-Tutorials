---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 이미지 채우기에 스트레치 오프셋을 추가하는 방법을 알아보세요. 단계별 튜토리얼이 포함되어 있습니다."
"linktitle": "PowerPoint에서 이미지 채우기에 스트레치 오프셋 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 이미지 채우기에 스트레치 오프셋 추가"
"url": "/ko/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 이미지 채우기에 스트레치 오프셋 추가

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 이미지 채우기에 스트레치 오프셋을 추가하는 방법을 알아봅니다. 이 기능을 사용하면 슬라이드 내 이미지를 조작하여 이미지 모양을 더욱 세밀하게 제어할 수 있습니다.
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
2. Java 프로젝트에 Aspose.Slides for Java 라이브러리를 다운로드하여 설치합니다.
## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 문서 디렉터리 설정
PowerPoint 문서가 있는 디렉토리를 정의하세요.
```java
String dataDir = "Your Document Directory";
```
## 2단계: 프레젠테이션 개체 만들기
PowerPoint 파일을 나타내기 위해 Presentation 클래스를 인스턴스화합니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드에 이미지 추가
첫 번째 슬라이드를 검색하여 이미지를 추가합니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## 4단계: 사진 프레임 추가
이미지와 동일한 크기의 사진 프레임을 만드세요:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## 5단계: 프레젠테이션 저장
수정된 PowerPoint 파일을 저장합니다.
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## 결론
축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint에서 이미지 채우기에 스트레치 오프셋을 추가하는 방법을 성공적으로 익혔습니다. 이 기능을 사용하면 사용자 지정 이미지로 프레젠테이션을 더욱 풍성하게 만들 수 있는 무한한 가능성이 열립니다.
## 자주 묻는 질문
### 이 방법을 사용하면 프레젠테이션의 특정 슬라이드에 이미지를 추가할 수 있나요?
네, 슬라이드 객체를 검색할 때 슬라이드 인덱스를 지정하여 특정 슬라이드를 대상으로 지정할 수 있습니다.
### Aspose.Slides for Java는 JPEG 외에 다른 이미지 형식을 지원합니까?
네, Aspose.Slides for Java는 PNG, GIF, BMP 등 다양한 이미지 형식을 지원합니다.
### 이 방법을 사용하여 추가할 수 있는 이미지 크기에 제한이 있나요?
Java용 Aspose.Slides는 다양한 크기의 이미지를 처리할 수 있지만, 프레젠테이션에서 더 나은 성능을 위해 이미지를 최적화하는 것이 좋습니다.
### 슬라이드에 이미지를 추가한 후, 추가 효과나 변형을 적용할 수 있나요?
네, Aspose.Slides for Java의 광범위한 API를 사용하여 다양한 효과와 변형을 이미지에 적용할 수 있습니다.
### Java용 Aspose.Slides에 대한 추가 리소스와 지원은 어디에서 찾을 수 있나요?
방문할 수 있습니다 [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 자세한 가이드를 보려면 다음을 탐색하세요. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지역사회 지원을 위해.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
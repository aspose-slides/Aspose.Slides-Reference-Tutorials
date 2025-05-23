---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 그림을 채우는 방법을 알아보세요. 시각적인 매력을 손쉽게 높여 보세요."
"linktitle": "PowerPoint에서 그림으로 도형 채우기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 그림으로 도형 채우기"
"url": "/ko/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 그림으로 도형 채우기

## 소개
파워포인트 프레젠테이션은 매력을 더하고 정보를 효과적으로 전달하기 위해 이미지로 채워진 도형과 같은 시각적 요소가 필요한 경우가 많습니다. Aspose.Slides for Java는 이러한 작업을 원활하게 수행할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 도형에 그림을 채우는 방법을 단계별로 살펴보겠습니다.
## 필수 조건
시작하기에 앞서 다음 사항이 있는지 확인하세요.
1. 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
2. Aspose.Slides for Java 라이브러리가 다운로드되었습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).
3. Java 프로그래밍에 대한 기본 지식.
## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 프로젝트 디렉토리 설정
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
교체를 확인하세요 `"Your Document Directory"` 프로젝트 디렉토리 경로를 포함합니다.
## 2단계: 프레젠테이션 만들기
```java
Presentation pres = new Presentation();
```
인스턴스화 `Presentation` 새로운 PowerPoint 프레젠테이션을 만드는 수업입니다.
## 3단계: 슬라이드 및 도형 추가
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
프레젠테이션에 슬라이드를 추가하고 그 위에 사각형 모양을 만듭니다.
## 4단계: 채우기 유형을 그림으로 설정
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
도형의 채우기 유형을 그림으로 설정합니다.
## 5단계: 그림 채우기 모드 설정
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
도형의 그림 채우기 모드를 설정합니다.
## 6단계: 그림 설정
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
이미지를 로드하여 모양의 채우기로 설정합니다.
## 7단계: 프레젠테이션 저장
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
수정된 프레젠테이션을 파일에 저장합니다.

## 결론
Aspose.Slides for Java를 사용하면 PowerPoint 프레젠테이션에서 도형에 그림을 채우는 작업이 훨씬 간편해집니다. 이 튜토리얼에 설명된 단계를 따라 하면 시각적으로 매력적인 요소로 프레젠테이션을 쉽게 꾸밀 수 있습니다.

## 자주 묻는 질문
### Aspose.Slides for Java를 사용하여 다양한 모양을 그림으로 채울 수 있나요?
네, Aspose.Slides for Java는 다양한 모양에 그림을 채우는 기능을 지원하여 디자인의 유연성을 제공합니다.
### Aspose.Slides for Java는 모든 버전의 PowerPoint와 호환됩니까?
Java용 Aspose.Slides는 PowerPoint 97 이상과 호환되는 프레젠테이션을 생성하여 광범위한 호환성을 보장합니다.
### 모양 내의 이미지 크기를 어떻게 조절할 수 있나요?
채우기로 설정하기 전에 도형의 크기를 조정하거나 이미지의 크기를 적절히 조정하여 도형 내 이미지의 크기를 조정할 수 있습니다.
### 도형 채우기에 지원되는 이미지 형식에 제한이 있나요?
Aspose.Slides for Java는 JPEG, PNG, GIF, BMP, TIFF 등 다양한 이미지 형식을 지원합니다.
### 채워진 모양에 효과를 적용할 수 있나요?
네, Java용 Aspose.Slides는 채워진 모양에 그림자, 반사, 3D 회전 등 다양한 효과를 적용하는 포괄적인 API를 제공합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
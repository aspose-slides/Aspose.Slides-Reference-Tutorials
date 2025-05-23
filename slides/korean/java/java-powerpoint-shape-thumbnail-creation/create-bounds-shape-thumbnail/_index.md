---
"description": "Aspose.Slides for Java를 사용하여 경계가 있는 도형 썸네일을 만드는 방법을 알아보세요. 이 단계별 튜토리얼은 제작 과정을 안내합니다."
"linktitle": "경계 모양 썸네일 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "경계 모양 썸네일 만들기"
"url": "/ko/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 경계 모양 썸네일 만들기

## 소개
Aspose.Slides for Java는 Java 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 제작, 조작 및 변환할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 경계가 있는 도형의 썸네일 이미지를 만드는 방법을 알아봅니다.
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
2. Aspose.Slides for Java 라이브러리가 다운로드되어 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
Java 코드에서 필요한 패키지를 가져왔는지 확인하세요.
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 프로젝트 설정
원하는 IDE에서 새로운 Java 프로젝트를 만들고 Java 라이브러리용 Aspose.Slides를 프로젝트 종속성에 추가합니다.
## 2단계: 프레젠테이션 개체 인스턴스화
인스턴스화 `Presentation` PowerPoint 프레젠테이션 파일의 경로를 제공하여 개체를 만듭니다.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## 3단계: 경계 모양 축소판 만들기
이제 프레젠테이션의 경계가 있는 모양의 썸네일 이미지를 만들어 보겠습니다.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 경계가 있는 도형의 썸네일 이미지를 만드는 방법을 알아보았습니다. 다음 단계를 따라 하면 PowerPoint 프레젠테이션에서 도형의 썸네일을 프로그래밍 방식으로 쉽게 생성할 수 있습니다.
## 자주 묻는 질문
### 슬라이드 내 특정 모양에 대한 축소판 그림을 만들 수 있나요?
네, Aspose.Slides for Java를 사용하여 슬라이드 내의 개별 모양에 접근하고 해당 모양에 대한 축소판 그림을 생성할 수 있습니다.
### Aspose.Slides for Java는 모든 버전의 PowerPoint 파일과 호환됩니까?
Aspose.Slides for Java는 PPT, PPTX, PPS, PPSX 등 다양한 PowerPoint 파일 형식을 지원합니다.
### 생성된 썸네일 이미지의 모양을 사용자 정의할 수 있나요?
네, 요구 사항에 맞게 크기, 품질 등 썸네일 이미지 속성을 조정할 수 있습니다.
### Java용 Aspose.Slides는 썸네일 생성 외에 다른 기능을 지원합니까?
네, Aspose.Slides for Java는 슬라이드 조작, 텍스트 추출, 차트 생성 등 PowerPoint 프레젠테이션 작업에 필요한 광범위한 기능을 제공합니다.
### Java용 Aspose.Slides의 평가판이 있나요?
네, 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
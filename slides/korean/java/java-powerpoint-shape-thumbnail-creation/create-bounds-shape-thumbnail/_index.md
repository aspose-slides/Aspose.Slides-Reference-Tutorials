---
title: 경계 모양 축소판 만들기
linktitle: 경계 모양 축소판 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 경계가 있는 모양 축소판을 만드는 방법을 알아보세요. 이 단계별 튜토리얼은 프로세스를 안내합니다.
weight: 10
url: /ko/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 경계 모양 축소판 만들기

## 소개
Aspose.Slides for Java는 Java 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 경계가 있는 모양의 썸네일 이미지를 만드는 방법을 알아봅니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Java 라이브러리용 Aspose.Slides가 다운로드되어 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
Java 코드에 필요한 패키지를 가져왔는지 확인하세요.
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 프로젝트 설정
원하는 IDE에서 새 Java 프로젝트를 만들고 프로젝트의 종속성에 Aspose.Slides for Java 라이브러리를 추가하세요.
## 2단계: 프레젠테이션 개체 인스턴스화
 인스턴스화`Presentation` PowerPoint 프리젠테이션 파일의 경로를 제공하여 개체를 만듭니다.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## 3단계: 경계 모양 썸네일 만들기
이제 프레젠테이션에서 경계가 있는 모양의 축소판 이미지를 만들어 보겠습니다.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 경계가 있는 모양의 썸네일 이미지를 만드는 방법을 배웠습니다. 다음 단계를 수행하면 PowerPoint 프레젠테이션에서 프로그래밍 방식으로 모양의 축소판을 쉽게 생성할 수 있습니다.
## FAQ
### 슬라이드 내의 특정 도형에 대한 축소판을 만들 수 있나요?
예, Aspose.Slides for Java를 사용하여 슬라이드 내의 개별 모양에 액세스하고 이에 대한 썸네일을 생성할 수 있습니다.
### Aspose.Slides for Java는 모든 버전의 PowerPoint 파일과 호환됩니까?
Aspose.Slides for Java는 PPT, PPTX, PPS, PPSX 등을 포함한 다양한 PowerPoint 파일 형식을 지원합니다.
### 생성된 썸네일 이미지의 모양을 사용자 정의할 수 있나요?
예. 요구 사항에 따라 크기, 품질 등 축소판 이미지의 속성을 조정할 수 있습니다.
### Aspose.Slides for Java는 썸네일 생성 외에 다른 기능을 지원합니까?
예, Aspose.Slides for Java는 슬라이드 조작, 텍스트 추출, 차트 생성을 포함하여 PowerPoint 프레젠테이션 작업을 위한 광범위한 기능을 제공합니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

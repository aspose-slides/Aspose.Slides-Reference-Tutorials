---
title: PowerPoint에서 모양 축소판 만들기
linktitle: PowerPoint에서 모양 축소판 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 모양 축소판을 생성하는 방법을 알아보세요. 단계별 가이드가 제공됩니다.
weight: 14
url: /ko/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 모양 축소판을 만드는 방법을 살펴보겠습니다. Aspose.Slides는 개발자가 프로그래밍 방식으로 PowerPoint 파일을 작업할 수 있도록 지원하는 강력한 라이브러리로, 모양 축소판 생성을 포함한 다양한 작업을 자동화할 수 있습니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Slides가 프로젝트에 다운로드되어 설정되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
먼저 Aspose.Slides의 기능을 활용하려면 Java 코드에 필요한 패키지를 가져와야 합니다. Java 파일 시작 부분에 다음 가져오기 문을 포함합니다.
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 문서 디렉터리 정의
```java
String dataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` PowerPoint 파일이 포함된 디렉터리의 경로를 사용하세요.
## 2단계: 프레젠테이션 개체 인스턴스화
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 새 인스턴스를 생성합니다.`Presentation` 클래스를 사용하여 PowerPoint 파일의 경로를 매개변수로 전달합니다.
## 3단계: 모양 축소판 생성
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
프레젠테이션의 첫 번째 슬라이드에서 원하는 모양의 축소판을 검색합니다.
## 4단계: 썸네일 이미지 저장
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
생성된 썸네일 이미지를 지정된 파일 이름으로 PNG 형식으로 디스크에 저장합니다.

## 결론
결론적으로 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 모양 축소판을 만드는 방법을 보여주었습니다. 단계별 가이드를 따르고 제공된 코드 조각을 활용하면 프로그래밍 방식으로 모양 축소판을 효율적으로 생성할 수 있습니다.

## FAQ
### 프레젠테이션의 모든 슬라이드에 있는 모양의 축소판을 만들 수 있나요?
예, 슬라이드 인덱스를 적절하게 조정하여 모든 슬라이드의 대상 모양에 맞게 코드를 수정할 수 있습니다.
### Aspose.Slides는 썸네일 저장을 위해 다른 이미지 형식을 지원합니까?
예, PNG 외에도 Aspose.Slides는 JPEG, GIF, BMP와 같은 다양한 이미지 형식으로 썸네일 저장을 지원합니다.
### Aspose.Slides는 상업용으로 적합합니까?
 예, Aspose.Slides는 기업 및 조직을 위한 상용 라이선스를 제공합니다. 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### 구매하기 전에 Aspose.Slides를 사용해 볼 수 있나요?
 전적으로! Aspose.Slides의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/) 그 특징과 능력을 평가합니다.
### Aspose.Slides에 대한 지원은 어디서 찾을 수 있나요?
 Aspose.Slides에 대해 질문이 있거나 도움이 필요하면 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지원을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

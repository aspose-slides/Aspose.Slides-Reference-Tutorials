---
"description": "Aspose.Slides를 사용하여 Java로 SmartArt 자식 노트 축소판을 만드는 방법을 배우고, PowerPoint 프레젠테이션을 손쉽게 향상시켜 보세요."
"linktitle": "SmartArt 자식 노트 썸네일 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "SmartArt 자식 노트 썸네일 만들기"
"url": "/ko/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# SmartArt 자식 노트 썸네일 만들기

## 소개
이 튜토리얼에서는 Aspose.Slides를 사용하여 Java에서 SmartArt 하위 노트 썸네일을 만드는 방법을 살펴보겠습니다. Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업하여 슬라이드를 쉽게 만들고, 수정하고, 조작할 수 있도록 하는 강력한 Java API입니다.
## 필수 조건
시작하기에 앞서 다음 사항이 있는지 확인하세요.
1. 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
2. 프로젝트에 다운로드하고 구성한 Aspose.Slides for Java 라이브러리를 다음 위치에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
Java 클래스에 필요한 패키지를 가져오는지 확인하세요.
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 프로젝트 설정
Aspose.Slides 라이브러리를 사용하여 Java 프로젝트를 설정하고 구성했는지 확인하세요.
## 2단계: 프레젠테이션 만들기
인스턴스화 `Presentation` PPTX 파일을 나타내는 클래스:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 3단계: SmartArt 추가
프레젠테이션 슬라이드에 SmartArt를 추가하세요.
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## 4단계: 노드 참조 얻기
인덱스를 사용하여 노드의 참조를 얻습니다.
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## 5단계: 썸네일 가져오기
SmartArt 노드의 썸네일 이미지를 검색합니다.
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## 6단계: 썸네일 저장
썸네일 이미지를 파일에 저장합니다.
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
프레젠테이션의 각 SmartArt 노드에 대해 필요에 따라 이 단계를 반복합니다.

## 결론
이 튜토리얼에서는 Aspose.Slides를 사용하여 Java에서 SmartArt 하위 노트 썸네일을 만드는 방법을 알아보았습니다. 이 지식을 바탕으로 시각적으로 매력적인 요소를 쉽게 추가하여 PowerPoint 프레젠테이션을 프로그래밍 방식으로 향상시킬 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides를 사용하여 기존 PowerPoint 파일을 조작할 수 있나요?
네, Aspose.Slides를 사용하면 기존 PowerPoint 파일을 수정할 수 있습니다. 여기에는 슬라이드와 그 내용을 추가, 삭제, 편집하는 것이 포함됩니다.
### Aspose.Slides는 슬라이드를 다양한 파일 형식으로 내보내는 것을 지원합니까?
물론입니다! Aspose.Slides는 PDF, 이미지, HTML 등 다양한 형식으로 슬라이드를 내보낼 수 있도록 지원합니다.
### Aspose.Slides는 기업 수준의 PowerPoint 자동화에 적합합니까?
네, Aspose.Slides는 엔터프라이즈 수준의 PowerPoint 자동화 작업을 효율적이고 안정적으로 처리하도록 설계되었습니다.
### Aspose.Slides를 사용하여 복잡한 SmartArt 다이어그램을 프로그래밍 방식으로 만들 수 있나요?
물론입니다! Aspose.Slides는 다양한 복잡성의 SmartArt 다이어그램을 만들고 조작할 수 있는 포괄적인 지원을 제공합니다.
### Aspose.Slides는 개발자에게 기술 지원을 제공합니까?
예, Aspose.Slides는 개발자를 위한 전담 기술 지원을 제공합니다. [법정](https://forum.aspose.com/c/slides/11) 및 기타 채널.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
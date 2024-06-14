---
title: 배율 축소판 만들기
linktitle: 배율 축소판 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java에서 배율 축소판을 만드는 방법을 알아보세요. 단계별 지침이 포함된 따라하기 쉬운 가이드입니다.
type: docs
weight: 12
url: /ko/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 스케일링 팩터 썸네일을 생성하는 과정을 안내합니다. 원하는 결과를 얻으려면 다음 단계별 지침을 따르십시오.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
- Java 라이브러리용 Aspose.Slides가 Java 프로젝트에 다운로드되어 설정되었습니다.
- Java 프로그래밍 언어에 대한 기본 이해.

## 패키지 가져오기
먼저 Java 코드에서 Aspose.Slides 작업에 필요한 필수 패키지를 가져옵니다. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

이제 제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉터리 설정
PowerPoint 프레젠테이션 파일이 있는 문서 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` 실제 문서 디렉토리의 경로로.
## 2단계: 프레젠테이션 개체 인스턴스화
PowerPoint 프레젠테이션 파일을 나타내는 Presentation 클래스의 인스턴스를 만듭니다.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 반드시 교체하세요`"HelloWorld.pptx"` PowerPoint 프레젠테이션 파일의 이름으로.
## 3단계: 실제 크기 이미지 생성
프레젠테이션에서 원하는 슬라이드의 전체 크기 이미지를 생성합니다.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
이 코드는 프레젠테이션의 첫 번째 슬라이드에서 첫 번째 도형의 축소판을 검색합니다.
## 4단계: 이미지 저장
생성된 이미지를 PNG 형식으로 디스크에 저장합니다.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 반드시 교체하세요`"Scaling Factor Thumbnail_out.png"` 원하는 출력 파일 이름으로.

## 결론
결론적으로, Aspose.Slides for Java를 사용하여 스케일링 팩터 썸네일을 성공적으로 생성했습니다. 제공된 단계를 따르면 이 기능을 Java 애플리케이션에 쉽게 통합할 수 있습니다.
## FAQ
### Java IDE에서 Aspose.Slides for Java를 사용할 수 있나요?
예, Aspose.Slides for Java는 Eclipse, IntelliJ IDEA 또는 NetBeans와 같은 모든 Java 통합 개발 환경(IDE)과 함께 사용할 수 있습니다.
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
 예, 다음 사이트를 방문하면 Aspose.Slides for Java의 무료 평가판을 이용할 수 있습니다.[웹사이트](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디서 찾을 수 있나요?
 Java용 Aspose.Slides에 대한 지원은 다음에서 찾을 수 있습니다.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### Java용 Aspose.Slides를 어떻게 구매할 수 있나요?
 Java용 Aspose.Slides를 다음에서 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
### Aspose.Slides for Java를 사용하려면 임시 라이선스가 필요합니까?
 네, 임시 면허는 다음 기관에서 받으실 수 있습니다.[임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/).
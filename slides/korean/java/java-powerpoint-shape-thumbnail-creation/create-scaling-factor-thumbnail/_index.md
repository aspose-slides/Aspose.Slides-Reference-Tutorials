---
"description": "Aspose.Slides for Java를 사용하여 Java에서 배율 썸네일을 만드는 방법을 알아보세요. 단계별 설명이 포함된 따라 하기 쉬운 가이드입니다."
"linktitle": "스케일링 인자 썸네일 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "스케일링 인자 썸네일 만들기"
"url": "/ko/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 스케일링 인자 썸네일 만들기

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 배율 썸네일을 만드는 과정을 안내합니다. 원하는 결과를 얻으려면 다음 단계별 지침을 따르세요.
## 필수 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Java 프로젝트에 Aspose.Slides for Java 라이브러리를 다운로드하여 설치합니다.
- Java 프로그래밍 언어에 대한 기본적인 이해.

## 패키지 가져오기
먼저, Java 코드에서 Aspose.Slides 작업에 필요한 패키지를 가져옵니다. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

이제 제공된 예를 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉터리 설정
PowerPoint 프레젠테이션 파일이 있는 문서 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` 실제 문서 디렉토리 경로를 사용합니다.
## 2단계: 프레젠테이션 개체 인스턴스화
PowerPoint 프레젠테이션 파일을 나타내기 위해 Presentation 클래스의 인스턴스를 생성합니다.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
교체를 확인하세요 `"HelloWorld.pptx"` PowerPoint 프레젠테이션 파일의 이름을 입력합니다.
## 3단계: 전체 크기 이미지 만들기
프레젠테이션에서 원하는 슬라이드의 전체 크기 이미지를 생성합니다.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
이 코드는 프레젠테이션의 첫 번째 슬라이드에 있는 첫 번째 모양의 썸네일을 검색합니다.
## 4단계: 이미지 저장
생성된 이미지를 PNG 형식으로 디스크에 저장합니다.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
교체를 확인하세요 `"Scaling Factor Thumbnail_out.png"` 원하는 출력 파일 이름을 입력합니다.

## 결론
결론적으로, Aspose.Slides for Java를 사용하여 배율 조정 썸네일을 성공적으로 만들었습니다. 제공된 단계에 따라 이 기능을 Java 애플리케이션에 쉽게 통합할 수 있습니다.
## 자주 묻는 질문
### 모든 Java IDE에서 Aspose.Slides for Java를 사용할 수 있나요?
네, Aspose.Slides for Java는 Eclipse, IntelliJ IDEA, NetBeans 등 모든 Java 통합 개발 환경(IDE)과 함께 사용할 수 있습니다.
### Aspose.Slides for Java에 대한 무료 평가판이 있나요?
예, Aspose.Slides for Java의 무료 평가판을 이용하려면 다음을 방문하세요. [웹사이트](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디에서 찾을 수 있나요?
Java용 Aspose.Slides에 대한 지원은 다음에서 찾을 수 있습니다. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### Java용 Aspose.Slides를 어떻게 구매할 수 있나요?
Java용 Aspose.Slides를 다음에서 구매할 수 있습니다. [구매 페이지](https://purchase.aspose.com/buy).
### Java용 Aspose.Slides를 사용하려면 임시 라이선스가 필요합니까?
네, 임시면허를 취득할 수 있습니다. [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
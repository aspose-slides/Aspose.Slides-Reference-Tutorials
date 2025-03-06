---
title: PowerPoint에서 확대/축소 프레임 만들기
linktitle: PowerPoint에서 확대/축소 프레임 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 매력적인 확대/축소 프레임을 만드는 방법을 알아보세요. 프레젠테이션에 대화형 요소를 추가하려면 가이드를 따르세요.
weight: 17
url: /ko/java/java-powerpoint-shape-thumbnail-creation/create-zoom-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
매력적인 PowerPoint 프레젠테이션을 만드는 것은 예술이며 때로는 아주 작은 추가 사항이 큰 차이를 만들 수 있습니다. 이러한 기능 중 하나는 특정 슬라이드나 이미지를 확대하여 역동적이고 대화형 프레젠테이션을 만들 수 있는 줌 프레임(Zoom Frame)입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint에서 확대/축소 프레임을 만드는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE).
- Java 프로그래밍에 대한 기본 지식.
## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져와야 합니다. 이러한 가져오기는 이 튜토리얼에 필요한 Aspose.Slides 기능에 대한 액세스를 제공합니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## 1단계: 프레젠테이션 설정
먼저 새 프리젠테이션을 만들고 슬라이드 몇 개를 추가해야 합니다.
```java
// 출력 파일 이름
String resultPath = "ZoomFramePresentation.pptx";
// 소스 이미지 경로
String imagePath = "Your Document Directory/aspose-logo.jpg";
Presentation pres = new Presentation();
try {
    // 프레젠테이션에 새 슬라이드 추가
    ISlide slide2 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
    ISlide slide3 = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
```
## 2단계: 슬라이드 배경 사용자 정의
배경색을 추가하여 슬라이드를 시각적으로 구별되게 만들고 싶습니다.
### 두 번째 슬라이드의 배경 설정
```java
    // 두 번째 슬라이드의 배경 만들기
    slide2.getBackground().setType(BackgroundType.OwnBackground);
    slide2.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide2.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
    // 두 번째 슬라이드에 대한 텍스트 상자 만들기
    IAutoShape autoshape = slide2.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Second Slide");
```
### 세 번째 슬라이드의 배경 설정
```java
    // 세 번째 슬라이드의 배경 만들기
    slide3.getBackground().setType(BackgroundType.OwnBackground);
    slide3.getBackground().getFillFormat().setFillType(FillType.Solid);
    slide3.getBackground().getFillFormat().getSolidFillColor().setColor(Color.DARK_GRAY);
    // 세 번째 슬라이드에 대한 텍스트 상자 만들기
    autoshape = slide3.getShapes().addAutoShape(ShapeType.Rectangle, 100, 200, 500, 200);
    autoshape.getTextFrame().setText("Third Slide");
```
## 3단계: 확대/축소 프레임 추가
이제 프레젠테이션에 확대/축소 프레임을 추가해 보겠습니다. 슬라이드 미리보기가 있는 확대 프레임 하나와 사용자 정의 이미지가 있는 확대 프레임을 추가하겠습니다.
### 슬라이드 미리보기로 확대/축소 프레임 추가
```java
    // 슬라이드 미리보기로 ZoomFrame 개체 추가
    IZoomFrame zoomFrame1 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(20, 20, 250, 200, slide2);
```
### 사용자 정의 이미지로 확대/축소 프레임 추가
```java
    // 사용자 정의 이미지로 ZoomFrame 개체 추가
    byte[] imageBytes = Files.readAllBytes(Paths.get(imagePath));
    IPPImage image = pres.getImages().addImage(imageBytes);
    IZoomFrame zoomFrame2 = pres.getSlides().get_Item(0).getShapes().addZoomFrame(200, 250, 250, 100, slide3, image);
```
## 4단계: 확대/축소 프레임 사용자 정의
확대/축소 프레임을 돋보이게 하기 위해 모양을 사용자 정의합니다.
### 두 번째 확대/축소 프레임 사용자 정의
```java
    // ZoomFrame2 객체에 대한 확대/축소 프레임 형식 설정
    zoomFrame2.getLineFormat().setWidth(5);
    zoomFrame2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    zoomFrame2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
    zoomFrame2.getLineFormat().setDashStyle(LineDashStyle.DashDot);
```
### 첫 번째 확대/축소 프레임의 배경 숨기기
```java
    // ZoomFrame1 객체의 배경을 표시하지 않습니다.
    zoomFrame1.setShowBackground(false);
```
## 5단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 지정된 경로에 저장합니다.
```java
    // 프레젠테이션 저장
    pres.save(resultPath, SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint에서 확대/축소 프레임을 만들면 프레젠테이션의 상호작용성과 참여도가 크게 향상됩니다. 이 튜토리얼에 설명된 단계를 따르면 슬라이드 미리 보기와 사용자 정의 이미지를 확대/축소 프레임으로 쉽게 추가하여 프레젠테이션 테마에 맞게 사용자 정의할 수 있습니다. 발표를 즐기세요!
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성하고 조작하기 위한 강력한 API입니다.
### Java용 Aspose.Slides를 어떻게 설치하나요?
 다음에서 Java용 Aspose.Slides를 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/java/) 프로젝트의 종속성에 추가하세요.
### 확대/축소 프레임의 모양을 사용자 정의할 수 있나요?
예, Aspose.Slides를 사용하면 선 스타일, 색상, 배경 가시성과 같은 확대/축소 프레임의 다양한 속성을 사용자 정의할 수 있습니다.
### 줌 프레임에 이미지를 추가할 수 있나요?
전적으로! 이미지 파일을 읽고 프레젠테이션에 추가하여 확대/축소 프레임에 사용자 정의 이미지를 추가할 수 있습니다.
### 더 많은 예제와 문서는 어디에서 찾을 수 있나요?
 다음에서 포괄적인 문서와 예제를 찾을 수 있습니다.[Java 문서 페이지용 Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

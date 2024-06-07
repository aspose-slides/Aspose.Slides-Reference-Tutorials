---
title: PowerPoint의 3D 렌더링
linktitle: PowerPoint의 3D 렌더링
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 멋진 3D 렌더링을 만드는 방법을 알아보세요. 프레젠테이션을 한 단계 더 발전시키세요.
type: docs
weight: 11
url: /ko/java/java-powerpoint-rendering-techniques/3d-rendering-powerpoint/
---
## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 멋진 3D 렌더링을 PowerPoint 프레젠테이션에 통합하는 방법을 살펴보겠습니다. 이러한 단계별 지침을 따르면 청중에게 깊은 인상을 줄 매혹적인 시각 효과를 만들 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
1.  Java 개발 환경: 시스템에 Java가 설치되어 있는지 확인하십시오. 다음에서 Java를 다운로드하고 설치할 수 있습니다.[여기](https://www.java.com/download/).
2.  Aspose.Slides for Java 라이브러리: 다음에서 Aspose.Slides for Java 라이브러리를 다운로드하세요.[웹사이트](https://releases.aspose.com/slides/java/). 프로젝트에 라이브러리를 설정하려면 설명서에 제공된 설치 지침을 따르세요.
## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.*;
import java.io.File;
import java.io.IOException;
```
## 1단계: 새 프레젠테이션 만들기
먼저 새 PowerPoint 프리젠테이션 개체를 만듭니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 3D 모양 추가
이제 슬라이드에 3D 모양을 추가해 보겠습니다.
```java
IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 150, 200, 200);
shape.getTextFrame().setText("3D");
shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(64);
```
## 3단계: 3D 설정 구성
다음으로 모양에 대한 3D 설정을 구성합니다.
```java
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getCamera().setRotation(20, 30, 40);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Flat);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
shape.getThreeDFormat().setMaterial(MaterialPresetType.Powder);
shape.getThreeDFormat().setExtrusionHeight(100);
shape.getThreeDFormat().getExtrusionColor().setColor(Color.BLUE);
```
## 4단계: 프레젠테이션 저장
3D 설정을 구성한 후 프레젠테이션을 저장합니다.
```java
String outPptxFile = RunExamples.getOutPath() + "sandbox_3d.pptx";
String outPngFile = RunExamples.getOutPath() + "sample_3d.png";
try {
    ImageIO.write(pres.getSlides().get_Item(0).getThumbnail(2, 2), "PNG", new File(outPngFile));
    pres.save(outPptxFile, SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint에서 멋진 3D 렌더링을 만드는 방법을 성공적으로 배웠습니다. 이러한 간단한 단계를 따르면 프레젠테이션을 한 단계 더 발전시키고 몰입감 넘치는 시각 효과로 청중의 마음을 사로잡을 수 있습니다.
## FAQ
### 3D 모양을 추가로 사용자 정의할 수 있나요?
예, Aspose.Slides에서 제공하는 다양한 속성과 방법을 탐색하여 요구 사항에 따라 3D 모양을 사용자 지정할 수 있습니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
예, Aspose.Slides는 다양한 PowerPoint 형식을 지원하여 다양한 소프트웨어 버전 간의 호환성을 보장합니다.
### 3D 도형에 애니메이션을 추가할 수 있나요?
전적으로! Aspose.Slides는 3D 모양을 포함하여 PowerPoint 프레젠테이션에 애니메이션 및 전환을 추가하기 위한 광범위한 지원을 제공합니다.
### 3D 렌더링 기능에 제한이 있나요?
Aspose.Slides는 고급 3D 렌더링 기능을 제공하지만 특히 복잡한 장면이나 대규모 프레젠테이션을 작업할 때 성능에 미치는 영향을 고려하는 것이 중요합니다.
### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지원, 문서 및 커뮤니티 지원이 필요합니다.
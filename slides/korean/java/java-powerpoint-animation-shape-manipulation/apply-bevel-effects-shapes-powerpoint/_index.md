---
title: PowerPoint에서 도형에 경사 효과 적용
linktitle: PowerPoint에서 도형에 경사 효과 적용
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 단계별 가이드를 통해 Java용 Aspose.Slides를 사용하여 PowerPoint의 모양에 경사 효과를 적용하는 방법을 알아보세요. 프레젠테이션을 향상시키세요.
type: docs
weight: 13
url: /ko/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---
## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 청중의 관심을 끌고 유지하는 데 중요합니다. 도형에 경사 효과를 추가하면 슬라이드의 전반적인 미학이 향상되어 프레젠테이션이 돋보이게 됩니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint의 도형에 경사 효과를 적용하는 과정을 안내합니다. 프레젠테이션 작성을 자동화하려는 개발자이거나 디자인 작업을 좋아하는 사람이라면 이 가이드가 도움이 될 것입니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- JDK(Java Development Kit): JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Java 라이브러리용 Aspose.Slides: 다음에서 라이브러리를 다운로드하세요.[Java용 Aspose.Slides](https://releases.aspose.com/slides/java/).
- IDE(통합 개발 환경): IntelliJ IDEA, Eclipse, NetBeans 등 원하는 IDE를 사용하세요.
-  Aspose 라이선스: Aspose.Slides를 제한 없이 사용하려면 다음에서 라이선스를 받으세요.[구매 제안](https://purchase.aspose.com/buy) 아니면[임시면허](https://purchase.aspose.com/temporary-license/) 평가를 위해.
## 패키지 가져오기
먼저 Java 프로젝트에서 Aspose.Slides 작업에 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## 1단계: 프로젝트 설정
 코딩을 시작하기 전에 프로젝트가 올바르게 설정되었는지 확인하세요. 프로젝트의 빌드 경로에 Aspose.Slides 라이브러리를 포함하세요. Maven을 사용하는 경우 다음 종속성을 추가하십시오.`pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## 2단계: 프레젠테이션 만들기
 Aspose.Slides 작업을 시작하려면 다음의 인스턴스를 생성해야 합니다.`Presentation` 수업. 이 클래스는 PowerPoint 파일을 나타냅니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드에 액세스
프레젠테이션을 만든 후 도형을 추가하고 조작할 첫 번째 슬라이드에 액세스하세요.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 4단계: 슬라이드에 도형 추가
이제 슬라이드에 도형을 추가합니다. 이 예에서는 타원을 추가하겠습니다.
```java
// 슬라이드에 도형 추가
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## 5단계: 모양에 경사 효과 적용
다음으로, 모양에 경사 효과를 적용하여 입체감을 줍니다.
```java
// 도형의 ThreeDFormat 속성 설정
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## 6단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 지정된 디렉터리에 PPTX 파일로 저장합니다.
```java
// 프레젠테이션을 PPTX 파일로 작성
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## 7단계: 프레젠테이션 개체 삭제
 리소스를 확보하려면 항상`Presentation` 물건이 적절하게 폐기되었습니다.
```java
if (pres != null) pres.dispose();
```
## 결론
 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양에 경사 효과를 적용하는 것은 슬라이드의 시각적 매력을 크게 향상시킬 수 있는 간단한 프로세스입니다. 이 가이드에 설명된 단계를 따르면 전문적이고 매력적인 프레젠테이션을 쉽게 만들 수 있습니다. 탐험하는 것을 잊지 마세요[Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 더 자세한 정보와 고급 기능을 확인하세요.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 관리할 수 있는 강력한 API입니다.
### Java용 Aspose.Slides를 무료로 사용할 수 있나요?
 Aspose.Slides는 다음에서 다운로드할 수 있는 무료 평가판을 제공합니다.[여기](https://releases.aspose.com/). 전체 기능을 사용하려면 라이센스를 구매해야 합니다.
### 내 슬라이드에 어떤 유형의 도형을 추가할 수 있나요?
Aspose.Slides for Java를 사용하면 직사각형, 타원, 선, 사용자 정의 모양 등 다양한 모양을 추가할 수 있습니다.
### 베벨 외에 다른 3D 효과도 적용할 수 있나요?
예, Aspose.Slides for Java를 사용하면 깊이, 조명, 카메라 효과를 포함한 다양한 3D 효과를 적용할 수 있습니다.
### Java용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 Aspose 커뮤니티 및 지원 팀으로부터 지원을 받을 수 있습니다.[지원 포럼](https://forum.aspose.com/c/slides/11).
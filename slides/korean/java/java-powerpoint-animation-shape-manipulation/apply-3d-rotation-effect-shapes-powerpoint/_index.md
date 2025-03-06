---
title: PowerPoint에서 도형에 3D 회전 효과 적용
linktitle: PowerPoint에서 도형에 3D 회전 효과 적용
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 포괄적인 단계별 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 PowerPoint의 모양에 3D 회전 효과를 적용하는 방법을 알아보세요.
weight: 12
url: /ko/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 도형에 3D 회전 효과 적용

## 소개
PowerPoint 프레젠테이션을 한 단계 더 발전시킬 준비가 되셨나요? 3D 회전 효과를 추가하면 슬라이드를 더욱 역동적이고 매력적으로 만들 수 있습니다. 숙련된 개발자이거나 이제 막 시작하는 개발자라면 이 단계별 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint의 도형에 3D 회전 효과를 적용하는 방법을 보여줍니다. 바로 뛰어 들어 봅시다!
## 전제 조건
시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Java용 Aspose.Slides: 다음 사이트에서 Java용 Aspose.Slides의 최신 버전을 다운로드하세요.[다운로드 링크](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용하여 코딩합니다.
4.  유효한 면허증: 면허증이 없을 경우,[임시면허](https://purchase.aspose.com/temporary-license/) 기능을 시험해 보세요.
## 패키지 가져오기
먼저 Java 프로젝트에 필요한 패키지를 가져옵니다. 이러한 가져오기는 Aspose.Slides를 사용하여 프레젠테이션과 모양을 처리하는 데 도움이 됩니다.
```java
import com.aspose.slides.*;

```
## 1단계: 프로젝트 설정
코드를 살펴보기 전에 프로젝트 환경을 설정하세요. 프로젝트의 종속성에 Aspose.Slides for Java를 추가했는지 확인하세요.
프로젝트에 Aspose.Slides를 추가하세요:
1.  Aspose.Slides JAR 파일을 다음에서 다운로드하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).
2. 프로젝트의 빌드 경로에 이러한 JAR 파일을 추가하세요.
## 2단계: 새 PowerPoint 프레젠테이션 만들기
이 단계에서는 새로운 PowerPoint 프레젠테이션을 만듭니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation pres = new Presentation();
```
이 코드 조각은 모양을 추가할 새 프레젠테이션 개체를 초기화합니다.
## 3단계: 직사각형 모양 추가
다음으로 첫 번째 슬라이드에 직사각형 도형을 추가해 보겠습니다.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
이 코드는 첫 번째 슬라이드의 지정된 위치와 크기에 직사각형 모양을 추가합니다.
## 4단계: 직사각형에 3D 회전 적용
이제 직사각형 모양에 3D 회전 효과를 적용해 보겠습니다.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
여기에서는 깊이, 카메라 회전 각도, 카메라 유형 및 조명 유형을 설정하여 직사각형에 3D 모양을 제공합니다.
## 5단계: 선 모양 추가
슬라이드에 또 다른 도형(이번에는 선)을 추가해 보겠습니다.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
이 코드는 슬라이드에 선 모양을 배치합니다.
## 6단계: 선에 3D 회전 적용
마지막으로 선 모양에 3D 회전 효과를 적용해 보겠습니다.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
직사각형과 유사하게 선 모양에 대한 3D 속성을 설정합니다.
## 7단계: 프레젠테이션 저장
모양을 추가하고 구성한 후 프레젠테이션을 저장합니다.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
이 코드는 프레젠테이션을 원하는 형식의 지정된 파일 이름으로 저장합니다.
## 결론
 축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양에 3D 회전 효과를 성공적으로 적용했습니다. 다음 단계를 따르면 시각적으로 매력적이고 역동적인 프레젠테이션을 만들 수 있습니다. 추가 사용자 정의 및 고급 기능에 대해서는 다음을 참조하십시오.[Aspose.Slides 문서](https://reference.aspose.com/slides/java/).
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 조작할 수 있는 강력한 API입니다.
### Java용 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 다음을 얻을 수 있습니다.[무료 시험판](https://releases.aspose.com/) 또는[임시면허](https://purchase.aspose.com/temporary-license/) 기능을 테스트합니다.
### Aspose.Slides에서 어떤 유형의 도형에 3D 효과를 추가할 수 있나요?
직사각형, 선, 타원, 사용자 정의 모양 등 다양한 모양에 3D 효과를 추가할 수 있습니다.
### Java용 Aspose.Slides에 대한 지원을 받으려면 어떻게 해야 하나요?
 당신은 방문 할 수 있습니다[지원 포럼](https://forum.aspose.com/c/slides/11) 도움을 요청하고 문제를 논의합니다.
### 상용 프로젝트에서 Java용 Aspose.Slides를 사용할 수 있나요?
 예, 하지만 라이센스를 구입해야 합니다. 에서 하나 구입하실 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

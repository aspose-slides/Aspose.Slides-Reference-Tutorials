---
"description": "이 포괄적인 단계별 튜토리얼을 통해 Aspose.Slides for Java를 사용하여 PowerPoint에서 도형에 3D 회전 효과를 적용하는 방법을 알아보세요."
"linktitle": "PowerPoint에서 도형에 3D 회전 효과 적용"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 도형에 3D 회전 효과 적용"
"url": "/ko/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 도형에 3D 회전 효과 적용

## 소개
PowerPoint 프레젠테이션을 한 단계 업그레이드할 준비가 되셨나요? 3D 회전 효과를 추가하면 슬라이드가 더욱 역동적이고 매력적으로 보일 수 있습니다. 숙련된 개발자든 초보자든, 이 단계별 튜토리얼을 통해 Aspose.Slides for Java를 사용하여 PowerPoint 도형에 3D 회전 효과를 적용하는 방법을 알아보세요. 바로 시작해 볼까요!
## 필수 조건
시작하기 전에 다음 사항이 준비되었는지 확인하세요.
1. Java Development Kit(JDK): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Java용 Aspose.Slides: 다음에서 Java용 Aspose.Slides의 최신 버전을 다운로드하세요. [다운로드 링크](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하여 코딩하세요.
4. 유효한 면허증: 면허증이 없는 경우 면허증을 취득할 수 있습니다. [임시 면허](https://purchase.aspose.com/temporary-license/) 기능을 시험해보려고요.
## 패키지 가져오기
먼저, Java 프로젝트에 필요한 패키지를 임포트해 보겠습니다. 이러한 임포트는 Aspose.Slides를 사용하여 프레젠테이션과 도형을 처리하는 데 도움이 됩니다.
```java
import com.aspose.slides.*;

```
## 1단계: 프로젝트 설정
코드를 작성하기 전에 프로젝트 환경을 설정하세요. 프로젝트 종속성에 Aspose.Slides for Java를 추가했는지 확인하세요.
프로젝트에 Aspose.Slides를 추가하세요:
1. Aspose.Slides JAR 파일을 다음에서 다운로드하세요. [다운로드 페이지](https://releases.aspose.com/slides/java/).
2. 이러한 JAR 파일을 프로젝트의 빌드 경로에 추가합니다.
## 2단계: 새 PowerPoint 프레젠테이션 만들기
이 단계에서는 새로운 PowerPoint 프레젠테이션을 만들어 보겠습니다.
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation pres = new Presentation();
```
이 코드 조각은 모양을 추가할 새로운 프레젠테이션 객체를 초기화합니다.
## 3단계: 사각형 모양 추가
다음으로, 첫 번째 슬라이드에 사각형 모양을 추가해 보겠습니다.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
이 코드는 첫 번째 슬라이드의 지정된 위치와 크기에 사각형 모양을 추가합니다.
## 4단계: 사각형에 3D 회전 적용
이제 사각형 모양에 3D 회전 효과를 적용해 보겠습니다.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
여기서는 사각형에 3D 모양을 주기 위해 깊이, 카메라 회전 각도, 카메라 유형, 조명 유형을 설정합니다.
## 5단계: 선 모양 추가
이번에는 슬라이드에 선이라는 또 다른 모양을 추가해 보겠습니다.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
이 코드는 슬라이드에 선 모양을 배치합니다.
## 6단계: 선에 3D 회전 적용
마지막으로 선 모양에 3D 회전 효과를 적용합니다.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
사각형과 마찬가지로 선 모양에 대한 3D 속성을 설정합니다.
## 7단계: 프레젠테이션 저장
모양을 추가하고 구성한 후 프레젠테이션을 저장합니다.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
이 코드는 원하는 형식으로 지정된 파일 이름으로 프레젠테이션을 저장합니다.
## 결론
축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 3D 회전 효과를 성공적으로 적용했습니다. 다음 단계를 따라 시각적으로 매력적이고 역동적인 프레젠테이션을 만들 수 있습니다. 추가 사용자 지정 및 고급 기능에 대한 자세한 내용은 다음을 참조하세요. [Aspose.Slides 문서](https://reference.aspose.com/slides/java/).
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 수정하고, 조작할 수 있는 강력한 API입니다.
### Aspose.Slides for Java를 무료로 사용해 볼 수 있나요?
네, 당신은 얻을 수 있습니다 [무료 체험](https://releases.aspose.com/) 또는 [임시 면허](https://purchase.aspose.com/temporary-license/) 기능을 테스트하려면.
### Aspose.Slides에서 어떤 유형의 모양에 3D 효과를 추가할 수 있나요?
사각형, 선, 타원, 사용자 정의 모양 등 다양한 모양에 3D 효과를 추가할 수 있습니다.
### Java용 Aspose.Slides에 대한 지원은 어떻게 받을 수 있나요?
방문할 수 있습니다 [지원 포럼](https://forum.aspose.com/c/slides/11) 도움을 요청하거나 문제점을 논의하려면 로 연락하세요.
### 상업용 프로젝트에서 Aspose.Slides for Java를 사용할 수 있나요?
네, 하지만 라이선스를 구매해야 합니다. 라이선스는 다음에서 구매할 수 있습니다. [구매 페이지](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
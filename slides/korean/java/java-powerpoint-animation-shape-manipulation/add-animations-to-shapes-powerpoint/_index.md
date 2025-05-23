---
"description": "이 상세한 튜토리얼을 통해 Aspose.Slides for Java를 사용하여 PowerPoint 도형에 애니메이션을 추가하는 방법을 알아보세요. 매력적인 프레젠테이션을 만드는 데 안성맞춤입니다."
"linktitle": "PowerPoint에서 도형에 애니메이션 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 도형에 애니메이션 추가"
"url": "/ko/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 도형에 애니메이션 추가

## 소개
매력적인 프레젠테이션을 만들려면 도형과 텍스트에 애니메이션을 추가해야 하는 경우가 많습니다. 애니메이션은 슬라이드를 더욱 역동적이고 매력적으로 만들어 청중의 관심을 사로잡습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 애니메이션을 추가하는 과정을 안내합니다. 이 글을 끝까지 읽으면 전문가 수준의 애니메이션을 손쉽게 제작할 수 있을 것입니다.
## 필수 조건
튜토리얼을 시작하기에 앞서, 필요한 모든 것이 있는지 확인해 보겠습니다.
1. Aspose.Slides for Java 라이브러리: Aspose.Slides for Java 라이브러리가 설치되어 있어야 합니다. [여기서 다운로드하세요](https://releases.aspose.com/slides/java/).
2. Java Development Kit(JDK): 컴퓨터에 JDK가 설치되어 있는지 확인하세요.
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java IDE를 사용하세요.
4. Java에 대한 기본 지식: 이 튜토리얼은 독자가 Java 프로그래밍에 대한 기본적인 지식을 가지고 있다고 가정합니다.
## 패키지 가져오기
시작하려면 Aspose.Slides 및 기타 필수 Java 클래스에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## 1단계: 프로젝트 디렉토리 설정
먼저, 프로젝트 파일을 위한 디렉토리를 만듭니다.
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## 2단계: 프레젠테이션 개체 초기화
다음으로 인스턴스화합니다. `Presentation` PowerPoint 파일을 나타내는 클래스입니다.
```java
// PPTX를 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드에 액세스
이제 애니메이션을 추가할 프레젠테이션의 첫 번째 슬라이드에 접근합니다.
```java
// 첫 번째 슬라이드에 접근하세요
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 슬라이드에 모양 추가
슬라이드에 사각형 모양을 추가하고 여기에 텍스트를 삽입합니다.
```java
// 슬라이드에 사각형 모양 추가
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## 5단계: 애니메이션 효과 적용
모양에 "PathFootball" 애니메이션 효과를 적용합니다.
```java
// PathFootBall 애니메이션 효과 추가
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## 6단계: 대화형 트리거 만들기
클릭하면 애니메이션이 실행되는 버튼 모양을 만듭니다.
```java
// 애니메이션을 트리거하기 위한 "버튼" 모양을 만듭니다.
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## 7단계: 대화형 시퀀스 정의
버튼에 대한 효과 시퀀스를 정의합니다.
```java
// 버튼에 대한 효과 시퀀스를 만듭니다.
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## 8단계: 사용자 정의 경로 추가
모양에 사용자 정의 경로 애니메이션을 추가합니다.
```java
// 사용자 정의 경로 애니메이션 효과 추가
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// 모션 효과 만들기
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// 경로 지점을 정의하세요
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## 9단계: 프레젠테이션 저장
마지막으로, 원하는 위치에 프레젠테이션을 저장합니다.
```java
// 프레젠테이션을 PPTX 파일로 저장합니다.
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// 프레젠테이션 객체를 폐기합니다
if (pres != null) pres.dispose();
```
## 결론
자, 이제 완성했습니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 애니메이션을 성공적으로 추가했습니다. 이 강력한 라이브러리를 사용하면 역동적인 효과로 프레젠테이션을 더욱 돋보이게 하고 청중의 참여를 유지할 수 있습니다. 연습이 완벽을 만든다는 것을 기억하세요. 다양한 효과와 트리거를 계속 실험하여 자신에게 가장 적합한 것을 찾아보세요.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 수정하고, 조작할 수 있는 강력한 API입니다.
### Aspose.Slides를 무료로 사용할 수 있나요?
Aspose.Slides를 무료로 사용해 보세요. [임시 면허](https://purchase.aspose.com/temporary-license/)계속 사용하려면 유료 라이선스가 필요합니다.
### Aspose.Slides와 호환되는 Java 버전은 무엇입니까?
Aspose.Slides는 Java SE 6 이상을 지원합니다.
### 여러 모양에 각기 다른 애니메이션을 추가하려면 어떻게 해야 하나요?
각 모양에 대해 단계를 반복하고 필요에 따라 다른 효과를 지정하여 여러 모양에 다양한 애니메이션을 추가할 수 있습니다.
### 더 많은 예와 문서는 어디에서 찾을 수 있나요?
확인해 보세요 [선적 서류 비치](https://reference.aspose.com/slides/java/) 그리고 [지원 포럼](https://forum.aspose.com/c/slides/11) 더 많은 예와 도움말을 보려면 여기를 클릭하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
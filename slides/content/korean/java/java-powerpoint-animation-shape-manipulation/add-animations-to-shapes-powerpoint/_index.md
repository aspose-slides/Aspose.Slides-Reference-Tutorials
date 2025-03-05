---
title: PowerPoint의 도형에 애니메이션 추가
linktitle: PowerPoint의 도형에 애니메이션 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 상세한 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 PowerPoint의 도형에 애니메이션을 추가하는 방법을 알아보세요. 매력적인 프레젠테이션을 만드는 데 적합합니다.
type: docs
weight: 10
url: /ko/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---
## 소개
매력적인 프레젠테이션을 만들려면 도형과 텍스트에 애니메이션을 추가해야 하는 경우가 많습니다. 애니메이션을 사용하면 슬라이드를 더욱 역동적이고 매력적으로 만들어 청중의 관심을 유지할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 애니메이션을 추가하는 과정을 안내합니다. 이 기사를 마치면 전문적인 애니메이션을 쉽게 만들 수 있게 될 것입니다.
## 전제 조건
튜토리얼을 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.
1.  Aspose.Slides for Java 라이브러리: Aspose.Slides for Java 라이브러리가 설치되어 있어야 합니다. 당신은 할 수 있습니다[여기에서 다운로드하십시오](https://releases.aspose.com/slides/java/).
2. JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요.
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java IDE를 사용합니다.
4. Java 기본 지식: 이 튜토리얼에서는 사용자가 Java 프로그래밍에 대한 기본 지식을 가지고 있다고 가정합니다.
## 패키지 가져오기
시작하려면 Aspose.Slides 및 기타 필수 Java 클래스에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## 1단계: 프로젝트 디렉터리 설정
먼저 프로젝트 파일용 디렉터리를 만듭니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## 2단계: 프레젠테이션 개체 초기화
 다음으로 인스턴스화`Presentation` PowerPoint 파일을 나타내는 클래스입니다.
```java
// PPTX를 나타내는 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드에 액세스
이제 애니메이션을 추가할 프레젠테이션의 첫 번째 슬라이드에 액세스합니다.
```java
// 첫 번째 슬라이드에 액세스
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 슬라이드에 도형 추가
슬라이드에 직사각형 모양을 추가하고 텍스트를 삽입하세요.
```java
// 슬라이드에 직사각형 도형 추가
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
// 애니메이션을 트리거하는 "버튼" 모양 만들기
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## 7단계: 대화형 시퀀스 정의
버튼에 대한 일련의 효과를 정의합니다.
```java
// 버튼에 대한 일련의 효과 만들기
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## 8단계: 사용자 정의 사용자 경로 추가
모양에 사용자 정의 사용자 경로 애니메이션을 추가합니다.
```java
// 사용자 정의 사용자 경로 애니메이션 효과 추가
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// 모션 효과 만들기
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// 경로 지점 정의
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## 9단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 원하는 위치에 저장합니다.
```java
// 프레젠테이션을 PPTX 파일로 저장
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// 프레젠테이션 개체 삭제
if (pres != null) pres.dispose();
```
## 결론
그리고 거기에 있습니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양에 애니메이션을 성공적으로 추가했습니다. 이 강력한 라이브러리를 사용하면 동적 효과로 프레젠테이션을 쉽게 향상시켜 청중의 참여를 유지할 수 있습니다. 연습이 완벽함을 기억하십시오. 다양한 효과와 트리거를 계속 실험하여 귀하의 필요에 가장 적합한 것이 무엇인지 확인하십시오.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 조작할 수 있는 강력한 API입니다.
### Aspose.Slides를 무료로 사용할 수 있나요?
 Aspose.Slides를 무료로 사용해 볼 수 있습니다.[임시면허](https://purchase.aspose.com/temporary-license/). 계속 사용하려면 유료 라이센스가 필요합니다.
### Aspose.Slides와 호환되는 Java 버전은 무엇입니까?
Aspose.Slides는 Java SE 6 이상을 지원합니다.
### 여러 도형에 다양한 애니메이션을 어떻게 추가하나요?
각 모양에 대해 단계를 반복하고 필요에 따라 다양한 효과를 지정하여 여러 모양에 다양한 애니메이션을 추가할 수 있습니다.
### 더 많은 예제와 문서는 어디에서 찾을 수 있나요?
 확인해 보세요[선적 서류 비치](https://reference.aspose.com/slides/java/) 그리고[지원 포럼](https://forum.aspose.com/c/slides/11)더 많은 예제와 도움말을 보려면
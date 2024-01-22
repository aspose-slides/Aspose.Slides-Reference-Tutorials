---
title: Aspose.Slides로 쉽게 만든 모양 애니메이션
linktitle: Aspose.Slides를 사용하여 프레젠테이션 슬라이드의 도형에 애니메이션 적용
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 멋진 프레젠테이션을 만드세요. 이 단계별 가이드에서 도형에 애니메이션을 적용하는 방법을 알아보세요. 지금 슬라이드를 높이세요!
type: docs
weight: 21
url: /ko/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---
## 소개
동적 프레젠테이션 세계에서 도형에 애니메이션을 추가하면 슬라이드의 시각적 매력과 참여도가 크게 향상될 수 있습니다. .NET용 Aspose.Slides는 이를 원활하게 수행할 수 있는 강력한 툴킷을 제공합니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 도형에 애니메이션을 적용하는 과정을 안내하여 지속적인 인상을 남기는 매력적인 프레젠테이션을 만들 수 있습니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.
1.  .NET용 Aspose.Slides: 라이브러리가 설치되어 있고 사용할 준비가 되었는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/slides/net/).
2. 개발 환경: 필요한 구성으로 원하는 개발 환경을 설정합니다.
3. 문서 디렉터리: 프레젠테이션 파일을 저장할 디렉터리를 만듭니다.
## 네임스페이스 가져오기
.NET 애플리케이션에서 필수 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## 1단계: 프레젠테이션 만들기
 다음을 사용하여 새 프레젠테이션을 만드는 것부터 시작하세요.`Presentation` 수업:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    //프레젠테이션을 만들기 위한 코드가 여기에 있습니다.
}
```
## 2단계: 애니메이션 모양 추가
이제 프레젠테이션의 첫 번째 슬라이드에 애니메이션 모양을 추가해 보겠습니다.
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## 3단계: 애니메이션 효과 적용
생성된 모양에 'PathFootball' 애니메이션 효과를 추가합니다.
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## 4단계: 트리거 버튼 생성
애니메이션을 트리거할 버튼을 만듭니다.
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## 5단계: 사용자 정의 사용자 경로 정의
애니메이션에 대한 사용자 정의 사용자 경로를 정의합니다.
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// 프레젠테이션을 PPTX로 디스크에 저장
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
이것으로 Aspose.Slides for .NET을 사용하여 모양에 애니메이션을 적용하는 단계별 가이드가 완성되었습니다.
## 결론
프레젠테이션에 애니메이션을 통합하면 청중의 관심을 사로잡는 역동적인 요소가 추가됩니다. Aspose.Slides를 사용하면 이러한 효과를 원활하게 통합하고 프레젠테이션을 다음 단계로 끌어올릴 수 있는 강력한 도구를 갖게 됩니다.
## 자주 묻는 질문
### 단일 도형에 여러 애니메이션을 적용할 수 있나요?
예, Aspose.Slides를 사용하면 단일 모양에 여러 애니메이션 효과를 추가할 수 있어 복잡한 애니메이션을 만드는 데 유연성을 제공합니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 PowerPoint 버전과의 호환성을 보장하여 프레젠테이션이 다양한 플랫폼에서 원활하게 작동하도록 보장합니다.
### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 탐색[선적 서류 비치](https://reference.aspose.com/slides/net/) 그리고 다음과 같은 분야에서 도움을 구하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### 라이브러리를 사용하려면 Aspose.Slides 라이선스가 필요합니까?
 네, 라이센스를 취득하실 수 있습니다[여기](https://purchase.aspose.com/buy) Aspose.Slides의 잠재력을 최대한 활용하세요.
### 구매하기 전에 Aspose.Slides를 사용해 볼 수 있나요?
 틀림없이! 활용[무료 시험판](https://releases.aspose.com/) 약속을 하기 전에 Aspose.Slides의 기능을 경험해보세요.
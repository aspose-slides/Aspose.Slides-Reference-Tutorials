---
title: .NET용 Aspose.Slides를 사용하여 프레젠테이션에서 3D 회전 마스터하기
linktitle: 프레젠테이션 슬라이드의 도형에 3D 회전 효과 적용
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 프레젠테이션을 향상시키세요! 이 튜토리얼에서는 모양에 3D 회전 효과를 적용하는 방법을 알아봅니다. 역동적이고 시각적으로 멋진 프레젠테이션을 만들어 보세요.
weight: 23
url: /ko/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
매력적이고 역동적인 프레젠테이션 슬라이드를 만드는 것은 효과적인 커뮤니케이션의 핵심 요소입니다. .NET용 Aspose.Slides는 도형에 3D 회전 효과를 적용하는 기능을 포함하여 프레젠테이션을 향상시키는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드의 도형에 3D 회전 효과를 적용하는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/net/).
- 개발 환경: Visual Studio와 같은 .NET 개발 환경을 설정하여 코드를 작성하고 실행합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Slides의 기능을 활용하는 데 필요한 네임스페이스를 가져옵니다. 코드 시작 부분에 다음 네임스페이스를 포함합니다.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1단계: 프로젝트 설정
원하는 .NET 개발 환경에서 새 프로젝트를 만듭니다. 프로젝트에 Aspose.Slides 참조를 추가했는지 확인하세요.
## 2단계: 프레젠테이션 초기화
프레젠테이션 클래스를 인스턴스화하여 슬라이드 작업을 시작합니다.
```csharp
Presentation pres = new Presentation();
```
## 3단계: 도형 추가
유형, 위치 및 크기를 지정하여 슬라이드에 도형을 추가합니다.
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## 4단계: 3D 회전 효과 설정
도형에 대한 3D 회전 효과를 구성합니다.
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## 5단계: 프레젠테이션 저장
3D 회전 효과가 적용된 수정된 프레젠테이션을 저장합니다.
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## 6단계: 다른 모양에도 반복
추가 모양이 있는 경우 각 모양에 대해 3~5단계를 반복합니다.
## 결론
프레젠테이션 슬라이드의 도형에 3D 회전 효과를 추가하면 시각적 매력이 크게 향상될 수 있습니다. .NET용 Aspose.Slides를 사용하면 이 프로세스가 간단해져서 매력적인 프레젠테이션을 만들 수 있습니다.
## 자주 묻는 질문
### .NET용 Aspose.Slides의 텍스트 상자에 3D 회전을 적용할 수 있나요?
예, Aspose.Slides를 사용하여 텍스트 상자를 포함한 다양한 도형에 3D 회전 효과를 적용할 수 있습니다.
### .NET용 Aspose.Slides 평가판이 있습니까?
 예, 평가판 버전에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### .NET용 Aspose.Slides에 대한 지원을 받으려면 어떻게 해야 합니까?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 지원 및 토론을 위해.
### .NET용 Aspose.Slides의 임시 라이선스를 구입할 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### .NET용 Aspose.Slides에 대한 자세한 문서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

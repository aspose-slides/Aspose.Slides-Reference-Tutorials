---
title: .NET용 Aspose.Slides를 사용하여 직사각형 모양 만들기
linktitle: Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 간단한 직사각형 모양 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 역동적인 PowerPoint 프레젠테이션의 세계를 탐험해보세요. 이 단계별 가이드를 통해 슬라이드에서 매력적인 직사각형 모양을 만드는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---
## 소개
역동적이고 시각적으로 매력적인 PowerPoint 프레젠테이션으로 .NET 애플리케이션을 향상시키려는 경우 Aspose.Slides for .NET이 최적의 솔루션입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 간단한 직사각형 모양을 만드는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Visual Studio: 개발 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요.
-  .NET용 Aspose.Slides: 다음에서 .NET용 Aspose.Slides 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/net/).
- 기본 C# 지식: C# 프로그래밍 언어에 대한 지식이 필수적입니다.
## 네임스페이스 가져오기
C# 프로젝트에서 Aspose.Slides 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## 1단계: 프로젝트 설정
Visual Studio에서 새 C# 프로젝트를 만드는 것부터 시작하세요. .NET용 Aspose.Slides가 프로젝트에서 올바르게 참조되는지 확인하세요.
## 2단계: 프레젠테이션 개체 초기화
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // 다음 단계를 위한 코드가 여기에 입력됩니다.
}
```
## 3단계: 첫 번째 슬라이드 가져오기
```csharp
ISlide sld = pres.Slides[0];
```
## 4단계: 직사각형 도형 추가
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
이 코드는 좌표 (50, 150)에 너비가 150이고 높이가 50인 직사각형 모양을 추가합니다.
## 5단계: 프레젠테이션 저장
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
이 단계에서는 직사각형 모양이 추가된 프레젠테이션을 지정된 디렉터리에 저장합니다.
## 결론
축하해요! Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 간단한 직사각형 모양을 성공적으로 만들었습니다. 이것은 시작에 불과합니다. Aspose.Slides는 프레젠테이션을 더욱 맞춤화하고 향상시킬 수 있는 다양한 기능을 제공합니다.
## 자주 묻는 질문
### Windows 및 Linux 환경 모두에서 Aspose.Slides for .NET을 사용할 수 있나요?
예, .NET용 Aspose.Slides는 플랫폼 독립적이며 Windows 및 Linux 환경 모두에서 사용할 수 있습니다.
### .NET용 Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).
### .NET용 Aspose.Slides에 대한 지원을 받으려면 어떻게 해야 합니까?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지역 사회 지원을 위해.
### .NET용 Aspose.Slides의 임시 라이선스를 구입할 수 있나요?
 예, 임시 라이센스를 구매하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### .NET용 Aspose.Slides에 대한 설명서는 어디서 찾을 수 있나요?
 문서를 참조하세요[여기](https://reference.aspose.com/slides/net/).
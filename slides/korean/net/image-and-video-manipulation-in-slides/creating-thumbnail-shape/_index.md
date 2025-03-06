---
title: PowerPoint 모양 축소판 만들기 - Aspose.Slides .NET
linktitle: Aspose.Slides에서 모양의 썸네일 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션의 모양에 대한 축소판을 만드는 방법을 알아보세요. 개발자를 위한 포괄적인 단계별 가이드입니다.
weight: 14
url: /ko/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint 모양 축소판 만들기 - Aspose.Slides .NET

## 소개
Aspose.Slides for .NET은 개발자가 PowerPoint 프레젠테이션을 원활하게 사용할 수 있도록 지원하는 강력한 라이브러리입니다. 주목할만한 기능 중 하나는 프레젠테이션 내의 모양에 대한 축소판을 생성하는 기능입니다. 이 튜토리얼은 Aspose.Slides for .NET을 사용하여 모양의 썸네일을 만드는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET용 Aspose.Slides: Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[릴리스 페이지](https://releases.aspose.com/slides/net/).
2. 개발 환경: Visual Studio 등 적합한 개발 환경을 설정하고 C# 프로그래밍에 대한 기본적인 이해가 있어야 합니다.
## 네임스페이스 가져오기
시작하려면 C# 코드에서 필요한 네임스페이스를 가져와야 합니다. 이러한 네임스페이스는 Aspose.Slides 라이브러리와의 통신을 용이하게 합니다. C# 파일 시작 부분에 다음 줄을 추가합니다.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## 1단계: 프로젝트 설정
원하는 개발 환경에서 새 C# 프로젝트를 만듭니다. Aspose.Slides 라이브러리가 프로젝트에서 참조되는지 확인하세요.
## 2단계: 프레젠테이션 초기화
PowerPoint 파일을 나타내기 위해 프레젠테이션 클래스를 인스턴스화합니다. 프레젠테이션 파일의 경로를 다음 위치에 입력하세요.`dataDir` 변하기 쉬운.
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // 썸네일 생성을 위한 코드가 여기에 있습니다.
}
```
## 3단계: 실물 크기 이미지 생성
썸네일을 만들려는 모양의 실제 크기 이미지를 생성합니다. 이 예에서는 첫 번째 슬라이드의 첫 번째 도형(`presentation.Slides[0].Shapes[0]`).
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail())
{
    // 썸네일 생성을 위한 코드가 여기에 있습니다.
}
```
## 4단계: 이미지 저장
생성된 썸네일 이미지를 디스크에 저장합니다. 이미지를 저장할 형식을 선택할 수 있습니다. 이 예에서는 PNG 형식으로 저장합니다.
```csharp
bitmap.Save(dataDir + "Shape_thumbnail_out.png", ImageFormat.Png);
```
## 결론
축하해요! .NET용 Aspose.Slides에서 모양의 축소판을 성공적으로 만들었습니다. 이 강력한 기능은 PowerPoint 프레젠테이션에서 정보를 조작하고 추출하는 능력에 새로운 차원을 추가합니다.
## 자주 묻는 질문
### Q: 프레젠테이션에서 여러 도형에 대한 축소판을 만들 수 있나요?
A: 예, 슬라이드의 모든 도형을 반복하여 각 도형에 대한 축소판을 생성할 수 있습니다.
### Q: Aspose.Slides는 다른 PowerPoint 파일 형식과 호환됩니까?
A: Aspose.Slides는 PPTX, PPT 등 다양한 파일 형식을 지원합니다.
### Q: 썸네일 생성 중 오류를 처리하려면 어떻게 해야 합니까?
A: try-catch 블록을 사용하여 오류 처리 메커니즘을 구현하여 예외를 관리할 수 있습니다.
### Q: 썸네일을 포함할 수 있는 도형의 크기나 유형에 제한이 있나요?
A: Aspose.Slides는 텍스트 상자, 이미지 등을 포함한 다양한 모양의 썸네일을 생성할 수 있는 유연성을 제공합니다.
### Q: 생성된 썸네일의 크기와 해상도를 사용자 정의할 수 있나요?
 A: 예, 전화를 걸 때 매개변수를 조정할 수 있습니다.`GetThumbnail` 크기와 해상도를 제어하는 방법.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

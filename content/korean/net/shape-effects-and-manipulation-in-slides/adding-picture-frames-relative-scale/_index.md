---
title: Aspose.Slides .NET을 사용하여 액자 튜토리얼 추가하기
linktitle: Aspose.Slides에서 상대 배율 높이를 사용하여 액자 추가하기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides에서 상대 배율 높이를 사용하여 사진 프레임을 추가하는 방법을 알아보세요. 원활한 프레젠테이션을 위해 이 단계별 가이드를 따르세요.
type: docs
weight: 17
url: /ko/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## 소개
Aspose.Slides for .NET은 개발자가 .NET 애플리케이션에서 PowerPoint 프레젠테이션을 손쉽게 생성, 조작 및 변환할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 상대 배율 높이를 가진 사진 프레임을 추가하는 과정을 살펴보겠습니다. 프레젠테이션 작성 기술을 향상하려면 이 단계별 가이드를 따르세요.
## 전제조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 지식.
- Visual Studio 또는 기타 기본 C# 개발 환경이 설치되어 있습니다.
- .NET용 Aspose.Slides 라이브러리가 프로젝트에 추가되었습니다.
## 네임스페이스 가져오기
필요한 네임스페이스를 C# 코드로 가져오는 것부터 시작하세요. 이 단계에서는 Aspose.Slides 라이브러리에서 제공하는 클래스와 기능에 액세스할 수 있는지 확인합니다.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1단계: 프로젝트 설정
선호하는 개발 환경에서 새 C# 프로젝트를 만드는 것부터 시작하세요. Aspose.Slides for .NET 라이브러리를 참조하여 프로젝트에 추가하세요.
## 2단계: 프리젠테이션 및 이미지 로드
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // 프리젠테이션 이미지 컬렉션에 추가할 이미지 로드
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
이 단계에서는 새 프레젠테이션 개체를 만들고 프레젠테이션에 추가할 이미지를 로드합니다.
## 3단계: 슬라이드에 그림 프레임 추가
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
이제 프레젠테이션의 첫 번째 슬라이드에 그림 프레임을 추가합니다. 요구 사항에 따라 모양 유형, 위치, 치수 등의 매개변수를 조정합니다.
## 4단계: 상대 배율 너비 및 높이 설정
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
원하는 크기 조정 효과를 얻으려면 그림 프레임의 상대적 크기 높이와 너비를 설정하십시오.
## 5단계: 프레젠테이션 저장
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
마지막으로 지정된 출력 형식으로 추가된 그림 프레임이 포함된 프레젠테이션을 저장합니다.
## 결론
축하해요! .NET용 Aspose.Slides를 사용하여 상대 배율 높이가 있는 사진 프레임을 추가하는 방법을 성공적으로 배웠습니다. 다양한 이미지, 위치 및 배율을 실험하여 필요에 맞는 시각적으로 매력적인 프레젠테이션을 만드십시오.
## 자주 묻는 질문
### Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Slides는 주로 .NET 언어를 지원하지만 다른 플랫폼과의 호환성을 위해 다른 Aspose 제품을 탐색할 수도 있습니다.
### .NET용 Aspose.Slides에 대한 자세한 문서는 어디서 찾을 수 있나요?
 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/slides/net/) 포괄적인 정보와 예시를 보려면
### .NET용 Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 다음을 얻을 수 있습니다.[무료 시험판](https://releases.aspose.com/) 도서관의 능력을 평가합니다.
### .NET용 Aspose.Slides에 대한 지원을 받으려면 어떻게 해야 합니까?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티와 Aspose 전문가의 도움을 구합니다.
### .NET용 Aspose.Slides를 어디서 구입할 수 있나요?
 .NET용 Aspose.Slides는 다음에서 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
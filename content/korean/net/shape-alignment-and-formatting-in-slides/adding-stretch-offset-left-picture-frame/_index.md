---
title: Aspose.Slide를 사용하여 PowerPoint에서 왼쪽에 스트레치 오프셋 추가
linktitle: Aspose.Slides의 그림 프레임 왼쪽에 스트레치 오프셋 추가
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요. 사진 프레임의 왼쪽에 스트레치 오프셋을 추가하려면 단계별 가이드를 따르세요.
type: docs
weight: 14
url: /ko/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## 소개
Aspose.Slides for .NET은 개발자가 PowerPoint 프레젠테이션을 쉽게 조작할 수 있도록 지원하는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 그림 프레임의 왼쪽에 스트레치 오프셋을 추가하는 과정을 살펴보겠습니다. PowerPoint 프레젠테이션 내에서 이미지 및 모양 작업 기술을 향상하려면 이 단계별 가이드를 따르세요.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET용 Aspose.Slides: 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드하십시오.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).
- 개발 환경: .NET 기능을 갖춘 작업 개발 환경을 갖추고 있습니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## 1단계: 프로젝트 설정
새 프로젝트를 만들거나 기존 프로젝트를 엽니다. 프로젝트에 Aspose.Slides 라이브러리가 참조되어 있는지 확인하세요.
## 2단계: 프리젠테이션 개체 만들기
 인스턴스화`Presentation` PPTX 파일을 나타내는 클래스:
```csharp
using (Presentation pres = new Presentation())
{
    // 후속 단계에 대한 코드가 여기에 표시됩니다.
}
```
## 3단계: 첫 번째 슬라이드 가져오기
프레젠테이션에서 첫 번째 슬라이드를 검색합니다.
```csharp
ISlide slide = pres.Slides[0];
```
## 4단계: 이미지 인스턴스화
사용하려는 이미지를 로드합니다.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## 5단계: 직사각형 도형 추가
직사각형 유형의 도형을 만듭니다.
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## 6단계: 채우기 유형 및 그림 채우기 모드 설정
도형의 채우기 유형 및 그림 채우기 모드를 구성합니다.
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## 7단계: 도형을 채우도록 이미지 설정
도형을 채울 이미지를 지정합니다.
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## 8단계: 늘이기 오프셋 지정
모양 경계 상자의 해당 가장자리로부터 이미지 오프셋을 정의합니다.
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## 9단계: 프레젠테이션 저장
PPTX 파일을 디스크에 씁니다.
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
축하해요! .NET용 Aspose.Slides를 사용하여 그림 프레임의 왼쪽에 스트레치 오프셋을 성공적으로 추가했습니다.
## 결론
이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 그림 프레임을 조작하는 과정을 살펴보았습니다. 단계별 가이드를 따라 이미지, 모양 및 오프셋 작업에 대한 통찰력을 얻었습니다.
## 자주 묻는 질문
### Q: 직사각형 외의 다른 모양에도 늘이기 오프셋을 적용할 수 있나요?
A: 이 튜토리얼은 직사각형에 초점을 맞추고 있지만 Aspose.Slides가 지원하는 다양한 모양에 스트레치 오프셋을 적용할 수 있습니다.
### Q: 다양한 효과에 대한 스트레치 오프셋을 어떻게 조정할 수 있습니까?
A: 원하는 시각적 효과를 얻으려면 다양한 오프셋 값을 사용해 보십시오. 특정 요구 사항에 맞게 값을 미세 조정합니다.
### Q: Aspose.Slides는 최신 .NET 프레임워크와 호환됩니까?
A: Aspose.Slides는 최신 .NET 프레임워크 버전과의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.
### Q: Aspose.Slides에 대한 추가 예제와 리소스는 어디서 찾을 수 있나요?
 A: 탐색해 보세요.[Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 포괄적인 예시와 지침을 확인하세요.
### Q: 단일 모양에 여러 스트레치 오프셋을 적용할 수 있습니까?
A: 예, 여러 스트레치 오프셋을 결합하여 복잡하고 사용자 정의된 시각 효과를 얻을 수 있습니다.
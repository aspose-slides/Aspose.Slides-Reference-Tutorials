---
title: Aspose.Slides의 모양에 대한 배율 조정 요소를 사용하여 축소판 만들기
linktitle: Aspose.Slides의 모양에 대한 배율 조정 요소를 사용하여 축소판 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 특정 범위의 PowerPoint 축소판 이미지를 만드는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
type: docs
weight: 12
url: /ko/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---
## 소개
.NET용 Aspose.Slides에서 모양 경계가 있는 썸네일 생성에 대한 포괄적인 가이드에 오신 것을 환영합니다. Aspose.Slides는 개발자가 .NET 애플리케이션에서 PowerPoint 프레젠테이션을 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 프레젠테이션 내의 모양에 대한 특정 경계가 있는 썸네일을 생성하는 프로세스를 자세히 살펴보겠습니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET용 Aspose.Slides: Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).
- 개발 환경: Visual Studio와 같은 .NET에 적합한 개발 환경을 컴퓨터에 설정하십시오.
## 네임스페이스 가져오기
.NET 애플리케이션에서 Aspose.Slides 기능에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작하세요.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## 1단계: 프레젠테이션 설정
작업하려는 PowerPoint 프레젠테이션 파일을 나타내는 프레젠테이션 클래스를 인스턴스화하는 것부터 시작하세요.
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // 썸네일 생성을 위한 코드는 여기에 있습니다.
}
```
## 2단계: 실제 크기 이미지 생성
프레젠테이션 블록 내에서 축소판을 생성하려는 모양의 실제 크기 이미지를 만듭니다.
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    //이미지 저장을 위한 코드는 여기에 있습니다.
}
```
## 3단계: 이미지를 디스크에 저장
생성된 이미지를 디스크에 저장하고 형식(이 경우 PNG)을 지정합니다.
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## 결론
축하해요! Aspose.Slides for .NET을 사용하여 모양의 경계가 있는 썸네일을 만드는 방법을 성공적으로 배웠습니다. 이 기능은 프로그래밍 방식으로 PowerPoint 프레젠테이션 내에서 특정 크기의 모양 이미지를 생성해야 할 때 매우 유용할 수 있습니다.
## 자주 묻는 질문
### Q1: Aspose.Slides를 다른 .NET 프레임워크와 함께 사용할 수 있나요?
예, Aspose.Slides는 다양한 .NET 프레임워크와 호환되므로 다양한 유형의 애플리케이션에 통합할 수 있는 유연성을 제공합니다.
### Q2: Aspose.Slides에 사용할 수 있는 평가판이 있습니까?
 예, 평가판을 다운로드하여 Aspose.Slides의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### Q3: Aspose.Slides의 임시 라이선스를 어떻게 얻을 수 있나요?
 다음 사이트를 방문하여 Aspose.Slides에 대한 임시 라이선스를 취득할 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).
### Q4: Aspose.Slides에 대한 추가 지원은 어디서 찾을 수 있나요?
질문이나 도움이 필요하면 Aspose.Slides 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/slides/11).
### Q5: .NET용 Aspose.Slides를 구입할 수 있나요?
 틀림없이! .NET용 Aspose.Slides를 구매하려면 구매 페이지를 방문하세요.[여기](https://purchase.aspose.com/buy).
---
title: Aspose.Slides에서 모양의 경계를 사용하여 썸네일 만들기
linktitle: Aspose.Slides에서 모양의 경계를 사용하여 썸네일 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides의 강력한 기능을 활용해 보세요! 단계별 가이드를 사용하여 경계가 있는 모양 축소판을 쉽게 만드는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/image-and-video-manipulation-in-slides/creating-thumbnail-bounds-shape/
---
## 소개
PowerPoint 프레젠테이션에서 모양의 경계가 있는 축소판 이미지를 생성하기 위한 강력한 솔루션을 찾고 있는 .NET 개발자라면 Aspose.Slides for .NET이 가장 적합한 도구입니다. 이 강력한 라이브러리는 원활한 통합을 제공하므로 PowerPoint 파일에서 중요한 정보를 효율적으로 조작하고 추출할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 모양의 경계가 있는 썸네일을 만드는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  .NET 라이브러리용 Aspose.Slides: 다음에서 .NET 라이브러리용 Aspose.Slides를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/net/).
2. 귀하의 문서 디렉토리: 코드 조각의 "귀하의 문서 디렉토리"를 귀하의 문서 디렉토리에 대한 실제 경로로 바꾸십시오.
## 네임스페이스 가져오기
Aspose.Slides의 기능을 활용하려면 필요한 네임스페이스를 가져오는 것부터 시작하세요. 프로젝트 시작 부분에 다음 코드를 추가합니다.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
이제 포괄적인 이해를 위해 제공된 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 클래스 인스턴스화
```csharp
string dataDir = "Your Documents Directory";
// 프레젠테이션 파일을 나타내는 프레젠테이션 클래스를 인스턴스화합니다.
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // 이제 프리젠테이션 개체를 추가로 조작할 준비가 되었습니다.
}
```
 이 단계에서는 Aspose.Slides를 초기화합니다.`Presentation` PowerPoint 프레젠테이션 파일을 나타내는 클래스입니다. 그만큼`using` 명령문은 블록이 종료되면 리소스가 올바르게 처리되도록 보장합니다.
## 2단계: 바인딩된 모양 이미지 만들기
```csharp
// Appearance 경계 모양 이미지 생성
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
    // 이제 비트맵 객체에는 지정된 경계가 있는 축소판 이미지가 포함됩니다.
}
```
 이 단계에는 지정된 경계가 있는 모양의 축소판 이미지를 만드는 작업이 포함됩니다. 여기,`ShapeThumbnailBounds.Appearance`모양 경계를 정의하는 데 사용됩니다. 요구 사항에 따라 매개변수(1, 1)를 조정합니다.
## 3단계: 이미지를 디스크에 저장
```csharp
// 이미지를 PNG 형식으로 디스크에 저장
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```
이 마지막 단계에서 생성된 축소판 이미지는 PNG 형식으로 디스크에 저장됩니다. 기본 설정에 따라 파일 이름과 형식을 사용자 정의할 수 있습니다.
이제 .NET용 Aspose.Slides를 사용하여 모양의 경계가 있는 썸네일을 성공적으로 만들었습니다! 이 프로세스는 효율적이며 PowerPoint 프레젠테이션 처리를 위해 .NET 프로젝트에 원활하게 통합될 수 있습니다.
## 결론
.NET용 Aspose.Slides는 PowerPoint 프레젠테이션 작업 프로세스를 단순화하여 개발자에게 모양 경계가 있는 썸네일 생성과 같은 작업을 위한 강력한 도구를 제공합니다. 이 단계별 가이드를 따르면 .NET 프로젝트에 이 라이브러리를 효율적으로 활용하는 방법에 대한 통찰력을 얻을 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides는 최신 .NET 프레임워크와 호환됩니까?
예, Aspose.Slides는 최신 .NET 프레임워크 버전과의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.
### 상업용 프로젝트에 Aspose.Slides를 사용할 수 있나요?
전적으로! Aspose.Slides는 개인용 및 상업용 모두에 대한 라이센스 옵션을 제공합니다. 방문하다[여기](https://purchase.aspose.com/buy) 라이선스 세부정보를 살펴보세요.
### Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/) 구매하기 전에 기능을 살펴보세요.
### Aspose.Slides에 대한 지원은 어떻게 받을 수 있나요?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티와 연결하고 숙련된 개발자의 도움을 구하세요.
### Aspose.Slides에 대한 임시 라이선스를 얻을 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/) 단기 프로젝트 요구에 적합합니다.
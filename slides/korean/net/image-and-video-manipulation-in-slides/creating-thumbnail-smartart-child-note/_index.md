---
title: Aspose.Slides에서 SmartArt 하위 노트의 썸네일 만들기
linktitle: Aspose.Slides에서 SmartArt 하위 노트의 썸네일 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 매력적인 SmartArt Child Note 썸네일을 만드는 방법을 알아보세요. 역동적인 시각적 요소로 프레젠테이션을 향상시키세요!
weight: 15
url: /ko/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides에서 SmartArt 하위 노트의 썸네일 만들기

## 소개
동적 프레젠테이션 영역에서 .NET용 Aspose.Slides는 개발자에게 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하고 향상시킬 수 있는 기능을 제공하는 강력한 도구로 돋보입니다. 흥미로운 기능 중 하나는 SmartArt Child Notes의 축소판을 생성하여 프레젠테이션에 시각적 매력을 더해주는 기능입니다. 이 단계별 가이드는 Aspose.Slides for .NET을 사용하여 SmartArt Child Notes의 썸네일을 만드는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET용 Aspose.Slides: Aspose.Slides 라이브러리가 .NET 프로젝트에 통합되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드하십시오.[릴리스 페이지](https://releases.aspose.com/slides/net/).
- 개발 환경: 작동하는 .NET 개발 환경을 설정하고 C# 프로그래밍에 대한 기본 지식을 갖추고 있습니다.
- 샘플 프레젠테이션: 테스트용 하위 노트가 포함된 SmartArt가 포함된 PowerPoint 프레젠테이션을 만들거나 얻습니다.
## 네임스페이스 가져오기
필요한 네임스페이스를 C# 프로젝트로 가져오는 것부터 시작하세요. 이러한 네임스페이스는 Aspose.Slides 작업에 필요한 클래스 및 메서드에 대한 액세스를 제공합니다.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## 1단계: 프레젠테이션 클래스 인스턴스화
 인스턴스화부터 시작하세요.`Presentation` 작업할 PPTX 파일을 나타내는 클래스입니다.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## 2단계: SmartArt 추가
 이제 프레젠테이션 내의 슬라이드에 SmartArt를 추가합니다. 이 예에서는`BasicCycle` 공들여 나열한 것.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## 3단계: 노드 참조 얻기
SmartArt의 특정 노드로 작업하려면 해당 인덱스를 사용하여 참조를 얻으세요.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## 4단계: 썸네일 가져오기
SmartArt 노드 내에서 하위 노트의 축소판 이미지를 검색합니다.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## 5단계: 썸네일 저장
생성된 썸네일 이미지를 지정된 디렉터리에 저장합니다.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
프레젠테이션의 각 SmartArt 노드에 대해 이 단계를 반복하여 필요에 따라 레이아웃과 스타일을 사용자 지정합니다.
## 결론
결론적으로 Aspose.Slides for .NET은 개발자가 매력적인 프레젠테이션을 쉽게 만들 수 있도록 지원합니다. SmartArt Child Notes의 축소판을 생성하는 기능은 프레젠테이션의 시각적 매력을 향상시켜 역동적이고 대화형 사용자 경험을 제공합니다.
## 자주 묻는 질문
### Q: 생성된 썸네일의 크기와 형식을 사용자 정의할 수 있나요?
A: 예, 코드에서 해당 매개변수를 수정하여 썸네일의 크기와 형식을 조정할 수 있습니다.
### Q: Aspose.Slides는 다른 SmartArt 레이아웃을 지원합니까?
답: 물론이죠! Aspose.Slides는 다양한 SmartArt 레이아웃을 제공하므로 프레젠테이션 요구 사항에 가장 적합한 레이아웃을 선택할 수 있습니다.
### Q: 테스트 목적으로 임시 라이센스를 사용할 수 있습니까?
 A: 예, 다음에서 임시 라이센스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 테스트 및 평가를 위해.
### Q: 어디서 도움을 구하거나 Aspose.Slides 커뮤니티에 연결할 수 있나요?
 답: 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티에 참여하고, 질문하고, 해결책을 찾으세요.
### Q: .NET용 Aspose.Slides를 구입할 수 있나요?
 답: 물론이죠! 구매 옵션 살펴보기[여기](https://purchase.aspose.com/buy) 프로젝트에서 Aspose.Slides의 잠재력을 최대한 활용하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

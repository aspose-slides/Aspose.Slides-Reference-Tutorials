---
title: PowerPoint에서 ActiveX 컨트롤을 통해 비디오 연결
linktitle: ActiveX 컨트롤을 통해 비디오 연결
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 비디오를 PowerPoint 슬라이드에 연결하는 방법을 알아보세요. 이 단계별 가이드에는 연결된 비디오를 사용하여 대화형의 매력적인 프레젠테이션을 만들기 위한 소스 코드와 팁이 포함되어 있습니다.
weight: 12
url: /ko/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 ActiveX 컨트롤을 통해 비디오 연결

.NET용 Aspose.Slides를 사용하여 프레젠테이션에서 ActiveX 컨트롤을 통해 비디오 연결

.NET용 Aspose.Slides에서는 ActiveX 컨트롤을 사용하여 비디오를 프레젠테이션 슬라이드에 프로그래밍 방식으로 연결할 수 있습니다. 이를 통해 슬라이드 내에서 비디오 콘텐츠를 직접 재생할 수 있는 대화형 프레젠테이션을 만들 수 있습니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 비디오를 프레젠테이션 슬라이드에 연결하는 과정을 안내합니다.

## 전제 조건:
- Visual Studio(또는 기타 .NET 개발 환경)
-  .NET 라이브러리용 Aspose.Slides. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

## 1단계: 새 프로젝트 만들기
선호하는 .NET 개발 환경(예: Visual Studio)에서 새 프로젝트를 만들고 .NET용 Aspose.Slides 라이브러리에 대한 참조를 추가하세요.

## 2단계: 필요한 네임스페이스 가져오기
프로젝트에서 Aspose.Slides 작업에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## 3단계: 프레젠테이션 로드
연결된 비디오를 추가하려는 PowerPoint 프레젠테이션을 로드합니다.

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // 연결된 동영상을 추가하는 코드가 여기에 표시됩니다.
}
```

## 4단계: ActiveX 컨트롤 추가
 인스턴스를 생성합니다.`IOleObjectFrame` 슬라이드에 ActiveX 컨트롤을 추가하는 인터페이스:

```csharp
ISlide slide = presentation.Slides[0]; // 비디오를 추가하려는 슬라이드를 선택하십시오
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

위 코드에서는 640x480 크기의 ActiveX 컨트롤 프레임을 슬라이드에 추가합니다. 비디오 삽입에 일반적으로 사용되는 ShockwaveFlash ActiveX 컨트롤의 ProgID를 지정합니다.

## 5단계: ActiveX 컨트롤 속성 설정
연결된 비디오 소스를 지정하려면 ActiveX 컨트롤의 속성을 설정하세요.

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // 실제 영상 파일 경로로 교체
oleObjectFrame.AlternativeText = "Linked Video";
```

 바꾸다`"YourVideoPathHere"` 비디오 파일의 실제 경로와 함께. 그만큼`AlternativeText` 속성은 링크된 비디오에 대한 설명을 제공합니다.

## 6단계: 프레젠테이션 저장
수정된 프레젠테이션을 저장합니다.

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## 자주 묻는 질문:

### 슬라이드에 링크된 동영상의 크기와 위치를 어떻게 지정하나요?
매개변수를 사용하여 ActiveX 제어 프레임의 크기와 위치를 조정할 수 있습니다.`AddOleObjectFrame` 방법. 4개의 숫자 인수는 각각 왼쪽 상단 모서리의 X 및 Y 좌표와 프레임의 너비 및 높이를 나타냅니다.

### 이 접근 방식을 사용하여 다양한 형식의 비디오를 연결할 수 있습니까?
예, 해당 형식에 적합한 ActiveX 컨트롤을 사용할 수 있는 한 다양한 형식의 비디오를 연결할 수 있습니다. 예를 들어, 이 가이드에 사용된 ShockwaveFlash ActiveX 컨트롤은 Flash 비디오(SWF)에 적합합니다. 다른 형식의 경우 다른 ProgID를 사용해야 할 수도 있습니다.

### 링크된 영상의 크기에 제한이 있나요?
연결된 비디오의 크기는 프레젠테이션의 전체 크기와 성능에 영향을 미칠 수 있습니다. 비디오를 프레젠테이션에 연결하기 전에 웹 재생에 맞게 최적화하는 것이 좋습니다.

### 결론:
이 가이드에 설명된 단계를 따르면 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 ActiveX 컨트롤을 통해 비디오를 쉽게 연결할 수 있습니다. 이 기능을 사용하면 멀티미디어 콘텐츠를 원활하게 통합하는 매력적인 대화형 프레젠테이션을 만들 수 있습니다.

 자세한 내용과 고급 옵션은 다음을 참조하세요.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

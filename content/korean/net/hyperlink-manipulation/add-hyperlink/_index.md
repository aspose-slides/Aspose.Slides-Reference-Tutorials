---
title: Aspose.Slides를 사용하여 .NET의 슬라이드에 하이퍼링크 추가
linktitle: 슬라이드에 하이퍼링크 추가
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에 하이퍼링크를 추가하는 방법을 알아보세요. 대화형 요소로 프레젠테이션을 향상시키세요.
type: docs
weight: 12
url: /ko/net/hyperlink-manipulation/add-hyperlink/
---

디지털 프레젠테이션의 세계에서는 상호작용이 핵심입니다. 슬라이드에 하이퍼링크를 추가하면 프레젠테이션을 더욱 매력적이고 유익하게 만들 수 있습니다. Aspose.Slides for .NET은 PowerPoint 프레젠테이션을 프로그래밍 방식으로 생성, 수정 및 조작할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 슬라이드에 하이퍼링크를 추가하는 방법을 보여줍니다. 

## 전제조건

슬라이드에 하이퍼링크를 추가하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Visual Studio: .NET 코드를 작성하고 실행하려면 컴퓨터에 Visual Studio가 설치되어 있어야 합니다.

2. .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

3. 기본 C# 지식: C# 프로그래밍에 익숙하면 도움이 됩니다.

## 네임스페이스 가져오기

시작하려면 C# 프로젝트에서 필요한 네임스페이스를 가져와야 합니다. 이 경우 Aspose.Slides 라이브러리에서 다음 네임스페이스가 필요합니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

이제 슬라이드에 하이퍼링크를 추가하는 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: 프레젠테이션 초기화

먼저 Aspose.Slides를 사용하여 새 프레젠테이션을 만듭니다. 방법은 다음과 같습니다.

```csharp
using (Presentation presentation = new Presentation())
{
    // 귀하의 코드는 여기에 있습니다
}
```

이 코드는 새 PowerPoint 프레젠테이션을 초기화합니다.

## 2단계: 텍스트 프레임 추가

이제 슬라이드에 텍스트 프레임을 추가해 보겠습니다. 이 텍스트 프레임은 슬라이드에서 클릭 가능한 요소로 사용됩니다. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

위의 코드는 직사각형 자동 모양을 만들고 "Aspose: File Format APIs"라는 텍스트가 있는 텍스트 프레임을 추가합니다.

## 3단계: 하이퍼링크 추가

다음으로, 생성한 텍스트 프레임에 하이퍼링크를 추가해 보겠습니다. 그러면 텍스트를 클릭할 수 있게 됩니다.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

이 단계에서는 하이퍼링크 URL을 "https://www.aspose.com/"으로 설정하고 추가 정보에 대한 툴팁을 제공합니다. 위에 표시된 대로 하이퍼링크 모양의 형식을 지정할 수도 있습니다.

## 4단계: 프레젠테이션 저장

마지막으로 추가된 하이퍼링크를 사용하여 프레젠테이션을 저장합니다.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

이 코드는 프레젠테이션을 "presentation-out.pptx"로 저장합니다.

이제 Aspose.Slides for .NET을 사용하여 슬라이드에 하이퍼링크를 성공적으로 추가했습니다.

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션의 슬라이드에 하이퍼링크를 추가하는 방법을 살펴보았습니다. 다음 단계를 수행하면 추가 리소스나 정보에 대한 귀중한 링크를 제공하여 프레젠테이션을 더욱 상호 작용적이고 매력적으로 만들 수 있습니다.

 더 자세한 정보와 문서를 보려면 다음을 방문하세요.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### 1. 텍스트 프레임 외에 다른 도형에 하이퍼링크를 추가할 수 있나요?

예, .NET용 Aspose.Slides를 사용하여 직사각형, 이미지 등과 같은 다양한 모양에 하이퍼링크를 추가할 수 있습니다.

### 2. PowerPoint 슬라이드의 도형에서 하이퍼링크를 제거하려면 어떻게 해야 합니까?

 다음을 설정하여 도형에서 하이퍼링크를 제거할 수 있습니다.`HyperlinkClick` 재산`null`.

### 3. 내 코드에서 하이퍼링크 URL을 동적으로 변경할 수 있습니까?

 전적으로! 코드의 어느 지점에서나 하이퍼링크의 URL을 수정하여 업데이트할 수 있습니다.`Hyperlink` 재산.

### 4. Aspose.Slides를 사용하여 PowerPoint 슬라이드에 추가할 수 있는 다른 대화형 요소는 무엇입니까?

Aspose.Slides는 작업 버튼, 멀티미디어 요소, 애니메이션을 포함한 광범위한 대화형 기능을 제공합니다.

### 5. Aspose.Slides를 다른 프로그래밍 언어에서도 사용할 수 있나요?

예, Aspose.Slides는 Java 및 Python을 포함한 다양한 프로그래밍 언어에서 사용할 수 있습니다.
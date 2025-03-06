---
title: Aspose.Slides의 하이퍼링크 조작
linktitle: Aspose.Slides의 하이퍼링크 조작
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides에서 하이퍼링크를 추가하고 제거하는 방법을 알아보세요. 대화형 링크를 사용하여 프레젠테이션을 쉽게 향상하세요.
weight: 10
url: /ko/net/hyperlink-manipulation/hyperlink-manipulation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


하이퍼링크는 슬라이드 간을 이동하거나 외부 리소스에 액세스할 수 있는 편리한 방법을 제공하므로 프레젠테이션의 필수 요소입니다. .NET용 Aspose.Slides는 프레젠테이션 슬라이드에 하이퍼링크를 추가하고 제거하는 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 하이퍼링크를 조작하는 과정을 안내합니다. 슬라이드에 하이퍼링크를 추가하고 슬라이드에서 하이퍼링크를 제거하는 방법을 다루겠습니다. 그럼, 뛰어 들어 봅시다!

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치 및 설정되어 있어야 합니다. 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/slides/net/) 그리고 에서 다운로드하세요[이 링크](https://releases.aspose.com/slides/net/).

2. 문서 디렉토리: 프리젠테이션 파일을 저장할 디렉토리가 필요합니다. 코드에서 이 디렉터리의 경로를 지정해야 합니다.

3. C#에 대한 기본 지식: 이 자습서에서는 사용자가 C# 프로그래밍에 대한 기본 지식을 가지고 있다고 가정합니다.

이제 전제 조건이 준비되었으므로 .NET용 Aspose.Slides를 사용하여 하이퍼링크 조작을 위한 단계별 가이드로 넘어가겠습니다.

## 슬라이드에 하이퍼링크 추가

### 1단계: 프레젠테이션 초기화

시작하려면 Aspose.Slides를 사용하여 프레젠테이션을 초기화해야 합니다. 다음 코드를 사용하여 이 작업을 수행할 수 있습니다.

```csharp
using (Presentation presentation = new Presentation())
{
    // 여기에 귀하의 코드가 있습니다
}
```

### 2단계: 텍스트 프레임 추가

이제 슬라이드에 텍스트 프레임을 추가해 보겠습니다. 이 코드는 텍스트가 포함된 직사각형 모양을 만듭니다.

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

### 3단계: 하이퍼링크 추가

다음으로, 만든 도형의 텍스트에 하이퍼링크를 추가합니다. 방법은 다음과 같습니다.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

### 4단계: 프레젠테이션 저장

마지막으로 추가된 하이퍼링크를 사용하여 프레젠테이션을 저장합니다.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

축하해요! Aspose.Slides for .NET을 사용하여 슬라이드에 하이퍼링크를 성공적으로 추가했습니다.

## 슬라이드에서 하이퍼링크 제거

### 1단계: 프레젠테이션 초기화

슬라이드에서 하이퍼링크를 제거하려면 기존 프레젠테이션을 열어야 합니다.

```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Hyperlink.pptx");
```

### 2단계: 하이퍼링크 제거

이제 다음 코드를 사용하여 프레젠테이션에서 모든 하이퍼링크를 제거합니다.

```csharp
presentation.HyperlinkQueries.RemoveAllHyperlinks();
```

### 3단계: 프레젠테이션 저장

하이퍼링크를 제거한 후 프레젠테이션을 저장합니다.

```csharp
presentation.Save(dataDir + "RemovedHyperlink_out.pptx", SaveFormat.Pptx);
```

그리고 그게 다야! .NET용 Aspose.Slides를 사용하여 슬라이드에서 하이퍼링크를 성공적으로 제거했습니다.

결론적으로 .NET용 Aspose.Slides는 프레젠테이션의 하이퍼링크를 조작하는 효율적인 방법을 제공하여 대화형의 매력적인 슬라이드를 만들 수 있도록 해줍니다. 외부 리소스에 하이퍼링크를 추가하거나 제거하려는 경우 Aspose.Slides는 프로세스를 단순화하고 프레젠테이션 작성 기능을 향상시킵니다.

 .NET용 Aspose.Slides의 하이퍼링크 조작에 대한 이 튜토리얼에 참여해 주셔서 감사합니다. 질문이 있거나 추가 지원이 필요한 경우 언제든지 다음을 탐색해 보세요.[Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 또는 Aspose 커뮤니티에 문의하세요.[지원 포럼](https://forum.aspose.com/).

---

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션의 하이퍼링크를 조작하는 방법을 배웠습니다. 동적 및 대화형 프레젠테이션을 만들 수 있도록 하는 하이퍼링크의 추가 및 제거에 대해 모두 다루었습니다. Aspose.Slides는 프로세스를 단순화하여 외부 리소스에 대한 하이퍼링크를 통해 슬라이드를 쉽게 향상시킬 수 있습니다.

Aspose.Slides 작업이나 프리젠테이션 디자인의 다른 측면에 대해 더 궁금한 점이 있으신가요? 더 많은 통찰력을 얻으려면 아래 FAQ를 확인하세요.

## FAQ(자주 묻는 질문)

### .NET용 Aspose.Slides를 사용하면 어떤 주요 이점이 있나요?
.NET용 Aspose.Slides는 프레젠테이션 생성, 조작 및 변환을 위한 광범위한 기능을 제공합니다. 슬라이드에 콘텐츠, 애니메이션 및 상호 작용을 추가하기 위한 포괄적인 도구 세트를 제공합니다.

### Aspose.Slides에서 텍스트가 아닌 개체에 하이퍼링크를 추가할 수 있나요?
예, Aspose.Slides를 사용하면 모양, 이미지, 텍스트를 포함한 다양한 개체에 하이퍼링크를 추가할 수 있어 대화형 프레젠테이션을 만드는 데 유연성을 제공합니다.

### Aspose.Slides는 다른 PowerPoint 파일 형식과 호환됩니까?
전적으로. Aspose.Slides는 PPT, PPTX, PPS 등을 포함한 다양한 PowerPoint 형식을 지원합니다. 다양한 버전의 Microsoft PowerPoint와의 호환성을 보장합니다.

### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 심층적인 문서 및 커뮤니티 지원을 보려면 다음을 방문하세요.[Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 그리고[Aspose 지원 포럼](https://forum.aspose.com/).

### Aspose.Slides의 임시 라이선스를 어떻게 얻을 수 있나요?
 Aspose.Slides에 대한 임시 라이선스가 필요한 경우 라이선스를 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

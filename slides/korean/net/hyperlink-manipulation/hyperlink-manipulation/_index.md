---
"description": "Aspose.Slides for .NET에서 하이퍼링크를 추가하고 제거하는 방법을 알아보세요. 대화형 링크로 프레젠테이션을 더욱 풍부하게 만들어 보세요."
"linktitle": "Aspose.Slides에서 하이퍼링크 조작"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides에서 하이퍼링크 조작"
"url": "/ko/net/hyperlink-manipulation/hyperlink-manipulation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides에서 하이퍼링크 조작


하이퍼링크는 프레젠테이션에서 필수적인 요소로, 슬라이드 간 이동이나 외부 리소스 접근을 편리하게 해줍니다. Aspose.Slides for .NET은 프레젠테이션 슬라이드에 하이퍼링크를 추가하고 제거하는 강력한 기능을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 하이퍼링크를 조작하는 과정을 안내합니다. 슬라이드에 하이퍼링크를 추가하고 제거하는 방법도 다룹니다. 자, 시작해 볼까요!

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. Aspose.Slides for .NET: Aspose.Slides for .NET 라이브러리가 설치 및 설정되어 있어야 합니다. 관련 문서는 여기에서 확인할 수 있습니다. [여기](https://reference.aspose.com/slides/net/) 그리고 그것을 다운로드하세요 [이 링크](https://releases.aspose.com/slides/net/).

2. 문서 디렉터리: 프레젠테이션 파일을 저장할 디렉터리가 필요합니다. 코드에 이 디렉터리 경로를 반드시 지정하세요.

3. C#에 대한 기본 지식: 이 튜토리얼에서는 사용자가 C# 프로그래밍에 대한 기본적인 이해가 있다고 가정합니다.

이제 필수 구성 요소를 갖추었으므로 Aspose.Slides for .NET을 사용하여 하이퍼링크를 조작하는 단계별 가이드로 넘어가겠습니다.

## 슬라이드에 하이퍼링크 추가

### 1단계: 프레젠테이션 초기화

시작하려면 Aspose.Slides를 사용하여 프레젠테이션을 초기화해야 합니다. 다음 코드를 사용하면 됩니다.

```csharp
using (Presentation presentation = new Presentation())
{
    // 여기에 코드를 입력하세요
}
```

### 2단계: 텍스트 프레임 추가

이제 슬라이드에 텍스트 프레임을 추가해 보겠습니다. 다음 코드는 텍스트가 있는 사각형 도형을 만듭니다.

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

마지막으로, 추가된 하이퍼링크로 프레젠테이션을 저장합니다.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

축하합니다! Aspose.Slides for .NET을 사용하여 슬라이드에 하이퍼링크를 성공적으로 추가했습니다.

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

이제 끝났습니다! Aspose.Slides for .NET을 사용하여 슬라이드에서 하이퍼링크를 성공적으로 제거했습니다.

결론적으로, Aspose.Slides for .NET은 프레젠테이션의 하이퍼링크를 효율적으로 조작하여 인터랙티브하고 매력적인 슬라이드를 제작할 수 있도록 지원합니다. 외부 리소스에 하이퍼링크를 추가하거나 삭제할 때 Aspose.Slides는 프로세스를 간소화하고 프레젠테이션 제작 역량을 향상시켜 줍니다.

Aspose.Slides for .NET에서 하이퍼링크를 조작하는 방법에 대한 이 튜토리얼에 참여해 주셔서 감사합니다. 질문이 있거나 추가 도움이 필요하시면 언제든지 문의해 주세요. [Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 또는 Aspose 커뮤니티에 연락하세요. [지원 포럼](https://forum.aspose.com/).

---

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 하이퍼링크를 조작하는 방법을 알아보았습니다. 하이퍼링크 추가 및 제거 방법을 모두 다루어 동적이고 인터랙티브한 프레젠테이션을 만들 수 있었습니다. Aspose.Slides는 이 과정을 간소화하여 외부 리소스에 대한 하이퍼링크를 통해 슬라이드를 더욱 쉽게 개선할 수 있도록 지원합니다.

Aspose.Slides 사용이나 프레젠테이션 디자인의 다른 측면에 대해 더 궁금한 점이 있으신가요? 아래 FAQ에서 더 자세한 정보를 확인하세요.

## FAQ(자주 묻는 질문)

### .NET에서 Aspose.Slides를 사용하는 주요 장점은 무엇입니까?
Aspose.Slides for .NET은 프레젠테이션을 제작, 조작 및 변환하는 데 필요한 다양한 기능을 제공합니다. 슬라이드에 콘텐츠, 애니메이션, 인터랙션을 추가할 수 있는 포괄적인 도구 세트를 제공합니다.

### Aspose.Slides에서 텍스트 이외의 객체에 하이퍼링크를 추가할 수 있나요?
네, Aspose.Slides를 사용하면 도형, 이미지, 텍스트 등 다양한 개체에 하이퍼링크를 추가할 수 있어 대화형 프레젠테이션을 유연하게 만들 수 있습니다.

### Aspose.Slides는 다양한 PowerPoint 파일 형식과 호환됩니까?
물론입니다. Aspose.Slides는 PPT, PPTX, PPS 등 다양한 PowerPoint 형식을 지원합니다. 또한 다양한 버전의 Microsoft PowerPoint와도 호환됩니다.

### Aspose.Slides에 대한 추가 리소스와 지원은 어디에서 찾을 수 있나요?
자세한 문서와 커뮤니티 지원을 보려면 다음을 방문하세요. [Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 그리고 [Aspose 지원 포럼](https://forum.aspose.com/).

### Aspose.Slides에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
Aspose.Slides에 대한 임시 라이센스가 필요한 경우 다음을 얻을 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션에 매크로 하이퍼링크를 설정하는 방법을 알아보세요. 상호작용성을 높이고 청중의 참여를 유도하세요."
"linktitle": "매크로를 사용한 하이퍼링크 관리"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides for .NET에서 매크로 하이퍼링크 클릭을 설정하는 방법"
"url": "/ko/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET에서 매크로 하이퍼링크 클릭을 설정하는 방법


현대 소프트웨어 개발 분야에서는 역동적이고 인터랙티브한 프레젠테이션을 만드는 것이 핵심입니다. Aspose.Slides for .NET은 프레젠테이션 작업을 원활하게 수행할 수 있도록 지원하는 강력한 라이브러리입니다. 비즈니스 프레젠테이션이든 교육용 슬라이드쇼든, 매크로 하이퍼링크 클릭 설정 기능은 사용자 경험을 크게 향상시킬 수 있습니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 매크로 하이퍼링크 클릭을 설정하는 과정을 안내합니다. 

## 필수 조건

단계별 튜토리얼을 시작하기 전에 꼭 갖춰야 할 몇 가지 전제 조건이 있습니다.

1. Visual Studio: 개발 환경이 될 Visual Studio가 컴퓨터에 설치되어 있는지 확인하세요.

2. Aspose.Slides for .NET: Aspose.Slides for .NET 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).

3. C#에 대한 기본 지식: 이 튜토리얼을 따라가려면 C# 프로그래밍 언어에 대한 지식이 필수입니다.

## 네임스페이스 가져오기

첫 번째 단계에서는 Aspose.Slides 작업에 필요한 네임스페이스를 가져와 보겠습니다.

### 1단계: 네임스페이스 가져오기

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

우리는 수입했습니다 `Aspose.Slides` 프레젠테이션 작업을 위한 핵심 네임스페이스인 네임스페이스와 `Aspose.Slides.Export` 네임스페이스.

## 매크로 하이퍼링크 클릭 설정

이제 이 튜토리얼의 주요 부분인 프레젠테이션에 매크로 하이퍼링크 클릭을 설정하는 방법으로 넘어가겠습니다.

### 2단계: 프레젠테이션 초기화

먼저, 새로운 프레젠테이션을 초기화해야 합니다.

```csharp
using (Presentation presentation = new Presentation())
{
    // 코드가 여기에 입력됩니다.
}
```

이 using 문 안에서 새로운 프레젠테이션 객체를 만들고 그 안에서 모든 작업을 수행합니다.

### 3단계: 자동 모양 추가

매크로 하이퍼링크 클릭을 설정하려면 사용자가 클릭할 수 있는 개체가 필요합니다. 이 예제에서는 클릭 가능한 요소로 도형을 사용하겠습니다.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

여기서는 특정 좌표(20, 20)에 "BlankButton" 유형의 도형을 만들고, 크기는 80x30입니다. 프레젠테이션 레이아웃에 맞게 이 값을 사용자 지정할 수 있습니다.

### 4단계: 매크로 하이퍼링크 클릭 설정

이제 매크로 하이퍼링크 클릭을 설정하는 단계입니다. 매크로 이름을 매개변수로 입력해야 합니다.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

이 예제에서는 매크로 하이퍼링크 클릭을 "TestMacro"로 설정했습니다. 사용자가 도형을 클릭하면 이 매크로가 실행됩니다.

### 5단계: 정보 검색

설정한 하이퍼링크에 대한 정보를 검색할 수도 있습니다.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

이 코드 줄을 사용하면 외부 URL과 하이퍼링크의 동작 유형을 인쇄할 수 있습니다.

이제 끝났습니다! Aspose.Slides for .NET을 사용하여 프레젠테이션에 매크로 하이퍼링크 클릭을 성공적으로 설정했습니다.

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에 매크로 하이퍼링크 클릭을 설정하는 방법을 알아보았습니다. 이 기능은 청중의 참여를 유도하는 인터랙티브하고 역동적인 프레젠테이션을 제작하는 데 매우 유용합니다. Aspose.Slides for .NET을 사용하면 프레젠테이션 개발을 한 단계 더 발전시킬 수 있는 강력한 도구를 활용할 수 있습니다.

이제 사용자 지정 매크로 하이퍼링크를 사용하여 매력적인 프레젠테이션을 실험하고 만들어 보세요. 자유롭게 살펴보세요. [.NET용 Aspose.Slides 설명서](https://reference.aspose.com/slides/net/) 더욱 자세한 정보와 가능성을 알아보려면.

## FAQ(자주 묻는 질문)

### Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Slides는 주로 .NET용으로 설계되었지만 Aspose는 Java 등 다른 프로그래밍 언어에 대해서도 비슷한 라이브러리를 제공합니다.

### Aspose.Slides for .NET은 무료 라이브러리인가요?
Aspose.Slides for .NET은 무료 평가판이 제공되는 상용 라이브러리입니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/).

### Aspose.Slides for .NET으로 만든 프레젠테이션에서 매크로를 사용하는 데 제한이 있습니까?
.NET용 Aspose.Slides를 사용하면 매크로를 사용하여 작업할 수 있지만 프레젠테이션에서 매크로를 사용할 때 보안 및 호환성을 고려해야 합니다.

### 하이퍼링크에 사용되는 자동 모양의 모양을 사용자 지정할 수 있나요?
네, 크기, 색상, 글꼴 등의 속성을 조정하여 자동 모양의 모양을 사용자 지정할 수 있습니다.

### Aspose.Slides for .NET에 대한 도움이나 지원은 어디에서 받을 수 있나요?
문제가 발생하거나 질문이 있는 경우 Aspose 지원 포럼에서 도움을 요청할 수 있습니다. [여기](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
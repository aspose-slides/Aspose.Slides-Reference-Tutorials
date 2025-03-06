---
title: .NET용 Aspose.Slides에서 매크로 하이퍼링크 클릭을 설정하는 방법
linktitle: 매크로를 이용한 하이퍼링크 관리
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 프레젠테이션에 매크로 하이퍼링크를 설정하는 방법을 알아보세요. 상호작용성을 향상하고 청중의 참여를 유도하세요.
weight: 13
url: /ko/net/hyperlink-manipulation/macro-hyperlink/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


현대 소프트웨어 개발 세계에서는 역동적이고 대화형 프레젠테이션을 만드는 것이 핵심입니다. Aspose.Slides for .NET은 프레젠테이션 작업을 원활하게 수행할 수 있는 강력한 라이브러리입니다. 비즈니스 프리젠테이션을 작성하든 교육용 슬라이드쇼를 작성하든 관계없이 매크로 하이퍼링크 클릭을 설정하는 기능은 사용자 경험을 크게 향상시킬 수 있습니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 매크로 하이퍼링크 클릭을 설정하는 과정을 안내합니다. 

## 전제 조건

단계별 튜토리얼을 시작하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.

1.Visual Studio: Visual Studio가 개발 환경이므로 컴퓨터에 Visual Studio가 설치되어 있는지 확인하세요.

 2.Aspose.Slides for .NET: Aspose.Slides for .NET 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

3. C#에 대한 기본 지식: 이 튜토리얼을 진행하려면 C# 프로그래밍 언어에 대한 지식이 필수적입니다.

## 네임스페이스 가져오기

첫 번째 단계에서는 Aspose.Slides를 사용하는 데 필요한 네임스페이스를 가져옵니다.

### 1단계: 네임스페이스 가져오기

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 우리는`Aspose.Slides` 프레젠테이션 작업을 위한 핵심 네임스페이스인 네임스페이스와`Aspose.Slides.Export` 네임스페이스.

## 매크로 하이퍼링크 클릭 설정

이제 이 튜토리얼의 주요 부분인 프레젠테이션에서 매크로 하이퍼링크 클릭 설정으로 넘어가겠습니다.

### 2단계: 프레젠테이션 초기화

먼저 새 프레젠테이션을 초기화해야 합니다.

```csharp
using (Presentation presentation = new Presentation())
{
    // 귀하의 코드가 여기에 표시됩니다.
}
```

이 using 문 내에서 새 프레젠테이션 개체를 만들고 그 안에서 모든 작업을 수행합니다.

### 3단계: 도형 추가

매크로 하이퍼링크 클릭을 설정하려면 사용자가 클릭할 수 있는 개체가 필요합니다. 이 예에서는 클릭 가능한 요소로 AutoShape를 사용합니다.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

여기서는 특정 좌표(20, 20)에 80x30 크기의 "BlankButton" 유형을 사용하여 도형을 만듭니다. 프레젠테이션 레이아웃에 맞게 이러한 값을 사용자 정의할 수 있습니다.

### 4단계: 매크로 하이퍼링크 클릭 설정

이제 매크로 하이퍼링크 클릭을 설정하는 부분이 나옵니다. 매크로 이름을 매개변수로 제공해야 합니다.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

이 예에서는 매크로 하이퍼링크 클릭을 "TestMacro"로 설정했습니다. 사용자가 도형을 클릭하면 이 매크로가 트리거됩니다.

### 5단계: 정보 검색

또한 설정한 하이퍼링크에 대한 정보를 검색할 수도 있습니다.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

이러한 코드 줄을 사용하면 외부 URL과 하이퍼링크의 작업 유형을 인쇄할 수 있습니다.

그리고 그게 다야! .NET용 Aspose.Slides를 사용하여 프레젠테이션에서 매크로 하이퍼링크 클릭을 성공적으로 설정했습니다.

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 매크로 하이퍼링크 클릭을 설정하는 방법을 배웠습니다. 이는 청중의 참여를 유도하는 대화형 및 동적 프레젠테이션을 만드는 데 유용한 기능이 될 수 있습니다. .NET용 Aspose.Slides를 사용하면 프레젠테이션 개발을 한 단계 더 발전시킬 수 있는 강력한 도구를 갖게 됩니다.

 이제 사용자 정의 매크로 하이퍼링크를 사용하여 매력적인 프레젠테이션을 실험하고 만들 차례입니다. 자유롭게 탐색해 보세요.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/) 더 자세한 정보와 가능성을 확인하세요.

## FAQ(자주 묻는 질문)

### Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Slides는 주로 .NET용으로 설계되었지만 Aspose는 Java와 같은 다른 프로그래밍 언어에도 유사한 라이브러리를 제공합니다.

### .NET용 Aspose.Slides는 무료 라이브러리인가요?
Aspose.Slides for .NET은 무료 평가판을 사용할 수 있는 상용 라이브러리입니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).

### Aspose.Slides for .NET으로 만든 프레젠테이션에서 매크로를 사용하는 데 제한이 있나요?
.NET용 Aspose.Slides를 사용하면 매크로 작업이 가능하지만 프레젠테이션에서 매크로를 사용할 때는 보안 및 호환성 고려 사항에 유의해야 합니다.

### 하이퍼링크에 사용되는 도형의 모양을 사용자 정의할 수 있습니까?
예, 크기, 색상, 글꼴 등의 속성을 조정하여 도형의 모양을 사용자 정의할 수 있습니다.

### .NET용 Aspose.Slides에 대한 도움말이나 지원은 어디서 얻을 수 있나요?
 문제가 발생하거나 질문이 있는 경우 Aspose 지원 포럼에서 도움을 구할 수 있습니다.[여기](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: .NET용 Aspose.Slides에서 변경 가능한 하이퍼링크 생성
linktitle: 가변 하이퍼링크 생성
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 변경 가능한 하이퍼링크로 PowerPoint 프레젠테이션을 향상하세요. 이전과는 전혀 다른 방식으로 청중의 참여를 유도하세요!
weight: 14
url: /ko/net/hyperlink-manipulation/mutable-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Slides에서 변경 가능한 하이퍼링크 생성


현대 소프트웨어 개발 세계에서는 대화형 하이퍼링크를 사용하여 역동적인 프레젠테이션을 만드는 것이 청중의 관심을 끄는 데 매우 중요합니다. Aspose.Slides for .NET은 변경 가능한 하이퍼링크 생성을 포함하여 PowerPoint 프레젠테이션을 조작하고 사용자 정의할 수 있는 강력한 도구입니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 변경 가능한 하이퍼링크를 만드는 과정을 안내합니다. 

## 전제 조건

변경 가능한 하이퍼링크의 세계로 뛰어들기 전에 갖춰야 할 몇 가지 전제 조건이 있습니다.

### 1. .NET용 Aspose.Slides
 개발 환경에 Aspose.Slides for .NET이 설치 및 설정되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/slides/net/).

### 2. .NET 프레임워크
컴퓨터에 .NET Framework가 설치되어 있는지 확인하세요. .NET용 Aspose.Slides가 작동하려면 .NET Framework가 필요합니다.

### 3. 통합 개발 환경(IDE)
.NET 코드를 작성하고 실행하려면 Visual Studio와 같은 IDE가 필요합니다.

이제 필요한 전제 조건이 준비되었으므로 .NET용 Aspose.Slides에서 변경 가능한 하이퍼링크를 만드는 방법으로 넘어갑니다.

## 가변 하이퍼링크 생성

### 1단계: 프로젝트 설정
먼저 새 프로젝트를 만들거나 IDE에서 기존 프로젝트를 엽니다. 프로젝트에서 Aspose.Slides for .NET이 올바르게 참조되었는지 확인하세요.

### 2단계: 네임스페이스 가져오기
코드 파일에서 Aspose.Slides 작업에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Shape;
```

### 3단계: 새 프레젠테이션 만들기
새 PowerPoint 프레젠테이션을 만들려면 다음 코드를 사용하세요.

```csharp
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation())
{
    // 프레젠테이션을 만들고 조작하기 위한 코드가 여기에 있습니다.
    presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
}
```

### 4단계: 하이퍼링크 도형 추가
이제 하이퍼링크를 사용하여 프레젠테이션에 도형을 추가해 보겠습니다. 이 예에서는 Aspose 웹사이트에 대한 하이퍼링크가 있는 직사각형 모양을 만듭니다.

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

이 단계에서는 "Aspose: File Format APIs"라는 텍스트와 클릭 가능한 하이퍼링크가 있는 직사각형 모양을 추가했습니다. 필요에 따라 모양, 텍스트, 하이퍼링크를 사용자 정의할 수 있습니다.

### 5단계: 프레젠테이션 저장
마지막으로 다음 코드를 사용하여 프레젠테이션을 파일에 저장합니다.

```csharp
presentation.Save(dataDir + "presentation-out.pptx", SaveFormat.Pptx);
```

이제 변경 가능한 하이퍼링크 프레젠테이션이 준비되었습니다!

## 결론

.NET용 Aspose.Slides를 사용하면 PowerPoint 프레젠테이션에서 변경 가능한 하이퍼링크를 쉽게 만들 수 있습니다. 이 가이드에 설명된 간단한 단계를 통해 청중의 관심을 끄는 역동적이고 대화형 프레젠테이션을 만들 수 있습니다. 기업 프레젠테이션이나 교육 자료를 작업하는 개발자라면 Aspose.Slides를 사용하면 쉽게 하이퍼링크를 추가하고 콘텐츠를 향상시킬 수 있습니다.

 더 자세한 정보와 문서를 보려면 다음을 참조하세요.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### 1. Aspose.Slides for .NET은 어떤 버전의 .NET Framework를 지원합니까?
.NET용 Aspose.Slides는 2.0, 3.5, 4.x 등을 포함한 여러 버전의 .NET Framework를 지원합니다.

### 2. Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 외부 웹사이트에 대한 하이퍼링크를 만들 수 있나요?
예, 이 가이드에 설명된 대로 외부 웹사이트에 대한 하이퍼링크를 만들 수 있습니다. .NET용 Aspose.Slides를 사용하면 웹 페이지, 파일 또는 기타 리소스에 연결할 수 있습니다.

### 3. Aspose.Slides for .NET에 사용할 수 있는 라이선스 옵션이 있습니까?
 예, Aspose는 다양한 사용 사례에 대한 라이선스 옵션을 제공합니다. 라이선스를 살펴보고 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy) 아니면 임시면허를 취득하세요.[여기](https://purchase.aspose.com/temporary-license/).

### 4. 프레젠테이션의 하이퍼링크 모양을 사용자 정의할 수 있습니까?
전적으로. .NET용 Aspose.Slides는 텍스트, 색상, 스타일을 포함하여 하이퍼링크 모양을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.

### 5. Aspose.Slides for .NET은 대화형 e-러닝 콘텐츠 제작에 적합합니까?
예, Aspose.Slides for .NET은 하이퍼링크, 퀴즈 및 멀티미디어 요소를 포함한 대화형 e-러닝 콘텐츠를 만드는 데 사용할 수 있는 다목적 도구입니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

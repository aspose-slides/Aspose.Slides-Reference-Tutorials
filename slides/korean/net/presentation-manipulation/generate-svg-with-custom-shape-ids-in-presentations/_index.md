---
title: 프레젠테이션에서 사용자 정의 모양 ID를 사용하여 SVG 생성
linktitle: 프레젠테이션에서 사용자 정의 모양 ID를 사용하여 SVG 생성
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 사용자 정의 SVG 모양과 ID로 매력적인 프레젠테이션을 생성하세요. 소스 코드 예제를 통해 대화형 슬라이드를 만드는 방법을 단계별로 알아보세요. 프레젠테이션의 시각적 매력과 사용자 상호 작용을 향상합니다.
weight: 19
url: /ko/net/presentation-manipulation/generate-svg-with-custom-shape-ids-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프레젠테이션에서 사용자 정의 모양 ID를 사용하여 SVG 생성


.NET용 Aspose.Slides의 강력한 기능을 활용하여 사용자 정의 모양 ID가 있는 SVG 파일을 생성하려고 하시나요? 당신은 바로 이곳에 있습니다! 이 단계별 튜토리얼에서는 다음 소스 코드 조각을 사용하여 프로세스를 안내합니다. 이 과정을 마치면 프레젠테이션에서 사용자 정의 모양 ID가 포함된 SVG 파일을 만들 수 있는 준비가 완료됩니다.

### 시작하기

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET용 Aspose.Slides: Aspose.Slides 라이브러리가 설치되어 있고 사용할 준비가 되었는지 확인하세요.

2. 샘플 프리젠테이션: SVG로 내보내려는 모양이 포함된 프리젠테이션 파일(예: "presentation.pptx")이 필요합니다.

3. 출력 디렉터리: SVG 파일을 저장할 디렉터리를 정의합니다(예: "출력 디렉터리").

이제 코드를 단계별로 분석해 보겠습니다.

### 1단계: 환경 설정

이 단계에서는 필요한 변수를 초기화하고 프리젠테이션 파일을 로드합니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // 귀하의 코드는 여기에 있습니다
}
```

 바꾸다`"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 사용하세요.

### 2단계: 도형을 SVG로 작성

이 섹션에서는 프레젠테이션의 모양을 SVG 파일로 작성하겠습니다. 또한 SVG 출력을 더 효과적으로 제어하기 위해 사용자 정의 모양 형식 지정 컨트롤러를 지정합니다.

```csharp
using (FileStream stream = new FileStream(dataDir + "pptxFileName.svg", FileMode.OpenOrCreate))
{
    SVGOptions svgOptions = new SVGOptions
    {
        ShapeFormattingController = new CustomSvgShapeFormattingController()
    };

    pres.Slides[0].WriteAsSvg(stream, svgOptions);
}
```

 꼭 교체하세요`"pptxFileName.svg"` 원하는 출력 파일 이름으로.

### 결론

그리고 거기에 있습니다! .NET용 Aspose.Slides를 사용하여 사용자 정의 모양 ID가 있는 SVG 파일을 성공적으로 생성했습니다. 이 강력한 기능을 사용하면 특정 요구 사항에 맞게 SVG 출력을 사용자 정의할 수 있습니다.

### 자주 묻는 질문

1. ### .NET용 Aspose.Slides란 무엇입니까?
   Aspose.Slides for .NET은 .NET 애플리케이션에서 PowerPoint 프레젠테이션 작업을 위한 강력한 라이브러리입니다. 프로그래밍 방식으로 프레젠테이션을 생성, 편집 및 조작하기 위한 다양한 기능을 제공합니다.

2. ### SVG 생성에서 사용자 정의 모양 형식이 중요한 이유는 무엇입니까?
   사용자 정의 모양 형식을 사용하면 SVG 출력에서 모양의 모양과 속성을 세밀하게 제어할 수 있습니다.

3. ### Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
   Aspose.Slides for .NET은 .NET 애플리케이션용으로 특별히 설계되었습니다. 그러나 Aspose는 다른 플랫폼과 언어에 대한 라이브러리도 제공합니다.

4. ### .NET용 Aspose.Slides를 사용하여 SVG 생성에 제한이 있나요?
   .NET용 Aspose.Slides는 강력한 SVG 생성 기능을 제공하지만 잠재력을 극대화하려면 라이브러리 문서를 이해하는 것이 중요합니다.

5. ### .NET용 Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
    추가 문서를 보려면 다음을 방문하세요.[.NET API 참조용 Aspose.Slides](https://reference.aspose.com/slides/net/).

이제 Aspose.Slides for .NET을 사용하여 SVG 생성의 무한한 가능성을 탐색해 보세요. 즐거운 코딩하세요!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

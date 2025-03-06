---
title: 프리젠테이션에서 도형을 SVG 형식으로 내보내기
linktitle: 프리젠테이션에서 도형을 SVG 형식으로 내보내기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션의 모양을 SVG 형식으로 내보내는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다. 다양한 애플리케이션에 맞게 형상을 효율적으로 추출합니다.
type: docs
weight: 16
url: /ko/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---

오늘날의 디지털 세계에서 프레젠테이션은 정보를 효과적으로 전달하는 데 중요한 역할을 합니다. 그러나 때로는 다양한 목적을 위해 프레젠테이션의 특정 모양을 다른 형식으로 내보내야 하는 경우도 있습니다. 그러한 형식 중 하나가 확장성과 적응성으로 잘 알려진 SVG(Scalable Vector Graphics)입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 모양을 SVG 형식으로 내보내는 과정을 안내합니다.

## 1. 소개

프레젠테이션에는 차트, 다이어그램, 일러스트레이션과 같은 중요한 시각적 요소가 포함되는 경우가 많습니다. 이러한 요소를 SVG 형식으로 내보내면 웹 기반 응용 프로그램, 인쇄 또는 벡터 그래픽 소프트웨어에서의 추가 편집에 유용할 수 있습니다. Aspose.Slides for .NET은 이와 같은 작업을 자동화할 수 있는 강력한 라이브러리입니다.

## 2. 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET용 Aspose.Slides가 설치된 개발 환경입니다.
- 내보내려는 모양이 포함된 PowerPoint 프레젠테이션(PPTX)입니다.
- C# 프로그래밍에 대한 기본 지식.

## 3. 환경 설정

시작하려면 즐겨 사용하는 IDE에서 새 C# 프로젝트를 만듭니다. 프로젝트에서 Aspose.Slides for .NET 라이브러리를 참조했는지 확인하세요.

## 4. 프레젠테이션 로드

C# 코드에서는 프레젠테이션 디렉터리와 SVG 파일의 출력 디렉터리를 지정해야 합니다. 예는 다음과 같습니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
string outSvgFileName = outPath + "SingleShape.svg";

using (Presentation pres = new Presentation(dataDir + "YourPresentation.pptx"))
{
    // 모양을 내보내기 위한 코드가 여기에 들어갑니다.
}
```

## 5. 도형을 SVG로 내보내기

 내`using` 블록을 사용하면 프레젠테이션의 도형에 액세스하여 SVG 형식으로 내보낼 수 있습니다. 여기서는 첫 번째 슬라이드의 첫 번째 도형을 내보내고 있습니다.

```csharp
using (Stream stream = new FileStream(outSvgFileName, FileMode.Create, FileAccess.Write))
{
    pres.Slides[0].Shapes[0].WriteAsSvg(stream);
}
```

이 코드를 사용자 정의하여 다양한 모양을 내보내거나 필요에 따라 추가 변환을 적용할 수 있습니다.

## 6. 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 도형을 SVG 형식으로 내보내는 과정을 살펴보았습니다. 이 강력한 라이브러리는 작업을 단순화하여 내보내기 프로세스를 자동화하고 작업 흐름을 향상시킬 수 있습니다.

## 7. 자주 묻는 질문

### Q1: SVG 형식이란 무엇입니까?

SVG(Scalable Vector Graphics)는 웹 브라우저와의 확장성과 호환성을 위해 널리 사용되는 XML 기반 벡터 이미지 형식입니다.

### Q2: 한 번에 여러 도형을 내보낼 수 있나요?

예, 프레젠테이션의 도형을 반복하여 하나씩 내보낼 수 있습니다.

### Q3: Aspose.Slides for .NET은 유료 라이브러리입니까?

예, .NET용 Aspose.Slides는 무료 평가판이 제공되는 상용 라이브러리입니다.

### Q4: Aspose.Slides로 도형을 내보내는 데 제한이 있나요?

모양을 내보내는 기능은 모양의 복잡성과 라이브러리에서 지원하는 기능에 따라 달라질 수 있습니다.

### Q5: .NET용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?

 당신은 방문 할 수 있습니다[Aspose.Slides 포럼](https://forum.aspose.com/) 지원 및 커뮤니티 토론을 위해.

이제 모양을 SVG 형식으로 내보내는 방법을 배웠으므로 프레젠테이션을 향상하고 다양한 목적에 맞게 더욱 다양하게 만들 수 있습니다. 즐거운 코딩하세요!

 자세한 내용과 고급 기능은 다음을 참조하세요.[.NET API 참조용 Aspose.Slides](https://reference.aspose.com/slides/net/).
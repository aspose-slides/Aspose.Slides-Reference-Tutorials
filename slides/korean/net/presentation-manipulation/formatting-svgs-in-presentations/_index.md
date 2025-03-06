---
title: 프레젠테이션에서 SVG 형식 지정
linktitle: 프레젠테이션에서 SVG 형식 지정
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 멋진 SVG로 프레젠테이션을 최적화하세요. 인상적인 시각적 효과를 위해 SVG 형식을 지정하는 방법을 단계별로 알아보세요. 오늘 프레젠테이션 게임을 한 단계 더 발전시켜 보세요!
weight: 31
url: /ko/net/presentation-manipulation/formatting-svgs-in-presentations/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


눈길을 끄는 SVG 모양으로 프레젠테이션을 향상시키고 싶으십니까? .NET용 Aspose.Slides는 이를 달성하기 위한 최고의 도구가 될 수 있습니다. 이 포괄적인 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 SVG 모양의 형식을 지정하는 과정을 안내합니다. 제공된 소스 코드를 따라 프레젠테이션을 시각적으로 매력적인 걸작으로 바꿔보세요.

## 소개

오늘날과 같은 디지털 시대에 프레젠테이션은 정보를 효과적으로 전달하는 데 중요한 역할을 합니다. SVG(Scalable Vector Graphics) 모양을 통합하면 프레젠테이션을 더욱 매력적이고 시각적으로 멋지게 만들 수 있습니다. .NET용 Aspose.Slides를 사용하면 특정 디자인 요구 사항에 맞게 SVG 모양의 형식을 쉽게 지정할 수 있습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 개발 환경에 설치된 .NET용 Aspose.Slides.
- C# 프로그래밍에 대한 실무 지식.
- SVG 모양으로 향상시키려는 샘플 PowerPoint 프리젠테이션 파일입니다.

## 시작하기

먼저 프로젝트를 설정하고 제공된 소스 코드를 이해해 보겠습니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";
string pptxFileName = Path.Combine(dataDir, "Convert_Svg_Custom.pptx");
string outSvgFileName = Path.Combine(outPath, "Convert_Svg_Custom.svg");

using (Presentation pres = new Presentation(pptxFileName))
{
    using (FileStream stream = new FileStream(outSvgFileName, FileMode.Create))
    {
        SVGOptions svgOptions = new SVGOptions
        {
            ShapeFormattingController = new MySvgShapeFormattingController()
        };

        pres.Slides[0].WriteAsSvg(stream, svgOptions);
    }
}
```

 이 코드 조각은 필요한 디렉터리와 파일 경로를 초기화하고 PowerPoint 프레젠테이션을 열고 이를 SVG 파일로 변환하는 동시에`MySvgShapeFormattingController`.

## SVG 모양 형식 지정 컨트롤러 이해

 좀 더 자세히 살펴 보겠습니다.`MySvgShapeFormattingController` 수업:

```csharp
class MySvgShapeFormattingController : ISvgShapeAndTextFormattingController
{
    private int m_shapeIndex, m_portionIndex, m_tspanIndex;

    public MySvgShapeFormattingController(int shapeStartIndex = 0)
    {
        m_shapeIndex = shapeStartIndex;
        m_portionIndex = 0;
    }

    public void FormatShape(Aspose.Slides.Export.ISvgShape svgShape, IShape shape)
    {
        svgShape.Id = string.Format("shape-{0}", m_shapeIndex++);
        m_portionIndex = m_tspanIndex = 0;
    }

    // 더 많은 서식 지정 방법은 여기를 참조하세요...

    public ISvgShapeFormattingController AsISvgShapeFormattingController
    {
        get { return this; }
    }
}
```

이 컨트롤러 클래스는 SVG 출력 내에서 모양과 텍스트의 형식을 모두 처리합니다. 모양과 텍스트 범위에 고유한 ID를 할당하여 적절한 렌더링을 보장합니다.

## 결론

 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 SVG 모양의 형식을 지정하는 방법을 살펴보았습니다. 프로젝트를 설정하고 적용하는 방법을 배웠습니다.`MySvgShapeFormattingController`정확한 서식을 지정하고 프레젠테이션을 SVG 파일로 변환하세요. 다음 단계를 따르면 청중에게 지속적인 인상을 남기는 매력적인 프레젠테이션을 만들 수 있습니다.

창의력을 발휘하려면 다양한 SVG 모양과 서식 옵션을 주저하지 말고 실험해 보세요. .NET용 Aspose.Slides는 프레젠테이션 디자인을 향상시킬 수 있는 강력한 플랫폼을 제공합니다.

자세한 내용, 세부 문서 및 지원을 보려면 .NET 리소스용 Aspose.Slides를 방문하세요.

- [API 문서](https://reference.aspose.com/slides/net/): 자세한 내용은 API 참조를 살펴보세요.
- [다운로드](https://releases.aspose.com/slides/net/): .NET용 최신 Aspose.Slides 버전을 받으세요.
- [구입](https://purchase.aspose.com/buy): 확장 사용을 위해서는 라이선스를 취득하세요.
- [무료 시험판](https://releases.aspose.com/): .NET용 Aspose.Slides를 무료로 사용해 보세요.
- [임시면허](https://purchase.aspose.com/temporary-license/): 프로젝트에 대한 임시 라이센스를 받으세요.
- [지원하다](https://forum.aspose.com/): 도움과 토론을 위해 Aspose 커뮤니티에 가입하세요.

이제 서식이 지정된 SVG 모양으로 매력적인 프레젠테이션을 만들 수 있는 지식과 도구를 갖게 되었습니다. 이전과는 전혀 다른 방식으로 프레젠테이션을 향상하고 청중을 사로잡으세요!

## 자주 묻는 질문

### SVG 형식은 무엇이며 프레젠테이션에서 왜 중요한가요?
SVG 형식은 프레젠테이션에 사용되는 확장 가능한 벡터 그래픽의 스타일과 디자인을 나타냅니다. 이는 슬라이드의 시각적 매력과 참여도를 향상시키기 때문에 매우 중요합니다.

### Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Slides for .NET은 주로 C#용으로 설계되었지만 VB.NET과 같은 다른 .NET 언어에서도 작동합니다.

### .NET용 Aspose.Slides 평가판이 있습니까?
예, 웹사이트에서 평가판을 다운로드하여 .NET용 Aspose.Slides를 무료로 사용해 볼 수 있습니다.

### .NET용 Aspose.Slides에 대한 기술 지원은 어떻게 받을 수 있나요?
Aspose 커뮤니티 포럼(위에 제공된 링크)을 방문하여 기술 지원을 구하고 전문가 및 동료 개발자와 토론에 참여할 수 있습니다.

### 시각적으로 매력적인 프레젠테이션을 만들기 위한 모범 사례는 무엇입니까?
시각적으로 매력적인 프레젠테이션을 만들려면 디자인 일관성에 집중하고, 고품질 그래픽을 사용하고, 콘텐츠를 간결하고 흥미롭게 유지하세요. 이 튜토리얼에 설명된 대로 다양한 형식 옵션을 실험해 보세요.

이제 이러한 기술을 적용하여 청중을 사로잡을 멋진 프레젠테이션을 만들어 보십시오!

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

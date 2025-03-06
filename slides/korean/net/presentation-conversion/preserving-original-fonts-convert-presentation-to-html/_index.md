---
title: 원본 글꼴 보존 - 프레젠테이션을 HTML로 변환
linktitle: 원본 글꼴 보존 - 프레젠테이션을 HTML로 변환
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 프레젠테이션을 HTML로 변환하는 동안 원본 글꼴을 유지하는 방법을 알아보세요. 손쉽게 글꼴 일관성과 시각적 효과를 보장하세요.
weight: 14
url: /ko/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


이 종합 가이드에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션을 HTML로 변환할 때 원본 글꼴을 유지하는 과정을 안내합니다. 필요한 C# 소스 코드를 제공하고 각 단계를 자세히 설명하겠습니다. 이 튜토리얼이 끝나면 변환된 HTML 문서의 글꼴이 원본 프리젠테이션에 충실하게 유지되도록 할 수 있습니다.

## 1. 소개

PowerPoint 프레젠테이션을 HTML로 변환할 때 콘텐츠의 시각적 일관성을 보장하려면 원본 글꼴을 유지하는 것이 중요합니다. .NET용 Aspose.Slides는 이를 달성하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 변환 프로세스 중에 원본 글꼴을 보존하는 데 필요한 단계를 안내합니다.

## 2. 전제조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 컴퓨터에 Visual Studio가 설치되어 있습니다.
- .NET용 Aspose.Slides 라이브러리가 프로젝트에 추가되었습니다.

## 3. 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 .NET용 Aspose.Slides 라이브러리를 참조로 추가하세요.

## 4. 프레젠테이션 로드

PowerPoint 프레젠테이션을 로드하려면 다음 코드를 사용하세요.

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // 여기에 귀하의 코드가 있습니다
}
```

 바꾸다`"Your Document Directory"` 프레젠테이션 파일의 경로를 사용하세요.

## 5. 기본 글꼴 제외

Calibri 및 Arial과 같은 기본 글꼴을 제외하려면 다음 코드를 사용하십시오.

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

필요에 따라 이 목록을 사용자 정의할 수 있습니다.

## 6. 모든 글꼴 포함

다음으로 HTML 문서에 모든 글꼴을 포함하겠습니다. 이렇게 하면 원본 글꼴이 보존됩니다. 다음 코드를 사용하세요.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. HTML로 저장하기

이제 프레젠테이션을 글꼴이 포함된 HTML 문서로 저장합니다.

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 바꾸다`"output.html"` 원하는 출력 파일 이름으로.

## 8. 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 HTML로 변환할 때 원본 글꼴을 유지하는 방법을 보여주었습니다. 다음 단계를 수행하면 변환된 HTML 문서가 원본 프리젠테이션의 시각적 무결성을 유지하는지 확인할 수 있습니다.

## 9. FAQ

### Q1: 제외된 글꼴 목록을 사용자 정의할 수 있나요?

 그래 넌 할수있어. 수정하다`fontNameExcludeList`요구 사항에 따라 특정 글꼴을 포함하거나 제외하도록 배열합니다.

### Q2: 모든 글꼴을 포함하고 싶지 않으면 어떻게 합니까?

특정 글꼴만 포함하려면 이에 따라 코드를 수정하면 됩니다. 자세한 내용은 .NET용 Aspose.Slides 설명서를 참조하세요.

### Q3: Aspose.Slides for .NET을 사용하기 위한 라이선스 요구 사항이 있나요?

예, 프로젝트에서 Aspose.Slides for .NET을 사용하려면 유효한 라이선스가 필요할 수 있습니다. 라이선스 정보는 Aspose 웹사이트를 참조하세요.

### Q4: Aspose.Slides for .NET을 사용하여 다른 파일 형식을 HTML로 변환할 수 있습니까?

.NET용 Aspose.Slides는 주로 PowerPoint 프레젠테이션에 중점을 둡니다. 다른 파일 형식을 HTML로 변환하려면 해당 형식에 맞는 다른 Aspose 제품을 탐색해야 할 수도 있습니다.

### Q5: 추가 리소스와 지원은 어디서 이용할 수 있나요?

 Aspose 웹사이트에서 더 많은 문서, 튜토리얼 및 지원을 찾을 수 있습니다. 방문하다[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/) 자세한 내용은.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

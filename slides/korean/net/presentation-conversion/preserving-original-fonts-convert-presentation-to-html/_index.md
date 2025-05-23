---
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션을 HTML로 변환하는 동안 원본 글꼴을 유지하는 방법을 알아보세요. 글꼴의 일관성과 시각적 효과를 손쉽게 확보하세요."
"linktitle": "원본 글꼴 보존 - 프레젠테이션을 HTML로 변환"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "원본 글꼴 보존 - 프레젠테이션을 HTML로 변환"
"url": "/ko/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 원본 글꼴 보존 - 프레젠테이션을 HTML로 변환


이 종합 가이드에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션을 HTML로 변환할 때 원본 글꼴을 유지하는 과정을 안내합니다. 필요한 C# 소스 코드를 제공하고 각 단계를 자세히 설명합니다. 이 튜토리얼을 마치면 변환된 HTML 문서의 글꼴이 원본 프레젠테이션과 동일하게 유지되도록 할 수 있을 것입니다.

## 1. 서론

PowerPoint 프레젠테이션을 HTML로 변환할 때는 콘텐츠의 시각적 일관성을 위해 원본 글꼴을 유지하는 것이 매우 중요합니다. Aspose.Slides for .NET은 이를 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 변환 과정에서 원본 글꼴을 유지하는 데 필요한 단계를 안내합니다.

## 2. 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- 컴퓨터에 Visual Studio가 설치되어 있어야 합니다.
- .NET 라이브러리용 Aspose.Slides가 프로젝트에 추가되었습니다.

## 3. 프로젝트 설정

시작하려면 Visual Studio에서 새 프로젝트를 만들고 Aspose.Slides for .NET 라이브러리를 참조로 추가하세요.

## 4. 프레젠테이션 로딩

다음 코드를 사용하여 PowerPoint 프레젠테이션을 로드하세요.

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // 여기에 코드를 입력하세요
}
```

바꾸다 `"Your Document Directory"` 프레젠테이션 파일의 경로를 포함합니다.

## 5. 기본 글꼴 제외

Calibri, Arial과 같은 기본 글꼴을 제외하려면 다음 코드를 사용하세요.

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

필요에 따라 이 목록을 사용자 정의할 수 있습니다.

## 6. 모든 글꼴 포함

다음으로, 모든 글꼴을 HTML 문서에 포함하겠습니다. 이렇게 하면 원본 글꼴이 그대로 유지됩니다. 다음 코드를 사용하세요.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. HTML로 저장

이제 프레젠테이션을 내장된 글꼴이 있는 HTML 문서로 저장합니다.

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

바꾸다 `"output.html"` 원하는 출력 파일 이름을 입력하세요.

## 8. 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 HTML로 변환할 때 원본 글꼴을 유지하는 방법을 살펴보았습니다. 다음 단계를 따르면 변환된 HTML 문서가 원본 프레젠테이션의 시각적 무결성을 유지할 수 있습니다.

## 9. FAQ

### 질문 1: 제외된 글꼴 목록을 사용자 지정할 수 있나요?

네, 가능합니다. 수정하세요. `fontNameExcludeList` 요구 사항에 따라 특정 글꼴을 포함하거나 제외하기 위한 배열입니다.

### 질문 2: 모든 글꼴을 포함하고 싶지 않으면 어떻게 해야 하나요?

특정 글꼴만 포함하려면 코드를 적절히 수정하면 됩니다. 자세한 내용은 Aspose.Slides for .NET 설명서를 참조하세요.

### 질문 3: Aspose.Slides for .NET을 사용하는 데 라이선스 요구 사항이 있습니까?

네, 프로젝트에서 Aspose.Slides for .NET을 사용하려면 유효한 라이선스가 필요할 수 있습니다. 라이선스 정보는 Aspose 웹사이트를 참조하세요.

### 질문 4: Aspose.Slides for .NET을 사용하여 다른 파일 형식을 HTML로 변환할 수 있나요?

Aspose.Slides for .NET은 주로 PowerPoint 프레젠테이션에 중점을 둡니다. 다른 파일 형식을 HTML로 변환하려면 해당 형식에 맞춰 개발된 다른 Aspose 제품을 살펴보는 것이 좋습니다.

### 질문 5: 추가 리소스와 지원은 어디에서 받을 수 있나요?

Aspose 웹사이트에서 더 많은 문서, 튜토리얼 및 지원을 확인하실 수 있습니다. 방문하세요. [.NET용 Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 자세한 내용은.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: 포함된 글꼴을 사용하여 프레젠테이션을 HTML로 변환
linktitle: 포함된 글꼴을 사용하여 프레젠테이션을 HTML로 변환
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 글꼴이 포함된 HTML로 변환합니다. 독창성을 원활하게 유지하세요.
weight: 13
url: /ko/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


오늘날 디지털 시대에는 프레젠테이션과 문서를 온라인으로 공유하는 것이 일반적인 관행이 되었습니다. 그러나 자주 발생하는 문제 중 하나는 프레젠테이션을 HTML로 변환할 때 글꼴이 올바르게 표시되는지 확인하는 것입니다. 이 단계별 튜토리얼은 .NET용 Aspose.Slides를 사용하여 프레젠테이션을 글꼴이 포함된 HTML로 변환하는 과정을 안내하여 문서가 의도한 대로 보이도록 보장합니다.

## .NET용 Aspose.Slides 소개

튜토리얼을 시작하기 전에 Aspose.Slides for .NET에 대해 간략하게 소개하겠습니다. 이는 개발자가 .NET 응용 프로그램에서 PowerPoint 프레젠테이션 작업을 할 수 있게 해주는 강력한 라이브러리입니다. Aspose.Slides를 사용하면 프로그래밍 방식으로 PowerPoint 파일을 생성, 수정 및 변환할 수 있습니다.

## 전제 조건

시작하기 전에 다음 필수 구성 요소가 갖추어져 있는지 확인하세요.

-  .NET용 Aspose.Slides: 프로젝트에 Aspose.Slides 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

## 1단계: 프로젝트 설정

1. 원하는 .NET 개발 환경에서 새 프로젝트를 만들거나 기존 프로젝트를 엽니다.

2. 프로젝트에 Aspose.Slides 라이브러리에 대한 참조를 추가하세요.

3. 코드에서 필요한 네임스페이스를 가져옵니다.

   ```csharp
   using Aspose.Slides;
   ```

## 2단계: 프레젠테이션 로드

 시작하려면 HTML로 변환하려는 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 프리젠테이션 파일이 있는 실제 디렉토리를 사용합니다.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // 귀하의 코드는 여기에 있습니다
}
```

## 3단계: 기본 프리젠테이션 글꼴 제외

이 단계에서는 포함에서 제외할 기본 프리젠테이션 글꼴을 지정할 수 있습니다. 이는 결과 HTML 파일의 크기를 최적화하는 데 도움이 될 수 있습니다.

```csharp
string[] fontNameExcludeList = { };
```

## 4단계: HTML 컨트롤러 선택

이제 HTML에 글꼴을 포함하는 두 가지 옵션이 있습니다.

### 옵션 1: 모든 글꼴 포함

 프레젠테이션에 사용된 모든 글꼴을 포함하려면`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### 옵션 2: 모든 글꼴 연결

 프레젠테이션에 사용된 모든 글꼴에 연결하려면`LinkAllFontsHtmlController`. 시스템에서 글꼴이 있는 디렉토리를 지정해야 합니다.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## 5단계: HTML 옵션 정의

 만들기`HtmlOptions` 개체를 선택하고 HTML 포맷터를 이전 단계에서 선택한 것으로 설정합니다.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // 모든 글꼴을 포함하려면 embedFontsController를 사용하세요.
};
```

## 6단계: HTML로 저장

 마지막으로 프레젠테이션을 HTML 파일로 저장합니다. 다음 중 하나를 선택할 수 있습니다.`SaveFormat.Html` 또는`SaveFormat.Html5` 귀하의 요구 사항에 따라.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 결론

축하해요! Aspose.Slides for .NET을 사용하여 글꼴이 포함된 HTML로 프레젠테이션을 성공적으로 변환했습니다. 이렇게 하면 프레젠테이션을 온라인으로 공유할 때 글꼴이 올바르게 표시됩니다.

이제 청중이 의도한 대로 정확하게 프레젠테이션을 보게 될 것이라는 확신을 갖고 아름다운 형식의 프레젠테이션을 자신있게 쉽게 공유할 수 있습니다.

 자세한 내용과 자세한 API 참조는 다음을 확인하세요.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### 1. 배치 모드에서 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 HTML로 변환할 수 있습니까?

예, Aspose.Slides for .NET을 사용하여 프레젠테이션 파일을 반복하고 각 프레젠테이션에 변환 프로세스를 적용하여 여러 프레젠테이션을 HTML로 일괄 변환할 수 있습니다.

### 2. HTML 출력의 모양을 사용자 정의할 수 있는 방법이 있습니까?

틀림없이! .NET용 Aspose.Slides는 색상, 글꼴, 레이아웃 조정과 같이 HTML 출력의 모양과 형식을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.

### 3. .NET용 Aspose.Slides를 사용하여 HTML에 글꼴을 삽입하는 데 제한이 있나요?

.NET용 Aspose.Slides는 뛰어난 글꼴 포함 기능을 제공하지만 글꼴을 포함할 때 HTML 파일의 크기가 증가할 수 있다는 점을 명심하세요. 웹 사용에 맞게 글꼴 선택을 최적화하십시오.

### 4. Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 다른 형식으로 변환할 수 있나요?

예, .NET용 Aspose.Slides는 PDF, 이미지 등을 포함한 광범위한 출력 형식을 지원합니다. 프레젠테이션을 원하는 형식으로 쉽게 변환할 수 있습니다.

### 5. .NET용 Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?

 문서를 포함한 풍부한 리소스에 액세스할 수 있습니다.[.NET API 참조용 Aspose.Slides](https://reference.aspose.com/slides/net/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

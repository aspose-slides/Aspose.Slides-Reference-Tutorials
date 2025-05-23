---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 내장된 글꼴이 포함된 HTML로 변환하세요. 독창적인 디자인을 완벽하게 유지하세요."
"linktitle": "내장된 글꼴을 사용하여 프레젠테이션을 HTML로 변환"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "내장된 글꼴을 사용하여 프레젠테이션을 HTML로 변환"
"url": "/ko/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 내장된 글꼴을 사용하여 프레젠테이션을 HTML로 변환


오늘날 디지털 시대에는 프레젠테이션과 문서를 온라인으로 공유하는 것이 일반적인 관행이 되었습니다. 하지만 프레젠테이션을 HTML로 변환할 때 글꼴이 제대로 표시되는지 확인하는 것은 종종 어려운 과제입니다. 이 단계별 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션을 글꼴이 포함된 HTML로 변환하는 과정을 안내합니다. 이를 통해 문서가 의도한 대로 표시되도록 할 수 있습니다.

## .NET용 Aspose.Slides 소개

튜토리얼을 시작하기 전에 Aspose.Slides for .NET을 간략하게 소개해 드리겠습니다. Aspose.Slides는 개발자가 .NET 애플리케이션에서 PowerPoint 프레젠테이션을 작업할 수 있도록 지원하는 강력한 라이브러리입니다. Aspose.Slides를 사용하면 PowerPoint 파일을 프로그래밍 방식으로 생성, 수정 및 변환할 수 있습니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET용 Aspose.Slides: 프로젝트에 Aspose.Slides 라이브러리가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).

## 1단계: 프로젝트 설정

1. 원하는 .NET 개발 환경에서 새 프로젝트를 만들거나 기존 프로젝트를 엽니다.

2. 프로젝트에 Aspose.Slides 라이브러리에 대한 참조를 추가합니다.

3. 코드에 필요한 네임스페이스를 가져옵니다.

   ```csharp
   using Aspose.Slides;
   ```

## 2단계: 프레젠테이션 로드

시작하려면 HTML로 변환하려는 프레젠테이션을 로드해야 합니다. 바꾸기 `"Your Document Directory"` 프레젠테이션 파일이 있는 실제 디렉토리와 함께.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // 여기에 코드를 입력하세요
}
```

## 3단계: 기본 프레젠테이션 글꼴 제외

이 단계에서는 임베드에서 제외할 기본 프레젠테이션 글꼴을 지정할 수 있습니다. 이렇게 하면 최종 HTML 파일의 크기를 최적화하는 데 도움이 됩니다.

```csharp
string[] fontNameExcludeList = { };
```

## 4단계: HTML 컨트롤러 선택

이제 HTML에 글꼴을 포함하는 데는 두 가지 옵션이 있습니다.

### 옵션 1: 모든 글꼴 포함

프레젠테이션에 사용된 모든 글꼴을 포함하려면 다음을 사용하세요. `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### 옵션 2: 모든 글꼴 연결

프레젠테이션에 사용된 모든 글꼴에 링크하려면 다음을 사용하세요. `LinkAllFontsHtmlController`시스템에서 글꼴이 있는 디렉토리를 지정해야 합니다.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## 5단계: HTML 옵션 정의

생성하다 `HtmlOptions` 객체를 선택하고 HTML 포매터를 이전 단계에서 선택한 포매터로 설정합니다.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // 모든 글꼴을 포함하려면 embedFontsController를 사용하세요.
};
```

## 6단계: HTML로 저장

마지막으로 프레젠테이션을 HTML 파일로 저장합니다. 다음 중 하나를 선택할 수 있습니다. `SaveF또는mat.Html` or `SaveFormat.Html5` 귀하의 요구 사항에 따라 다릅니다.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## 결론

축하합니다! Aspose.Slides for .NET을 사용하여 프레젠테이션을 내장 글꼴이 포함된 HTML로 성공적으로 변환했습니다. 이제 온라인으로 프레젠테이션을 공유할 때 글꼴이 제대로 표시됩니다.

이제 청중이 여러분의 의도대로 프레젠테이션을 볼 것이라는 확신을 가지고, 아름답게 구성된 프레젠테이션을 손쉽게 공유할 수 있습니다.

자세한 정보와 자세한 API 참조는 다음을 확인하세요. [.NET용 Aspose.Slides 설명서](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### 1. Aspose.Slides for .NET을 배치 모드로 사용하여 PowerPoint 프레젠테이션을 HTML로 변환할 수 있나요?

네, Aspose.Slides for .NET을 사용하여 여러 프레젠테이션을 HTML로 일괄 변환할 수 있습니다. 프레젠테이션 파일을 반복하고 각 파일에 변환 프로세스를 적용하면 됩니다.

### 2. HTML 출력의 모양을 사용자 정의할 수 있는 방법이 있나요?

물론입니다! Aspose.Slides for .NET은 HTML 출력의 모양과 서식을 사용자 지정할 수 있는 다양한 옵션을 제공합니다. 예를 들어 색상, 글꼴, 레이아웃을 조정할 수 있습니다.

### 3. Aspose.Slides for .NET을 사용하여 HTML에 글꼴을 포함하는 데 제한이 있습니까?

Aspose.Slides for .NET은 뛰어난 글꼴 임베딩 기능을 제공하지만, 글꼴을 임베딩할 경우 HTML 파일 크기가 커질 수 있다는 점에 유의하세요. 웹 사용에 맞춰 글꼴을 최적화하는 것이 좋습니다.

### 4. Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 다른 형식으로 변환할 수 있나요?

네, Aspose.Slides for .NET은 PDF, 이미지 등 다양한 출력 형식을 지원합니다. 원하는 형식으로 프레젠테이션을 쉽게 변환할 수 있습니다.

### 5. Aspose.Slides for .NET에 대한 추가 리소스와 지원은 어디에서 찾을 수 있나요?

문서를 포함한 다양한 리소스에 액세스할 수 있습니다. [.NET API 참조용 Aspose.Slides](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
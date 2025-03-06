---
title: 숨겨진 슬라이드를 사용하여 프레젠테이션을 PDF로 변환
linktitle: 숨겨진 슬라이드를 사용하여 프레젠테이션을 PDF로 변환
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 프레젠테이션을 숨겨진 슬라이드가 있는 PDF로 원활하게 변환하는 방법을 알아보세요.
weight: 26
url: /ko/net/presentation-conversion/convert-presentation-to-pdf-with-hidden-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## .NET용 Aspose.Slides 소개

Aspose.Slides for .NET은 .NET 애플리케이션에서 프레젠테이션 작업을 위한 포괄적인 기능을 제공하는 강력한 라이브러리입니다. 이를 통해 개발자는 프레젠테이션을 PDF를 포함한 다양한 형식으로 생성, 편집, 조작 및 변환할 수 있습니다.

## 프레젠테이션의 숨겨진 슬라이드 이해

숨겨진 슬라이드는 일반 슬라이드쇼 중에는 표시되지 않는 프레젠테이션 내의 슬라이드입니다. 여기에는 보충 정보, 백업 콘텐츠 또는 특정 대상을 대상으로 하는 콘텐츠가 포함될 수 있습니다. 프레젠테이션을 PDF로 변환할 때 프레젠테이션의 무결성을 유지하려면 숨겨진 슬라이드도 포함되어 있는지 확인하는 것이 중요합니다.

## 개발 환경 설정

시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.

- Visual Studio 또는 .NET 개발 환경이 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Slides. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net).

## 프리젠테이션 파일 로드

시작하려면 .NET용 Aspose.Slides를 사용하여 프레젠테이션 파일을 로드해 보겠습니다.

```csharp
using Aspose.Slides;

// 프레젠테이션 로드
using var presentation = new Presentation("sample.pptx");
```

## 숨겨진 슬라이드를 사용하여 프레젠테이션을 PDF로 변환

이제 숨겨진 슬라이드를 식별할 수 있으므로 숨겨진 슬라이드가 포함되었는지 확인하면서 프레젠테이션을 PDF로 변환해 보겠습니다.

```csharp
var pdfOptions = new PdfOptions();
pdfOptions.ShowHiddenSlides = true; // PDF에 숨겨진 슬라이드 포함

presentation.Save("output.pdf", SaveFormat.Pdf, pdfOptions);
```

## 추가 옵션 및 사용자 정의

.NET용 Aspose.Slides는 변환 프로세스에 대한 다양한 옵션과 사용자 정의를 제공합니다. 페이지 크기, 방향, 품질 등 PDF 관련 옵션을 설정하여 출력 PDF를 최적화할 수 있습니다.

## 코드 예: 숨겨진 슬라이드를 사용하여 프레젠테이션을 PDF로 변환

다음은 Aspose.Slides for .NET을 사용하여 프레젠테이션을 숨겨진 슬라이드가 있는 PDF로 변환하는 전체 예입니다.

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        using var presentation = new Presentation("sample.pptx");

        var pdfOptions = new PdfOptions();
        pdfOptions.ShowHiddenSlides = true;

        presentation.Save("output.pdf", SaveFormat.Pdf, pdfOptions);
    }
}
```

## 결론

프레젠테이션을 PDF로 변환하는 것은 일반적인 작업이지만 숨겨진 슬라이드를 처리할 때는 Aspose.Slides for .NET과 같은 신뢰할 수 있는 라이브러리를 사용하는 것이 중요합니다. 이 가이드에 설명된 단계를 따르면 프레젠테이션의 전반적인 품질과 컨텍스트를 유지하면서 숨겨진 슬라이드를 포함하면서 프레젠테이션을 PDF로 원활하게 변환할 수 있습니다.

## FAQ

### .NET용 Aspose.Slides를 사용하여 PDF에 숨겨진 슬라이드를 어떻게 포함합니까?

 PDF 변환에 숨겨진 슬라이드를 포함하려면`ShowHiddenSlides` 재산`true` 프레젠테이션을 PDF로 저장하기 전에 PDF 옵션에서

### Aspose.Slides를 사용하여 PDF 출력 설정을 사용자 정의할 수 있나요?

예, Aspose.Slides for .NET은 페이지 크기, 방향, 이미지 품질과 같은 PDF 출력 설정을 사용자 정의할 수 있는 다양한 옵션을 제공합니다.

### Aspose.Slides for .NET은 간단한 프레젠테이션과 복잡한 프레젠테이션 모두에 적합합니까?

물론, Aspose.Slides for .NET은 다양한 복잡성의 프레젠테이션을 처리하도록 설계되었습니다. 간단하고 복잡한 프레젠테이션 변환 작업에 모두 적합합니다.

### .NET용 Aspose.Slides 라이브러리는 어디서 다운로드할 수 있나요?

 .NET용 Aspose.Slides 라이브러리는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net).

### .NET용 Aspose.Slides에 대한 문서가 있습니까?

 예, .NET용 Aspose.Slides에 대한 문서 및 사용 예제는 다음에서 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/net).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

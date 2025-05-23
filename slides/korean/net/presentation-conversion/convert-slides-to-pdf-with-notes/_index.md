---
"description": "Aspose.Slides for .NET을 사용하여 발표자 노트가 포함된 프레젠테이션 슬라이드를 PDF로 손쉽게 변환하세요. 콘텐츠와 맥락을 완벽하게 보존할 수 있습니다."
"linktitle": "슬라이드를 노트와 함께 PDF로 변환"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "슬라이드를 노트와 함께 PDF로 변환"
"url": "/ko/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 슬라이드를 노트와 함께 PDF로 변환


# Aspose.Slides for .NET을 사용하여 슬라이드를 노트가 포함된 PDF로 변환하는 방법에 대한 단계별 튜토리얼 가이드 작성

중요한 메모를 모두 보존하면서 PowerPoint 슬라이드를 PDF 형식으로 변환할 수 있는 안정적인 방법을 찾고 계신가요? 더 이상 고민하지 마세요! 이 포괄적인 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 이 작업을 단계별로 수행하는 방법을 안내해 드립니다.

## 1. 서론

PowerPoint 슬라이드를 메모가 포함된 PDF로 변환하는 기능은 중요한 맥락과 주석을 유지하면서 프레젠테이션을 공유하는 데 유용한 도구가 될 수 있습니다. Aspose.Slides for .NET은 이러한 작업을 위한 강력한 솔루션을 제공합니다.

## 2. 환경 설정

코딩 과정을 시작하기 전에 필요한 환경이 설정되어 있는지 확인하세요. 필요한 사항은 다음과 같습니다.

- Visual Studio 또는 선호하는 .NET 개발 환경.
- .NET 라이브러리용 Aspose.Slides가 설치되었습니다.
- 변환하려는 노트가 포함된 PowerPoint 프레젠테이션입니다.

## 3. 프레젠테이션 로딩

C# 코드에서 변환하려는 PowerPoint 프레젠테이션을 로드해야 합니다. 방법은 다음과 같습니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. 슬라이드 복제

PDF에 필요한 모든 슬라이드와 메모가 포함되도록 하려면 원본 프레젠테이션에서 슬라이드를 복제하세요. 방법은 다음과 같습니다.

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. 슬라이드 크기 조정

PDF에 맞게 슬라이드 크기를 조정하고 싶을 수 있습니다. Aspose.Slides for .NET을 사용하면 간편하게 조정할 수 있습니다.

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. PDF 옵션 구성

PDF에 메모가 표시되는 방식을 제어하려면 PDF 옵션을 구성하세요.

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Notes와 함께 PDF로 저장

마지막으로, 프레젠테이션을 메모와 함께 PDF로 저장할 수 있습니다.

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. 결론

축하합니다! 중요한 메모는 모두 그대로 유지하면서 PowerPoint 슬라이드를 PDF 형식으로 변환했습니다. Aspose.Slides for .NET을 사용하면 이 과정을 간편하고 효율적으로 진행할 수 있습니다.

## 9. FAQ

### 질문 1: PDF의 노트 레이아웃을 사용자 지정할 수 있나요?

예, 다음을 사용하여 메모 레이아웃을 사용자 정의할 수 있습니다. `INotesCommentsLayoutingOptions` PDF 옵션에서.

### 질문 2: Aspose.Slides for .NET은 PDF 외에 다른 출력 형식을 지원합니까?

네, Aspose.Slides for .NET은 PPTX, DOCX 등 다양한 출력 형식을 지원합니다.

### 질문 3: Aspose.Slides for .NET의 평가판이 있나요?

네, Aspose.Slides for .NET의 무료 평가판을 다음에서 받으실 수 있습니다. [https://releases.aspose.com/](https://releases.aspose.com/).

### 질문 4: Aspose.Slides for .NET에 대한 지원은 어디에서 받을 수 있나요?

지원 및 커뮤니티 토론은 다음에서 찾을 수 있습니다. [https://forum.aspose.com/](https://forum.aspose.com/).

### 질문 5: Aspose.Slides for .NET에 대한 임시 라이선스를 구매할 수 있나요?

네, 임시 라이센스를 구매할 수 있습니다. [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

결론적으로, Aspose.Slides for .NET을 사용하면 PowerPoint 슬라이드를 노트를 그대로 유지한 채 PDF 형식으로 쉽게 변환할 수 있습니다. 동료 및 고객과 프레젠테이션을 공유하면서 중요한 맥락을 놓치지 않아야 하는 전문가에게 유용한 도구입니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
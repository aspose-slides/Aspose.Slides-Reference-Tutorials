---
title: Notes를 사용하여 슬라이드를 PDF로 변환
linktitle: Notes를 사용하여 슬라이드를 PDF로 변환
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 발표자 노트가 포함된 프레젠테이션 슬라이드를 PDF로 쉽게 변환하세요. 콘텐츠와 맥락을 원활하게 보존합니다.
weight: 18
url: /ko/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


# .NET용 Aspose.Slides를 사용하여 슬라이드를 노트와 함께 PDF로 변환하는 방법에 대한 단계별 튜토리얼 가이드 작성

모든 중요한 메모를 유지하면서 PowerPoint 슬라이드를 PDF 형식으로 변환하는 안정적인 방법을 찾고 계십니까? 더 이상 보지 마세요! 이 포괄적인 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 이 작업을 단계별로 수행하는 과정을 안내합니다.

## 1. 소개

PowerPoint 슬라이드를 메모가 포함된 PDF로 변환하는 것은 중요한 컨텍스트와 설명을 유지하면서 프레젠테이션을 공유하는 데 유용한 도구가 될 수 있습니다. .NET용 Aspose.Slides는 이 작업을 위한 강력한 솔루션을 제공합니다.

## 2. 환경 설정

코딩 프로세스를 시작하기 전에 필요한 환경이 설정되어 있는지 확인하세요. 너는 필요할거야:

- Visual Studio 또는 선호하는 .NET 개발 환경.
- .NET 라이브러리용 Aspose.Slides가 설치되었습니다.
- 변환하려는 메모가 포함된 PowerPoint 프레젠테이션.

## 3. 프레젠테이션 로드

C# 코드에서는 변환하려는 PowerPoint 프레젠테이션을 로드해야 합니다. 방법은 다음과 같습니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. 슬라이드 복제

PDF에 메모와 함께 필요한 모든 슬라이드가 포함되도록 하려면 원본 프레젠테이션에서 해당 슬라이드를 복제할 수 있습니다. 방법은 다음과 같습니다.

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. 슬라이드 크기 조정

PDF에 맞게 슬라이드 크기를 조정할 수 있습니다. .NET용 Aspose.Slides를 사용하면 이 작업을 쉽게 수행할 수 있습니다.

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. PDF 옵션 구성

PDF에 메모가 표시되는 방식을 제어하려면 PDF 옵션을 구성하면 됩니다.

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. 노트와 함께 PDF로 저장

마지막으로 프레젠테이션을 메모가 포함된 PDF로 저장할 수 있습니다.

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. 결론

축하해요! 모든 중요한 메모를 유지하면서 PowerPoint 슬라이드를 PDF 형식으로 성공적으로 변환했습니다. .NET용 Aspose.Slides는 이 프로세스를 간단하고 효율적으로 만듭니다.

## 9. FAQ

### Q1: PDF의 노트 레이아웃을 사용자 정의할 수 있습니까?

 예, 다음을 사용하여 메모 레이아웃을 사용자 정의할 수 있습니다.`INotesCommentsLayoutingOptions` PDF 옵션에서.

### Q2: .NET용 Aspose.Slides는 PDF 외에 다른 출력 형식을 지원합니까?

예, .NET용 Aspose.Slides는 PPTX, DOCX 등을 포함한 다양한 출력 형식을 지원합니다.

### Q3: Aspose.Slides for .NET에 사용할 수 있는 평가판이 있습니까?

 예, 다음에서 .NET용 Aspose.Slides의 무료 평가판을 받을 수 있습니다.[https://releases.aspose.com/](https://releases.aspose.com/).

### Q4: .NET용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?

 다음에서 지원 및 커뮤니티 토론을 찾을 수 있습니다.[https://forum.aspose.com/](https://forum.aspose.com/).

### Q5: Aspose.Slides for .NET의 임시 라이선스를 구입할 수 있나요?

 예, 다음에서 임시 라이센스를 구입할 수 있습니다.[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

결론적으로 Aspose.Slides for .NET을 사용하면 PowerPoint 슬라이드를 메모를 그대로 유지하면서 PDF 형식으로 쉽게 변환할 수 있습니다. 이는 중요한 컨텍스트가 손실되지 않도록 하면서 동료 및 고객과 프레젠테이션을 공유해야 하는 전문가를 위한 귀중한 도구입니다.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

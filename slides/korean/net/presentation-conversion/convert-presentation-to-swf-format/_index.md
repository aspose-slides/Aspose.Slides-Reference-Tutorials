---
title: 프레젠테이션을 SWF 형식으로 변환
linktitle: 프레젠테이션을 SWF 형식으로 변환
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 SWF 형식으로 변환하는 방법을 알아보세요. 다이내믹한 콘텐츠를 손쉽게 만들어보세요!
type: docs
weight: 28
url: /ko/net/presentation-conversion/convert-presentation-to-swf-format/
---

오늘날의 디지털 시대에 멀티미디어 프레젠테이션은 강력한 의사소통 수단입니다. 때로는 프레젠테이션을 SWF(Shockwave Flash) 형식으로 변환하는 등 보다 동적인 방식으로 공유하고 싶을 수도 있습니다. 이 가이드는 Aspose.Slides for .NET을 사용하여 프레젠테이션을 SWF 형식으로 변환하는 과정을 안내합니다.

## 필요한 것

튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.

-  .NET용 Aspose.Slides: 아직 가지고 있지 않다면 다음을 수행하세요.[여기에서 다운로드하십시오](https://releases.aspose.com/slides/net/).

- 프레젠테이션 파일: SWF 형식으로 변환하려는 PowerPoint 프레젠테이션 파일이 필요합니다.

## 1단계: 환경 설정

시작하려면 프로젝트용 디렉터리를 만드세요. 이를 "프로젝트 디렉토리"라고 부르겠습니다. 이 디렉터리 안에 다음 소스 코드를 배치해야 합니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// 프리젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // 프레젠테이션 및 메모 페이지 저장
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

 꼭 교체하세요`"Your Document Directory"` 그리고`"Your Output Directory"` 프레젠테이션 파일이 있는 실제 경로와 SWF 파일을 저장할 위치를 입력합니다.

## 2단계: 프레젠테이션 로드

이 단계에서는 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 로드합니다.

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

 바꾸다`"HelloWorld.pptx"` 프리젠테이션 파일 이름으로

## 3단계: SWF 변환 옵션 구성

출력을 사용자 정의하기 위해 SWF 변환 옵션을 구성합니다.

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

요구 사항에 따라 이러한 옵션을 조정할 수 있습니다.

## 4단계: SWF로 저장

이제 프레젠테이션을 SWF 파일로 저장합니다.

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

이 줄은 기본 프레젠테이션을 SWF 파일로 저장합니다.

## 5단계: 메모와 함께 저장

메모를 포함하려면 다음 코드를 사용하세요.

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

이 코드는 SWF 형식의 메모와 함께 프레젠테이션을 저장합니다.

## 결론

축하해요! Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 SWF 형식으로 성공적으로 변환했습니다. 이는 프레젠테이션을 온라인으로 공유하거나 웹 페이지에 포함해야 할 때 특히 유용할 수 있습니다.

 자세한 내용과 자세한 문서를 보려면 다음 사이트를 방문하세요.[.NET 참조용 Aspose.Slides](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### SWF 형식이란 무엇입니까?
SWF(Shockwave Flash)는 웹의 애니메이션, 게임 및 대화형 콘텐츠에 사용되는 멀티미디어 형식입니다.

### .NET용 Aspose.Slides는 무료로 사용할 수 있나요?
 .NET용 Aspose.Slides는 무료 평가판을 제공하지만 전체 기능을 사용하려면 라이센스를 구매해야 할 수도 있습니다. 가격 및 라이선스 세부정보를 확인할 수 있습니다.[여기](https://purchase.aspose.com/buy).

### 라이선스를 구매하기 전에 Aspose.Slides for .NET을 사용해 볼 수 있나요?
 예, .NET용 Aspose.Slides의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### .NET용 Aspose.Slides를 사용하려면 프로그래밍 기술이 필요합니까?
예, Aspose.Slides를 효과적으로 사용하려면 C# 프로그래밍에 대한 지식이 있어야 합니다.

### .NET용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 질문이 있거나 도움이 필요하신 경우,[.NET 포럼용 Aspose.Slides](https://forum.aspose.com/)지원 및 지역사회 지원을 위해.

---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 SWF 형식으로 변환하는 방법을 알아보세요. 동적 콘텐츠를 손쉽게 제작해 보세요!"
"linktitle": "프레젠테이션을 SWF 형식으로 변환"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "프레젠테이션을 SWF 형식으로 변환"
"url": "/ko/net/presentation-conversion/convert-presentation-to-swf-format/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 프레젠테이션을 SWF 형식으로 변환


오늘날 디지털 시대에 멀티미디어 프레젠테이션은 강력한 소통 수단입니다. 때로는 SWF(Shockwave Flash) 형식으로 변환하는 등 더욱 역동적인 방식으로 프레젠테이션을 공유하고 싶을 수 있습니다. 이 가이드에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션을 SWF 형식으로 변환하는 과정을 안내합니다.

## 필요한 것

튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.

- .NET용 Aspose.Slides: 아직 없다면 다음을 사용할 수 있습니다. [여기서 다운로드하세요](https://releases.aspose.com/slides/net/).

- 프레젠테이션 파일: SWF 형식으로 변환하려는 PowerPoint 프레젠테이션 파일이 필요합니다.

## 1단계: 환경 설정

시작하려면 프로젝트 디렉터리를 만드세요. "프로젝트 디렉터리"라고 부르겠습니다. 이 디렉터리 안에 다음 소스 코드를 넣어야 합니다.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// 프레젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    SwfOptions swfOptions = new SwfOptions();
    swfOptions.ViewerIncluded = false;

    INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
    notesOptions.NotesPosition = NotesPositions.BottomFull;

    // 프레젠테이션 및 노트 페이지 저장
    presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
    swfOptions.ViewerIncluded = true;
    presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
```

교체해야 합니다 `"Your Document Directory"` 그리고 `"Your Output Directory"` 프레젠테이션 파일이 있는 실제 경로와 SWF 파일을 저장하려는 위치를 지정합니다.

## 2단계: 프레젠테이션 로딩

이 단계에서는 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 로드합니다.

```csharp
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
```

바꾸다 `"HelloWorld.pptx"` 프레젠테이션 파일의 이름을 입력하세요.

## 3단계: SWF 변환 옵션 구성

SWF 변환 옵션을 구성하여 출력을 사용자 정의합니다.

```csharp
SwfOptions swfOptions = new SwfOptions();
swfOptions.ViewerIncluded = false;

INotesCommentsLayoutingOptions notesOptions = swfOptions.NotesCommentsLayouting;
notesOptions.NotesPosition = NotesPositions.BottomFull;
```

귀하의 요구 사항에 맞게 이러한 옵션을 조정할 수 있습니다.

## 4단계: SWF로 저장

이제 프레젠테이션을 SWF 파일로 저장합니다.

```csharp
presentation.Save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

이 줄은 주요 프레젠테이션을 SWF 파일로 저장합니다.

## 5단계: 메모로 저장

메모를 포함하려면 다음 코드를 사용하세요.

```csharp
swfOptions.ViewerIncluded = true;
presentation.Save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

이 코드는 SWF 형식으로 노트가 포함된 프레젠테이션을 저장합니다.

## 결론

축하합니다! Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션을 SWF 형식으로 변환했습니다. 이 기능은 프레젠테이션을 온라인으로 공유하거나 웹 페이지에 삽입해야 할 때 특히 유용합니다.

더 많은 정보와 자세한 문서는 다음에서 확인하실 수 있습니다. [.NET용 Aspose.Slides 참조](https://reference.aspose.com/slides/net/).

## 자주 묻는 질문

### SWF 형식은 무엇인가요?
SWF(Shockwave Flash)는 웹에서 애니메이션, 게임, 대화형 콘텐츠에 사용되는 멀티미디어 형식입니다.

### Aspose.Slides for .NET은 무료로 사용할 수 있나요?
Aspose.Slides for .NET은 무료 평가판을 제공하지만, 모든 기능을 사용하려면 라이선스를 구매해야 할 수 있습니다. 가격 및 라이선스 세부 정보는 여기에서 확인하실 수 있습니다. [여기](https://purchase.aspose.com/buy).

### 라이선스를 구매하기 전에 Aspose.Slides for .NET을 사용해 볼 수 있나요?
네, Aspose.Slides for .NET의 무료 평가판을 받으실 수 있습니다. [여기](https://releases.aspose.com/).

### Aspose.Slides for .NET을 사용하려면 프로그래밍 기술이 필요합니까?
네, Aspose.Slides를 효과적으로 사용하려면 C# 프로그래밍에 대한 지식이 필요합니다.

### .NET용 Aspose.Slides에 대한 지원은 어디에서 받을 수 있나요?
질문이 있거나 도움이 필요하면 다음을 방문하세요. [.NET 포럼용 Aspose.Slides](https://forum.aspose.com/) 지원과 지역 사회의 도움을 요청하세요.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
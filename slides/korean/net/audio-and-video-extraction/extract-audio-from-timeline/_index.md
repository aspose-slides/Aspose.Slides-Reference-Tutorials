---
title: PowerPoint 타임라인에서 오디오 추출
linktitle: 타임라인에서 오디오 추출
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 오디오를 추출하는 방법을 알아보세요. 멀티미디어 콘텐츠를 쉽게 향상시키세요.
weight: 13
url: /ko/net/audio-and-video-extraction/extract-audio-from-timeline/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


멀티미디어 프리젠테이션 세계에서 사운드는 메시지를 효과적으로 전달하는 강력한 도구가 될 수 있습니다. Aspose.Slides for .NET은 PowerPoint 프레젠테이션에서 오디오를 추출하기 위한 완벽한 솔루션을 제공합니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 오디오를 추출하는 방법을 보여줍니다.

## 전제 조건

PowerPoint 프레젠테이션에서 오디오 추출을 시작하기 전에 다음 전제 조건이 필요합니다.

1.  .NET 라이브러리용 Aspose.Slides: .NET 라이브러리용 Aspose.Slides가 설치되어 있어야 합니다. 아직 설치하지 않으셨다면 아래에서 다운로드 받으실 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

2. PowerPoint 프레젠테이션: 오디오를 추출하려는 PowerPoint 프레젠테이션(PPTX)이 있는지 확인하세요. 프리젠테이션 파일을 원하는 디렉토리에 배치하십시오.

3. C#에 대한 기본 지식: 이 자습서에서는 사용자가 C# 프로그래밍에 대한 기본 지식을 가지고 있다고 가정합니다.

이제 모든 것이 준비되었으므로 단계별 가이드를 진행해 보겠습니다.

## 1단계: 네임스페이스 가져오기

시작하려면 Aspose.Slides 작업 및 파일 작업 처리에 필요한 네임스페이스를 가져와야 합니다. C# 프로젝트에 다음 코드를 추가합니다.

```csharp
using Aspose.Slides;
using System.IO;
```

## 2단계: 타임라인에서 오디오 추출

이제 제공한 예제를 여러 단계로 분석해 보겠습니다.

### 2.1단계: 프레젠테이션 로드

```csharp
string pptxFile = Path.Combine("Your Document Directory", "AnimationAudio.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // 여기에 귀하의 코드가 있습니다
}
```

이 단계에서는 지정된 파일에서 PowerPoint 프레젠테이션을 로드합니다. 꼭 교체하세요`"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 사용하세요.

### 2.2단계: 슬라이드 및 타임라인에 액세스

```csharp
ISlide slide = pres.Slides[0];
```

여기서는 프레젠테이션의 첫 번째 슬라이드에 액세스합니다. 필요한 경우 색인을 변경하여 다른 슬라이드에 액세스할 수 있습니다.

### 2.3단계: 효과 시퀀스 추출

```csharp
ISequence effectsSequence = slide.Timeline.MainSequence;
```

 그만큼`MainSequence` 속성을 사용하면 선택한 슬라이드의 효과 시퀀스에 액세스할 수 있습니다.

### 2.4단계: 오디오를 바이트 배열로 추출

```csharp
byte[] audio = effectsSequence[0].Sound.BinaryData;
```

이 코드는 오디오를 바이트 배열로 추출합니다. 이 예에서는 추출하려는 오디오가 효과 시퀀스의 첫 번째 위치(인덱스 0)에 있다고 가정합니다. 오디오가 다른 위치에 있는 경우 색인을 변경할 수 있습니다.

### 2.5단계: 추출된 오디오 저장

```csharp
string outMediaPath = Path.Combine(RunExamples.OutPath, "MediaTimeline.mpg");
File.WriteAllBytes(outMediaPath, audio);
```

 마지막으로 추출된 오디오를 미디어 파일로 저장합니다. 위의 코드는`"MediaTimeline.mpg"` 출력 디렉터리 내의 파일입니다.

그게 다야! .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 오디오를 성공적으로 추출했습니다.

## 결론

.NET용 Aspose.Slides를 사용하면 PowerPoint 프레젠테이션의 멀티미디어 요소를 쉽게 사용할 수 있습니다. 이 튜토리얼에서는 프레젠테이션에서 오디오를 추출하는 방법을 단계별로 배웠습니다. 올바른 도구와 약간의 C# 지식만 있으면 프레젠테이션을 향상하고 매력적인 멀티미디어 콘텐츠를 만들 수 있습니다.

 질문이 있거나 추가 지원이 필요한 경우 주저하지 말고[Aspose.Slides 지원 포럼](https://forum.aspose.com/).

## 자주 묻는 질문(FAQ)

### 1. PowerPoint 프레젠테이션 내의 특정 슬라이드에서 오디오를 추출할 수 있습니까?

예, 제공된 코드의 색인을 수정하여 PowerPoint 프레젠테이션 내의 모든 슬라이드에서 오디오를 추출할 수 있습니다.

### 2. Aspose.Slides for .NET을 사용하여 추출된 오디오를 어떤 형식으로 저장할 수 있나요?

.NET용 Aspose.Slides를 사용하면 추출된 오디오를 MP3, WAV 또는 기타 지원되는 오디오 형식과 같은 다양한 형식으로 저장할 수 있습니다.

### 3. Aspose.Slides for .NET은 최신 버전의 PowerPoint와 호환됩니까?

Aspose.Slides for .NET은 최신 버전을 포함한 다양한 PowerPoint 버전과 호환되도록 설계되었습니다.

### 4. Aspose.Slides를 사용하여 추출된 오디오를 조작하고 편집할 수 있나요?

예, Aspose.Slides는 PowerPoint 프레젠테이션에서 추출된 오디오 조작 및 편집을 위한 광범위한 기능을 제공합니다.

### 5. .NET용 Aspose.Slides에 대한 포괄적인 문서는 어디에서 찾을 수 있습니까?

 .NET용 Aspose.Slides에 대한 자세한 문서와 예제를 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

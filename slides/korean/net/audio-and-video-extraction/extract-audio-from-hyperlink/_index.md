---
title: Aspose.Slides를 사용하여 PowerPoint 하이퍼링크에서 오디오 추출
linktitle: 하이퍼링크에서 오디오 추출
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션의 하이퍼링크에서 오디오를 추출합니다. 멀티미디어 프로젝트를 쉽게 향상시키세요.
weight: 12
url: /ko/net/audio-and-video-extraction/extract-audio-from-hyperlink/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


멀티미디어 프리젠테이션 세계에서 오디오는 슬라이드의 전반적인 효과를 높이는 데 중요한 역할을 합니다. 오디오 하이퍼링크가 포함된 PowerPoint 프레젠테이션을 접하고 다른 용도로 오디오를 추출하는 방법이 궁금한 적이 있습니까? .NET용 Aspose.Slides를 사용하면 이 작업을 쉽게 수행할 수 있습니다. 이 단계별 가이드에서는 PowerPoint 프레젠테이션의 하이퍼링크에서 오디오를 추출하는 과정을 안내합니다.

## 전제 조건

추출 프로세스를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. .NET 라이브러리용 Aspose.Slides

개발 환경에 Aspose.Slides for .NET 라이브러리가 설치되어 있어야 합니다. 아직 다운로드하지 않으셨다면, 다음 웹사이트에서 다운로드하실 수 있습니다.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/).

### 2. 오디오 하이퍼링크가 포함된 PowerPoint 프레젠테이션

관련 오디오가 포함된 하이퍼링크가 포함된 PowerPoint 프레젠테이션(PPTX)이 있는지 확인하세요. 이것이 오디오를 추출할 소스가 됩니다.

## 네임스페이스 가져오기

먼저 Aspose.Slides for .NET을 효과적으로 사용하기 위해 C# 프로젝트에서 필요한 네임스페이스를 가져옵니다. 이러한 네임스페이스는 PowerPoint 프레젠테이션 작업과 하이퍼링크에서 오디오 추출에 필수적입니다.

```csharp
using System;
using System.IO;
using Aspose.Slides;
```

이제 전제 조건이 준비되었고 필수 네임스페이스를 가져왔으므로 추출 프로세스를 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉터리 정의

 PowerPoint 프리젠테이션이 있는 디렉토리를 지정하여 시작하십시오. 교체할 수 있습니다`"Your Document Directory"` 문서 디렉토리의 실제 경로를 사용하십시오.

```csharp
string dataDir = "Your Document Directory";
```

## 2단계: PowerPoint 프레젠테이션 로드

 Aspose.Slides를 사용하여 오디오 하이퍼링크가 포함된 PowerPoint 프레젠테이션(PPTX)을 로드합니다. 바꾸다`"HyperlinkSound.pptx"`프레젠테이션의 실제 파일 이름을 사용하세요.

```csharp
string pptxFile = Path.Combine(dataDir, "HyperlinkSound.pptx");

using (Presentation pres = new Presentation(pptxFile))
{
    // 다음 단계를 계속 진행하세요.
}
```

## 3단계: 하이퍼링크 사운드 가져오기

PowerPoint 슬라이드에서 첫 번째 도형의 하이퍼링크를 가져옵니다. 하이퍼링크에 연결된 사운드가 있으면 추출을 진행합니다.

```csharp
IHyperlink link = pres.Slides[0].Shapes[0].HyperlinkClick;

if (link.Sound != null)
{
    // 다음 단계를 계속 진행하세요.
}
```

## 4단계: 하이퍼링크에서 오디오 추출

하이퍼링크에 관련 사운드가 있는 경우 이를 바이트 배열로 추출하여 미디어 파일로 저장할 수 있습니다.

```csharp
// 하이퍼링크 사운드를 바이트 배열로 추출합니다.
byte[] audioData = link.Sound.BinaryData;

// 추출된 오디오를 저장할 경로를 지정하세요.
string outMediaPath = Path.Combine(dataDir, "HyperlinkSound.mpg");

// 추출된 오디오를 미디어 파일에 저장
File.WriteAllBytes(outMediaPath, audioData);
```

축하해요! .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션의 하이퍼링크에서 오디오를 성공적으로 추출했습니다. 추출된 오디오는 이제 멀티미디어 프로젝트에서 다른 목적으로 사용될 수 있습니다.

## 결론

.NET용 Aspose.Slides는 PowerPoint 프레젠테이션의 하이퍼링크에서 오디오를 추출할 수 있는 강력하고 사용자 친화적인 솔루션을 제공합니다. 이 가이드에 설명된 단계를 따르면 프레젠테이션의 오디오 콘텐츠를 재사용하여 멀티미디어 프로젝트를 쉽게 향상시킬 수 있습니다.

### 자주 묻는 질문(FAQ)

### .NET용 Aspose.Slides는 무료 라이브러리인가요?
 아니요, Aspose.Slides for .NET은 상업용 라이브러리이지만 다음에서 무료 평가판을 다운로드하여 기능과 문서를 탐색할 수 있습니다.[여기](https://releases.aspose.com/).

### PPT와 같은 이전 PowerPoint 형식의 하이퍼링크에서 오디오를 추출할 수 있나요?
예, .NET용 Aspose.Slides는 하이퍼링크에서 오디오를 추출하기 위해 PPTX와 PPT 형식을 모두 지원합니다.

### Aspose.Slides 지원을 위한 커뮤니티 포럼이 있습니까?
 예, Aspose에 대한 도움을 받고 경험을 공유할 수 있습니다.[Aspose.Slides 커뮤니티 포럼](https://forum.aspose.com/).

### 단기 프로젝트를 위해 Aspose.Slides의 임시 라이선스를 구입할 수 있나요?
예, 다음 사이트를 방문하여 단기 프로젝트 요구 사항을 충족하기 위해 Aspose.Slides for .NET에 대한 임시 라이센스를 얻을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### MPG 외에 추출을 지원하는 다른 오디오 형식이 있습니까?
.NET용 Aspose.Slides를 사용하면 MPG에 국한되지 않고 다양한 형식으로 오디오를 추출할 수 있습니다. 추출 후 원하는 형식으로 변환할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

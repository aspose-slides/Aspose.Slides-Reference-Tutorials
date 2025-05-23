---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에서 비디오를 추출하는 방법을 알아보세요. 이 단계별 가이드는 추출 과정을 간소화해 줍니다."
"linktitle": "슬라이드에서 비디오 추출"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides for .NET을 사용하여 슬라이드에서 비디오를 추출하는 방법"
"url": "/ko/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET을 사용하여 슬라이드에서 비디오를 추출하는 방법


Aspose.Slides for .NET은 .NET 환경에서 PowerPoint 프레젠테이션 작업을 할 수 있는 강력한 라이브러리입니다. 이 라이브러리의 유용한 기능 중 하나는 슬라이드에서 비디오를 추출하는 기능입니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에서 비디오를 추출하는 방법을 보여줍니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- Aspose.Slides for .NET: Aspose.Slides for .NET이 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다. [웹사이트](https://purchase.aspose.com/buy).

- PowerPoint 프레젠테이션: 추출하려는 비디오가 포함된 PowerPoint 프레젠테이션(예: Video.pptx)을 준비합니다.

## 네임스페이스 가져오기

Aspose.Slides for .NET을 사용하려면 필요한 네임스페이스를 가져와야 합니다. 방법은 다음과 같습니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

이제 슬라이드에서 비디오를 추출하는 과정을 여러 단계로 나누어 살펴보겠습니다.

## 1단계: 문서 디렉터리 설정

```csharp
string dataDir = "Your Document Directory";
```

바꾸다 `"Your Document Directory"` PowerPoint 프레젠테이션이 있는 디렉토리 경로를 포함합니다.

## 2단계: 프레젠테이션 로드

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

이 코드는 PowerPoint 프레젠테이션 파일을 나타내는 Presentation 객체를 초기화합니다.

## 3단계: 슬라이드 및 도형 반복

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

여기에서는 프레젠테이션의 각 슬라이드를 반복한 다음 첫 번째 슬라이드의 모양을 반복합니다(필요에 따라 수정).

## 4단계: 모양이 비디오 프레임인지 확인

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

이 단계에서는 슬라이드의 모양이 비디오 프레임인지 확인합니다.

## 5단계: 비디오 데이터 추출

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

이 코드는 비디오의 콘텐츠 유형과 바이너리 데이터를 포함한 비디오에 대한 정보를 추출합니다.

## 6단계: 비디오 저장

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

마지막으로, 이 단계에서는 비디오를 지정된 디렉토리의 새 파일에 저장합니다.

이러한 단계를 완료하면 Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에서 비디오를 성공적으로 추출할 수 있습니다.

## 결론

Aspose.Slides for .NET은 PowerPoint 프레젠테이션 작업 과정을 간소화하여 슬라이드에서 비디오를 추출하는 등의 작업을 손쉽게 수행할 수 있도록 지원합니다. 이 단계별 가이드를 따라 Aspose.Slides 라이브러리를 활용하면 강력한 PowerPoint 기능으로 .NET 애플리케이션을 더욱 강화할 수 있습니다.

## 자주 묻는 질문(FAQ)

### Aspose.Slides for .NET이란 무엇인가요?
.NET용 Aspose.Slides는 .NET 애플리케이션에서 PowerPoint 프레젠테이션 작업을 할 수 있도록 해주는 라이브러리로, 콘텐츠를 만들고, 편집하고, 추출하는 등의 작업을 할 수 있습니다.

### .NET용 Aspose.Slides에 대한 설명서는 어디에서 찾을 수 있나요?
문서를 찾을 수 있습니다 [여기](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET을 무료 평가판으로 이용할 수 있나요?
네, 무료 체험판을 받으실 수 있습니다. [여기](https://releases.aspose.com/).

### Aspose.Slides for .NET에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
임시 면허를 요청할 수 있습니다. [이 링크](https://purchase.aspose.com/temporary-license/).

### .NET용 Aspose.Slides에 대한 지원은 어디에서 받을 수 있나요?
지원은 다음에서 찾을 수 있습니다. [Aspose.Slides 포럼](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
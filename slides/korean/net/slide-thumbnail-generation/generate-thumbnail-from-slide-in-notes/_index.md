---
title: Notes의 슬라이드에서 축소판 생성
linktitle: Notes의 슬라이드에서 축소판 생성
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 프레젠테이션의 노트 섹션에 있는 슬라이드에서 축소판을 생성하는 방법을 알아보세요. 시각적 콘텐츠를 강화해보세요!
type: docs
weight: 12
url: /ko/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

현대 프레젠테이션의 세계에서는 시각적 콘텐츠가 가장 중요합니다. 효과적인 의사소통을 위해서는 매력적인 슬라이드를 만드는 것이 필수적입니다. 프레젠테이션을 향상시키는 한 가지 방법은 특히 특정 세부 사항을 강조하거나 개요를 공유하려는 경우 슬라이드에서 축소판을 생성하는 것입니다. Aspose.Slides for .NET은 이를 원활하게 달성하는 데 도움이 되는 강력한 도구입니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션의 노트 섹션에 있는 슬라이드에서 썸네일을 생성하는 과정을 안내합니다.

## 전제 조건

세부 사항을 살펴보기 전에 다음과 같은 전제 조건을 갖추어야 합니다.

### 1. .NET용 Aspose.Slides

 .NET용 Aspose.Slides가 설치 및 설정되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

### 2. .NET 환경

시스템에 .NET 개발 환경이 준비되어 있어야 합니다.

### 3. 프리젠테이션 파일

 프리젠테이션 파일이 있어야 합니다(예:`ThumbnailFromSlideInNotes.pptx`) 썸네일을 생성하려는 위치입니다.

이제 프로세스를 단계로 나누어 보겠습니다.

## 1단계: 네임스페이스 가져오기

먼저 Aspose.Slides를 사용하려면 필요한 네임스페이스를 가져와야 합니다. C# 스크립트 시작 부분에 다음 코드를 추가합니다.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 2단계: 프레젠테이션 로드

 다음으로 메모가 포함된 슬라이드가 포함된 프레젠테이션 파일을 로드해야 합니다. 다음 코드를 사용하여 인스턴스화`Presentation` 수업:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // 귀하의 코드는 여기에 있습니다
}
```

## 3단계: 슬라이드에 액세스

프레젠테이션에서 축소판을 생성하려는 슬라이드를 선택할 수 있습니다. 이 예에서는 첫 번째 슬라이드에 액세스합니다.

```csharp
ISlide sld = pres.Slides[0];
```

## 4단계: 원하는 치수 정의

생성하려는 축소판의 크기(너비 및 높이)를 지정합니다. 예를 들어:

```csharp
int desiredX = 1200; // 너비
int desiredY = 800;  // 키
```

## 5단계: 스케일링 인자 계산

축소판이 원하는 크기에 맞는지 확인하려면 다음과 같이 배율 인수를 계산하세요.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 6단계: 썸네일 만들기

이제 계산된 배율 인수를 사용하여 실제 크기 이미지 축소판을 만듭니다.

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## 7단계: 썸네일 저장

마지막으로 생성된 썸네일을 JPEG 이미지로 저장합니다.

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

그게 다야! Aspose.Slides for .NET을 사용하여 프레젠테이션의 노트 섹션에 있는 슬라이드에서 썸네일을 성공적으로 생성했습니다.

## 결론

프리젠테이션에 축소판을 통합하면 시각적 매력과 효과가 크게 향상될 수 있습니다. .NET용 Aspose.Slides는 이 프로세스를 간단하게 만들어 슬라이드에서 맞춤형 썸네일을 쉽게 만들 수 있도록 해줍니다.

## FAQ(자주 묻는 질문)

### 생성된 썸네일을 어떤 형식으로 저장할 수 있나요?
요구 사항에 따라 JPEG, PNG 등 다양한 형식으로 축소판을 저장할 수 있습니다.

### 여러 슬라이드의 축소판을 동시에 생성할 수 있나요?
예, 프레젠테이션의 슬라이드를 반복하면서 각 슬라이드에 대한 축소판을 생성할 수 있습니다.

### Aspose.Slides for .NET은 다른 .NET 프레임워크와 호환됩니까?
예, Aspose.Slides for .NET은 .NET Core 및 .NET Framework를 포함한 다양한 .NET 프레임워크와 호환됩니다.

### 생성된 썸네일의 모양을 사용자 정의할 수 있나요?
전적으로! .NET용 Aspose.Slides는 크기, 품질 등과 같은 썸네일의 모양을 사용자 정의하기 위한 옵션을 제공합니다.

### .NET용 Aspose.Slides에 대한 지원이나 추가 지원은 어디서 받을 수 있나요?
 다음에서 도움을 찾고 Aspose 커뮤니티에 참여할 수 있습니다.[Aspose 지원 포럼](https://forum.aspose.com/).
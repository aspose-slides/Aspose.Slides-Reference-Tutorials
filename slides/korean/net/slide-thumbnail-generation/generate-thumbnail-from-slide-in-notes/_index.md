---
"description": "Aspose.Slides for .NET을 사용하여 프레젠테이션의 노트 섹션에 있는 슬라이드에서 썸네일을 생성하는 방법을 알아보세요. 시각적 콘텐츠를 더욱 풍부하게 만들어 보세요!"
"linktitle": "슬라이드에서 썸네일 생성"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "슬라이드에서 썸네일 생성"
"url": "/ko/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 슬라이드에서 썸네일 생성


현대 프레젠테이션에서는 시각적 콘텐츠가 핵심입니다. 효과적인 소통을 위해서는 매력적인 슬라이드를 만드는 것이 필수적입니다. 프레젠테이션을 더욱 돋보이게 하는 한 가지 방법은 슬라이드에서 썸네일을 생성하는 것입니다. 특히 특정 세부 사항을 강조하거나 개요를 공유하고 싶을 때 더욱 그렇습니다. Aspose.Slides for .NET은 이러한 작업을 원활하게 수행할 수 있도록 도와주는 강력한 도구입니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션의 노트 섹션에 있는 슬라이드에서 썸네일을 생성하는 과정을 안내합니다.

## 필수 조건

자세한 내용을 살펴보기 전에 다음과 같은 전제 조건이 충족되어야 합니다.

### 1. .NET용 Aspose.Slides

Aspose.Slides for .NET이 설치 및 설정되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).

### 2. .NET 환경

시스템에 .NET 개발 환경이 준비되어 있어야 합니다.

### 3. 프레젠테이션 파일

프레젠테이션 파일을 가지고 있습니다(예: `ThumbnailFromSlideInNotes.pptx`)을 통해 썸네일을 생성하고자 합니다.

이제 이 과정을 단계별로 나누어 보겠습니다.

## 1단계: 네임스페이스 가져오기

먼저 Aspose.Slides를 사용하는 데 필요한 네임스페이스를 가져와야 합니다. C# 스크립트 시작 부분에 다음 코드를 추가하세요.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 2단계: 프레젠테이션 로드

다음으로, 노트가 포함된 슬라이드가 포함된 프레젠테이션 파일을 로드해야 합니다. 다음 코드를 사용하여 `Presentation` 수업:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // 여기에 코드를 입력하세요
}
```

## 3단계: 슬라이드에 액세스

프레젠테이션에서 어떤 슬라이드에 대한 썸네일을 생성할지 선택할 수 있습니다. 이 예시에서는 첫 번째 슬라이드에 접근해 보겠습니다.

```csharp
ISlide sld = pres.Slides[0];
```

## 4단계: 원하는 차원 정의

생성할 썸네일의 크기(너비와 높이)를 지정하세요. 예:

```csharp
int desiredX = 1200; // 너비
int desiredY = 800;  // 키
```

## 5단계: 스케일링 계수 계산

썸네일이 원하는 크기에 맞는지 확인하려면 다음과 같이 크기 조정 요소를 계산하세요.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 6단계: 썸네일 만들기

이제 계산된 크기 조정 요소를 사용하여 전체 크기 이미지 썸네일을 만듭니다.

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## 7단계: 썸네일 저장

마지막으로 생성된 썸네일을 JPEG 이미지로 저장합니다.

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

이제 Aspose.Slides for .NET을 사용하여 프레젠테이션의 노트 섹션에 있는 슬라이드에서 썸네일을 성공적으로 생성했습니다.

## 결론

프레젠테이션에 썸네일을 추가하면 시각적인 매력과 효과를 크게 향상시킬 수 있습니다. Aspose.Slides for .NET을 사용하면 이 과정을 간소화하여 슬라이드에서 사용자 지정 썸네일을 손쉽게 만들 수 있습니다.

## FAQ(자주 묻는 질문)

### 생성된 썸네일은 어떤 형식으로 저장할 수 있나요?
요구 사항에 따라 JPEG, PNG 등 다양한 형식으로 썸네일을 저장할 수 있습니다.

### 여러 슬라이드의 썸네일을 한 번에 생성할 수 있나요?
네, 프레젠테이션의 슬라이드를 반복해서 살펴보고 각 슬라이드에 대한 썸네일을 생성할 수 있습니다.

### Aspose.Slides for .NET은 다른 .NET 프레임워크와 호환됩니까?
네, Aspose.Slides for .NET은 .NET Core 및 .NET Framework를 포함한 다양한 .NET 프레임워크와 호환됩니다.

### 생성된 썸네일의 모양을 사용자 지정할 수 있나요?
물론입니다! Aspose.Slides for .NET은 크기, 품질 등 썸네일 모양을 사용자 지정할 수 있는 옵션을 제공합니다.

### Aspose.Slides for .NET에 대한 지원이나 추가 도움말은 어디에서 받을 수 있나요?
Aspose 커뮤니티에서 도움을 받고 참여할 수 있습니다. [Aspose 지원 포럼](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
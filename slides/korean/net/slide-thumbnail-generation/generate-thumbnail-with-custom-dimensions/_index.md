---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 사용자 지정 썸네일 이미지를 생성하는 방법을 알아보세요. 사용자 경험과 기능을 향상시켜 보세요."
"linktitle": "사용자 정의 치수로 썸네일 생성"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "사용자 정의 치수로 슬라이드에 썸네일 생성"
"url": "/ko/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 사용자 정의 치수로 슬라이드에 썸네일 생성


PowerPoint 프레젠테이션의 사용자 지정 썸네일 이미지를 만드는 것은 대화형 애플리케이션 구축, 사용자 경험 향상, 다양한 플랫폼에 맞춰 콘텐츠 최적화 등 어떤 작업이든 매우 유용한 자산이 될 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 사용자 지정 썸네일 이미지를 생성하는 과정을 안내합니다. 이 강력한 라이브러리를 사용하면 .NET 애플리케이션에서 PowerPoint 파일을 프로그래밍 방식으로 조작, 변환 및 향상시킬 수 있습니다.

## 필수 조건

사용자 정의 썸네일 이미지를 생성하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. .NET용 Aspose.Slides

프로젝트에 Aspose.Slides for .NET 라이브러리가 설치되어 있어야 합니다. 아직 설치되어 있지 않다면 필요한 문서와 다운로드 링크를 확인하세요. [여기](https://reference.aspose.com/slides/net/).

### 2. 파워포인트 프레젠테이션

사용자 지정 썸네일 이미지를 생성할 PowerPoint 프레젠테이션이 있는지 확인하세요. 이 프레젠테이션은 프로젝트 디렉터리에서 액세스할 수 있어야 합니다.

### 3. 개발 환경

이 튜토리얼을 따르려면 C#을 사용한 .NET 프로그래밍에 대한 실무 지식이 있어야 하며 Visual Studio와 같은 개발 환경이 설정되어 있어야 합니다.

이제 필수 조건을 살펴보았으니, 사용자 정의 썸네일을 생성하는 과정을 단계별 지침으로 나누어 살펴보겠습니다.

## 네임스페이스 가져오기

먼저, C# 코드에 필요한 네임스페이스를 포함해야 합니다. 이 네임스페이스를 사용하면 Aspose.Slides를 사용하고 PowerPoint 프레젠테이션을 조작할 수 있습니다.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 1단계: 프레젠테이션 로드

먼저, 사용자 지정 썸네일 이미지를 생성할 PowerPoint 프레젠테이션을 로드합니다. 이 작업은 Aspose.Slides 라이브러리를 사용하여 수행합니다.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// 프레젠테이션 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
using (Presentation pres = new Presentation(srcFileName))
{
    // 썸네일 생성을 위한 코드는 여기에 입력됩니다.
}
```

## 2단계: 슬라이드에 액세스

로드된 프레젠테이션 내에서 사용자 지정 썸네일 이미지를 생성할 특정 슬라이드에 접근해야 합니다. 슬라이드의 인덱스를 통해 슬라이드를 선택할 수 있습니다.

```csharp
// 첫 번째 슬라이드에 접근하세요(필요에 따라 인덱스를 변경할 수 있습니다)
ISlide sld = pres.Slides[0];
```

## 3단계: 사용자 정의 썸네일 크기 정의

사용자 지정 썸네일 이미지의 원하는 크기를 지정하세요. 애플리케이션의 요구 사항에 따라 너비와 높이를 픽셀 단위로 정의할 수 있습니다.

```csharp
int desiredX = 1200; // 너비
int desiredY = 800;  // 키
```

## 4단계: 스케일링 계수 계산

슬라이드의 종횡비를 유지하려면 슬라이드 크기와 원하는 치수에 따라 X 및 Y 치수에 대한 크기 조정 요소를 계산합니다.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 5단계: 썸네일 이미지 생성

지정된 사용자 정의 치수로 슬라이드의 전체 크기 이미지를 만들고 JPEG 형식으로 디스크에 저장합니다.

```csharp
// 실물 크기의 이미지를 만듭니다
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// JPEG 형식으로 이미지를 디스크에 저장합니다.
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

이제 이러한 단계를 따라가면 PowerPoint 프레젠테이션에서 사용자 지정 썸네일 이미지가 성공적으로 생성되었을 것입니다.

## 결론

Aspose.Slides for .NET을 사용하여 PowerPoint 프레젠테이션에서 사용자 지정 썸네일 이미지를 생성하는 것은 애플리케이션의 사용자 경험과 기능을 향상시킬 수 있는 귀중한 기술입니다. 이 튜토리얼에 설명된 단계를 따르면 특정 요구 사항을 충족하는 사용자 지정 썸네일을 쉽게 만들 수 있습니다.

---

## FAQ(자주 묻는 질문)

### Aspose.Slides for .NET이란 무엇인가요?
Aspose.Slides for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 PowerPoint 프레젠테이션을 작업할 수 있게 해주는 강력한 라이브러리입니다.

### .NET용 Aspose.Slides에 대한 설명서는 어디에서 찾을 수 있나요?
문서를 찾을 수 있습니다 [여기](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET은 무료로 사용할 수 있나요?
Aspose.Slides for .NET은 상용 라이브러리입니다. 가격 및 라이선스 정보는 여기에서 확인하실 수 있습니다. [여기](https://purchase.aspose.com/buy).

### Aspose.Slides for .NET을 사용하려면 고급 프로그래밍 기술이 필요합니까?
.NET 프로그래밍에 대한 지식이 어느 정도 있는 것이 유익하지만, Aspose.Slides for .NET은 PowerPoint 프레젠테이션 작업을 간소화하는 사용자 친화적인 API를 제공합니다.

### Aspose.Slides for .NET에 대한 기술 지원을 받을 수 있나요?
네, 기술 지원 및 커뮤니티 포럼에 접속할 수 있습니다. [여기](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
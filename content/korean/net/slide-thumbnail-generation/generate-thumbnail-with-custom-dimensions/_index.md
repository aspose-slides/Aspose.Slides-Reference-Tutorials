---
title: 사용자 정의 차원을 사용하여 슬라이드에서 축소판 생성
linktitle: 사용자 정의 차원으로 썸네일 생성
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 사용자 정의 축소판 이미지를 생성하는 방법을 알아보세요. 사용자 경험과 기능을 향상시킵니다.
type: docs
weight: 13
url: /ko/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

PowerPoint 프레젠테이션의 사용자 정의 축소판 이미지를 만드는 것은 대화형 응용 프로그램을 구축하든, 사용자 경험을 향상시키든, 다양한 플랫폼에 맞게 콘텐츠를 최적화하든 귀중한 자산이 될 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 사용자 정의 썸네일 이미지를 생성하는 과정을 안내합니다. 이 강력한 라이브러리를 사용하면 .NET 응용 프로그램에서 프로그래밍 방식으로 PowerPoint 파일을 조작, 변환 및 향상할 수 있습니다.

## 전제조건

사용자 정의 썸네일 이미지 생성을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. .NET용 Aspose.Slides

 프로젝트에 Aspose.Slides for .NET 라이브러리가 설치되어 있어야 합니다. 아직 찾지 않았다면 필요한 문서와 다운로드 링크를 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/net/).

### 2. 파워포인트 프레젠테이션

사용자 정의 축소판 이미지를 생성하려는 PowerPoint 프레젠테이션이 있는지 확인하십시오. 이 프레젠테이션은 프로젝트 디렉터리 내에서 액세스할 수 있어야 합니다.

### 3. 개발 환경

이 자습서를 따르려면 C#을 사용한 .NET 프로그래밍 및 Visual Studio와 같은 개발 환경 설정에 대한 실무 지식이 있어야 합니다.

이제 전제조건을 다루었으므로 사용자 정의 썸네일을 생성하는 과정을 단계별 지침으로 나누어 보겠습니다.

## 네임스페이스 가져오기

먼저 C# 코드에 필수 네임스페이스를 포함해야 합니다. 이러한 네임스페이스를 사용하면 Aspose.Slides로 작업하고 PowerPoint 프레젠테이션을 조작할 수 있습니다.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 1단계: 프레젠테이션 로드

시작하려면 사용자 정의 축소판 이미지를 생성하려는 PowerPoint 프레젠테이션을 로드합니다. 이는 Aspose.Slides 라이브러리를 사용하여 달성됩니다.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// 프레젠테이션 파일을 나타내는 프레젠테이션 클래스를 인스턴스화합니다.
using (Presentation pres = new Presentation(srcFileName))
{
    // 썸네일 생성을 위한 코드가 여기에 표시됩니다.
}
```

## 2단계: 슬라이드에 액세스

로드된 프레젠테이션 내에서 사용자 정의 축소판 이미지를 생성하려는 특정 슬라이드에 액세스해야 합니다. 색인별로 슬라이드를 선택할 수 있습니다.

```csharp
// 첫 번째 슬라이드에 액세스합니다(필요에 따라 색인을 변경할 수 있음).
ISlide sld = pres.Slides[0];
```

## 3단계: 사용자 정의 썸네일 크기 정의

맞춤 썸네일 이미지에 원하는 크기를 지정하세요. 애플리케이션 요구 사항에 따라 너비와 높이를 픽셀 단위로 정의할 수 있습니다.

```csharp
int desiredX = 1200; // 너비
int desiredY = 800;  // 키
```

## 4단계: 스케일링 인자 계산

슬라이드의 가로 세로 비율을 유지하려면 슬라이드 크기와 원하는 치수를 기준으로 X 및 Y 치수의 배율 인수를 계산하세요.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 5단계: 썸네일 이미지 생성

지정된 사용자 정의 크기로 슬라이드의 실제 크기 이미지를 생성하고 JPEG 형식으로 디스크에 저장합니다.

```csharp
// 실물 크기 이미지 만들기
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// 이미지를 JPEG 형식으로 디스크에 저장
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

이제 이러한 단계를 수행했으므로 PowerPoint 프레젠테이션에서 사용자 정의 축소판 이미지가 성공적으로 생성되었을 것입니다.

## 결론

.NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 사용자 정의 축소판 이미지를 생성하는 것은 애플리케이션의 사용자 경험과 기능을 향상시킬 수 있는 귀중한 기술입니다. 이 튜토리얼에 설명된 단계를 따르면 특정 요구 사항을 충족하는 사용자 정의 축소판을 쉽게 만들 수 있습니다.

---

## FAQ(자주 묻는 질문)

### .NET용 Aspose.Slides란 무엇입니까?
Aspose.Slides for .NET은 개발자가 .NET 애플리케이션에서 프로그래밍 방식으로 PowerPoint 프레젠테이션 작업을 할 수 있게 해주는 강력한 라이브러리입니다.

### .NET용 Aspose.Slides에 대한 설명서는 어디서 찾을 수 있나요?
 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/slides/net/).

### .NET용 Aspose.Slides는 무료로 사용할 수 있나요?
 Aspose.Slides for .NET은 상용 라이브러리입니다. 가격 및 라이선스 정보를 확인할 수 있습니다.[여기](https://purchase.aspose.com/buy).

### .NET용 Aspose.Slides를 사용하려면 고급 프로그래밍 기술이 필요합니까?
.NET 프로그래밍에 대한 일부 지식이 도움이 되지만 .NET용 Aspose.Slides는 PowerPoint 프레젠테이션 작업을 단순화하는 사용자 친화적인 API를 제공합니다.

### .NET용 Aspose.Slides에 대한 기술 지원이 제공됩니까?
 예, 기술 지원 및 커뮤니티 포럼에 액세스할 수 있습니다.[여기](https://forum.aspose.com/).
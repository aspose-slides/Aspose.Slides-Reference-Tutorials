---
title: Aspose.Slides의 슬라이드 썸네일 생성
linktitle: Aspose.Slides의 슬라이드 썸네일 생성
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: 단계별 가이드 및 코드 예제를 사용하여 Aspose.Slides for .NET에서 슬라이드 축소판을 생성합니다. 모양을 사용자 정의하고 축소판을 저장합니다. 프레젠테이션 미리보기를 향상하세요.
weight: 10
url: /ko/net/slide-thumbnail-generation/slide-thumbnail-generation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Aspose.Slides를 사용하여 .NET 애플리케이션에서 슬라이드 축소판을 생성하려는 경우 올바른 위치에 있습니다. 슬라이드 축소판 만들기는 사용자 지정 PowerPoint 뷰어를 만들거나 프레젠테이션의 이미지 미리 보기를 생성하는 등 다양한 시나리오에서 유용한 기능이 될 수 있습니다. 이 종합 가이드에서는 프로세스를 단계별로 안내해 드립니다. 사전 요구 사항, 네임스페이스 가져오기 및 각 예를 여러 단계로 나누어 슬라이드 축소판 생성을 원활하게 구현할 수 있도록 도와드립니다.

## 전제 조건

.NET용 Aspose.Slides를 사용하여 슬라이드 썸네일을 생성하는 프로세스를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. Aspose.Slides 설치
시작하려면 개발 환경에 Aspose.Slides for .NET이 설치되어 있는지 확인하세요. 아직 다운로드하지 않았다면 Aspose 웹사이트에서 다운로드할 수 있습니다.

-  다운로드 링크:[.NET용 Aspose.Slides](https://releases.aspose.com/slides/net/)

### 2. 작업할 문서
슬라이드 축소판을 추출하려면 PowerPoint 문서가 필요합니다. 프레젠테이션 파일이 준비되어 있는지 확인하세요.

### 3. .NET 개발 환경
이 튜토리얼에서는 .NET에 대한 실무 지식과 개발 환경 설정이 필수적입니다.

이제 전제 조건을 다루었으므로 .NET용 Aspose.Slides에서 슬라이드 썸네일 생성에 대한 단계별 가이드를 시작하겠습니다.

## 네임스페이스 가져오기

Aspose.Slides 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 이 단계는 코드가 라이브러리와 올바르게 상호 작용하는지 확인하는 데 중요합니다.

### 1단계: 지시문을 사용하여 추가

C# 코드에서 파일 시작 부분에 다음 using 지시문을 포함합니다.

```csharp
using Aspose.Slides;
using System.Drawing;
using System.Drawing.Imaging;
```

이러한 지시문을 사용하면 슬라이드 축소판을 생성하는 데 필요한 클래스와 메서드를 사용할 수 있습니다.

이제 슬라이드 축소판 생성 프로세스를 여러 단계로 나누어 보겠습니다.

## 2단계: 문서 디렉터리 설정

 먼저 PowerPoint 문서가 있는 디렉터리를 정의합니다. 바꾸다`"Your Document Directory"` 파일의 실제 경로와 함께.

```csharp
string dataDir = "Your Document Directory";
```

## 3단계: 프레젠테이션 클래스 인스턴스화

 이 단계에서는`Presentation` 프리젠테이션 파일을 나타내는 클래스입니다.

```csharp
using (Presentation presentation = new Presentation(dataDir + "YourPresentation.pptx"))
{
 // 슬라이드 축소판 생성을 위한 코드는 여기에 있습니다.
}
```

 꼭 교체하세요`"YourPresentation.pptx"` PowerPoint 파일의 실제 이름으로.

## 4단계: 썸네일 생성

 이제 프로세스의 핵심이 나옵니다. 내부`using` 블록에 원하는 슬라이드의 썸네일을 생성하는 코드를 추가하세요. 제공된 예에서는 첫 번째 슬라이드에서 첫 번째 도형의 축소판을 생성합니다.

```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Appearance, 1, 1))
{
 // 썸네일 이미지를 저장하는 코드는 여기에 있습니다.
}
```

이 코드를 수정하여 필요에 따라 특정 슬라이드 및 모양의 축소판을 캡처할 수 있습니다.

## 5단계: 썸네일 저장

마지막 단계에서는 생성된 썸네일을 원하는 이미지 형식으로 디스크에 저장하는 작업이 포함됩니다. 이 예에서는 축소판을 PNG 형식으로 저장합니다.

```csharp
bitmap.Save(dataDir + "Shape_thumbnail_Bound_Shape_out.png", ImageFormat.Png);
```

 바꾸다`"Shape_thumbnail_Bound_Shape_out.png"` 원하는 파일 이름과 위치로

## 결론

축하해요! .NET용 Aspose.Slides를 사용하여 슬라이드 축소판을 생성하는 방법을 성공적으로 배웠습니다. 이 강력한 기능은 PowerPoint 프레젠테이션의 시각적 미리 보기를 제공하여 응용 프로그램을 향상시킬 수 있습니다. 올바른 전제 조건을 갖추고 단계별 가이드를 따르면 이 기능을 원활하게 구현할 수 있습니다.

## 자주 묻는 질문

### Q: 프레젠테이션의 여러 슬라이드에 대한 축소판을 생성할 수 있습니까?
A: 예, 프레젠테이션 내의 모든 슬라이드나 도형에 대한 축소판을 생성하도록 코드를 수정할 수 있습니다.

### Q: 썸네일 저장에 지원되는 이미지 형식은 무엇입니까?
A: .NET용 Aspose.Slides는 PNG, JPEG, BMP를 포함한 다양한 이미지 형식을 지원합니다.

### Q: 썸네일 생성 과정에 제한 사항이 있나요?
A: 더 큰 프리젠테이션이나 복잡한 모양의 경우 프로세스에서 추가 메모리와 처리 시간을 소비할 수 있습니다.

### Q: 생성된 썸네일의 크기를 사용자 정의할 수 있나요?
A: 예, 매개변수를 수정하여 치수를 조정할 수 있습니다.`GetThumbnail` 방법.

### Q: Aspose.Slides for .NET은 상업용으로 적합합니까?
A: 예, Aspose.Slides는 개인 및 상업용 애플리케이션 모두를 위한 강력한 솔루션입니다. Aspose 웹사이트에서 라이선스 세부정보를 확인할 수 있습니다.

 추가 지원이나 질문이 있는 경우 언제든지 다음 사이트를 방문하세요.[Aspose.Slides 지원 포럼](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: 프레젠테이션에 레이아웃 슬라이드 추가
linktitle: 프레젠테이션에 레이아웃 슬라이드 추가
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요. 전문적인 터치를 위해 레이아웃 슬라이드를 추가하세요.
weight: 11
url: /ko/net/chart-creation-and-customization/add-layout-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


오늘날의 디지털 시대에 영향력 있는 프레젠테이션을 만드는 것은 필수적인 기술입니다. 잘 구성되어 있고 시각적으로 매력적인 프레젠테이션은 메시지를 효과적으로 전달할 수 있습니다. Aspose.Slides for .NET은 멋진 프레젠테이션을 즉시 만드는 데 도움이 되는 강력한 도구입니다. 이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에 레이아웃 슬라이드를 추가하는 방법을 살펴보겠습니다. 프로세스를 따라하기 쉬운 단계로 나누어 개념을 철저하게 이해할 수 있도록 하겠습니다. 시작하자!

## 전제 조건

튜토리얼을 시작하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.

1.  .NET 라이브러리용 Aspose.Slides: .NET 라이브러리용 Aspose.Slides가 설치되어 있어야 합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

2. 개발 환경: 코드를 작성하고 실행하려면 Visual Studio와 같은 개발 환경이 설정되어 있는지 확인하세요.

3. 샘플 프레젠테이션: 작업하려면 샘플 PowerPoint 프레젠테이션이 필요합니다. 기존 프레젠테이션을 사용하거나 새 프레젠테이션을 만들 수 있습니다.

이제 전제 조건이 준비되었으므로 프레젠테이션에 레이아웃 슬라이드를 추가해 보겠습니다.

## 네임스페이스 가져오기

먼저 Aspose.Slides를 사용하려면 .NET 프로젝트에 필요한 네임스페이스를 가져와야 합니다. 코드에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## 1단계: 프레젠테이션 인스턴스화

 이 단계에서는`Presentation` 작업하려는 프리젠테이션 파일을 나타내는 클래스입니다. 방법은 다음과 같습니다.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // 귀하의 코드는 여기에 저장됩니다
}
```

 여기,`FileName` PowerPoint 프레젠테이션 파일의 경로입니다. 이에 따라 파일 경로를 조정하십시오.

## 2단계: 레이아웃 슬라이드 선택

다음 단계에서는 프레젠테이션에 추가할 레이아웃 슬라이드를 선택합니다. Aspose.Slides를 사용하면 "제목 및 개체" 또는 "제목"과 같은 미리 정의된 다양한 레이아웃 슬라이드 유형 중에서 선택할 수 있습니다. 프레젠테이션에 특정 레이아웃이 포함되어 있지 않은 경우 사용자 정의 레이아웃을 만들 수도 있습니다. 레이아웃 슬라이드를 선택하는 방법은 다음과 같습니다.

```csharp
IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
ILayoutSlide layoutSlide =
    layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
    layoutSlides.GetByType(SlideLayoutType.Title);
```

위 코드에서 볼 수 있듯이 "제목 및 개체" 유형의 레이아웃 슬라이드를 찾으려고 합니다. 찾을 수 없으면 "제목" 레이아웃으로 대체됩니다. 필요에 맞게 이 논리를 조정할 수 있습니다.

## 3단계: 빈 슬라이드 삽입

 이제 레이아웃 슬라이드를 선택했으므로 해당 레이아웃이 포함된 빈 슬라이드를 프레젠테이션에 추가할 수 있습니다. 이는 다음을 사용하여 달성됩니다.`InsertEmptySlide` 방법. 이 단계의 코드는 다음과 같습니다.

```csharp
p.Slides.InsertEmptySlide(0, layoutSlide);
```

이 예에서는 빈 슬라이드를 위치 0에 삽입하지만 필요에 따라 다른 위치를 지정할 수 있습니다.

## 4단계: 프레젠테이션 저장

 마지막으로 업데이트된 프레젠테이션을 저장할 시간입니다. 당신은 사용할 수 있습니다`Save`프레젠테이션을 원하는 형식으로 저장하는 방법입니다. 코드는 다음과 같습니다.

```csharp
p.Save(FileName, SaveFormat.Pptx);
```

 꼭 조정하세요`FileName` 원하는 파일 이름과 형식으로 프레젠테이션을 저장하는 변수입니다.

축하해요! Aspose.Slides for .NET을 사용하여 프레젠테이션에 레이아웃 슬라이드를 성공적으로 추가했습니다. 이렇게 하면 슬라이드의 구조와 시각적 매력이 향상되어 프레젠테이션이 더욱 매력적으로 만들어집니다.

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에 레이아웃 슬라이드를 추가하는 방법을 살펴보았습니다. 올바른 레이아웃을 사용하면 콘텐츠가 더욱 체계적이고 시각적으로 보기 좋은 방식으로 표시됩니다. Aspose.Slides는 이 프로세스를 단순화하여 전문적인 프레젠테이션을 쉽게 만들 수 있도록 해줍니다.

다양한 레이아웃 슬라이드 유형을 자유롭게 시험해보고 필요에 맞게 프레젠테이션을 맞춤설정해 보세요. .NET용 Aspose.Slides를 사용하면 프레젠테이션 기술을 한 단계 더 발전시킬 수 있는 강력한 도구를 사용할 수 있습니다.

## 자주 묻는 질문(FAQ)

### .NET용 Aspose.Slides란 무엇입니까?
Aspose.Slides for .NET은 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 작업할 수 있도록 하는 .NET 라이브러리입니다. PowerPoint 파일을 생성, 편집 및 조작하기 위한 다양한 기능을 제공합니다.

### .NET용 Aspose.Slides에 대한 설명서는 어디서 찾을 수 있나요?
 문서는 다음에서 찾을 수 있습니다.[.NET 문서용 Aspose.Slides](https://reference.aspose.com/slides/net/). 시작하는 데 도움이 되는 자세한 정보와 예제를 제공합니다.

### .NET용 Aspose.Slides의 무료 평가판이 있습니까?
 예, .NET용 Aspose.Slides 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/). 이 평가판을 사용하면 구매하기 전에 라이브러리의 기능을 살펴볼 수 있습니다.

### .NET용 Aspose.Slides의 임시 라이선스를 어떻게 얻을 수 있나요?
 방문하셔서 임시면허를 취득하실 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/). 임시 라이센스는 평가 및 테스트 목적으로 유용합니다.

### .NET용 Aspose.Slides에 대한 지원이나 도움을 어디서 구할 수 있나요?
 질문이 있거나 도움이 필요한 경우 Aspose.Slides for .NET 포럼을 방문하세요.[Aspose 커뮤니티 포럼](https://forum.aspose.com/). 커뮤니티는 활성화되어 있으며 사용자 쿼리를 해결하는 데 도움이 됩니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

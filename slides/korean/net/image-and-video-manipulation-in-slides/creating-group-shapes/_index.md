---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint에서 그룹 도형을 만드는 방법을 알아보세요. 시각적으로 매력적인 프레젠테이션을 위한 단계별 가이드를 따라해 보세요."
"linktitle": "Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 그룹 모양 만들기"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides - .NET에서 그룹 모양 만들기"
"url": "/ko/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET에서 그룹 모양 만들기

## 소개
프레젠테이션 슬라이드의 시각적 매력을 높이고 콘텐츠를 더욱 효율적으로 구성하고 싶다면 그룹 도형을 통합하는 것이 효과적인 솔루션입니다. Aspose.Slides for .NET은 PowerPoint 프레젠테이션에서 그룹 도형을 만들고 조작하는 간편한 방법을 제공합니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 그룹 도형을 만드는 과정을 단계별로 나누어 살펴보겠습니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
- Aspose.Slides for .NET: Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [웹사이트](https://releases.aspose.com/slides/net/).
- 개발 환경: Visual Studio와 같은 .NET 호환 IDE로 작업 환경을 설정합니다.
- C#에 대한 기본 지식: C# 프로그래밍 언어의 기본 사항을 익혀보세요.
## 네임스페이스 가져오기
C# 프로젝트에서 먼저 필요한 네임스페이스를 가져옵니다.
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1단계: 프레젠테이션 클래스 인스턴스화

인스턴스를 생성합니다 `Presentation` 클래스를 지정하고 문서가 저장된 디렉토리를 지정합니다.

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // 이 블록 내에서 다음 단계를 계속 진행하세요.
}
```

## 2단계: 첫 번째 슬라이드에 액세스

프레젠테이션에서 첫 번째 슬라이드를 검색합니다.

```csharp
ISlide sld = pres.Slides[0];
```

## 3단계: 모양 컬렉션에 액세스하기

슬라이드의 모양 컬렉션에 액세스하세요.

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## 4단계: 그룹 모양 추가

슬라이드에 그룹 모양을 추가합니다.

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## 5단계: 그룹 모양 내부에 모양 추가

그룹 모양을 개별 모양으로 채웁니다.

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## 6단계: 그룹 모양 프레임 추가

전체 그룹 모양에 대한 프레임을 정의합니다.

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## 7단계: 프레젠테이션 저장

수정된 프레젠테이션을 지정된 디렉토리에 저장합니다.

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 그룹 모양을 성공적으로 만들려면 C# 애플리케이션에서 이 단계를 반복합니다.

## 결론
이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 그룹 도형을 만드는 과정을 살펴보았습니다. 다음 단계를 따라 하면 PowerPoint 프레젠테이션의 시각적인 매력과 구성력을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides는 최신 버전의 .NET과 호환됩니까?
네, Aspose.Slides는 최신 .NET 버전을 지원하도록 정기적으로 업데이트됩니다. [선적 서류 비치](https://reference.aspose.com/slides/net/) 호환성에 대한 자세한 내용은 다음을 참조하세요.
### 구매하기 전에 Aspose.Slides를 사용해 볼 수 있나요?
물론입니다! 무료 체험판을 다운로드하실 수 있습니다. [여기](https://releases.aspose.com/).
### Aspose.Slides 관련 질의에 대한 지원은 어디에서 찾을 수 있나요?
Aspose.Slides를 방문하세요 [법정](https://forum.aspose.com/c/slides/11) 지역사회의 지원과 토론을 위해.
### Aspose.Slides에 대한 임시 라이선스를 얻으려면 어떻게 해야 하나요?
임시면허를 받을 수 있습니다 [여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides의 전체 라이선스는 어디에서 구매할 수 있나요?
라이센스는 다음에서 구매할 수 있습니다. [구매 페이지](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
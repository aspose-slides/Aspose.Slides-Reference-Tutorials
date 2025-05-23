---
"date": "2025-04-16"
"description": "Aspose.Slides for .NET을 사용하여 도형 내 텍스트의 언어 속성을 설정하는 방법을 알아보세요. 이 가이드에서는 자동 도형 추가, 언어 ID 설정, 프레젠테이션 저장 방법을 다룹니다."
"title": "Aspose.Slides for .NET을 사용하여 PowerPoint 도형에 언어를 설정하는 방법"
"url": "/ko/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET을 사용하여 PowerPoint 도형에 언어를 설정하는 방법

디지털 프레젠테이션 환경에서는 콘텐츠가 다양한 언어로 접근 가능하고 올바른 형식을 유지하는 것이 어려울 수 있습니다. Aspose.Slides for .NET을 사용하면 PowerPoint 슬라이드의 도형 내 텍스트에 언어 속성을 손쉽게 설정할 수 있습니다. 이 기능은 특히 다국어 문서를 준비하거나 글로벌 커뮤니케이션의 일관성을 유지할 때 유용합니다.

**배울 내용:**
- 자동 모양을 추가하고 모양을 텍스트로 삽입합니다.
- Aspose.Slides를 사용하여 텍스트 부분의 언어 ID를 설정합니다.
- 사용자 정의 구성으로 프레젠테이션을 저장합니다.

이 기능을 원활하게 구현하는 방법을 자세히 살펴보겠습니다.

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

- **라이브러리 및 종속성**: Aspose.Slides for .NET이 설치되어 있어야 합니다. 이 라이브러리는 C#에서 PowerPoint 프레젠테이션을 조작하는 데 필수적입니다.
  
- **환경 설정**: .NET Core 또는 .NET Framework를 갖춘 개발 환경이 필요합니다.

- **지식 전제 조건**: 기본적인 C# 프로그래밍 개념에 익숙하고 객체 지향 프로그래밍 원칙을 이해하면 도움이 됩니다.

## .NET용 Aspose.Slides 설정

시작하려면 Aspose.Slides 라이브러리를 설치해야 합니다. 다음 방법 중 하나를 사용하여 설치할 수 있습니다.

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**패키지 관리자**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI**
"Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득

임시 라이센스를 다운로드하여 무료 평가판을 시작할 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/). 지속적으로 사용하려면 다음을 통해 라이센스 구매를 고려하세요. [이 링크](https://purchase.aspose.com/buy).

설정이 완료되면 프로젝트에서 Aspose.Slides를 초기화합니다.

```csharp
using Aspose.Slides;
```

## 구현 가이드

이제 설정이 끝났으니 모양 텍스트에 대한 언어를 설정하는 기능을 구현해 보겠습니다.

### 기능 개요: 모양 텍스트 언어 설정

이 기능을 사용하면 PowerPoint 도형 내의 텍스트 언어를 지정할 수 있습니다. 언어 ID를 설정하면 맞춤법 검사 및 기타 언어별 기능이 올바르게 적용됩니다.

#### 1단계: 프레젠테이션 초기화

인스턴스를 생성하여 시작하세요. `Presentation` 수업.

```csharp
using (Presentation pres = new Presentation())
{
    // 여기에 코드를 입력하세요
}
```

이렇게 하면 우리가 조작할 새로운 PowerPoint 프레젠테이션 개체가 초기화됩니다.

#### 2단계: 자동 모양 및 텍스트 프레임 추가

슬라이드에 사각형 모양을 추가하고 텍스트를 삽입합니다.

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

여기, `AddAutoShape` 첫 번째 슬라이드에 사각형을 추가합니다. 매개변수는 사각형의 위치와 크기를 정의합니다.

#### 3단계: 언어 ID 설정

모양 내의 텍스트 부분에 대한 언어를 설정합니다.

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

이렇게 하면 맞춤법 검사 언어로 영어(영국)가 지정됩니다.

#### 4단계: 프레젠테이션 저장

마지막으로, 프레젠테이션을 지정된 경로에 저장합니다.

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"description": "Aspose.Slides for .NET을 사용하여 PowerPoint 슬라이드에서 도형을 숨기는 방법을 알아보세요. 이 단계별 가이드를 통해 프로그래밍 방식으로 프레젠테이션을 사용자 지정해 보세요."
"linktitle": "Aspose.Slides를 사용하여 프레젠테이션 슬라이드에서 모양 숨기기"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides .NET 튜토리얼을 사용하여 PowerPoint에서 도형 숨기기"
"url": "/ko/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET 튜토리얼을 사용하여 PowerPoint에서 도형 숨기기

## 소개
역동적인 프레젠테이션 환경에서는 사용자 정의가 매우 중요합니다. Aspose.Slides for .NET은 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작할 수 있는 강력한 솔루션을 제공합니다. 일반적으로 슬라이드 내에서 특정 도형을 숨기는 기능이 필요합니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에서 도형을 숨기는 방법을 안내합니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Aspose.Slides for .NET: Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).
- 개발 환경: .NET에 대한 선호하는 개발 환경을 설정합니다.
- C#에 대한 기본 지식: 제공된 코드 예제가 C# 언어로 작성되었으므로 C#에 익숙해지세요.
## 네임스페이스 가져오기
Aspose.Slides 작업을 시작하려면 C# 프로젝트에 필요한 네임스페이스를 가져오세요. 이렇게 하면 필요한 클래스와 메서드에 액세스할 수 있습니다.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
이제 명확하고 간결하게 이해할 수 있도록 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
새로운 C# 프로젝트를 만들고 Aspose.Slides 라이브러리를 포함하세요.
## 2단계: 프레젠테이션 만들기
인스턴스화 `Presentation` PowerPoint 파일을 나타내는 클래스입니다. 슬라이드를 추가하고 참조를 가져옵니다.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## 3단계: 슬라이드에 모양 추가
사각형이나 달 등 특정 치수를 가진 자동 모양을 슬라이드에 추가합니다.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## 4단계: 대체 텍스트를 기준으로 모양 숨기기
대체 텍스트를 지정하고 이 텍스트와 일치하는 모양을 숨깁니다.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## 5단계: 프레젠테이션 저장
수정된 프레젠테이션을 PPTX 형식으로 디스크에 저장합니다.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## 결론
축하합니다! Aspose.Slides for .NET을 사용하여 프레젠테이션에서 도형을 숨기는 데 성공했습니다. 이제 프로그래밍 방식으로 동적이고 사용자 정의된 슬라이드를 만들 수 있는 무궁무진한 가능성이 열립니다.
---
## 자주 묻는 질문
### Aspose.Slides는 .NET Core와 호환됩니까?
네, Aspose.Slides는 .NET Core를 지원하여 개발 환경에 유연성을 제공합니다.
### 대체 텍스트 이외의 조건에 따라 모양을 숨길 수 있나요?
물론입니다! 모양 유형, 색상, 위치 등 다양한 속성을 기반으로 숨기기 로직을 사용자 지정할 수 있습니다.
### 추가적인 Aspose.Slides 문서는 어디에서 찾을 수 있나요?
문서를 탐색하세요 [여기](https://reference.aspose.com/slides/net/) 자세한 정보와 예를 보려면 여기를 클릭하세요.
### Aspose.Slides에 대한 임시 라이선스를 받을 수 있나요?
네, 임시면허를 취득할 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/) 테스트 목적으로.
### Aspose.Slides에 대한 커뮤니티 지원을 받으려면 어떻게 해야 하나요?
Aspose.Slides 커뮤니티에 가입하세요. [법정](https://forum.aspose.com/c/slides/11) 토론과 도움을 위해.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
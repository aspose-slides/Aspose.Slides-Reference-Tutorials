---
title: .NET용 Aspose.Slides를 사용하여 타원 모양 튜토리얼 서식 지정
linktitle: Aspose.Slides를 사용하여 슬라이드에서 타원 모양 서식 지정
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint에서 멋진 타원 모양을 만들어 보세요. 전문적인 프레젠테이션을 위한 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/net/shape-geometry-and-positioning-in-slides/formatting-ellipse-shape/
---
## 소개
청중을 사로잡으려면 시각적으로 매력적인 모양으로 PowerPoint 프레젠테이션을 향상시키는 것이 중요합니다. 그러한 모양 중 하나는 슬라이드에 우아함과 전문성을 더할 수 있는 타원입니다. 이 튜토리얼에서는 .NET용 Aspose.Slides를 사용하여 PowerPoint에서 타원 모양의 서식을 지정하는 과정을 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 지식.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Slides(다음에서 다운로드할 수 있음)[여기](https://releases.aspose.com/slides/net/).
- 시스템에 파일을 생성하고 저장하는 데 필요한 권한이 있는지 확인하세요.
## 네임스페이스 가져오기
시작하려면 필수 네임스페이스를 C# 프로젝트로 가져와야 합니다. 이렇게 하면 Aspose.Slides 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using System.Drawing;
```
이제 .NET용 Aspose.Slides를 사용하여 PowerPoint에서 타원 모양의 서식을 지정하는 방법에 대한 포괄적인 가이드를 위해 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
 Visual Studio에서 새 C# 프로젝트를 만들고 Aspose.Slides 라이브러리에 대한 참조를 추가합니다. 아직 다운로드하지 않으셨다면 다운로드 링크를 찾아보실 수 있습니다[여기](https://releases.aspose.com/slides/net/).
## 2단계: 문서 디렉터리 정의
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
지정된 디렉토리가 존재하는지 확인하고 존재하지 않으면 생성하십시오.
## 3단계: 프레젠테이션 클래스 인스턴스화
```csharp
using (Presentation pres = new Presentation())
{
    // 타원 모양 서식 지정을 위한 코드가 여기에 표시됩니다.
}
```
 인스턴스를 생성합니다.`Presentation` PowerPoint 파일을 나타내는 클래스입니다.
## 4단계: 첫 번째 슬라이드 가져오기
```csharp
ISlide sld = pres.Slides[0];
```
프레젠테이션의 첫 번째 슬라이드에 액세스합니다.
## 5단계: 타원 도형 추가
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
타원 도형을 슬라이드에 삽입하고 위치와 치수를 지정합니다.
## 6단계: 타원 모양 서식 지정
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
타원 모양에 서식을 적용하고 채우기 색상과 선 속성을 설정합니다.
## 7단계: 프레젠테이션 저장
```csharp
pres.Save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
수정된 프레젠테이션을 디스크에 저장합니다.
다음 단계를 꼼꼼하게 수행하면 PowerPoint 프레젠테이션에 아름다운 형식의 타원 모양이 만들어집니다.
## 결론
타원과 같이 시각적으로 매력적인 모양을 통합하면 PowerPoint 프레젠테이션의 미적 매력을 크게 향상시킬 수 있습니다. .NET용 Aspose.Slides는 이 프로세스를 원활하게 만들어 전문가 수준의 슬라이드를 쉽게 만들 수 있도록 해줍니다.

## 자주 묻는 질문
### Aspose.Slides는 최신 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 최신 버전을 포함한 다양한 PowerPoint 버전과의 호환성을 보장합니다. 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/slides/net/) 자세한 내용은
### .NET용 Aspose.Slides 무료 평가판을 다운로드할 수 있나요?
 예, 무료 평가판을 사용해 볼 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.Slides의 임시 라이선스를 어떻게 얻을 수 있나요?
 방문하다[이 링크](https://purchase.aspose.com/temporary-license/) 임시면허를 취득하기 위해
### Aspose.Slides 관련 쿼리에 대한 지원은 어디서 찾을 수 있나요?
 지역사회에서 도움을 구하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### .NET용 Aspose.Slides를 직접 구매할 수 있는 옵션이 있나요?
 예, 라이브러리를 직접 구매할 수 있습니다[여기](https://purchase.aspose.com/buy).
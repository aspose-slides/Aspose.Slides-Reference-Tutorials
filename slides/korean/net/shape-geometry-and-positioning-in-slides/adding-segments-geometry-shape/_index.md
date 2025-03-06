---
title: 비주얼 마스터하기 - .NET에서 Aspose.Slides를 사용하여 세그먼트 추가
linktitle: Aspose.Slides를 사용하여 프레젠테이션의 기하학 모양에 세그먼트 추가
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides를 사용하여 .NET 애플리케이션을 향상시키는 방법을 알아보세요. 이 튜토리얼에서는 매력적인 프레젠테이션을 위해 기하학 모양에 세그먼트를 추가하는 방법을 안내합니다.
weight: 13
url: /ko/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
.NET 개발 세계에서는 시각적으로 매력적인 프레젠테이션을 만드는 것이 일반적인 요구 사항입니다. Aspose.Slides for .NET은 강력한 프레젠테이션 생성 기능을 .NET 애플리케이션에 원활하게 통합할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼은 프리젠테이션 디자인의 특정 측면, 즉 기하학적 모양에 세그먼트를 추가하는 데 중점을 둡니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 지식.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
- .NET용 Aspose.Slides 라이브러리가 다운로드되어 프로젝트에서 참조됩니다.
## 네임스페이스 가져오기
C# 코드에서 Aspose.Slides 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 코드에 다음 줄을 추가합니다.
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
이제 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
Visual Studio에서 새 C# 프로젝트를 만드는 것부터 시작하세요. 프로젝트에 Aspose.Slides 라이브러리가 참조되어 있는지 확인하세요.
## 2단계: 프레젠테이션 만들기
Aspose.Slides 라이브러리를 사용하여 새 프레젠테이션 개체를 초기화합니다. 이는 기하학 모양의 캔버스 역할을 합니다.
```csharp
using (Presentation pres = new Presentation())
{
    // 프레젠테이션을 만들기 위한 코드는 여기에 있습니다.
}
```
## 3단계: 기하학 모양 추가
프레젠테이션 내에서 기하학적 모양을 만듭니다. 예를 들어 첫 번째 슬라이드에 직사각형을 추가해 보겠습니다.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## 4단계: 형상 경로 가져오기
생성된 모양의 형상 경로를 검색하여 해당 세그먼트를 조작합니다.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## 5단계: 세그먼트 추가
형상 경로에 세그먼트(선)를 추가합니다. 이 예에서는 두 줄이 경로에 추가됩니다.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## 6단계: 편집된 형상 경로 할당
수정된 형상 경로를 모양에 다시 할당하여 변경 사항을 적용합니다.
```csharp
shape.SetGeometryPath(geometryPath);
```
## 7단계: 프레젠테이션 저장
수정된 프레젠테이션을 원하는 위치에 저장합니다.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
이 단계를 통해 Aspose.Slides for .NET을 사용하여 프레젠테이션의 기하학적 모양에 세그먼트를 성공적으로 추가했습니다.
## 결론
.NET용 Aspose.Slides는 개발자가 고급 프레젠테이션 생성 기능을 통해 애플리케이션을 향상시킬 수 있도록 지원합니다. 기하학 모양에 세그먼트를 추가하면 프리젠테이션의 시각적 요소를 사용자 정의할 수 있습니다.
### 자주 묻는 질문
### Aspose.Slides를 사용하여 다양한 유형의 도형을 추가할 수 있나요?
예, Aspose.Slides는 직사각형, 원, 사용자 정의 기하학 모양을 포함한 다양한 모양 유형을 지원합니다.
### 내 프로젝트에서 Aspose.Slides를 사용하려면 라이선스가 필요합니까?
예, 유효한 라이센스가 필요합니다. 테스트 목적으로 임시 라이센스를 얻거나 프로덕션용으로 정식 라이센스를 구입할 수 있습니다.
### Aspose.Slides 관련 쿼리에 대한 지원을 어떻게 받을 수 있나요?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 지원 및 토론을 위해.
### Aspose.Slides에 사용할 수 있는 다른 튜토리얼이 있나요?
 탐색[선적 서류 비치](https://reference.aspose.com/slides/net/) 포괄적인 가이드와 예시를 보려면
### 구매하기 전에 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

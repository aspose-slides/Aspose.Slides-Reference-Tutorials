---
title: 프레젠테이션에서 복합 기하학 모양 마스터하기
linktitle: Aspose.Slides를 사용하여 기하학 모양의 복합 개체 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 복합 기하학 모양으로 멋진 프레젠테이션을 만드는 방법을 알아보세요. 인상적인 결과를 얻으려면 단계별 가이드를 따르십시오.
weight: 14
url: /ko/net/shape-geometry-and-positioning-in-slides/creating-composite-objects-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 프레젠테이션에서 복합 기하학 모양 마스터하기

## 소개
Aspose.Slides for .NET의 강력한 기능을 활용하여 기하학적 모양으로 복합 개체를 만들어 프레젠테이션을 향상하세요. 이 튜토리얼은 Aspose.Slides를 사용하여 복잡한 기하학적 구조로 시각적으로 매력적인 슬라이드를 생성하는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본 이해.
-  .NET 라이브러리용 Aspose.Slides를 설치했습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Slides 문서](https://reference.aspose.com/slides/net/).
- Visual Studio 또는 기타 C# 개발 도구를 사용하여 설정된 개발 환경입니다.
## 네임스페이스 가져오기
Aspose.Slides 기능을 사용하려면 C# 코드에서 필요한 네임스페이스를 가져와야 합니다. 코드 시작 부분에 다음 네임스페이스를 포함합니다.
```csharp
using System.IO;
using Aspose.Slides.Export;
```
이제 예제 코드를 여러 단계로 나누어 .NET용 Aspose.Slides를 사용하여 기하학적 형태로 복합 개체를 만드는 과정을 안내해 보겠습니다.
## 1단계: 환경 설정
```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
string resultPath = Path.Combine(dataDir, "GeometryShapeCompositeObjects.pptx");
```
이 단계에서는 프레젠테이션의 디렉터리와 결과 경로를 설정하여 환경을 초기화합니다.
## 2단계: 프리젠테이션 및 기하학 모양 만들기
```csharp
using (Presentation pres = new Presentation())
{
    // 새 모양 만들기
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
여기서는 새 프레젠테이션을 만들고 직사각형을 기하학 모양으로 추가합니다.
## 3단계: 형상 경로 정의
```csharp
// 첫 번째 기하학 경로 만들기
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.MoveTo(0, 0);
geometryPath0.LineTo(shape.Width, 0);
geometryPath0.LineTo(shape.Width, shape.Height / 3);
geometryPath0.LineTo(0, shape.Height / 3);
geometryPath0.CloseFigure();
// 두 번째 기하학 경로 만들기
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.MoveTo(0, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height);
geometryPath1.LineTo(0, shape.Height);
geometryPath1.CloseFigure();
```
이 단계에서는 기하학 모양을 구성할 두 개의 기하학 경로를 정의합니다.
## 4단계: 도형 기하학 설정
```csharp
// 모양 기하학을 두 개의 기하학 경로의 구성으로 설정
shape.SetGeometryPaths(new GeometryPath[] { geometryPath0, geometryPath1 });
```
이제 앞서 정의한 두 개의 기하학 경로의 구성으로 모양의 기하학을 설정합니다.
## 5단계: 프레젠테이션 저장
```csharp
// 프레젠테이션 저장
pres.Save(resultPath, SaveFormat.Pptx);
}
```
마지막으로 복합 기하학 형태로 프리젠테이션을 저장합니다.
## 결론
축하해요! Aspose.Slides for .NET을 사용하여 기하학 모양의 복합 개체를 성공적으로 만들었습니다. 프레젠테이션에 생동감을 불어넣기 위해 다양한 모양과 경로를 실험해보세요.
## 자주 묻는 질문
### Q: Aspose.Slides를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Slides는 Java 및 Python을 포함한 다양한 프로그래밍 언어를 지원합니다. 그러나 이 자습서에서는 C#에 중점을 둡니다.
### Q: 더 많은 예제와 문서는 어디서 찾을 수 있나요?
 탐색[Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 포괄적인 정보와 예시를 보려면
### Q: 무료 평가판이 제공됩니까?
 예, .NET용 Aspose.Slides를 사용해 볼 수 있습니다.[무료 시험판](https://releases.aspose.com/).
### Q: 어떻게 지원을 받거나 질문을 할 수 있나요?
 방문하다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지역 사회 지원 및 지원을 위해.
### Q: 임시 라이센스를 구매할 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

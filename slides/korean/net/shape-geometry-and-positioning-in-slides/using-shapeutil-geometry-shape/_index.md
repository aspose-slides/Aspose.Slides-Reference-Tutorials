---
title: ShapeUtil로 기하학 도형 마스터하기 - Aspose.Slides .NET
linktitle: 프레젠테이션 슬라이드의 기하학 모양에 ShapeUtil 사용
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: 동적 기하학 모양을 위한 ShapeUtil을 사용하여 .NET용 Aspose.Slides의 강력한 기능을 살펴보세요. 매력적인 프레젠테이션을 손쉽게 만들어 보세요. 지금 다운로드하세요! Aspose.Slides로 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요. 기하학적 모양 조작을 위해 ShapeUtil을 살펴보세요. .NET 소스 코드가 포함된 단계별 가이드입니다. 프레젠테이션을 효과적으로 최적화하세요.
weight: 17
url: /ko/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ShapeUtil로 기하학 도형 마스터하기 - Aspose.Slides .NET

## 소개
시각적으로 매력적이고 역동적인 프레젠테이션 슬라이드를 만드는 것은 필수적인 기술이며 .NET용 Aspose.Slides는 이를 달성하기 위한 강력한 툴킷을 제공합니다. 이 튜토리얼에서는 프리젠테이션 슬라이드에서 기하학적 모양을 처리하기 위해 ShapeUtil을 사용하는 방법을 살펴보겠습니다. 숙련된 개발자이든 Aspose.Slides를 처음 시작하든 이 가이드는 ShapeUtil을 활용하여 프레젠테이션을 향상시키는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 및 .NET 프로그래밍에 대한 기본 이해.
-  .NET 라이브러리용 Aspose.Slides를 설치했습니다. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).
- .NET 애플리케이션을 실행하도록 설정된 개발 환경입니다.
## 네임스페이스 가져오기
C# 코드에서 Aspose.Slides 기능에 액세스하는 데 필요한 네임스페이스를 가져와야 합니다. 스크립트 시작 부분에 다음을 추가합니다.
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
이제 제공된 예제를 여러 단계로 나누어 프리젠테이션 슬라이드의 기하학적 모양에 ShapeUtil을 사용하기 위한 단계별 가이드를 만들어 보겠습니다.
## 1단계: 문서 디렉토리 설정
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
"문서 디렉토리"를 프레젠테이션을 저장하려는 실제 경로로 바꾸십시오.
## 2단계: 출력 파일 이름 정의
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
파일 확장자를 포함하여 원하는 출력 파일 이름을 지정합니다.
## 3단계: 프레젠테이션 만들기
```csharp
using (Presentation pres = new Presentation())
```
Aspose.Slides 라이브러리를 사용하여 새 프레젠테이션 개체를 초기화합니다.
## 4단계: 기하학 모양 추가
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
프레젠테이션의 첫 번째 슬라이드에 직사각형 모양을 추가합니다.
## 5단계: 원본 형상 경로 가져오기
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
모양의 형상 경로를 검색하고 채우기 모드를 설정합니다.
## 6단계: 텍스트가 포함된 그래픽 경로 만들기
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
모양에 추가할 텍스트가 포함된 그래픽 경로를 생성합니다.
## 7단계: 그래픽 경로를 형상 경로로 변환
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
ShapeUtil을 활용하여 그래픽 경로를 형상 경로로 변환하고 채우기 모드를 설정합니다.
## 8단계: 결합된 형상 경로를 모양에 설정
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
새 형상 경로를 원래 경로와 결합하고 모양으로 설정합니다.
## 9단계: 프레젠테이션 저장
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
새로운 기하학 형태로 수정된 프리젠테이션을 저장합니다.
## 결론
축하해요! Aspose.Slides for .NET을 사용하여 프리젠테이션 슬라이드에서 기하학적 모양을 처리하기 위해 ShapeUtil을 사용하는 방법을 성공적으로 살펴보았습니다. 이 강력한 기능을 사용하면 역동적이고 매력적인 프레젠테이션을 쉽게 만들 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Slides는 주로 .NET 언어를 지원합니다. 그러나 Aspose는 다른 플랫폼 및 언어에 대해 유사한 라이브러리를 제공합니다.
### .NET용 Aspose.Slides에 대한 자세한 문서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/slides/net/).
### .NET용 Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 찾을 수 있습니다[여기](https://releases.aspose.com/).
### .NET용 Aspose.Slides에 대한 지원을 받으려면 어떻게 해야 합니까?
 커뮤니티 지원 포럼을 방문하세요[여기](https://forum.aspose.com/c/slides/11).
### .NET용 Aspose.Slides의 임시 라이선스를 구입할 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

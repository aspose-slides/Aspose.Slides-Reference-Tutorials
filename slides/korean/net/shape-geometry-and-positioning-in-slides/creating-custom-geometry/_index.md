---
title: .NET용 Aspose.Slides를 사용하여 C#에서 사용자 정의 지오메트리 만들기
linktitle: Aspose.Slides를 사용하여 기하학 모양에 사용자 정의 기하학 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides에서 사용자 정의 지오메트리를 만드는 방법을 알아보세요. 독특한 모양으로 프레젠테이션을 향상시키세요. C# 개발자를 위한 단계별 가이드입니다.
weight: 15
url: /ko/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
역동적인 프레젠테이션 세계에서 고유한 모양과 기하학적 구조를 추가하면 콘텐츠를 더욱 매력적이고 시각적으로 매력적으로 만들어 줄 수 있습니다. .NET용 Aspose.Slides는 모양 내에서 사용자 정의 기하학을 생성할 수 있는 강력한 솔루션을 제공하므로 기존 디자인에서 벗어날 수 있습니다. 이 튜토리얼은 .NET용 Aspose.Slides를 사용하여 GeometryShape에서 사용자 정의 지오메트리를 생성하는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- C# 프로그래밍 언어에 대한 기본적인 이해.
- 개발 환경에 설치된 .NET 라이브러리용 Aspose.Slides.
- Visual Studio 또는 선호하는 C# 개발 환경 설정.
## 네임스페이스 가져오기
시작하려면 필요한 네임스페이스를 C# 프로젝트로 가져옵니다.
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## 1단계: 프로젝트 설정
원하는 개발 환경에서 새 C# 프로젝트를 만듭니다. .NET용 Aspose.Slides가 제대로 설치되었는지 확인하세요.
## 2단계: 문서 디렉터리 정의
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## 3단계: 외부 및 내부 별 반경 설정
```csharp
float R = 100, r = 50; // 외부 및 내부 별 반경
```
## 4단계: 별 형상 경로 생성
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## 5단계: 프레젠테이션 만들기
```csharp
using (Presentation pres = new Presentation())
{
    // 새 모양 만들기
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // 모양에 새 형상 경로 설정
    shape.SetGeometryPath(starPath);
    // 프레젠테이션 저장
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## 6단계: CreateStarGeometry 메서드 정의
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## 결론
축하해요! .NET용 Aspose.Slides를 사용하여 GeometryShape에서 사용자 정의 형상을 만드는 방법을 성공적으로 배웠습니다. 이는 독특하고 시각적으로 놀라운 프레젠테이션을 만들 수 있는 가능성의 세계를 열어줍니다.
## 자주 묻는 질문
### 1. Aspose.Slides for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?
예, Aspose.Slides는 다양한 프로그래밍 언어를 지원하지만 이 튜토리얼은 C#에 중점을 둡니다.
### 2. .NET용 Aspose.Slides에 대한 문서는 어디서 찾을 수 있나요?
 방문하다[선적 서류 비치](https://reference.aspose.com/slides/net/) 자세한 내용은.
### 3. Aspose.Slides for .NET에 대한 무료 평가판이 있습니까?
 예, 다음을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 기능을 경험해 보세요.
### 4. .NET용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 도움을 구하고 지역사회에 참여하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### 5. .NET용 Aspose.Slides를 어디서 구입할 수 있나요?
 .NET용 Aspose.Slides를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

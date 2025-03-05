---
title: Aspose.Slides를 사용하여 멋진 스케치 모양 만들기
linktitle: Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 스케치된 모양 만들기
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 창의적인 스케치 모양을 추가하는 방법을 알아보세요. 손쉽게 시각적 매력을 강화해보세요!
type: docs
weight: 13
url: /ko/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## 소개
.NET용 Aspose.Slides를 사용하여 프레젠테이션 슬라이드에 스케치된 모양을 만드는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. 프레젠테이션에 창의성을 더하고 싶다면 스케치된 모양이 독특하고 손으로 그린 미학을 제공합니다. 이 튜토리얼에서는 원활한 경험을 보장하기 위해 프로세스를 간단한 단계로 나누어 프로세스를 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/slides/net/).
- 개발 환경: 선호하는 IDE로 .NET 개발 환경을 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작하세요. 이 단계를 통해 Aspose.Slides 작업에 필요한 클래스와 기능에 액세스할 수 있습니다.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## 1단계: 프로젝트 설정
새 .NET 프로젝트를 만들거나 기존 프로젝트를 열어 시작하세요. 프로젝트 참조에 Aspose.Slides를 포함해야 합니다.
## 2단계: Aspose.Slides 초기화
다음 코드 조각을 추가하여 Aspose.Slides를 초기화합니다. 프레젠테이션을 설정하고 프레젠테이션 파일과 축소판 이미지의 출력 경로를 지정합니다.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // 다음 단계를 계속하세요...
}
```
## 3단계: 스케치된 모양 추가
이제 슬라이드에 스케치된 모양을 추가해 보겠습니다. 이 예에서는 프리핸드 스케치 효과가 있는 직사각형을 추가하겠습니다.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// 모양을 자유형 스타일의 스케치로 변환
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## 4단계: 썸네일 생성
슬라이드의 축소판을 생성하여 스케치된 모양을 시각화합니다. 썸네일을 PNG 파일로 저장합니다.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## 5단계: 프레젠테이션 저장
스케치된 모양으로 프리젠테이션 파일을 저장합니다.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
그게 다야! .NET용 Aspose.Slides를 사용하여 스케치된 모양으로 프레젠테이션을 성공적으로 만들었습니다.
## 결론
프레젠테이션 슬라이드에 스케치된 모양을 추가하면 시각적 매력을 향상하고 청중의 관심을 끌 수 있습니다. .NET용 Aspose.Slides를 사용하면 프로세스가 간단해져서 창의력을 쉽게 발휘할 수 있습니다.
## 자주 묻는 질문
### 1. 스케치 효과를 사용자 정의할 수 있나요?
 예, .NET용 Aspose.Slides는 스케치 효과에 대한 다양한 사용자 정의 옵션을 제공합니다. 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/slides/net/) 자세한 내용은.
### 2. 무료 평가판이 있나요?
 틀림없이! .NET용 Aspose.Slides의 무료 평가판을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### 3. 어디서 지원을 받을 수 있나요?
 도움이나 문의사항이 있으면 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### 4. .NET용 Aspose.Slides를 어떻게 구매할 수 있나요?
 .NET용 Aspose.Slides를 구입하려면 다음을 방문하세요.[구매 페이지](https://purchase.aspose.com/buy).
### 5. 임시 라이센스를 제공합니까?
 예, 임시 라이센스를 사용할 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
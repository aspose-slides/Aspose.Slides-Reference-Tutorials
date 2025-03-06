---
title: .NET용 Aspose.Slides를 사용하여 아름다운 차트 만들기
linktitle: 차트 엔터티 및 서식 지정
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 멋진 차트를 만드는 방법을 알아보세요. 단계별 가이드를 통해 데이터 시각화 게임의 수준을 높이세요.
weight: 13
url: /ko/net/advanced-chart-customization/chart-entities/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


오늘날의 데이터 중심 세계에서 효과적인 데이터 시각화는 청중에게 정보를 전달하는 데 핵심입니다. Aspose.Slides for .NET은 눈길을 끄는 차트를 포함하여 멋진 프레젠테이션과 슬라이드를 만들 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 아름다운 차트를 만드는 과정을 안내합니다. 차트 엔터티와 서식을 이해하고 구현하는 데 도움이 되도록 각 예를 여러 단계로 나누어 보겠습니다. 자, 시작해 봅시다!

## 전제 조건

.NET용 Aspose.Slides를 사용하여 아름다운 차트를 만들기 전에 다음 전제 조건이 충족되었는지 확인해야 합니다.

1.  .NET용 Aspose.Slides: .NET용 Aspose.Slides 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/net/).

2. 개발 환경: Visual Studio 또는 .NET 개발을 지원하는 다른 IDE를 사용하는 작업 개발 환경이 있어야 합니다.

3. 기본 C# 지식: 이 튜토리얼에서는 C# 프로그래밍에 대한 지식이 필수적입니다.

이제 전제 조건이 정렬되었으므로 .NET용 Aspose.Slides를 사용하여 아름다운 차트를 만들어 보겠습니다.

## 네임스페이스 가져오기

먼저 .NET용 Aspose.Slides를 사용하려면 필요한 네임스페이스를 가져와야 합니다.

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## 1단계: 프레젠테이션 만들기

작업할 새 프레젠테이션을 만드는 것부터 시작합니다. 이 프레젠테이션은 차트의 캔버스 역할을 할 것입니다.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";

// 디렉터리가 아직 없으면 만듭니다.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// 프레젠테이션 인스턴스화
Presentation pres = new Presentation();
```

## 2단계: 첫 번째 슬라이드에 액세스

차트를 배치할 프레젠테이션의 첫 번째 슬라이드에 액세스해 보겠습니다.

```csharp
// 첫 번째 슬라이드에 액세스하기
ISlide slide = pres.Slides[0];
```

## 3단계: 샘플 차트 추가

이제 슬라이드에 샘플 차트를 추가하겠습니다. 이 예에서는 마커가 있는 꺾은선형 차트를 만듭니다.

```csharp
// 샘플 차트 추가
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 4단계: 차트 제목 설정

차트에 제목을 지정하여 더 많은 정보를 제공하고 시각적으로 매력적으로 만들겠습니다.

```csharp
// 차트 제목 설정
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## 5단계: 수직축 격자선 사용자 정의

이 단계에서는 차트를 시각적으로 더욱 매력적으로 만들기 위해 세로축 격자선을 사용자 정의합니다.

```csharp
// 값 축의 주요 그리드 선 형식 설정
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// 값 축의 보조 눈금선 형식 설정
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// 설정값 축 번호 형식
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## 6단계: 세로축 범위 정의

이번 단계에서는 세로축의 최대값, 최소값, 단위값을 설정하겠습니다.

```csharp
// 차트 최대값, 최소값 설정
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## 7단계: 세로축 텍스트 사용자 정의

이제 세로 축의 텍스트 모양을 사용자 정의하겠습니다.

```csharp
// 값 축 텍스트 속성 설정
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// 설정값 축 제목
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## 8단계: 가로 축 그리드 선 사용자 정의

이제 가로 축의 그리드 선을 사용자 정의해 보겠습니다.

```csharp
// 범주 축의 주요 그리드선 형식 설정
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// 범주 축에 대한 보조 그리드선 형식 설정
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// 범주 축 텍스트 속성 설정
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## 9단계: 가로 축 레이블 사용자 정의

이 단계에서는 가로 축 레이블의 위치와 회전을 조정합니다.

```csharp
// 카테고리 축 라벨 위치 설정
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// 카테고리 축 라벨 회전 각도 설정
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## 10단계: 범례 사용자 정의

가독성을 높이기 위해 차트의 범례를 개선해 보겠습니다.

```csharp
// 범례 텍스트 속성 설정
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// 차트가 겹치지 않도록 차트 범례 표시 설정
chart.Legend.Overlay = true;
```

## 11단계: 차트 배경 사용자 정의

차트, 뒷벽, 바닥의 배경색을 맞춤설정해 드립니다.

```csharp
// 차트 뒷벽 색상 설정
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//플롯 영역 색상 설정
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## 12단계: 프레젠테이션 저장

마지막으로 서식이 지정된 차트를 사용하여 프레젠테이션을 저장해 보겠습니다.

```csharp
// 프레젠테이션 저장
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## 결론

Aspose.Slides for .NET을 사용하면 프레젠테이션에서 아름답고 유익한 차트를 만드는 것이 그 어느 때보다 쉬워졌습니다. 이 튜토리얼에서는 차트의 다양한 측면을 사용자 정의하여 시각적으로 매력적이고 유익하게 만드는 필수 단계를 다루었습니다. 이러한 기술을 사용하면 청중에게 데이터를 효과적으로 전달하는 멋진 차트를 만들 수 있습니다.

.NET용 Aspose.Slides를 사용해 실험을 시작하고 데이터 시각화를 한 단계 더 발전시키세요!

## 자주 묻는 질문

### 1. .NET용 Aspose.Slides란 무엇입니까?

Aspose.Slides for .NET은 .NET 개발자가 Microsoft PowerPoint 프레젠테이션을 생성, 조작 및 변환할 수 있는 강력한 라이브러리입니다. 슬라이드, 도형, 차트 등을 작업하기 위한 다양한 기능을 제공합니다.

### 2. .NET용 Aspose.Slides를 어디에서 다운로드할 수 있나요?

 웹사이트에서 .NET용 Aspose.Slides를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

### 3. Aspose.Slides for .NET에 대한 무료 평가판이 있습니까?

 예, 다음에서 .NET용 Aspose.Slides의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### 4. Aspose.Slides for .NET에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 임시 라이센스가 필요한 경우 다음에서 얻을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### 5. .NET용 Aspose.Slides에 대한 커뮤니티나 지원 포럼이 있습니까?

 예, Aspose.Slides 커뮤니티 및 지원 포럼을 찾을 수 있습니다[여기](https://forum.aspose.com/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

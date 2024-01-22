---
title: Aspose.Slides의 고급 차트 사용자 정의
linktitle: Aspose.Slides의 고급 차트 사용자 정의
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides에서 고급 차트 사용자 정의를 알아보세요. 단계별 지침을 통해 시각적으로 매력적인 차트를 만듭니다.
type: docs
weight: 10
url: /ko/net/advanced-chart-customization/advanced-chart-customization/
---

시각적으로 매력적이고 유익한 차트를 만드는 것은 많은 응용 프로그램에서 데이터 표현의 필수적인 부분입니다. Aspose.Slides for .NET은 차트 사용자 정의를 위한 강력한 도구를 제공하여 차트의 모든 측면을 미세 조정할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 고급 차트 사용자 정의 기술을 살펴보겠습니다.

## 전제조건

.NET용 Aspose.Slides를 사용하여 고급 차트 사용자 정의를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET 라이브러리용 Aspose.Slides: .NET 프로젝트에 Aspose.Slides 라이브러리를 설치하고 적절하게 구성해야 합니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).

2. .NET 개발 환경: Visual Studio 또는 원하는 다른 IDE를 포함하여 .NET 개발 환경이 설정되어 있어야 합니다.

3. C#에 대한 기본 지식: Aspose.Slides와 함께 작동하기 위해 C# 코드를 작성할 것이므로 C# 프로그래밍 언어에 익숙하면 도움이 될 것입니다.

이제 고급 차트 사용자 정의를 여러 단계로 나누어 프로세스를 안내해 보겠습니다.

## 1단계: 프레젠테이션 만들기

먼저 Aspose.Slides를 사용하여 새 프레젠테이션을 만듭니다.

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

이 단계에서는 차트를 보관할 새 프레젠테이션을 시작합니다.

## 2단계: 첫 번째 슬라이드에 액세스

그런 다음 차트를 추가하려는 프레젠테이션의 첫 번째 슬라이드에 액세스합니다.

```csharp
// 첫 번째 슬라이드에 액세스하기
ISlide slide = pres.Slides[0];
```

이 코드 조각을 사용하면 프레젠테이션의 첫 번째 슬라이드로 작업할 수 있습니다.

## 3단계: 샘플 차트 추가

이제 슬라이드에 샘플 차트를 추가해 보겠습니다. 이 예에서는 마커가 있는 꺾은선형 차트를 만듭니다.

```csharp
// 샘플 차트 추가
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

여기서는 차트 유형(LineWithMarkers)과 슬라이드의 위치 및 크기를 지정합니다.

## 4단계: 차트 제목 설정

컨텍스트를 제공하기 위해 차트 제목을 설정해 보겠습니다.

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

이 코드는 텍스트, 모양, 글꼴 스타일을 지정하여 차트 제목을 설정합니다.

## 5단계: 주요 그리드선 사용자 정의

이제 값 축의 주요 그리드 선을 사용자 정의해 보겠습니다.

```csharp
// 값 축의 주요 그리드 선 형식 설정
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

이 단계에서는 값 축의 주요 눈금선 모양을 구성합니다.

## 6단계: 보조 그리드선 사용자 정의

마찬가지로 값 축의 보조 격자선을 사용자 정의할 수 있습니다.

```csharp
// 값 축의 보조 눈금선 형식 설정
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

이 코드는 값 축의 보조 격자선 모양을 조정합니다.

## 7단계: 값 축 숫자 형식 정의

값 축의 숫자 형식을 사용자 정의합니다.

```csharp
// 설정값 축 번호 형식
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

이 단계를 통해 값 축에 표시되는 숫자의 형식을 지정할 수 있습니다.

## 8단계: 차트 최대값 및 최소값 설정

차트의 최대값과 최소값을 정의합니다.

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

여기에서는 차트 축이 표시해야 하는 값의 범위를 지정합니다.

## 9단계: 값 축 텍스트 속성 사용자 정의

값 축의 텍스트 속성을 사용자 정의할 수도 있습니다.

```csharp
// 값 축 텍스트 속성 설정
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

이 코드를 사용하면 값 축 레이블의 글꼴 스타일과 모양을 조정할 수 있습니다.

## 10단계: 값 축 제목 추가

차트에 값 축의 제목이 필요한 경우 이 단계를 통해 제목을 추가할 수 있습니다.

```csharp
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

이 단계에서는 값 축의 제목을 설정할 수 있습니다.

## 11단계: 범주 축의 주요 그리드선 사용자 정의

이제 범주 축의 주요 그리드 선에 초점을 맞춰 보겠습니다.

```csharp
// 범주 축의 주요 그리드선 형식 설정
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

이 코드는 범주 축의 주요 그리드 선 모양을 구성합니다.

## 12단계: 범주 축에 대한 보조 격자선 사용자 정의

값 축과 유사하게 범주 축의 보조 그리드 선을 사용자 정의할 수 있습니다.

```csharp
//범주 축에 대한 보조 그리드선 형식 설정
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

여기에서는 범주 축의 보조 격자선 모양을 조정합니다.

## 13단계: 범주 축 텍스트 속성 사용자 정의

범주 축 레이블의 텍스트 속성을 사용자 정의합니다.

```csharp
// 범주 축 텍스트 속성 설정
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

이 코드를 사용하면 범주 축 레이블의 글꼴 스타일과 모양을 조정할 수 있습니다.

## 14단계: 카테고리 축 제목 추가

필요한 경우 범주 축에 제목을 추가할 수도 있습니다.

```csharp
// 카테고리 제목 설정
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

이 단계에서는 범주 축의 제목을 설정할 수 있습니다.

## 15단계: 추가 사용자 정의

범례, 차트 뒷벽, 바닥 및 그림 영역 색상과 같은 추가 사용자 정의를 탐색할 수 있습니다. 이러한 사용자 정의를 통해 차트의 시각적 매력을 향상할 수 있습니다.

```csharp
// 추가 사용자 정의(선택 사항)

// 범례 텍스트 속성 설정
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// 차트가 겹치지 않도록 차트 범례 표시 설정
chart.Legend.Overlay = true;

// 보조 값 축에 첫 번째 계열 표시(필요한 경우)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// 차트 뒷벽 색상 설정
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// 차트 바닥 색상 설정
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// 플롯 영역 색상 설정
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// 프레젠테이션 저장
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

이러한 추가 사용자 정의는 선택 사항이며 특정 차트 디자인 요구 사항에 따라 적용될 수 있습니다.

## 결론

이 단계별 가이드에서는 Aspose.Slides for .NET을 사용하여 고급 차트 사용자 정의를 살펴보았습니다. 프레젠테이션을 만들고, 차트를 추가하고, 눈금선, 축 레이블 및 기타 시각적 요소를 포함하여 모양을 미세 조정하는 방법을 배웠습니다. Aspose.Slides가 제공하는 강력한 사용자 정의 옵션을 사용하면 데이터를 효과적으로 전달하고 청중의 참여를 유도하는 차트를 만들 수 있습니다.

 .NET용 Aspose.Slides로 작업하는 동안 질문이 있거나 문제가 발생하는 경우 자유롭게 문서를 살펴보세요.[여기](https://reference.aspose.com/slides/net/) 또는 Aspose.Slides에서 도움을 구하세요.[법정](https://forum.aspose.com/).

## 자주 묻는 질문

### .NET용 Aspose.Slides는 어떤 버전의 .NET을 지원합니까?
.NET용 Aspose.Slides는 .NET Framework 및 .NET Core를 포함한 다양한 .NET 버전을 지원합니다. 지원되는 버전의 전체 목록은 설명서를 참조할 수 있습니다.

### Aspose.Slides for .NET을 사용하여 Excel 파일과 같은 데이터 소스에서 차트를 만들 수 있나요?
예, .NET용 Aspose.Slides를 사용하면 Excel 스프레드시트와 같은 외부 데이터 소스에서 차트를 만들 수 있습니다. 자세한 예제는 설명서를 살펴보세요.

### 내 차트 시리즈에 사용자 정의 데이터 레이블을 어떻게 추가할 수 있나요?
 차트 시리즈에 사용자 정의 데이터 레이블을 추가하려면`DataLabels` 시리즈의 속성을 선택하고 필요에 따라 라벨을 사용자 정의합니다. 코드 샘플 및 예제는 설명서를 참조하세요.

### 차트를 PDF나 이미지 형식 등 다른 파일 형식으로 내보낼 수 있나요?
예, Aspose.Slides for .NET은 차트가 포함된 프레젠테이션을 PDF 및 이미지 형식을 포함한 다양한 형식으로 내보낼 수 있는 옵션을 제공합니다. 라이브러리를 사용하여 원하는 출력 형식으로 작업을 저장할 수 있습니다.

### .NET용 Aspose.Slides에 대한 추가 튜토리얼과 예제는 어디서 찾을 수 있나요?
 Aspose.Slides에서 풍부한 튜토리얼, 코드 예제 및 문서를 찾을 수 있습니다.[웹사이트](https://reference.aspose.com/slides/net/).
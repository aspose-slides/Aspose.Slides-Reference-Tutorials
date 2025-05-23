---
"date": "2025-04-15"
"description": "Aspose.Slides를 사용하여 .NET 프레젠테이션에서 파이 차트를 자동으로 만드는 방법을 배우고, 손쉽게 데이터 시각화를 향상시켜 보세요."
"title": "Aspose.Slides를 사용하여 .NET 프레젠테이션에서 원형 차트를 만들고 사용자 지정하는 방법"
"url": "/ko/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 .NET 프레젠테이션에서 원형 차트를 만들고 사용자 지정하는 방법

## 소개
효과적인 소통을 위해서는 매력적이고 유익한 프레젠테이션을 만드는 것이 중요합니다. 직장에서 데이터를 발표하든 최근 프로젝트 결과를 보여주든 마찬가지입니다. 데이터를 시각화하는 효과적인 방법 중 하나는 원형 차트를 활용하는 것입니다. 원형 차트는 전체의 각 부분을 간결하게 표현할 수 있습니다. 하지만 파워포인트와 같은 프레젠테이션 소프트웨어에서 이러한 차트를 직접 만드는 것은 시간이 많이 소요될 뿐만 아니라 동적 업데이트에 필요한 유연성이 부족할 수 있습니다.

바로 이 부분에서 Aspose.Slides for .NET이 중요한 역할을 합니다. 이 포괄적인 라이브러리를 사용하면 프로그래밍 방식으로 프레젠테이션을 만들고, 수정하고, 스타일을 지정할 수 있어 워크플로를 자동화하고 프레젠테이션 전반의 일관성을 유지하려는 개발자에게 매우 유용한 도구입니다.

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 원형 차트를 만들고 사용자 지정하는 방법을 살펴보겠습니다. 다음 내용을 배우게 됩니다.
- **프레젠테이션을 만들고 슬라이드에 액세스하세요**
- **파이 차트 추가 및 구성**
- **차트 데이터 및 시리즈 사용자 지정**
- **스타일 파이 차트 섹터**
- **사용자 정의 라벨 추가**
- **디스플레이 속성을 구성하고 프레젠테이션을 저장합니다.**

멋진 원형 차트를 손쉽게 만들어 볼 준비가 되셨나요? 시작해 볼까요!

## 필수 조건
시작하기 전에 다음 설정이 완료되었는지 확인하세요.

### 필수 라이브러리
- .NET용 Aspose.Slides(버전 21.11 이상 권장)

### 환경 설정
- .NET Framework 또는 .NET Core/5+/6+를 실행하는 개발 환경
- Visual Studio와 같은 코드 편집기

### 지식 전제 조건
- C# 프로그래밍에 대한 기본적인 이해
- 객체 지향 개념에 대한 익숙함

## .NET용 Aspose.Slides 설정
시작하려면 Aspose.Slides 라이브러리를 설치해야 합니다. 다음 방법 중 하나를 사용하여 설치할 수 있습니다.

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI**
- Visual Studio에서 프로젝트를 엽니다.
- "도구" > "NuGet 패키지 관리자" > "솔루션용 NuGet 패키지 관리"로 이동합니다.
- "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득 단계
Aspose.Slides를 사용하려면 임시 라이선스를 다운로드하여 무료 평가판을 시작하세요. [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/) 얻으려면. 지속적으로 사용하려면 정식 라이선스 구매를 고려해 보세요.

### 기본 초기화 및 설정
설치가 완료되면 PPTX 파일을 나타내는 Presentation 클래스를 초기화합니다.

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## 구현 가이드
원형 차트 제작 과정을 관리하기 쉬운 섹션으로 나누어 설명하겠습니다. 각 섹션은 특정 기능에 집중하도록 설계되어 있어 점진적으로 지식을 쌓을 수 있습니다.

### 프레젠테이션을 만들고 슬라이드에 액세스하세요
**개요:** 새 프레젠테이션을 만들고 첫 번째 슬라이드를 열어 보세요. 이렇게 하면 차트와 기타 요소를 추가할 수 있는 단계가 마련됩니다.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
    Presentation presentation = new Presentation();
    
    // 첫 번째 슬라이드에 접근하세요
    ISlide slides = presentation.Slides[0];
}
```

### 파이 차트 추가 및 구성
**개요:** 슬라이드에 원형 차트를 추가하고 맥락에 맞는 제목을 설정하는 방법을 알아보세요.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
    Presentation presentation = new Presentation();
    
    // 첫 번째 슬라이드에 접근하세요
    ISlide slides = presentation.Slides[0];
    
    // 슬라이드에 기본 데이터가 포함된 차트 추가
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 차트 제목 설정
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### 차트 데이터 및 시리즈 사용자 지정
**개요:** 귀하의 특정 요구 사항에 맞게 데이터 범주와 시리즈를 사용자 정의하세요.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
    Presentation presentation = new Presentation();
    
    // 첫 번째 슬라이드에 접근하세요
    ISlide slides = presentation.Slides[0];
    
    // 슬라이드에 기본 데이터가 포함된 차트 추가
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 첫 번째 시리즈를 값 표시로 설정
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // 차트 데이터 시트의 인덱스 설정
    int defaultWorksheetIndex = 0;
    
    // 차트 데이터 워크시트 가져오기
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // 기본으로 생성된 시리즈 및 카테고리 삭제
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // 새로운 카테고리 추가
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // 새로운 시리즈 추가
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // 이제 시리즈 데이터를 채우고 있습니다
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### 원형 차트 섹터 스타일 사용자 지정
**개요:** 원형 차트의 각 부분에 스타일을 지정하여 시각적 매력을 높이고 주요 데이터 포인트를 강조합니다.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
    Presentation presentation = new Presentation();
    
    // 첫 번째 슬라이드에 접근하세요
    ISlide slides = presentation.Slides[0];
    
    // 슬라이드에 기본 데이터가 포함된 차트 추가
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // 차트에서 시리즈 가져오기
    IChartSeries series = chart.ChartData.Series[0];
    
    // 시리즈의 각 데이터 포인트에 대한 섹터 스타일 사용자 정의
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // 섹터 경계 설정
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // 섹터 경계 설정
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // 섹터 경계 설정
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### 원형 차트에 사용자 정의 레이블 추가
**개요:** 사용자 정의 레이블을 추가하여 원형 차트를 개선하고 데이터를 더 명확하게 표현하세요.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // 필요에 따라 라벨 위치를 조정하세요
    }
}
```

### 결론
이제 Aspose.Slides를 사용하여 .NET 프레젠테이션에서 원형 차트를 만들고 사용자 지정하는 방법을 알아보았습니다. 이 자동화는 데이터 시각화 작업을 크게 향상시켜 시간을 절약하고 프레젠테이션 전체의 일관성을 유지할 수 있도록 도와줍니다.

Aspose.Slides for .NET의 기능을 더욱 자세히 알아보려면 다른 차트 유형을 만들거나 보다 복잡한 디자인 요소를 슬라이드에 통합하는 등의 추가 기능을 살펴보세요.

즐거운 코딩 되세요!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
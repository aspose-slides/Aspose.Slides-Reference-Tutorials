---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 동적 도넛형 차트를 만드는 방법을 알아보세요. 설정 및 고급 기능을 포함한 단계별 지침은 이 가이드를 참조하세요."
"title": "Aspose.Slides .NET을 사용하여 도넛형 차트 만들기 단계별 가이드 | 차트 및 그래프"
"url": "/ko/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# 단계별 가이드: Aspose.Slides .NET을 사용하여 도넛 차트 만들기

## 소개

팀이나 고객에게 데이터 분석 결과를 발표해야 하는데, 정보를 시각적으로 효과적으로 표현할 방법이 필요하다면 어떻게 해야 할까요? 바로 도넛 차트입니다. 원시 숫자를 이해하기 쉬운 통찰력으로 바꿔주는 다재다능한 도구입니다. Aspose.Slides for .NET을 사용하면 프레젠테이션 슬라이드에 사용자 지정 도넛 차트를 간단하고 효율적으로 만들 수 있습니다. 이 가이드에서는 Aspose.Slides를 사용하여 시각적으로 매력적인 도넛 차트를 만들고, 각 차트에 맞는 계열 구성을 완성하는 방법을 안내합니다.

**배울 내용:**
- Aspose.Slides for .NET을 사용하여 개발 환경 설정
- 프레젠테이션에서 도넛형 차트 만들기 및 사용자 지정
- 카테고리 이름 및 리더 라인과 같은 고급 기능 구현
- 대용량 데이터 세트에 대한 성능 최적화

시작하는 데 필요한 전제 조건을 살펴보겠습니다.

## 필수 조건

이 기능을 구현하기 전에 개발 환경이 제대로 설정되어 있는지 확인하세요. 이 튜토리얼은 .NET 프로그래밍에 대한 기본 지식과 Visual Studio 또는 이와 유사한 IDE 사용 경험을 전제로 합니다.

### 필수 라이브러리 및 버전
- **.NET용 Aspose.Slides**: 최신 버전과의 호환성을 확인하려면 다음을 확인하세요. [공식 문서](https://reference.aspose.com/slides/net/).

### 환경 설정 요구 사항
- 작동하는 .NET 환경.
- Visual Studio와 같은 코드 편집기에 대한 액세스.

### 지식 전제 조건
- C# 및 .NET 프레임워크에 대한 기본적인 이해.
- 프레젠테이션 소프트웨어 개념에 대한 지식(선택 사항이지만 도움이 됨)

## .NET용 Aspose.Slides 설정

프로젝트에서 Aspose.Slides를 사용하려면 NuGet을 통해 설치해야 합니다. 사용 가능한 방법은 다음과 같습니다.

**.NET CLI 사용:**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 사용:**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI:**
"Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득 단계

1. **무료 체험**: ~로 시작하다 [무료 체험](https://releases.aspose.com/slides/net/) 기본 기능을 살펴보세요.
2. **임시 면허**: 평가 목적으로 전체 기능에 액세스해야 하는 경우 임시 라이선스를 얻으려면 다음을 방문하세요. [여기](https://purchase.aspose.com/temporary-license/).
3. **구입**: 상업적인 용도로 사용하려면 라이센스를 구매하세요. [Aspose 웹사이트](https://purchase.aspose.com/buy).

설치하고 라이선스를 받은 후 프로젝트에서 Aspose.Slides를 초기화합니다.
```csharp
using Aspose.Slides;

// .NET용 Aspose.Slides 초기화
var presentation = new Presentation();
```

## 구현 가이드

### 새 프레젠테이션 만들기 및 도넛 차트 추가

#### 개요
먼저 새 프레젠테이션을 만들고 첫 번째 슬라이드에 도넛형 차트를 추가해 보겠습니다. 이 섹션에서는 기존 프레젠테이션 불러오기, 슬라이드 접근, 차트 삽입에 대해 다룹니다.

**1단계: 프레젠테이션 로드 또는 생성**
먼저 문서 디렉터리를 지정하고 기존 프레젠테이션을 로드합니다.
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
기존 파일이 없으면 다음을 사용하여 새 파일을 만듭니다. `new Presentation()`.

**2단계: 첫 번째 슬라이드에 액세스**
차트를 추가할 첫 번째 슬라이드에 액세스하세요.
```csharp
ISlide slide = pres.Slides[0];
```

**3단계: 도넛 차트 추가**
지정된 좌표와 치수에 도넛형 차트를 추가합니다.
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 데이터 워크북 구성

#### 개요
이 섹션에서는 도넛형 차트와 관련된 데이터 통합 문서를 구성하는 방법을 설명합니다.

**4단계: 기존 데이터 액세스 및 지우기**
차트의 데이터 통합 문서에 액세스합니다. 그런 다음 기존 시리즈나 범주를 모두 지웁니다.
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**5단계: 범례 비활성화 및 시리즈 추가**
차트를 깔끔하게 유지하려면 범례를 비활성화한 다음 사용자 정의 구성으로 최대 15개의 시리즈를 추가합니다.
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### 카테고리 및 데이터 포인트 추가

#### 개요
이제 각 시리즈에 대한 범주와 데이터 포인트로 차트를 채워 보겠습니다.

**6단계: 카테고리 추가**
루프를 실행하여 15개 카테고리를 추가합니다.
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**7단계: 데이터 포인트 채우기**
현재 카테고리 내 각 시리즈에 대한 데이터 포인트를 추가합니다.
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // 모양 사용자 정의
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // 마지막 시리즈에 대한 레이블 형식 구성
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // 라벨 표시 구성
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### 프레젠테이션 저장

**8단계: 파일 저장**
마지막으로, 프레젠테이션을 지정된 디렉토리에 저장합니다.
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
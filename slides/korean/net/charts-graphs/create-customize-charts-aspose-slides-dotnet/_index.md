---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 차트를 만들고 사용자 지정하는 방법(백분율을 데이터 레이블로 표시하는 방법 포함)을 알아보세요. 이 단계별 가이드를 따라 해 보세요."
"title": "Aspose.Slides .NET을 사용하여 차트를 만들고 사용자 지정하는 방법&#58; 백분율을 레이블로 표시"
"url": "/ko/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET을 사용하여 차트를 만들고 사용자 지정하는 방법: 백분율을 레이블로 표시

## 소개

여러 분야에서 데이터를 효과적으로 표현하는 것은 매우 중요하며, 차트는 복잡한 정보를 명확한 시각적 요소로 변환하는 데 중요한 역할을 합니다. 완벽한 차트를 만들려면 레이블에 백분율을 표시하는 것과 같은 사용자 지정 작업이 필요한데, Aspose.Slides for .NET을 사용하면 이러한 작업이 훨씬 수월해집니다. 이 라이브러리는 PowerPoint 프레젠테이션 내에서 차트를 만들고 수정하는 과정을 간소화합니다.

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 처음부터 누적 세로 막대형 차트를 만들고 백분율 값을 데이터 레이블로 표시하여 사용자 지정하는 방법을 알아봅니다. 이 단계를 따라 하면 정확하고 시각적으로 매력적인 데이터 표현으로 슬라이드를 더욱 돋보이게 할 수 있습니다.

**배울 내용:**
- .NET용 Aspose.Slides 초기화
- 쌓인 막대형 차트 만들기
- 데이터 레이블에 백분율 계산 및 표시
- 차트 성능 최적화 모범 사례

구현에 들어가기 전에 시작하는 데 필요한 모든 것이 준비되었는지 확인해 보겠습니다.

## 필수 조건

이 튜토리얼을 효과적으로 따르려면 다음 사항이 있는지 확인하세요.
- **.NET 코어 SDK** 귀하의 컴퓨터에 설치되었습니다.
- C# 및 .NET 애플리케이션 개발에 대한 기본적인 이해.
- C# 코드를 작성하고 실행하기 위한 Visual Studio 또는 유사한 IDE.

차트를 만들려면 Aspose.Slides for .NET이 필요하므로 아래 설명한 대로 설정해야 합니다.

## .NET용 Aspose.Slides 설정

Aspose.Slides for .NET은 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업할 수 있는 강력한 라이브러리입니다. 프로젝트에 추가하는 방법은 다음과 같습니다.

### 설치

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔:**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI:** 
- NuGet 패키지 관리자를 열고 "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득

Aspose.Slides를 최대한 활용하려면 무료 체험판을 사용해 보세요. 장기간 사용하려면 임시 라이선스를 구매하거나 [아스포제](https://purchase.aspose.com/buy)프로젝트 환경에서 라이선스를 설정하려면 해당 지침을 따르세요.

### 기본 초기화

설치 후 초기화 `Presentation` 슬라이드 만들기를 시작하는 수업:
```csharp
using Aspose.Slides;

// Presentation 클래스 인스턴스 초기화
tPresentation presentation = new Presentation();
```

이제 Aspose.Slides for .NET을 사용하여 차트 생성 및 사용자 지정 기능을 구현하는 단계로 넘어가겠습니다.

## 구현 가이드

### 누적 막대형 차트 만들기

목표는 누적 세로 막대형 차트를 만들고 데이터 레이블로 백분율을 표시하여 맞춤 설정하는 것입니다. 방법은 다음과 같습니다.

#### 프레젠테이션 초기화

인스턴스를 생성하여 시작하세요 `Presentation`:
```csharp
using Aspose.Slides;

// Presentation 클래스 인스턴스 초기화
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### 슬라이드에 차트 추가

첫 번째 슬라이드에 지정된 좌표와 크기로 쌓인 막대형 차트를 추가합니다.
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
이 라인은 다음을 생성합니다. `StackedColumn` 위치(20, 20)에 너비와 높이가 400인 차트.

#### 백분율 계산을 위한 총 값 계산

백분율을 표시하려면 모든 시리즈의 각 범주에 대한 총 가치를 계산하세요.
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // 각 카테고리의 모든 시리즈 값을 합산합니다.
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### 데이터 레이블을 사용자 지정하여 백분율 값 표시

다음으로, 각 시리즈를 반복하고 데이터 레이블을 사용자 지정합니다.
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // 백분율을 계산하다
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // 중복을 피하기 위해 텍스트를 지웁니다.
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // 기본 데이터 레이블을 숨기도록 레이블 형식 구성
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

이 섹션에서는 각 데이터 포인트의 백분율을 계산하고 이를 사용자 지정 레이블로 설정하여 기본 레이블과 겹치지 않도록 합니다.

#### 프레젠테이션 저장

마지막으로, 결과를 보려면 프레젠테이션을 저장하세요.
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## 실제 응용 프로그램

차트에 백분율을 표시하는 것은 다음과 같은 상황에서 특히 유용할 수 있습니다.
1. **재무 보고:** 포트폴리오 분포 또는 투자 수익률을 백분율로 표시합니다.
2. **판매 분석:** 지역별 성과를 강조하기 위해 시장 점유율 데이터를 백분율로 나타냅니다.
3. **설문조사 결과:** 설문조사 응답을 백분율로 표시하여 시각적으로 더 잘 비교할 수 있습니다.
4. **프로젝트 관리:** 백분율이 표시된 원형 차트를 사용하여 리소스 할당을 설명합니다.
5. **교육:** 명확한 백분율 기반 시각 자료를 사용하여 통계적 개념을 설명합니다.

이러한 맞춤형 차트를 CRM이나 ERP와 같은 시스템에 통합하면 대시보드와 보고서를 향상시켜 의사 결정 프로세스를 도울 수 있습니다.

## 성능 고려 사항

특히 대규모 데이터 세트를 사용하는 .NET용 Aspose.Slides를 사용하는 경우:
- **메모리 관리:** 메모리를 확보하려면 프레젠테이션 객체를 적절히 삭제하세요. `using` 해당되는 경우 진술.
- **효율적인 데이터 처리:** 가능하다면 계산 오버헤드를 줄이기 위해 루프 외부에서 계산을 수행합니다.
- **부하 분산:** 웹 애플리케이션의 경우 동시 차트 생성 요청에 대비해 서버 리소스가 적절하게 제공되어 있는지 확인하세요.

## 결론

이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 백분율 값을 레이블로 표시하여 차트를 만들고 사용자 지정하는 방법을 다루었습니다. 이러한 기법을 숙달하면 상세하고 시각적으로 매력적인 데이터 표현으로 프레젠테이션을 더욱 풍부하게 만들 수 있습니다.

다음 단계로, Aspose.Slides에서 제공하는 다른 차트 유형과 사용자 지정 옵션을 살펴보세요. 다양한 데이터 세트를 실험하여 통찰력을 명확하게 전달하는 강력한 시각적 요소로 변환해 보세요.

## FAQ 섹션

**질문 1: Aspose.Slides for .NET으로 차트를 만들 때 대용량 데이터 세트를 어떻게 처리합니까?**
A1: 대용량 데이터 세트의 경우, 계산을 최적화하고 효율적인 메모리 관리 기법을 사용하세요. 메모리 과부하를 방지하기 위해 처리 작업을 분할하세요.

**질문 2: 웹 애플리케이션에서 Aspose.Slides for .NET을 사용할 수 있나요?**
A2: 네, ASP.NET 애플리케이션에 통합할 수 있습니다. 최적의 성능을 위해 적절한 서버 리소스 할당을 확인하세요.

**질문 3: Aspose.Slides로 만든 차트를 다른 형식으로 내보낼 수 있나요?**
A3: 물론입니다! 라이브러리 기능을 사용하여 사용자 지정 차트가 포함된 프레젠테이션을 PDF 및 이미지 파일 등 다양한 형식으로 내보낼 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
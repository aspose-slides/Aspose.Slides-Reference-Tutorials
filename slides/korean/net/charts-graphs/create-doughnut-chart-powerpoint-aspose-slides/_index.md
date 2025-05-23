---
"date": "2025-04-15"
"description": "강력한 Aspose.Slides for .NET 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 역동적이고 시각적으로 매력적인 도넛형 차트를 만드는 방법을 알아보세요."
"title": "Aspose.Slides for .NET을 사용하여 PowerPoint에서 도넛형 차트를 만드는 방법"
"url": "/ko/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET을 사용하여 PowerPoint에서 도넛형 차트를 만드는 방법
효과적인 데이터 표현을 위해서는 시각적으로 매력적인 차트를 만드는 것이 필수적입니다. 도넛 차트는 전체의 일부를 보여주는 데 적합하여 백분율 기반 데이터 시각화에 이상적입니다. 이 튜토리얼에서는 강력한 Aspose.Slides for .NET 라이브러리를 사용하여 PowerPoint에서 동적 도넛 차트를 만드는 방법을 안내합니다.

## 소개
프레젠테이션에서는 복잡한 데이터 세트를 시각적으로 표현해야 하는 경우가 많은데, 기존의 막대형 차트나 선형 차트로는 부족할 수 있습니다. 도넛형 차트는 백분율 기반 데이터를 스타일과 명확성을 바탕으로 효과적으로 전달하는 다재다능한 도구로 부상하고 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 PowerPoint에서 직접 이러한 차트를 만드는 과정을 어떻게 간소화하는지 살펴보겠습니다.

**배울 내용:**
- .NET용 Aspose.Slides 설정
- 도넛형 차트를 만드는 단계별 지침
- 차트에 시리즈 및 범주 추가
- 명확성을 높이기 위한 데이터 레이블 구성
- 최종 프레젠테이션 저장

Aspose.Slides for .NET을 활용해 사용자 정의 도넛형 차트로 프레젠테이션을 향상시키는 방법을 알아보겠습니다.

## 필수 조건
시작하기 전에 다음 사항이 준비되었는지 확인하세요.
- **.NET 라이브러리용 Aspose.Slides**: NuGet이나 직접 다운로드를 통해 이용 가능합니다.
- **개발 환경**.NET 프로젝트에는 Visual Studio를 사용하는 것이 좋습니다.
- C#에 대한 기본 지식과 PowerPoint 구조에 대한 익숙함이 필요합니다.

## .NET용 Aspose.Slides 설정
차트를 만들려면 먼저 프로젝트에 Aspose.Slides 라이브러리를 설정해야 합니다. 설치하는 방법은 다음과 같습니다.

**.NET CLI 사용:**

```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔 사용:**

```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI를 통해:**
"Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

설치가 완료되면 프로젝트 설정을 시작할 수 있습니다. Aspose.Slides를 처음 사용하시는 경우, 임시 라이선스 또는 무료 평가판을 구매하여 제한 없이 모든 기능을 사용해 보세요.

### 프로젝트 초기화
애플리케이션에서 Aspose.Slides를 초기화하는 방법은 다음과 같습니다.

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Presentation 클래스의 인스턴스를 생성합니다.
        Presentation presentation = new Presentation();
        
        // 프레젠테이션을 조작하는 코드는 여기에 있습니다.
        
        // 프레젠테이션을 저장하세요
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## 구현 가이드
### 도넛 차트 만들기
#### 개요
먼저, PowerPoint 슬라이드에 빈 도넛형 차트를 만들어 보겠습니다. 이 차트는 데이터를 추가하고 차트 모양을 사용자 지정하는 데 사용됩니다.

**1단계: 도넛 차트 추가**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // 첫 번째 슬라이드에 위치(10, 10)에 크기(500, 500)의 도넛형 차트를 추가합니다.
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // 기존 시리즈 및 카테고리 지우기
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // 더 깔끔한 모양을 위해 범례를 비활성화하세요
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**설명:**
- **차트 추가**: 슬라이드에 새로운 도넛형 차트를 삽입합니다.
- **getChartDataWorkbook**: 차트의 데이터 셀에 접근하여 조작할 수 있습니다.

### 시리즈 및 카테고리 추가
#### 개요
다음으로, 시리즈와 카테고리를 추가하여 차트에 의미 있는 데이터를 채워 보겠습니다.

**2단계: 데이터 시리즈 추가**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // 시리즈 추가
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // 도넛 구멍 및 시작 각도 사용자 지정
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // 카테고리 추가
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // 데이터 포인트의 채우기 및 선 서식 지정
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**설명:**
- **추가하다**: 차트에 새로운 시리즈와 카테고리를 삽입합니다.
- **도넛 구멍 크기 설정**도넛 구멍의 크기를 조절하여 시각적인 매력을 높여줍니다.

### 데이터 레이블 구성
#### 개요
데이터 레이블은 차트 데이터에 맥락을 제공합니다. 데이터 레이블을 맞춤설정하여 가독성을 높여 보세요.

**3단계: 데이터 레이블 사용자 지정**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // 데이터 레이블 사용자 정의
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**설명:**
- **IDataLabel**: 명확성과 표현을 위해 데이터 레이블을 사용자 지정합니다.
- **setCenterText**, **표시 백분율**: 텍스트를 가운데 정렬하고 백분율을 표시하여 라벨의 가독성을 높입니다.

## 결론
이 가이드를 따라 하면 Aspose.Slides for .NET을 사용하여 PowerPoint에서 동적 도넛형 차트를 만드는 방법을 배우게 됩니다. 이 강력한 라이브러리는 광범위한 사용자 지정을 지원하여 프레젠테이션 요구 사항에 맞게 차트를 정확하게 맞춤 설정할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
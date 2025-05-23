---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 시각적으로 매력적인 백분율 기반 누적 세로 막대형 차트를 만드는 방법을 알아보세요. 명확한 데이터 시각화를 위한 단계별 가이드를 따라해 보세요."
"title": "Aspose.Slides를 사용하여 .NET에서 백분율 기반 누적 막대형 차트를 만드는 방법"
"url": "/ko/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET을 사용하여 백분율 기반 누적 막대형 차트를 만드는 방법

## 소개

데이터 시각화 영역에서 정보를 명확하고 효과적으로 표현하는 것은 효과적인 의사 결정을 위해 매우 중요합니다. 복잡한 데이터 세트를 직관적으로 표시하려면 백분율 기반 누적 세로 막대형 차트가 이상적입니다. 이 가이드에서는 프레젠테이션 파일 조작을 위해 설계된 강력한 라이브러리인 Aspose.Slides for .NET을 사용하여 이러한 차트를 만드는 방법을 안내합니다.

이 튜토리얼을 따라가면 다음 내용을 배울 수 있습니다.
- 차트 데이터 설정 및 숫자 형식 구성.
- 시리즈를 추가하고 모양을 사용자 지정합니다.
- 가독성을 높이기 위해 라벨 서식을 지정합니다.

뛰어들 준비되셨나요? 먼저 필요한 사전 준비 사항부터 살펴보겠습니다!

## 필수 조건

백분율 기반 누적 세로 막대형 차트를 만들기 전에 환경이 올바르게 설정되어 있는지 확인하세요. 다음이 필요합니다.

### 필수 라이브러리, 버전 및 종속성
- **.NET용 Aspose.Slides**: 이 라이브러리가 설치되어 있는지 확인하세요.

### 환경 설정 요구 사항
- .NET SDK가 설치된 개발 환경.
- C# 코드를 실행하기 위한 Visual Studio 또는 호환 IDE.

### 지식 전제 조건
- C# 프로그래밍에 대한 기본적인 이해.
- .NET 프로젝트 설정 및 패키지 관리에 대한 지식이 필요합니다.

## .NET용 Aspose.Slides 설정

Aspose.Slides를 사용하여 차트를 만들려면 먼저 다음 방법 중 하나를 사용하여 라이브러리를 설치하세요.

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI**
- "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득 단계

임시 라이센스를 다운로드하여 무료 평가판을 시작하세요. [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)계속 사용하려면 정식 라이선스 구매를 고려해 보세요. 

설정이 완료되면 프로젝트에서 Aspose.Slides를 시작합니다.
```csharp
using Aspose.Slides;
```

## 구현 가이드

환경이 준비되었으니, 백분율 기반의 누적 막대형 차트를 만드는 과정을 단계별로 살펴보겠습니다.

### 차트 만들기 및 구성

#### 개요
인스턴스를 생성합니다 `Presentation` 슬라이드 작업에 필수적인 클래스를 만듭니다. 그런 다음 슬라이드에 누적 세로 막대형 차트를 추가하고 구성합니다.

#### 누적 막대형 차트 추가
```csharp
// Presentation 클래스의 인스턴스를 생성합니다.
document = new Presentation();

// 첫 번째 슬라이드에 대한 참조를 얻으세요
slide = document.Slides[0];

// 위치(20, 20)에 크기(500x400)의 PercentsStackedColumn 차트를 추가합니다.
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### 숫자 형식 구성
데이터가 백분율로 표시되는지 확인하세요.
```csharp
// 세로축에 대한 숫자 형식 구성
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // 숫자 형식을 백분율로 설정
```

#### 데이터 시리즈 및 포인트 추가
기존 시리즈 데이터를 지우고 새 시리즈 데이터를 추가합니다.
```csharp
// 기존 시리즈 데이터를 지웁니다.
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// 차트 데이터 통합 문서 액세스
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// 새로운 데이터 시리즈 "Reds"를 추가합니다.
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// 시리즈의 채우기 색상을 빨간색으로 설정
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// "Reds" 시리즈에 대한 레이블 형식 속성 구성
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // 백분율 형식 설정
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// "블루스" 시리즈를 하나 더 추가하세요
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// 시리즈의 채우기 색상을 파란색으로 설정
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // 백분율 형식 설정
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### 프레젠테이션 저장
프레젠테이션을 파일에 저장하세요.
```csharp
// PPTX 형식으로 프레젠테이션을 저장합니다.
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### 문제 해결 팁
- 모든 네임스페이스가 올바르게 가져왔는지 확인하세요.
- 속성 이름과 메서드 호출에 오타가 있는지 확인하세요.
- 파일을 저장할 경로가 있는지, 그리고 올바른 권한이 있는지 확인하세요.

## 실제 응용 프로그램

백분율 기반의 누적 막대형 차트가 유용한 몇 가지 시나리오는 다음과 같습니다.
1. **판매 분석**: 전체 매출에 대한 비율로 다양한 지역의 제품 성과를 시각화합니다.
2. **예산 할당**: 각 부서가 전체 회사 지출과 관련하여 예산을 어떻게 할당하는지 보여줍니다.
3. **시장 조사**: 시간 경과에 따른 다양한 제품 범주에 대한 소비자 선호도를 비교합니다.
4. **교육 데이터**: 다양한 과목의 학생 성적 분포를 표시합니다.
5. **의료 통계**: 다양한 건강 상태에 따른 환자 인구 통계를 나타냅니다.

## 성능 고려 사항

최적의 성능을 위해 다음을 고려하세요.
- 데이터 포인트의 수를 필요한 수준으로 제한합니다.
- 런타임 처리를 최소화하기 위해 데이터를 미리 로드합니다.
- Aspose.Slides for .NET을 사용하여 효율적인 메모리 관리 방법을 사용합니다.

## 결론

축하합니다! Aspose.Slides for .NET을 사용하여 백분율 기반 누적 세로 막대형 차트를 만드는 방법을 성공적으로 배우셨습니다. 이 도구는 복잡한 데이터를 더 이해하기 쉽고 시각적으로 매력적으로 만들어 프레젠테이션을 더욱 향상시켜 줍니다.

다음 단계는 무엇일까요? Aspose.Slides에서 제공하는 다른 차트 유형을 살펴보거나 이 기능을 더 큰 애플리케이션에 통합해 보세요. 즐거운 코딩 되세요!

## FAQ 섹션

**질문 1: Aspose.Slides를 무료로 사용할 수 있나요?**
A1: 네, Aspose.Slides의 기능을 테스트하기 위해 무료 체험판으로 시작할 수 있습니다.

**질문 2: Aspose.Slides for .NET에서 지원하는 차트 유형은 무엇입니까?**
A2: 파이형, 막대형, 세로형, 선형 등 다양한 차트를 지원합니다.

**질문 3: Aspose.Slides for .NET을 시작하려면 어떻게 해야 하나요?**
A3: 위에서 설명한 대로 NuGet 또는 .NET CLI를 사용하여 라이브러리를 설치하세요. 설명서를 따라 첫 번째 차트를 만들어 보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
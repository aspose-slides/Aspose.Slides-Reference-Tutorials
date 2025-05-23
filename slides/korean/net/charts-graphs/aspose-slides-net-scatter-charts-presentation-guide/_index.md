---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET을 사용하여 분산형 차트로 프레젠테이션을 더욱 돋보이게 하는 방법을 알아보세요. 이 종합 가이드를 따라 차트를 효과적으로 만들고 사용자 정의해 보세요."
"title": "Aspose.Slides .NET을 사용하여 프레젠테이션에 분산형 차트 추가하기 - 단계별 가이드"
"url": "/ko/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET을 사용하여 프레젠테이션에 분산형 차트 추가: 단계별 가이드

## 소개
분산형 차트를 손쉽게 통합하여 프레젠테이션을 더욱 풍성하게 만들고 싶으신가요? Aspose.Slides for .NET의 강력한 기능을 활용하면 차트를 쉽게 만들고 사용자 지정할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 슬라이드에 분산형 차트를 추가하는 방법을 안내합니다. 이러한 기술을 익히면 데이터를 더욱 효과적으로 표현하고 시각적으로 매력적인 프레젠테이션을 만들 수 있습니다.

**배울 내용:**
- 프로젝트에서 .NET용 Aspose.Slides 설정
- 새 프레젠테이션 만들기 및 첫 번째 슬라이드 액세스
- 슬라이드에 부드러운 선이 있는 분산형 차트 추가
- 기존 시리즈를 지우고 차트에 새 시리즈를 추가합니다.
- 향상된 시각화를 위해 데이터 포인트 및 마커 스타일 수정
- 지정된 디렉토리에 프레젠테이션 저장

먼저 전제 조건을 검토해 보겠습니다.

## 필수 조건
.NET용 Aspose.Slides를 구현하기 전에 다음 사항이 있는지 확인하세요.
- **.NET용 Aspose.Slides 라이브러리**: 버전 23.7 이상.
- **개발 환경**: .NET Framework 4.6.1 이상 또는 .NET Core/5 이상이 설치된 Visual Studio 2019 이상.
- **기본 C# 지식**: C#의 객체 지향 프로그래밍에 익숙함.

## .NET용 Aspose.Slides 설정
Aspose.Slides를 사용하려면 프로젝트에 라이브러리를 설치해야 합니다. 설치 방법은 다음과 같습니다.

**.NET CLI 사용:**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 콘솔 사용:**
```powershell
Install-Package Aspose.Slides
```

**NuGet 패키지 관리자 UI:**
- "Aspose.Slides"를 검색하여 최신 버전을 설치하세요.

### 라이센스 취득
무료 체험판을 시작하거나 임시 라이선스를 신청하여 모든 기능을 사용해 보세요. 구매하려면 다음 단계를 따르세요.
1. 방문하다 [Aspose.Slides 구매](https://purchase.aspose.com/buy) 전체 라이센스를 구매하세요.
2. 임시 면허증을 받으려면 방문하세요. [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).

라이선스 파일을 얻었으면 다음을 사용하여 프로젝트에 추가하세요.
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## 구현 가이드
우리는 기능에 따라 구현을 논리적 섹션으로 나누어 보겠습니다.

### 프레젠테이션 만들기 및 슬라이드 추가
이 섹션에서는 프레젠테이션을 만들고 첫 번째 슬라이드에 액세스하는 방법을 보여줍니다.

#### 개요
인스턴스를 생성하여 시작하세요. `Presentation` PowerPoint 파일을 나타내는 클래스입니다. 이 객체 모델을 사용하면 슬라이드에 쉽게 액세스할 수 있습니다.

#### 구현 단계
**1단계: 프레젠테이션 초기화**
```csharp
using Aspose.Slides;

// 새로운 프레젠테이션을 만드세요
t Presentation pres = new Presentation();
```
이 코드는 새로운 프레젠테이션 문서를 초기화합니다.

**2단계: 첫 번째 슬라이드에 액세스**
```csharp
// 프레젠테이션의 첫 번째 슬라이드에 접근하세요
ISlide slide = pres.Slides[0];
```
여기, `pres.Slides[0]` 첫 번째 슬라이드에 접근합니다. 

### 슬라이드에 분산형 차트 추가
이제 프레젠테이션에 분산형 차트를 추가해 보겠습니다.

#### 개요
차트를 추가하면 프레젠테이션에 데이터를 시각적으로 표현하는 데 도움이 됩니다. Aspose.Slides를 사용하면 산점도를 포함한 다양한 유형의 차트를 쉽게 추가할 수 있습니다.

#### 구현 단계
**1단계: 분산형 차트 만들기 및 추가**
```csharp
using Aspose.Slides.Charts;

// 부드러운 선이 있는 기본 분산형 차트를 만들고 추가합니다.
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
이 스니펫은 지정된 위치와 크기에 분산형 차트를 추가합니다.

### 차트 데이터에 시리즈 추가 및 지우기
#### 개요
기존 시리즈를 삭제하고 새 시리즈를 추가하여 차트를 사용자 지정해야 할 수도 있습니다. 이 섹션에서는 해당 기능에 대해 설명합니다.

#### 구현 단계
**1단계: 차트 데이터 통합 문서 액세스**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// 기존 시리즈를 모두 지웁니다.
chart.ChartData.Series.Clear();
```
이 코드는 기존 데이터를 지워서 새로운 시리즈로 시작합니다.

**2단계: 새 시리즈 추가**
```csharp
// "시리즈 1"이라는 이름의 새 시리즈를 추가합니다.
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// "시리즈 2"라는 이름의 다른 시리즈를 추가합니다.
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
이 단계를 거치면 차트에 두 개의 새로운 시리즈가 추가됩니다.

### 첫 번째 시리즈 데이터 포인트 및 마커 스타일 수정
#### 개요
산점도를 더 잘 시각화하려면 데이터 포인트와 마커 스타일을 사용자 지정하세요.

#### 구현 단계
**1단계: 데이터 포인트 액세스 및 추가**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// 데이터 포인트 (1, 3)과 (2, 10)을 추가합니다.
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**2단계: 마커 스타일 수정**
```csharp
// 시리즈 유형을 변경하고 마커 스타일을 수정합니다.
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### 두 번째 시리즈 데이터 포인트 및 마커 스타일 수정
#### 개요
마찬가지로, 두 번째 시리즈도 프레젠테이션 요구 사항에 맞게 사용자 정의하세요.

#### 구현 단계
**1단계: 여러 데이터 포인트에 액세스하고 추가**
```csharp
// 두 번째 차트 시리즈에 접속하세요
series = chart.ChartData.Series[1];

// 여러 데이터 포인트 추가
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**2단계: 마커 스타일 수정**
```csharp
// 두 번째 시리즈의 마커 크기와 기호 변경
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### 프레젠테이션 저장
마지막으로, 프레젠테이션을 지정된 디렉토리에 저장합니다.

#### 구현 단계
**1단계: 디렉토리 정의**
출력 디렉터리가 있는지 확인하세요. 없으면 새로 만드세요.
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// 프레젠테이션을 저장하세요
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
이 코드는 프레젠테이션 파일을 지정된 위치에 저장합니다.

## 결론
이제 Aspose.Slides for .NET을 사용하여 프레젠테이션에 분산형 차트를 성공적으로 추가했습니다. 라이브러리에서 제공하는 추가 기능과 사용자 지정 기능을 계속 탐색하여 데이터 시각화 기술을 향상시키세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Aspose.Slides .NET의 데이터 포인트에 차트 마커 옵션 사용
linktitle: 데이터 포인트의 차트 마커 옵션
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: .NET용 Aspose.Slides를 사용하여 PowerPoint 차트를 향상시키는 방법을 알아보세요. 이미지로 데이터 포인트 마커를 사용자 정의하세요. 매력적인 프레젠테이션을 만드세요.
weight: 11
url: /ko/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


프레젠테이션 및 데이터 시각화 작업을 할 때 Aspose.Slides for .NET은 차트를 생성, 사용자 정의 및 조작할 수 있는 광범위하고 강력한 기능을 제공합니다. 이 튜토리얼에서는 데이터 포인트의 차트 마커 옵션을 사용하여 차트 프리젠테이션을 향상시키는 방법을 살펴보겠습니다. 이 단계별 가이드에서는 필수 구성 요소부터 네임스페이스 가져오기를 시작하여 각 예제를 여러 단계로 분류하는 프로세스를 안내합니다.

## 전제 조건

데이터 포인트에 차트 표시 옵션을 사용하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Slides: .NET용 Aspose.Slides가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/net/).

- 샘플 프리젠테이션: 이 튜토리얼에서는 "Test.pptx"라는 샘플 프리젠테이션을 사용합니다. 이 프리젠테이션은 문서 디렉토리에 있어야 합니다.

이제 필요한 네임스페이스를 가져오는 것부터 시작해 보겠습니다.

## 네임스페이스 가져오기

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

필요한 네임스페이스를 가져오고 프레젠테이션을 초기화했습니다. 이제 데이터 포인트에 차트 표시 옵션을 사용해 보겠습니다.

## 1단계: 기본 차트 만들기

```csharp

// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//기본 차트 만들기
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

슬라이드에 지정된 위치와 크기로 "LineWithMarkers" 유형의 기본 차트를 만듭니다.

## 2단계: 기본 차트 데이터 워크시트 색인 가져오기

```csharp
// 기본 차트 데이터 워크시트 색인 가져오기
int defaultWorksheetIndex = 0;
```

여기서는 기본 차트 데이터 워크시트의 인덱스를 얻습니다.

## 3단계: 차트 데이터 워크시트 가져오기

```csharp
// 차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

차트 데이터 작업을 위해 차트 데이터 통합 문서를 가져옵니다.

## 4단계: 차트 시리즈 수정

```csharp
// 데모 시리즈 삭제
chart.ChartData.Series.Clear();

// 새 시리즈 추가
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

이 단계에서는 기존 데모 시리즈를 제거하고 "시리즈 1"이라는 새 시리즈를 차트에 추가합니다.

## 5단계: 데이터 포인트에 대한 그림 채우기 설정

```csharp
// 마커에 대한 그림 설정
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// 첫 번째 차트 시리즈를 살펴보세요
IChartSeries series = chart.ChartData.Series[0];

// 그림 채우기로 새 데이터 포인트 추가
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

데이터 포인트에 대한 그림 표시를 설정하여 각 데이터 포인트가 차트에 표시되는 방식을 사용자 정의할 수 있습니다.

## 6단계: 차트 시리즈 표시자 크기 변경

```csharp
// 차트 시리즈 마커 크기 변경
series.Marker.Size = 15;
```

여기서는 시각적으로 매력적이도록 차트 시리즈 표시의 크기를 조정합니다.

## 7단계: 프레젠테이션 저장

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

마지막으로 새로운 차트 설정으로 프레젠테이션을 저장합니다.

## 결론

.NET용 Aspose.Slides를 사용하면 다양한 사용자 정의 옵션을 사용하여 멋진 차트 프레젠테이션을 만들 수 있습니다. 이 튜토리얼에서는 데이터 포인트의 차트 표시 옵션을 사용하여 데이터의 시각적 표현을 향상시키는 데 중점을 두었습니다. .NET용 Aspose.Slides를 사용하면 프레젠테이션을 한 단계 더 발전시켜 더욱 매력적이고 유익하게 만들 수 있습니다.

.NET용 Aspose.Slides에 대해 질문이 있거나 도움이 필요하면 언제든지 다음을 방문하세요.[Aspose.Slides 문서](https://reference.aspose.com/slides/net/) 또는 다음 연락처로 연락하세요.[커뮤니티를 제안하세요](https://forum.aspose.com/) 지원을 위해.

## 자주 묻는 질문(FAQ)

### .NET용 Aspose.Slides에서 데이터 포인트의 마커로 사용자 정의 이미지를 사용할 수 있습니까?
예, 이 튜토리얼에서 설명한 대로 Aspose.Slides for .NET의 데이터 포인트에 대한 마커로 사용자 정의 이미지를 사용할 수 있습니다.

### .NET용 Aspose.Slides에서 차트 유형을 어떻게 변경할 수 있나요?
 다른 항목을 지정하여 차트 유형을 변경할 수 있습니다.`ChartType` "Bar", "Pie" 또는 "Area"와 같은 차트를 만들 때

### Aspose.Slides for .NET은 최신 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for .NET은 다양한 PowerPoint 형식과 작동하도록 설계되었으며 최신 PowerPoint 버전과의 호환성을 유지하기 위해 정기적으로 업데이트됩니다.

### .NET용 Aspose.Slides에 대한 추가 튜토리얼과 리소스는 어디에서 찾을 수 있나요?
 다음에서 추가 튜토리얼과 리소스를 탐색할 수 있습니다.[Aspose.Slides 문서](https://reference.aspose.com/slides/net/).

### .NET용 Aspose.Slides 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드하여 .NET용 Aspose.Slides를 사용해 볼 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

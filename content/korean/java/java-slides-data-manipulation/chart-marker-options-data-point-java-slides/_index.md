---
title: Java 슬라이드의 데이터 포인트에 대한 차트 표시 옵션
linktitle: Java 슬라이드의 데이터 포인트에 대한 차트 표시 옵션
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 사용자 정의 차트 마커 옵션으로 Java 슬라이드를 최적화하세요. Aspose.Slides for Java를 사용하여 데이터 포인트를 시각적으로 향상시키는 방법을 알아보세요. 단계별 지침과 FAQ를 살펴보세요.
type: docs
weight: 14
url: /ko/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Java 슬라이드의 데이터 포인트에 대한 차트 표시 옵션 소개

영향력 있는 프레젠테이션을 만들려면 데이터 포인트의 차트 표시를 사용자 정의하고 조작하는 기능이 큰 차이를 만들 수 있습니다. Aspose.Slides for Java를 사용하면 차트를 역동적이고 시각적으로 매력적인 요소로 변환할 수 있습니다.

## 전제조건

코딩 부분을 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 자바 개발 환경
- Java 라이브러리용 Aspose.Slides
- Java IDE(통합 개발 환경)
- 샘플 프레젠테이션 문서(예: "Test.pptx")

## 1단계: 환경 설정

먼저, 필요한 도구가 설치되어 준비되었는지 확인하세요. IDE에서 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 가져옵니다.

## 2단계: 프레젠테이션 로드

시작하려면 샘플 프레젠테이션 문서를 로드하세요. 제공된 코드에서는 문서 이름이 "Test.pptx"라고 가정합니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 3단계: 차트 만들기

이제 프레젠테이션에 차트를 만들어 보겠습니다. 이 예에서는 마커가 있는 선형 차트를 사용합니다.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## 4단계: 차트 데이터 작업

차트 데이터를 조작하려면 차트 데이터 통합 문서에 접근하여 데이터 시리즈를 준비해야 합니다. 기본 계열을 지우고 사용자 정의 데이터를 추가하겠습니다.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## 5단계: 사용자 정의 마커 추가하기

여기에 흥미로운 부분이 있습니다. 즉, 데이터 포인트의 마커를 사용자 정의하는 것입니다. 이 예에서는 이미지를 마커로 사용하겠습니다.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// 데이터 포인트에 사용자 정의 마커 추가
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// 다른 데이터 포인트에 대해서도 반복합니다.
// ...

//차트 시리즈 마커 크기 변경
series.getMarker().setSize(15);
```

## 6단계: 프레젠테이션 저장

차트 표시를 사용자 정의한 후 프레젠테이션을 저장하여 실제 변경 사항을 확인하세요.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 데이터 포인트에 대한 차트 표시 옵션에 대한 전체 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//기본 차트 만들기
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//기본 차트 데이터 워크시트 색인 가져오기
int defaultWorksheetIndex = 0;
//차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//데모 시리즈 삭제
chart.getChartData().getSeries().clear();
//새 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//그림을 설정하세요
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//그림을 설정하세요
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//첫 번째 차트 시리즈 가져오기
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//거기에 새로운 포인트(1:3)를 추가하세요.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//차트 시리즈 마커 변경하기
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## 결론

Aspose.Slides for Java를 사용하면 데이터 포인트의 차트 마커를 사용자 정의하여 프레젠테이션을 향상시킬 수 있습니다. 이를 통해 청중의 시선을 사로잡는 시각적으로 훌륭하고 유익한 슬라이드를 만들 수 있습니다.

## FAQ

### 데이터 포인트의 마커 크기를 어떻게 변경할 수 있나요?

 데이터 포인트의 마커 크기를 변경하려면`series.getMarker().setSize()` 메서드를 사용하고 원하는 크기를 인수로 제공합니다.

### 이미지를 맞춤 마커로 사용할 수 있나요?

예, 이미지를 데이터 포인트의 사용자 정의 마커로 사용할 수 있습니다. 채우기 유형을 다음으로 설정합니다.`FillType.Picture` 사용하고 싶은 이미지를 제공하세요.

### Aspose.Slides for Java는 동적 차트 생성에 적합합니까?

전적으로! Aspose.Slides for Java는 프레젠테이션에서 동적 및 대화형 차트를 생성할 수 있는 광범위한 기능을 제공합니다.

### Aspose.Slides를 사용하여 차트의 다른 측면을 사용자 정의할 수 있나요?

예, Aspose.Slides for Java를 사용하면 제목, 축, 데이터 레이블 등을 포함하여 차트의 다양한 측면을 사용자 정의할 수 있습니다.

### Java 문서 및 다운로드용 Aspose.Slides에 어디서 액세스할 수 있나요?

 문서는 다음에서 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/java/) 그리고 다음에서 라이브러리를 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
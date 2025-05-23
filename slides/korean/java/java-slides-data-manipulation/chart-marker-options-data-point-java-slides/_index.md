---
"description": "사용자 지정 차트 마커 옵션으로 Java 슬라이드를 최적화하세요. Aspose.Slides for Java를 사용하여 데이터 포인트를 시각적으로 개선하는 방법을 알아보세요. 단계별 안내와 FAQ도 살펴보세요."
"linktitle": "Java 슬라이드의 데이터 포인트에 대한 차트 마커 옵션"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드의 데이터 포인트에 대한 차트 마커 옵션"
"url": "/ko/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드의 데이터 포인트에 대한 차트 마커 옵션


## Java 슬라이드의 데이터 포인트에 대한 차트 마커 옵션 소개

인상적인 프레젠테이션을 만들 때, 데이터 포인트에 차트 마커를 맞춤 설정하고 조작하는 기능은 큰 차이를 만들어낼 수 있습니다. Aspose.Slides for Java를 사용하면 차트를 역동적이고 시각적으로 매력적인 요소로 변환할 수 있습니다.

## 필수 조건

코딩 부분을 살펴보기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- 자바 개발 환경
- Java용 Aspose.Slides 라이브러리
- Java 통합 개발 환경(IDE)
- 샘플 프레젠테이션 문서(예: "Test.pptx")

## 1단계: 환경 설정

먼저, 필요한 도구가 설치되어 있는지 확인하세요. IDE에서 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 가져오세요.

## 2단계: 프레젠테이션 로딩

시작하려면 샘플 프레젠테이션 문서를 불러오세요. 제공된 코드에서는 문서 이름이 "Test.pptx"라고 가정합니다.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 3단계: 차트 만들기

이제 프레젠테이션에 차트를 만들어 보겠습니다. 이 예제에서는 마커가 있는 선형 차트를 사용하겠습니다.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## 4단계: 차트 데이터 작업

차트 데이터를 조작하려면 차트 데이터 통합 문서에 접근하여 데이터 시리즈를 준비해야 합니다. 기본 시리즈를 지우고 사용자 지정 데이터를 추가하겠습니다.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## 5단계: 사용자 정의 마커 추가

이제 흥미로운 부분입니다. 바로 데이터 포인트의 마커를 맞춤 설정하는 것입니다. 이 예제에서는 이미지를 마커로 사용하겠습니다.

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

// 차트 시리즈 마커 크기 변경
series.getMarker().setSize(15);
```

## 6단계: 프레젠테이션 저장

차트 마커를 사용자 지정한 후 프레젠테이션을 저장하여 변경 사항이 실제로 적용되는지 확인하세요.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Java 슬라이드의 데이터 포인트에 대한 차트 마커 옵션에 대한 전체 소스 코드

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//기본 차트 만들기
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//기본 차트 데이터 워크시트 인덱스 가져오기
int defaultWorksheetIndex = 0;
//차트 데이터 워크시트 가져오기
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//데모 시리즈 삭제
chart.getChartData().getSeries().clear();
//새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//그림을 설정하다
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//그림을 설정하다
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//첫 번째 차트 시리즈를 가져가세요
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//거기에 새로운 지점(1:3)을 추가합니다.
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
//차트 시리즈 마커 변경
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## 결론

Aspose.Slides for Java를 사용하면 데이터 포인트에 차트 마커를 맞춤 설정하여 프레젠테이션의 완성도를 높일 수 있습니다. 이를 통해 시각적으로 아름답고 유익한 슬라이드를 제작하여 청중을 사로잡을 수 있습니다.

## 자주 묻는 질문

### 데이터 포인트의 마커 크기를 어떻게 변경할 수 있나요?

데이터 포인트의 마커 크기를 변경하려면 다음을 사용하세요. `series.getMarker().setSize()` 메서드를 사용하고 원하는 크기를 인수로 제공합니다.

### 이미지를 사용자 정의 마커로 사용할 수 있나요?

네, 이미지를 데이터 포인트의 사용자 지정 마커로 사용할 수 있습니다. 채우기 유형을 다음과 같이 설정하세요. `FillType.Picture` 그리고 사용하고 싶은 이미지를 제공하세요.

### Java용 Aspose.Slides는 동적 차트를 만드는 데 적합합니까?

물론입니다! Aspose.Slides for Java는 프레젠테이션에서 동적이고 인터랙티브한 차트를 제작할 수 있는 다양한 기능을 제공합니다.

### Aspose.Slides를 사용하여 차트의 다른 측면을 사용자 정의할 수 있나요?

네, Aspose.Slides for Java를 사용하면 제목, 축, 데이터 레이블 등 차트의 다양한 측면을 사용자 정의할 수 있습니다.

### Java용 Aspose.Slides 문서와 다운로드는 어디에서 볼 수 있나요?

설명서는 다음에서 찾을 수 있습니다. [여기](https://reference.aspose.com/slides/java/) 그리고 라이브러리를 다운로드하세요 [여기](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
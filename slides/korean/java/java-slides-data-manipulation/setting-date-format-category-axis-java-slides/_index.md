---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 차트의 범주 축에 날짜 형식을 설정하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다."
"linktitle": "Java Slides에서 카테고리 축의 날짜 형식 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 카테고리 축의 날짜 형식 설정"
"url": "/ko/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 카테고리 축의 날짜 형식 설정


## Java Slides에서 범주 축의 날짜 형식 설정 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 차트의 범주 축에 날짜 형식을 설정하는 방법을 알아봅니다. Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 조작하고, 관리할 수 있는 강력한 라이브러리입니다.

## 필수 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

1. Java 라이브러리용 Aspose.Slides(다음에서 다운로드 가능) [여기](https://releases.aspose.com/slides/java/).
2. Java 개발 환경 설정.

## 1단계: PowerPoint 프레젠테이션 만들기

먼저 차트를 추가할 PowerPoint 프레젠테이션을 만들어야 합니다. 필요한 Aspose.Slides 클래스를 가져왔는지 확인하세요.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2단계: 슬라이드에 차트 추가

이제 PowerPoint 슬라이드에 차트를 추가해 보겠습니다. 이 예제에서는 영역형 차트를 사용하겠습니다.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## 3단계: 차트 데이터 준비

차트 데이터와 범주를 설정하겠습니다. 이 예에서는 날짜 범주를 사용하겠습니다.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// 날짜 카테고리 추가
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// 데이터 시리즈 추가
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## 4단계: 카테고리 축 사용자 정의
이제 날짜를 특정 형식(예: yyyy)으로 표시하도록 범주 축을 사용자 지정해 보겠습니다.

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## 5단계: 프레젠테이션 저장
마지막으로 PowerPoint 프레젠테이션을 저장합니다.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

이제 Aspose.Slides for Java를 사용하여 PowerPoint 차트의 범주 축에 날짜 형식을 성공적으로 설정했습니다.

## Java Slides에서 카테고리 축의 날짜 형식을 설정하기 위한 완전한 소스 코드

```java
	// 문서 디렉토리의 경로입니다.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##결론

Aspose.Slides for Java를 사용하여 Java Slides 차트의 범주 축에 대한 날짜 형식을 성공적으로 사용자 지정했습니다. 이제 차트에 날짜 값을 원하는 형식으로 표시할 수 있습니다. 특정 요구 사항에 따라 추가 사용자 지정 옵션을 자유롭게 살펴보세요.

## 자주 묻는 질문

### 카테고리 축의 날짜 형식을 어떻게 변경합니까?

카테고리 축의 날짜 형식을 변경하려면 다음을 사용하세요. `setNumberFormat` 범주 축에 메서드를 추가하고 "yyyy-MM-dd" 또는 "MM/yyyy"와 같이 원하는 날짜 형식 패턴을 제공하세요. `setNumberFormatLinkedToSource(false)` 기본 형식을 재정의합니다.

### 동일한 프레젠테이션에서 각 차트에 다른 날짜 형식을 사용할 수 있나요?

네, 같은 프레젠테이션 내에서 여러 차트의 범주 축에 대해 서로 다른 날짜 형식을 설정할 수 있습니다. 필요에 따라 각 차트의 범주 축을 사용자 지정하기만 하면 됩니다.

### 차트에 더 많은 데이터 포인트를 추가하려면 어떻게 해야 하나요?

차트에 더 많은 데이터 포인트를 추가하려면 다음을 사용하세요. `getDataPoints().addDataPointForLineSeries` 데이터 시리즈에 대한 방법을 사용하고 데이터 값을 제공합니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
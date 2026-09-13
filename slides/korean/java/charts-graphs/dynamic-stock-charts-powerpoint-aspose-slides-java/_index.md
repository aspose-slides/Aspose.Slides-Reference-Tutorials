---
date: '2026-09-12'
description: Maven Aspose Slides를 사용하여 Java로 PowerPoint에 동적 주식 차트를 추가하고 사용자 정의하는 방법을
  배웁니다. 설정, 데이터 시리즈 추가, 라인 서식 지정 및 저장을 포함합니다.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides 튜토리얼은 Java를 사용하여 PowerPoint에서 동적 주식 차트를 만들고 사용자
  정의하는 방법을 보여주며, 데이터 시리즈, 라인 서식 지정 및 저장을 다룹니다.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides 가이드: PowerPoint에서 동적 주식 차트 만들기'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: Java를 사용하여 PowerPoint에서 동적 주식 차트 만들기'
url: /ko/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: Java로 PowerPoint에서 동적 주식 차트 만들기

## 소개

**Maven Aspose Slides**는 Java에서 프로그래밍 방식으로 정교한 PowerPoint 프레젠테이션을 생성할 수 있게 해줍니다. 이 튜토리얼에서는 동적 주식 차트를 만들고, 데이터 시리즈를 추가 및 서식 지정하고, 차트 라인을 커스터마이징하고, 마지막으로 파일을 저장하는 방법을 배웁니다. 분기 보고서를 준비하는 금융 분석가이든 자동 슬라이드 데크를 구축하는 개발자이든, 아래 단계는 완전하고 프로덕션 준비된 솔루션을 제공합니다.

**배우게 될 내용**
- Maven을 Aspose.Slides for Java와 함께 설정하는 방법
- 주식 차트를 추가하고 기본 데이터를 지우는 방법
- **데이터 시리즈 차트 추가** 및 **차트 라인 서식 지정** 방법
- **Java 전용 차트** 시각 요소를 커스터마이징하는 방법
- 업데이트된 프레젠테이션을 저장하는 방법

원시 데이터를 눈에 띄는 주식 시각 자료로 바꿀 준비가 되셨나요? 시작해봅시다!

## 빠른 답변
- **필요한 Maven 아티팩트는 무엇인가요?** `aspose-slides` version 25.4 (or newer).  
- **이것을 모든 OS에서 실행할 수 있나요?** 예 – the library is pure Java and works on Windows, macOS, and Linux.  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 임시 라이선스로 충분하고, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 차트 유형은 무엇인가요?** Stock, Line, Bar 차트를 포함한 70개 이상의 내장 차트 유형을 지원합니다.  
- **처리할 수 있는 프레젠테이션 크기는 어느 정도인가요?** Aspose.Slides는 전체 파일을 메모리에 로드하지 않고도 500장 이상의 슬라이드를 처리할 수 있습니다.

## Maven Aspose Slides란?

`Aspose.Slides for Java`는 Microsoft Office 없이 PowerPoint 파일을 생성, 조작 및 변환할 수 있는 Java API입니다. Maven 통합을 통해 의존성 관리를 단순화하고, Maven Central에서 직접 라이브러리를 가져올 수 있습니다.

## 주식 차트에 Maven Aspose Slides를 사용하는 이유는?

Aspose.Slides는 **70개 이상의 차트 유형**을 지원하며 일반 서버 하드웨어에서 수백 페이지 프레젠테이션을 1초 미만에 렌더링할 수 있습니다. **high‑low line** 및 **up/down bar** 기능을 통해 PowerPoint UI가 제공하는 것보다 훨씬 정밀한 금융 시각화를 제어할 수 있습니다.

## 사전 요구 사항

- **Java Development Kit (JDK)** – version 11 or higher.  
- **IDE** – IntelliJ IDEA, Eclipse, 또는 선호하는 편집기.  
- **Aspose.Slides for Java** – version 25.4 (작성 시 최신 버전).  

### Aspose.Slides for Java 설정

#### Maven
Maven을 사용해 프로젝트에 Aspose.Slides를 통합하려면 `pom.xml`에 다음 의존성을 추가하십시오:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Gradle 사용자는 `build.gradle`에 다음을 포함하십시오:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direct download
또는 최신 JAR 파일을 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

**라이선스 획득** – 무료 체험으로 시작하거나 임시 라이선스를 요청하십시오. 상업적 사용을 위해서는 정식 라이선스를 구매해야 합니다.

자세한 API 참조는 [Aspose.Slides documentation](https://docs.aspose.com/slides/java/)를 참고하십시오.

## 동적 주식 차트를 단계별로 만드는 방법

프레젠테이션을 로드하고, 주식 차트를 추가하고, 기본 데이터를 지운 다음 자체 시리즈와 카테고리를 삽입합니다. 핵심 질문에 대한 직접적인 답은 다음과 같습니다:

> 기존 PPTX 파일을 `new Presentation("template.pptx")` 로 로드하고, `ChartType.Stock` 유형의 `Chart`를 추가한 뒤 기본 시리즈와 카테고리를 지웁니다. 그런 다음 자체 데이터 포인트와 서식 옵션으로 채웁니다. 마지막으로 `presentation.save("output.pptx", SaveFormat.Pptx)` 를 호출합니다.

### 프레젠테이션 초기화
#### 개요
기존 PowerPoint 파일을 로드하여 그대로 수정할 수 있도록 시작합니다.

#### 단계별
1. **라이브러리 가져오기** – `Presentation` 클래스는 모든 슬라이드 작업의 진입점입니다.

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **프레젠테이션 파일 로드** – 템플릿 PPTX 파일 경로를 지정합니다.

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 슬라이드에 주식 차트 추가
#### 개요
프레젠테이션의 첫 번째 슬라이드에 Stock 차트를 삽입합니다.

`Chart` 클래스는 슬라이드에 추가할 수 있는 차트 도형을 나타냅니다.

#### 직접 답변
`slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` 를 호출하여 주식 차트를 추가합니다. 이렇게 하면 즉시 조작할 수 있는 차트 객체가 생성됩니다.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 차트에서 기존 데이터 시리즈 및 카테고리 삭제
#### 개요
사전 채워진 시리즈나 카테고리를 모두 제거하여 깨끗한 데이터 세트로 시작합니다.

`ChartData` 객체는 차트의 시리즈와 카테고리를 보유합니다.

#### 직접 답변
자체 데이터를 추가하기 전에 기본 내용을 지우려면 `chart.getChartData().getSeries().clear()` 및 `chart.getChartData().getCategories().clear()` 를 호출합니다.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 차트 데이터에 카테고리 추가
#### 개요
주식 값을 그룹화하는 X축 카테고리(예: 날짜)를 정의합니다.

`ChartCategory`는 차트의 X축 레이블을 나타냅니다.

#### 직접 답변
`chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` 와 같이 각 레이블에 대해 새로운 `ChartCategory`를 생성하고, 각 월 또는 기간마다 반복합니다.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 차트에 데이터 시리즈 추가
#### 개요
네 가지 필수 시리즈인 Open, High, Low, Close를 추가합니다.

`ChartSeries`는 차트 내 특정 시리즈의 데이터 포인트 컬렉션을 보유합니다.

#### 직접 답변
각 시리즈에 대해 `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())` 를 호출합니다. 이렇게 하면 시리즈가 차트의 데이터 워크북에 등록됩니다.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 시리즈에 데이터 포인트 추가
#### 개요
각 시리즈에 주식 가격을 나타내는 숫자 값을 채웁니다.

`DataPoint`는 시리즈 내 단일 값을 나타냅니다.

#### 직접 답변
데이터 컬렉션을 반복하면서 `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (또는 해당 시리즈 유형에 맞는 메서드)를 사용해 각 포인트를 삽입합니다.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### high‑low 라인 및 up/down 바 서식 지정
#### 개요
high‑low 연결선과 up/down 바 채우기의 시각 스타일을 조정합니다.

`Marker`는 데이터 포인트의 시각 기호를 정의합니다.

#### 직접 답변
`chart.getChartData().getSeries().get(0).getMarker().setSize(10)` 를 설정하고 `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` 로 선 두께와 색상을 제어합니다.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### up/down 바 표시
차트의 `setShowUpDownBars(true)` 메서드를 사용하여 up/down 바를 표시합니다.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### high‑low 라인에 데이터 레이블 커스터마이징
#### 개요
high‑low 라인에 숫자 값을 직접 표시하여 빠르게 참고할 수 있게 합니다.

`DataLabel`은 데이터 포인트에 연결된 레이블의 모양을 제어합니다.

#### 직접 답변
`chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` 로 데이터 레이블을 활성화하고 필요에 따라 스타일을 지정합니다.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### up/down 바 채우기 색상 설정
#### 개요
up 바에는 녹색 채우기, down 바에는 빨간색 채우기를 적용하여 시장 움직임을 직관적으로 전달합니다.

`UpDownBars` 객체는 up 및 down 바 서식에 접근할 수 있게 합니다.

#### 직접 답변
`chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` 를 적용하고 고정 색상을 `Color.GREEN` 로 설정합니다; down 바에도 `Color.RED` 로 동일하게 적용합니다.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### PowerPoint 파일 저장
#### 개요
변경 사항을 새로운 PPTX 파일에 저장합니다.

`save` 메서드는 프레젠테이션을 지정된 형식으로 디스크에 기록합니다.

#### 직접 답변
`presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` 를 호출합니다 – 이렇게 하면 수정된 프레젠테이션이 표준 PowerPoint 형식으로 디스크에 저장됩니다.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## 일반적인 문제 및 해결 방법

- **차트가 표시되지 않음** – 차트의 X/Y 좌표와 크기가 슬라이드 경계 내에 있는지 확인하십시오.  
- **데이터 포인트 누락** – 데이터 워크북 셀 인덱스가 채우려는 시리즈/행과 일치하는지 확인하십시오.  
- **라이선스 예외** – 임시 체험 라이선스는 30일 후에 만료됩니다; 프로덕션 빌드에서는 영구 라이선스로 교체하십시오.  
- **대용량 파일에서 성능 저하** – 배치로 수천 개 슬라이드를 처리할 경우 `Presentation.setCacheSize(0)` 를 사용해 캐시를 비활성화하십시오.

## 자주 묻는 질문

**Q: 이 코드를 웹 애플리케이션에서 사용할 수 있나요?**  
A: 예. 라이브러리는 순수 Java이므로 모든 서블릿 컨테이너나 Spring Boot 서비스에서 실행할 수 있습니다.

**Q: Aspose.Slides가 Stock 외에 다른 차트 유형을 지원하나요?**  
A: 물론입니다. Line, Bar, Pie, Radar 차트를 포함해 70개 이상의 차트 유형을 지원합니다.

**Q: 차트 제목을 프로그래밍 방식으로 추가하려면 어떻게 해야 하나요?**  
A: `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` 를 사용하고 필요에 따라 제목을 서식 지정하십시오.

**Q: 시리즈당 데이터 포인트 수에 제한이 있나요?**  
A: 실질적으로 수만 개의 포인트를 추가할 수 있으며, 메모리 사용량은 선형적으로 증가하고 라이브러리는 데이터를 스트리밍하여 메모리 사용량을 낮게 유지합니다.

**Q: 최신 버전을 위한 Maven 좌표는 무엇인가요?**  
A: 최신 버전은 Maven Central에서 `com.aspose:aspose-slides:25.4` (또는 최신) 로 항상 제공됩니다.

**마지막 업데이트:** 2026-09-12  
**테스트 환경:** Aspose.Slides for Java 25.4  
**작성자:** Aspose

## 관련 튜토리얼

- [aspose slides maven 종속성: Aspose.Slides for Java를 사용하여 프레젠테이션에 차트 추가 및 구성](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint 차트 Java 만들기 – Aspose.Slides를 사용하여 차트가 포함된 프레젠테이션 저장](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [PowerPoint 차트 생성 및 서식 지정 Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
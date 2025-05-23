---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 주식형 차트를 만들고 사용자 지정하는 방법을 알아보세요. 이 가이드에서는 프레젠테이션 초기화, 데이터 시리즈 추가, 차트 서식 지정, 파일 저장 방법을 다룹니다."
"title": "Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 주식 차트 만들기"
"url": "/ko/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 주식 차트 만들기

## 소개

역동적인 주식 차트를 활용하여 PowerPoint 프레젠테이션을 더욱 풍성하게 만들어 보세요. 재무 분석가, 비즈니스 전문가, 데이터 추세를 효과적으로 시각화해야 하는 교육자 등 누구에게나 이 튜토리얼은 Aspose.Slides for Java를 사용하여 주식 차트를 만들고 사용자 지정하는 방법을 안내합니다. 이 가이드를 마치면 기존 PowerPoint 파일을 불러오고, 사용자 지정 시리즈와 범주를 사용하여 상세한 주식 차트를 추가하고, 차트를 아름답게 서식 지정하고, 향상된 프레젠테이션을 저장할 수 있게 될 것입니다.

**배울 내용:**
- Aspose.Slides를 사용하여 Java로 프레젠테이션을 초기화합니다.
- 주식 차트 추가 및 사용자 정의
- 데이터 시리즈 및 범주 지우기
- 종합적인 분석을 위해 새로운 데이터 포인트를 삽입합니다.
- 차트 선과 막대를 효과적으로 포맷하세요
- 업데이트된 프레젠테이션을 저장합니다

시각적으로 매력적인 프레젠테이션을 만들 준비가 되셨나요? 시작해 볼까요!

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

- **자바 개발 키트(JDK)**시스템에 JDK가 설치되어 있는지 확인하세요.
- **IDE**: IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하여 Java 코드를 작성하고 실행하세요.
- **Java용 Aspose.Slides 라이브러리**: 이 튜토리얼을 실행하려면 Java용 Aspose.Slides 25.4 버전이 필요합니다.

### Java용 Aspose.Slides 설정

#### 메이븐
Maven을 사용하여 Aspose.Slides를 프로젝트에 통합하려면 다음 종속성을 추가하세요. `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### 그래들
Gradle 사용자의 경우 다음을 포함합니다. `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 직접 다운로드
또는 다음에서 최신 JAR을 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

**라이센스 취득**: 무료 체험판으로 시작하거나 임시 라이선스를 요청할 수 있습니다. 장기간 사용하려면 정식 라이선스 구매를 고려해 보세요.

## 구현 가이드

각 기능을 단계별로 살펴보겠습니다.

### 프레젠테이션 초기화
#### 개요
기존 PowerPoint 파일을 로드하여 수정 작업을 준비합니다.

#### 단계별 가이드
1. **라이브러리 가져오기**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **프레젠테이션 파일 로드**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // 'pres'에서 작업 수행 준비 완료
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 슬라이드에 주식 차트 추가
#### 개요
이 단계에서는 프레젠테이션의 첫 번째 슬라이드에 주식 차트를 추가하는 작업이 포함됩니다.

3. **차트 추가**:
   
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

### 차트에서 기존 데이터 시리즈 및 범주 지우기
#### 개요
차트에서 기존 데이터 시리즈나 범주를 제거하여 새로 시작하세요.

4. **데이터 지우기**:
   
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

### 차트 데이터에 범주 추가
#### 개요
더 나은 데이터 세분화 및 이해를 위해 사용자 정의 카테고리를 추가하세요.

5. **카테고리 삽입**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // 카테고리 추가
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 차트에 데이터 시리즈 추가
#### 개요
시가, 고가, 저가, 종가 등 다양한 데이터 시리즈를 통합하여 포괄적인 분석을 수행합니다.

6. **데이터 시리즈 추가**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // '시가', '고가', '저가', '종가' 시리즈를 추가합니다.
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
정확한 표현을 위해 각 시리즈에 구체적인 데이터 포인트를 채웁니다.

7. **데이터 포인트 삽입**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // '열기' 시리즈에 데이터 포인트 추가
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // 'High' 시리즈에 데이터 포인트 추가
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // '낮음' 시리즈에 데이터 포인트 추가
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // '닫기' 시리즈에 데이터 포인트 추가
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### 하이-로우 라인 및 위/아래 막대 형식
#### 개요
더 나은 시각화를 위해 고저선과 상하 막대의 모양을 사용자 정의합니다.

8. **하이-로우 라인 포맷**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // '닫기' 시리즈에 대한 높은-낮은 선 형식 지정
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **위/아래 막대 표시**:
   
   ```java
   // 주식 차트 시리즈 그룹의 상향/하향 막대 표시
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### 고가-저가 선의 데이터 레이블 사용자 지정
#### 개요
데이터 레이블을 추가하고 서식을 지정하여 높은 값-낮은 값 선에 값을 표시합니다.

10. **위/아래 막대에 값 표시**:
    
    ```java
    // 차트 그룹의 각 시리즈에 대해 위/아래 막대에 값 표시
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### 아래로 막대 채우기 색상 설정
#### 개요
위/아래 막대에 사용자 정의 채우기 색상을 설정하여 시각적 구분을 강화합니다.

11. **위/아래 막대 색상 변경**:
    
    ```java
    // 차트 그룹의 각 시리즈에 대한 위쪽/아래쪽 막대 색상 변경
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // '오픈' 시리즈
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // 청록색 위쪽 막대
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // '하이' 시리즈
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // 진한 바다색의 다운 바
        }
    }
    ```

### PowerPoint 파일 저장
#### 개요
새 PowerPoint 파일에 변경 사항을 저장합니다.

12. **프레젠테이션 저장**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## 결론

축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 주식 차트를 만들고 사용자 지정했습니다. 이 과정을 통해 시각적으로 매력적인 데이터 시각화로 프레젠테이션을 향상시키고 재무 정보를 효과적으로 전달할 수 있습니다. 다른 차트 유형을 추가로 사용자 지정하거나 살펴보고 싶으시다면, 포괄적인 내용을 살펴보세요. [Aspose.Slides 문서](https://docs.aspose.com/slides/java/).

## 추가 자료 및 참고문헌
- Java용 Aspose.Slides 문서: Aspose.Slides의 다양한 기능을 사용하는 방법에 대한 자세한 가이드를 살펴보세요.
- PowerPoint 차트 도구 개요: Microsoft PowerPoint에서 사용할 수 있는 다양한 차트 도구를 알아봅니다.
- 데이터 시각화 모범 사례: 시각적 수단을 통해 데이터를 효과적으로 표현하는 방법을 알아보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
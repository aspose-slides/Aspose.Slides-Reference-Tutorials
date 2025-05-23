---
"date": "2025-04-17"
"description": "Aspose.Slides를 사용하여 Java로 멋진 도넛형 차트를 만드는 방법을 알아보세요. 이 종합 가이드에서는 초기화, 데이터 구성, 프레젠테이션 저장에 대한 내용을 다룹니다."
"title": "Aspose.Slides를 사용하여 Java로 도넛 차트 만들기 - 포괄적인 가이드"
"url": "/ko/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java로 도넛 차트 만들기: 단계별 가이드

## 소개

오늘날의 데이터 중심 환경에서 정보를 효과적으로 시각화하는 것은 이해도와 참여도를 높이는 데 매우 중요합니다. 특히 Java를 사용하는 경우, 전문적인 차트를 프로그래밍 방식으로 만드는 것은 어려워 보일 수 있지만, 이 가이드에서는 Java용 Aspose.Slides를 사용하여 도넛 차트를 손쉽게 만드는 방법을 안내합니다.

이러한 단계를 따르면 개발자는 프레젠테이션 슬라이드를 조작하고 데이터 시각화를 원활하게 통합하는 실무 경험을 얻을 수 있습니다.

**주요 내용:**
- Aspose.Slides Java를 사용하여 Presentation 객체를 초기화합니다.
- 차트 데이터를 구성하고 기존 시리즈나 범주를 관리합니다.
- 차트에 시리즈와 카테고리를 추가하고 사용자 정의하세요.
- 데이터 포인트를 효과적으로 포맷하고 표시합니다.
- 다양한 형식으로 프레젠테이션을 손쉽게 저장하세요.

구현에 들어가기 전에 시작하는 데 필요한 모든 것이 있는지 확인하세요.

## 필수 조건

이 튜토리얼을 따르려면 다음 사항이 필요합니다.

- **필수 라이브러리:**
  - Java 버전 25.4 이상용 Aspose.Slides.
  
- **환경 설정:**
  - 시스템에 JDK 16 이상이 설치되어 있어야 합니다.
  - IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 IDE.

- **지식 전제 조건:**
  - Java 프로그래밍 개념에 대한 기본적인 이해.
  - Maven 또는 Gradle 프로젝트에서 종속성을 관리하는 데 익숙합니다.

## Java용 Aspose.Slides 설정

Aspose.Slides를 프로젝트에 통합하려면 빌드 도구에 따라 다음 단계를 따르세요.

**Maven 설정:**
다음 종속성을 추가하세요. `pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle 설정:**
다음을 포함하세요. `build.gradle` 파일:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드:**
또는 최신 버전을 다음에서 직접 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 면허 취득

평가 제한 없이 Aspose.Slides를 사용하려면:
- **무료 체험:** 모든 기능을 탐색하려면 임시 라이선스로 시작하세요.
- **임시 면허:** 다음을 통해 하나를 얻으십시오. [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/).
- **구입:** 지속적으로 사용하려면 구매를 고려해 보세요.

다음을 사용하여 Java 애플리케이션에 라이선스를 적용하세요.
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## 구현 가이드

### 프레젠테이션 및 차트 초기화

#### 개요
프레젠테이션 객체를 초기화하고 첫 번째 슬라이드에 도넛 차트를 추가하여 시작합니다.

**1단계: 프레젠테이션 초기화**
기존 PPTX 파일을 로드하거나 새 파일을 만듭니다.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**2단계: 도넛 차트 추가**
첫 번째 슬라이드의 지정된 좌표에 차트를 만듭니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### 차트 데이터 통합 문서 구성 및 기존 시리즈/범주 지우기

#### 개요
차트 데이터 통합 문서를 구성하고 기존 시리즈나 범주를 제거합니다.

**1단계: 차트 데이터 통합 문서 액세스**
차트와 연결된 통합 문서를 검색합니다.
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**2단계: 기존 시리즈 및 카테고리 지우기**
잔여 데이터 포인트가 없는지 확인하세요.
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### 차트에 시리즈 추가

#### 개요
여러 개의 시리즈로 차트를 채우고, 각 시리즈는 모양과 동작이 사용자 지정되도록 합니다.

**1단계: 반복적으로 시리즈 추가**
인덱스를 반복하여 시리즈를 추가합니다.
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // 시리즈를 사용자 정의하세요
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### 차트에 카테고리 및 데이터 포인트 추가

#### 개요
라벨에 대한 특정 서식을 사용하여 범주를 구성하고 데이터 포인트를 추가합니다.

**1단계: 카테고리 추가**
각 카테고리에 대한 인덱스를 반복합니다.
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**2단계: 각 시리즈에 데이터 포인트 추가**
현재 카테고리에 대해 각 시리즈를 반복합니다.
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // 데이터 포인트 형식 설정
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // 마지막 시리즈에 대한 레이블 형식
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // 디스플레이 옵션 조정
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // 라벨 위치 조정
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### 프레젠테이션 저장

#### 개요
차트를 구성한 후 프레젠테이션을 지정된 디렉토리에 저장합니다.

**1단계: 프레젠테이션 저장**
사용하세요 `save` 변경 사항을 작성하는 방법:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 결론

이제 Aspose.Slides를 사용하여 Java에서 도넛 차트를 만들고 사용자 지정하는 방법을 알아보았습니다. 이 단계들은 정교한 데이터 시각화를 프레젠테이션에 통합하는 데 필요한 기반을 제공합니다.

**다음 단계:**
- Aspose.Slides에서 제공하는 다양한 차트 유형을 실험해 보세요.
- 브랜드 요구 사항에 맞게 색상, 글꼴, 스타일 등의 추가 사용자 정의 옵션을 살펴보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
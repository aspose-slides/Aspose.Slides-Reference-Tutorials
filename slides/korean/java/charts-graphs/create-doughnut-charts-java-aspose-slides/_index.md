---
date: '2026-08-16'
description: Aspose.Slides를 사용하여 Java에서 doughnut chart를 추가하는 방법을 배웁니다. 이 단계별 가이드에서는
  Maven 의존성 설정, 차트 구성, 색상, 레이블 및 PPTX 저장 방법을 다룹니다.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Aspose.Slides를 사용하여 Java에서 doughnut chart를 추가하는 방법. 이 가이드를 따라 Maven을
  설정하고 색상과 레이블을 맞춤화하며 PPTX 파일을 생성하세요.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Aspose.Slides를 사용해 Java에서 doughnut chart 추가하는 방법
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Aspose.Slides를 사용해 Java에서 doughnut chart 추가하는 방법
url: /ko/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java와 Aspose.Slides에서 도넛 차트 추가 방법

## 소개

프로그램matically **도넛 차트**를 만들면 원시 데이터를 즉시 이야기를 전달하는 눈에 띄는 시각 자료로 바꿀 수 있습니다. Java에서 **Aspose.Slides**는 이 과정을 간단하게 만들어, PowerPoint를 열지 않고도 프레젠테이션용 차트를 생성할 수 있게 합니다. 이 튜토리얼에서는 Maven Aspose Slides 의존성을 설정하고, 시리즈, 카테고리, 색상 및 레이블을 사용자 지정하고, 마지막으로 프레젠테이션을 저장하는 단계별로 **도넛 차트 추가 방법**을 배웁니다.

이 가이드를 마치면 동적인 도넛 차트를 모든 PPTX 파일에 삽입할 수 있게 되며, 보고서, 대시보드 또는 자동 슬라이드 데크에 이상적입니다.

### 빠른 답변
- **어떤 라이브러리를 사용합니까?** Aspose.Slides for Java  
- **주요 작업은?** Add a doughnut chart in a PPTX file  
- **라이브러리를 어떻게 추가합니까?** Use the Maven Aspose Slides dependency (or Gradle)  
- **최소 Java 버전은?** JDK 16 or higher  
- **색상 및 레이블을 사용자 지정할 수 있습니까?** Yes, the API provides full formatting control  

## 도넛 차트란 무엇이며 왜 사용합니까?

도넛 차트는 중앙이 비어 있는 파이 차트의 변형으로, 여러 데이터 시리즈를 동심원 형태로 표시할 수 있습니다. **여러 카테고리에서 전체 대비 부분을 시각화하면서 중앙에 추가 정보를 위한 공간을 유지합니다.** 이는 여러 분기에 걸친 지역별 매출 비교, 부서별 예산 배분, 또는 계층적 비율 데이터를 보여줘야 하는 모든 상황에 이상적입니다.

## 왜 Java용 Aspose.Slides를 사용합니까?

Microsoft Office를 설치하지 않아도 도넛 차트를 추가할 수 있으며, 라이브러리는 **50 + 입력 및 출력 형식**을 지원하고 500 슬라이드가 넘는 프레젠테이션도 처리합니다. Aspose.Slides는 동일 하드웨어에서 네이티브 Office 자동화에 비해 **최대 3배 빠른 렌더링**을 제공하며 Windows, Linux, macOS에서 작동합니다. 이러한 정량적 이점 덕분에 헤드리스 서버에서 예측 가능한 성능으로 대용량 슬라이드 데크를 생성할 수 있습니다.

## 전제 조건

- **필수 라이브러리**  
  - Aspose.Slides for Java 25.4 or later (도넛 차트를 추가할 수 있게 해주는 라이브러리).  

- **환경**  
  - JDK 16 or higher installed on your machine. → 머신에 JDK 16 이상이 설치되어 있어야 합니다.  
  - IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 IDE.  

- **지식**  
  - 기본 Java 문법 및 객체‑지향 개념.  
  - 의존성 관리를 위한 Maven 또는 Gradle에 대한 친숙함.  

## Maven Aspose Slides 의존성

`pom.xml`에 다음 Maven 의존성을 추가합니다. 이것이 **maven aspose slides dependency**이며 라이브러리를 프로젝트에 가져오는 데 필요합니다.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Gradle을 선호한다면 아래와 같은 스니펫을 사용하십시오.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

공식 릴리스 페이지에서 JAR를 직접 다운로드할 수도 있습니다:  
[ Aspose.Slides for Java 릴리스 ](https://releases.aspose.com/slides/java/)

### 라이선스 획득

평가 워터마크를 제거하고 전체 기능을 사용하려면:

- **무료 체험** – 임시 라이선스로 시작합니다.  
- **임시 라이선스** – [Aspose 웹사이트](https://purchase.aspose.com/temporary-license/)에서 요청합니다.  
- **상업용 라이선스** – 프로덕션 사용을 위해 구매합니다.

코드에 라이선스를 적용합니다:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## 구현 가이드

### 프레젠테이션 초기화 및 도넛 차트 추가

Presentation은 PowerPoint 프레젠테이션을 나타내는 Aspose.Slides 클래스입니다. 기존 PPTX를 로드하거나 새 `Presentation` 객체를 만든 뒤, 첫 번째 슬라이드에 도넛 차트를 추가합니다.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### 차트 데이터 워크북 구성 및 기존 데이터 정리

워크북은 차트 데이터를 저장하는 내부 스프레드시트입니다. 차트를 지원하는 워크북을 가져온 뒤, 기본 시리즈와 카테고리를 모두 정리하여 깨끗한 상태에서 시작합니다.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 차트에 시리즈 추가

시리즈는 차트에 플롯되는 데이터 포인트 컬렉션을 나타냅니다. 최대 15개의 시리즈를 추가할 수 있습니다. 각 시리즈는 사용자 지정이 가능하며, 여기서는 폭발 효과, 도넛‑홀 크기, 첫 슬라이스 각도를 설정합니다.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### 카테고리 및 데이터 포인트 추가

카테고리는 차트 축을 따라 각 데이터 포인트에 대한 레이블입니다. 15개의 카테고리를 만들고 각 시리즈에 데이터 포인트를 채웁니다. 마지막 시리즈에는 특수 레이블 서식을 적용합니다.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### 색상 및 데이터 레이블 사용자 지정

`FillType.Solid`은 차트 요소에 단색 채우기를 지정합니다. 각 시리즈에 단색 채우기를 설정하고 데이터 레이블을 활성화합니다. 마지막 시리즈에서는 레이블 폰트 색상도 변경합니다.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### 프레젠테이션 저장

`save`는 선택한 형식으로 프레젠테이션을 파일에 기록합니다. 업데이트된 프레젠테이션을 PPTX 형식으로 디스크에 저장하거나 필요에 따라 PDF로 내보냅니다.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## 일반적인 문제 및 해결책

- **라이선스를 찾을 수 없음** – `license.lic` 경로가 올바르고 파일을 읽을 수 있는지 확인합니다.  
- **차트가 비어 있음** – 새 시리즈/카테고리를 추가하기 전에 기존 것을 정리했는지 확인합니다.  
- **색상이 올바르지 않음** – `FillType.Solid`가 채우기와 선 형식 모두에 설정되었는지 확인합니다.  
- **다수 시리즈 시 성능** – 시리즈/카테고리 수를 제한하거나 워크북 셀을 재사용하여 메모리 사용량을 제어합니다.  

## 자주 묻는 질문

**Q: 기존 PPTX 파일 없이 도넛 차트를 생성할 수 있나요?**  
A: 예, `new Presentation()`을 인스턴스화하여 빈 슬라이드 데크에서 시작한 뒤 위와 같이 차트를 추가하면 됩니다.

**Q: Aspose.Slides가 PDF로 내보내는 것을 지원합니까?**  
A: 물론입니다. 차트를 만든 후 `pres.save("output.pdf", SaveFormat.Pdf);`를 호출하면 슬라이드의 PDF 버전을 얻을 수 있습니다.

**Q: 도넛 홀 크기를 어떻게 변경합니까?**  
A: `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`를 사용하며, `value`는 0 ~ 100 사이의 값입니다.

**Q: 마지막 시리즈가 아니라 모든 시리즈에 데이터 레이블을 추가할 수 있나요?**  
A: 예, 레이블‑포맷 블록을 `if (i == ...)` 조건 밖으로 이동하여 각 `dataPoint`에 적용하면 됩니다.

**Q: 지원되는 Java 버전은 무엇입니까?**  
A: Aspose.Slides 25.4는 JDK 16 및 그 이후 버전을 지원합니다. 이전 JDK는 Maven 의존성에 적절한 classifier가 필요합니다.

---

**마지막 업데이트:** 2026-08-16  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
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

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## 관련 튜토리얼

- [Aspose.Slides for Java를 사용하여 PowerPoint에 차트 추가: 단계별 가이드](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Aspose.Slides와 Java로 파이 차트 색상 사용자 지정 – 완전 가이드](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Aspose.Slides for Java로 PowerPoint 차트 카테고리 애니메이션 | 단계별 가이드](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
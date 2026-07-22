---
date: '2026-07-22'
description: Aspose Slides Maven Dependency를 사용하여 Java에서 스택형 컬럼 차트를 만들고, 데이터 레이블을
  추가하고, 수직 축 숫자 형식을 변경하고, 결과를 PPTX 파일로 내보내는 방법을 배웁니다.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency를 사용하면 Java에서 스택형 컬럼 차트를 만들고, 데이터 레이블을
  맞춤 설정하며, 수직 축 형식을 조정하고, PPTX로 저장할 수 있습니다 – 모두 간결하고 production‑ready 코드로 제공됩니다.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Java에서 스택형 컬럼 차트'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Java에서 스택형 컬럼 차트'
url: /ko/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: Java에서 누적 세로 막대 차트

## 소개

**Aspose.Slides for Java**의 강력한 기능을 활용하여 프레젠테이션에 인사이트 있는 데이터 시각화를 추가하세요. 이 가이드에서는 비즈니스 보고서 작성이나 프로젝트 통계 표시 등 어떤 상황에서도 전문적인 **누적 세로 막대 차트**를 **생성**하는 방법을 다룹니다. 튜토리얼을 마치면 다음을 수행할 수 있습니다:

- **Aspose Slides Maven Dependency**를 사용해 환경 설정
- 처음부터 프레젠테이션 생성
- **백분율 누적 차트**를 추가하고 모양을 맞춤 설정
- **차트 데이터 레이블**을 포맷하고 **세로 축 숫자 형식**을 변경
- 한 줄 코드로 **PPTX** 파일 저장

## 빠른 답변
- **필요한 라이브러리는?** `aspose-slides` Maven/Gradle 종속성을 추가하세요(아래 “Aspose Slides Maven Dependency” 참고).  
- **어떤 차트 유형이 누적 뷰를 제공하나요?** 백분율 누적 세로 막대 차트는 `ChartType.PercentsStackedColumn`을 사용합니다.  
- **축 숫자 형식을 어떻게 바꾸나요?** `IAxis.setNumberFormat()`을 호출하고 `setNumberFormatLinkedToSource(false)`를 설정합니다.  
- **데이터 레이블을 커스터마이즈할 수 있나요?** 네 – 각 `IChartDataPoint`를 순회하면서 사용자 정의 `ITextFrame`을 지정하면 됩니다.  
- **파일을 어떻게 저장하나요?** `presentation.save("output.pptx", SaveFormat.Pptx)`를 호출합니다.

## 누적 세로 막대 차트란?
누적 세로 막대 차트는 각 카테고리 열에 여러 데이터 시리즈를 수직으로 쌓아 표시합니다. **백분율 누적** 변형은 각 열을 100 %로 정규화하여 비율 비교를 쉽게 합니다. 이 형식은 시청자가 다양한 카테고리에서 각 구성 요소가 전체에 어떻게 기여하는지 빠르게 파악하도록 도와주어 트렌드와 상대적 크기를 즉시 명확히 보여줍니다.

## 왜 Aspose.Slides for Java를 사용하나요?
Aspose.Slides for Java는 **Microsoft Office 없이** PowerPoint 파일을 생성·편집·변환할 수 있으며, Windows, Linux, macOS에서 **50개 이상의 출력 형식**을 지원합니다. 라이브러리는 JRE 위에서 완전히 실행되어 서버‑사이드 자동화와 고처리량 보고에 적합합니다. 차트 객체, 슬라이드 레이아웃, 문서 속성 등에 대한 세밀한 제어를 제공하므로 엔터프라이즈 수준 프레젠테이션 생성에 이상적입니다.

## 사전 요구 사항
- **Java Development Kit (JDK):** 8 이상  
- **IDE:** IntelliJ IDEA, Eclipse 또는 Java 호환 편집기  
- **빌드 도구:** Maven 또는 Gradle(선택 사항이지만 권장)  
- **기본 Java 지식** – 클래스와 메서드 사용에 익숙해야 합니다  

## Aspose.Slides for Java 설정
프로젝트에 Aspose.Slides 라이브러리를 추가합니다.

### Aspose Slides Maven Dependency
`pom.xml`에 다음을 추가하세요(필요한 **aspose slides maven dependency**):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle 대안
Gradle을 선호한다면 `build.gradle`에 다음 라인을 포함합니다:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
또는 최신 JAR 파일을 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/)에서 다운로드하세요.

### 라이선스 획득
무료 체험판으로 Aspose.Slides 기능을 탐색할 수 있습니다. 평가 제한을 해제하려면 임시 또는 정식 라이선스를 구매하세요.

- **무료 체험:** 비용 없이 제한된 기능 사용.  
- **임시 라이선스:** [Aspose 사이트](https://purchase.aspose.com/temporary-license/)에서 요청.  
- **구매:** 전체 기능 이용을 위해 구매 페이지 방문.

### 기본 초기화
`Presentation`은 메모리 내 PowerPoint 파일을 나타내는 Aspose.Slides 핵심 클래스입니다. 다음 최소 코드 스니펫은 `Presentation` 객체를 생성하는 방법을 보여줍니다:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## 구현 가이드

### 프레젠테이션 생성 및 슬라이드 추가
**개요:**  
먼저 빈 프레젠테이션을 만들고 슬라이드가 존재하는지 확인합니다.

#### 단계 1: Presentation 객체 초기화
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 단계 2: 프레젠테이션 저장
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### 슬라이드에 백분율 누적 세로 막대 차트 추가
**개요:**  
첫 번째 슬라이드에 **백분율 누적 차트**를 배치합니다.

`ChartType.PercentsStackedColumn`은 백분율 누적 세로 막대 차트 유형을 지정합니다.

#### 단계 1: 슬라이드 초기화 및 접근
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### 단계 2: 슬라이드에 차트 추가
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### 차트 축 숫자 형식 커스터마이징
**개요:**  
가독성을 높이기 위해 **세로 축 형식**을 백분율로 변경합니다.

`IAxis`는 차트 축을 나타내는 인터페이스로, 형식 및 스케일 조정을 할 수 있습니다.

#### 단계 1: 차트 추가 및 접근
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### 단계 2: 사용자 정의 숫자 형식 설정
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### 차트에 시리즈 및 데이터 포인트 추가
**개요:**  
샘플 데이터 시리즈로 차트를 채웁니다.

#### 단계 1: Presentation 및 차트 초기화
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 단계 2: 데이터 시리즈 추가
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### 시리즈 채우기 색상 포맷팅
**개요:**  
각 시리즈에 구별되는 색상을 지정해 차트를 더 읽기 쉽게 만듭니다.

#### 단계 1: 차트 초기화 및 접근
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### 단계 2: 채우기 색상 설정
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### 데이터 레이블 포맷팅
**개요:**  
이제 **차트 데이터 레이블**을 포맷해 사용자 정의 텍스트를 표시합니다.

`IChartDataPoint`는 차트 시리즈 내 개별 데이터 포인트를 나타내며, `ITextFrame`은 레이블 텍스트를 보관합니다.

#### 단계 1: 차트 시리즈 및 데이터 포인트 접근
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 단계 2: 데이터 레이블 커스터마이징
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## 일반적인 문제와 해결책
- **차트가 비어 있음:** 저장하기 전에 최소 하나의 데이터 시리즈와 데이터 포인트를 추가했는지 확인하세요.  
- **축 숫자가 백분율로 표시되지 않음:** `verticalAxis.setNumberFormatLinkedToSource(false)`를 설정해야 커스텀 형식이 적용됩니다.  
- **라이선스 평가 메시지:** `Presentation` 객체를 생성하기 전에 유효한 라이선스 파일을 적용해 평가 배너를 숨기세요.

## 자주 묻는 질문

**Q: Java 11 이상에서도 이 코드를 사용할 수 있나요?**  
A: 네. 라이브러리는 JDK 8+를 지원하며, 해당 JDK 버전에 맞는 classifier(e.g., `jdk16`)를 사용하면 됩니다.

**Q: 차트를 PPTX가 아니라 이미지로 내보내려면 어떻게 하나요?**  
A: 슬라이드에 차트를 추가한 뒤 `chart.getImage().save("chart.png", ImageFormat.Png);`를 호출하면 됩니다.

**Q: 누적 세로 막대 차트에 범례를 추가할 수 있나요?**  
A: 물론 가능합니다. `chart.getChartTitle().addTextFrameForOverriding("My Chart");`를 호출하고 `chart.getLegend()`를 필요에 맞게 구성하세요.

**Q: 프레젠테이션 생성 후 데이터를 업데이트하려면?**  
A: `ChartDataWorkbook` 셀을 수정한 뒤 `chart.refresh();`를 호출하면 변경 사항이 반영됩니다.

**Q: Aspose.Slides가 Linux 서버에서 작동하나요?**  
A: 네. 순수 Java 라이브러리이므로 호환 가능한 JRE가 설치된 모든 OS에서 실행됩니다.

## 결론
이 가이드를 따라 **Aspose Slides Maven Dependency**를 활용해 Java에서 **누적 세로 막대 차트**를 만드는 전체 과정을 익혔습니다. 환경 설정부터 세밀한 시각 스타일링까지 마스터했으니, 다양한 데이터 세트, 색상, 레이블 포맷을 실험해 보고 보고서를 더욱 돋보이게 만들어 보세요.

---

**마지막 업데이트:** 2026-07-22  
**테스트 환경:** Aspose.Slides 25.4 (jdk16 classifier)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [How to create clustered column chart in Java with Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [How to Set Number Formats in Chart Data Points Using Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [How to Add and Configure Charts in Presentations Using Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
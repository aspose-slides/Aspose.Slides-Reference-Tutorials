---
date: '2026-03-20'
description: Aspose.Slides를 사용하여 Java 프레젠테이션에 차트를 추가하고 프레젠테이션 차트 파일을 빠르게 생성하는 방법을
  배워보세요.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Aspose.Slides를 사용하여 Java 프레젠테이션에 차트 추가하는 방법
url: /ko/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 프레젠테이션에 차트 추가하는 방법

## 소개

오늘날 빠르게 변화하는 비즈니스 환경에서 데이터를 효과적으로 전달하는 동적 프레젠테이션을 만드는 것은 필수적입니다. 재무 보고서, 마케팅 자료, 프로젝트 상태 업데이트 등 어떤 자료를 준비하든 슬라이드에 **차트를 추가하는 방법**을 알면 청중 참여도를 크게 높일 수 있습니다. 이 튜토리얼에서는 3D 누적 세로 막대 차트를 추가하고, 데이터를 구성하며, 최종 파일을 저장하는 과정을 Aspose.Slides for Java를 사용해 단계별로 배웁니다.

### 빠른 답변
- **주요 라이브러리는 무엇인가요?** Aspose.Slides for Java  
- **시연된 차트 유형은?** 3D Stacked Column  
- **프레젠테이션 차트 파일을 프로그래밍 방식으로 생성할 수 있나요?** 예, 아래에 표시된 API 메서드를 사용합니다  
- **추천 Java 버전은?** JDK 16 이상  
- **프로덕션에 라이선스가 필요합니까?** 상업적 사용을 위해서는 유효한 Aspose.Slides 라이선스가 필요합니다  

## Aspose.Slides에서 “차트 추가 방법”이란?

Aspose.Slides for Java는 Microsoft Office 없이 PowerPoint 파일을 생성, 편집 및 내보낼 수 있는 풍부한 객체 세트를 제공합니다. 차트를 추가하는 것은 `Presentation` 객체를 생성하고, 차트 모양을 삽입한 뒤, 내장 워크북을 통해 데이터를 공급하는 것만큼 간단합니다.

## 왜 Java 프레젠테이션에 차트를 추가하나요?

- **시각적 효과:** 차트는 원시 데이터를 즉시 이해 가능한 시각 자료로 변환합니다.  
- **자동화:** 실시간으로 보고서를 생성합니다—정기 이메일 요약이나 대시보드에 이상적입니다.  
- **일관성:** 모든 생성된 프레젠테이션에 동일한 스타일과 브랜딩을 적용합니다.  
- **이식성:** 단일 메서드 호출로 PPTX, PDF 또는 이미지로 내보낼 수 있습니다.  

## 전제 조건

- **라이브러리 및 종속성:** Aspose.Slides for Java가 설치되어 있어야 합니다.  
- **환경 설정:** Java 환경에서 작업합니다 (JDK 16 이상 권장).  
- **지식 기반:** 기본 Java 프로그래밍 개념에 익숙하면 도움이 됩니다.  

## Aspose.Slides for Java 설정

### 설치

프로젝트에 Aspose.Slides를 통합하려면 아래 옵션 중 하나를 따르세요.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**: Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### 라이선스 획득
- **무료 체험:** 기능을 살펴보기 위해 무료 체험을 시작합니다.  
- **임시 라이선스:** 장기 테스트를 위해 임시 라이선스를 획득합니다.  
- **구매:** 상업적 사용을 위한 전체 라이선스를 획득합니다.

설치가 완료되면 `Presentation` 클래스를 인스턴스화할 수 있으며, 이는 모든 차트 관련 작업의 진입점 역할을 합니다.

## 구현 가이드

### 3D 누적 세로 막대 차트를 사용하여 프레젠테이션에 차트를 추가하는 방법

#### 개요
Aspose.Slides를 사용하면 처음부터 프레젠테이션을 만드는 것이 간단합니다. 이 섹션에서는 프레젠테이션의 첫 번째 슬라이드에 3D 누적 세로 막대 차트를 추가합니다.

**단계:**

1. **Presentation 객체 초기화**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **매개변수 설명**  
   - `ChartType.StackedColumn3D`: 차트 유형을 지정합니다.  
   - 위치 및 크기 `(0, 0, 500, 500)`: 차트가 슬라이드에 표시되는 위치를 결정합니다.

### 차트 데이터 구성

#### 개요
차트를 의미 있게 만들려면 데이터 시리즈와 카테고리를 구성해야 합니다. 이 섹션에서는 차트에 특정 데이터 포인트를 추가하는 방법을 보여줍니다.

**단계:**

1. **차트 데이터 워크북에 접근**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### 차트에 대한 Rotation3D 속성 설정

#### 개요
3D 회전 속성을 사용하여 차트의 시각적 매력을 강화합니다. 이 맞춤 설정을 통해 시점과 깊이를 조정할 수 있습니다.

**단계:**

1. **3D 회전 구성**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **매개변수 설명**  
   - `setRightAngleAxes(true)`: 축이 직각이 되도록 보장합니다.  
   - 회전 값: 3D 뷰의 각도와 깊이를 조정합니다.

### 차트에 시리즈 데이터 채우기

#### 개요
차트에 데이터 포인트를 채우는 것은 분석에 필수적입니다. 여기서는 차트 내 시리즈에 특정 값을 추가합니다.

**단계:**

1. **데이터 포인트 추가**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### 차트에서 시리즈 겹침 조정

#### 개요
차트의 외관을 미세 조정하면 가독성을 높일 수 있습니다. 이 섹션에서는 데이터 시각화를 개선하기 위해 겹침 속성을 조정하는 방법을 다룹니다.

**단계:**

1. **시리즈 겹침 설정**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### 프레젠테이션 저장

#### 개요
프레젠테이션 구성이 완료되면 원하는 형식으로 디스크에 저장합니다. 이 단계는 모든 변경 사항이 보존되도록 합니다.

**단계:**

1. **프레젠테이션 저장**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결책 |
|------|------|--------|
| **차트가 평면으로 보임** | 3D 회전이 설정되지 않음 | `setRotation3D`를 적절한 X/Y 값으로 호출합니다. |
| **데이터가 표시되지 않음** | 워크북 셀 연결이 안 됨 | `fact.getCell`이 올바른 행/열 인덱스를 참조하도록 확인합니다. |
| **파일이 저장되지 않음** | 경로가 잘못되었거나 권한이 없음 | `outputFilePath`가 쓰기 가능하고 폴더가 존재하는지 확인합니다. |

## 자주 묻는 질문

**Q: PPTX 외에 다른 형식으로 프레젠테이션 차트 파일을 생성할 수 있나요?**  
A: 예, Aspose.Slides는 `SaveFormat` 열거형을 통해 PDF, ODP 및 이미지 형식을 지원합니다.

**Q: 개발 단계에서 코드를 실행하려면 라이선스가 필요합니까?**  
A: 개발에는 임시 또는 평가 라이선스를 사용할 수 있지만, 프로덕션 배포에는 전체 라이선스가 필요합니다.

**Q: 같은 슬라이드에 여러 차트를 추가할 수 있나요?**  
A: 물론입니다. 다른 위치나 크기로 `slide.getShapes().addChart`를 여러 번 호출하면 됩니다.

**Q: 차트의 색상 팔레트를 어떻게 변경하나요?**  
A: `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)`을 사용하고 `SolidFillColor`를 설정합니다.

**Q: 차트를 데이터베이스와 같은 외부 데이터 소스에 연결할 수 있나요?**  
A: 예. JDBC로 데이터를 가져온 후 워크북 셀을 프로그래밍 방식으로 채워 저장하면 됩니다.

## 결론

이제 **Java 프레젠테이션에 차트를 추가하는 방법**, 데이터 구성, 3D 회전 맞춤 설정, 시리즈 겹침 조정 및 최종 파일 저장을 배웠습니다. 이 지식을 활용하면 보고서 자동화, 일관된 브랜딩 및 수동 작업 없이 데이터 기반 프레젠테이션을 제공할 수 있습니다. 범례, 축 스타일링 또는 테마 적용과 같은 보다 깊은 맞춤 설정을 위해서는 공식 문서에서 전체 기능을 확인하세요.

보다 고급 기능 및 맞춤 옵션은 [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/)을 참조하십시오.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2026-03-20  
**테스트 환경:** Aspose.Slides for Java 25.4 (JDK 16)  
**작성자:** Aspose
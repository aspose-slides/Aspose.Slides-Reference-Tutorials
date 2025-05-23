---
"date": "2025-04-17"
"description": "Aspose.Slides를 사용하여 Java에서 차트를 활용한 동적 프레젠테이션을 만들고 구성하는 방법을 알아보세요. 프레젠테이션을 효과적으로 추가, 사용자 지정 및 저장하는 방법을 익혀보세요."
"title": "Aspose.Slides for Java를 사용하여 차트가 포함된 Java 프레젠테이션 만들기"
"url": "/ko/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 차트가 있는 프레젠테이션을 만들고 구성하는 방법

## 소개

오늘날처럼 빠르게 변화하는 비즈니스 환경에서는 데이터를 효과적으로 전달하는 역동적인 프레젠테이션을 만드는 것이 필수적입니다. 재무 보고서를 작성하든 프로젝트 지표를 보여주든, 차트를 추가하면 프레젠테이션의 효과를 크게 높일 수 있습니다. 이 튜토리얼에서는 프로그래밍 방식으로 프레젠테이션을 처리하도록 설계된 강력한 라이브러리인 Aspose.Slides for Java를 사용하여 3D 누적 세로 막대형 차트가 포함된 프레젠테이션을 만들고 구성하는 방법을 안내합니다.

**배울 내용:**
- 새로운 프레젠테이션을 만드는 방법
- 슬라이드에 차트 추가 및 구성
- 차트 데이터 및 모양 사용자 지정
- 프레젠테이션을 효과적으로 저장하세요

Java로 시각적으로 매력적인 프레젠테이션을 만드는 법을 마스터할 준비가 되셨나요? 시작해 볼까요!

## 필수 조건

튜토리얼을 시작하기 전에 다음 전제 조건을 충족했는지 확인하세요.

- **라이브러리 및 종속성**: Java용 Aspose.Slides를 설치해야 합니다.
- **환경 설정**: Java 환경에서 작업합니다(JDK 16 이상 권장).
- **지식 기반**: 기본적인 Java 프로그래밍 개념에 익숙해지면 도움이 됩니다.

## Java용 Aspose.Slides 설정

### 설치

Aspose.Slides를 프로젝트에 통합하려면 다음 단계를 따르세요.

**메이븐**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드**: 또는 다음에서 최신 버전을 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 라이센스 취득
- **무료 체험**: 무료 체험판을 통해 기능을 살펴보세요.
- **임시 면허**: 장기 테스트를 위해 임시 라이센스를 얻으세요.
- **구입**: 상업적 사용을 위한 전체 라이센스를 취득하세요.

설치가 완료되면 Java 환경에서 라이브러리 인스턴스를 생성하여 라이브러리를 초기화합니다. `Presentation` 클래스입니다. 이를 통해 프레젠테이션에 차트 및 기타 요소를 추가할 수 있는 토대를 마련합니다.

## 구현 가이드

### 차트를 사용하여 프레젠테이션 만들기 및 구성

#### 개요
Aspose.Slides를 사용하면 프레젠테이션을 처음부터 간편하게 만들 수 있습니다. 이 섹션에서는 프레젠테이션의 첫 번째 슬라이드에 3D 누적 세로 막대형 차트를 추가해 보겠습니다.

**단계:**

1. **프레젠테이션 객체 초기화**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // 새로운 프레젠테이션 객체를 초기화합니다
           Presentation presentation = new Presentation();
           
           // 프레젠테이션의 첫 번째 슬라이드에 접근하세요
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // 슬라이드의 위치 (0,0)에 3D 쌓인 막대형 차트를 추가합니다.
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

2. **매개변수 설명**:
   - `ChartType.StackedColumn3D`: 차트 유형을 지정합니다.
   - 위치 및 크기 `(0, 0, 500, 500)`: 슬라이드에 차트가 나타나는 위치를 결정합니다.

### 차트 데이터 구성

#### 개요
차트에 의미를 부여하려면 데이터 계열과 범주를 구성하세요. 이 섹션에서는 차트에 특정 데이터 요소를 추가하는 방법을 보여줍니다.

**단계:**

1. **Access Chart의 데이터 통합 문서**

   ```java
   public static void configureChartData(IChart chart) {
       // 차트 데이터가 포함된 워크시트의 인덱스를 설정합니다.
       int defaultWorksheetIndex = 0;
       
       // 차트의 데이터 통합 문서에 액세스
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // 이름이 있는 두 개의 시리즈 추가
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // 세 가지 카테고리를 추가하세요
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### 차트의 Rotation3D 속성 설정

#### 개요
3D 회전 속성을 사용하여 차트의 시각적 매력을 향상시켜 보세요. 이 사용자 지정 기능을 통해 원근감과 깊이를 조절할 수 있습니다.

**단계:**

1. **3D 회전 구성**

   ```java
   public static void setRotation3D(IChart chart) {
       // 직각 축을 활성화하고 X, Y 방향 및 깊이 백분율로 회전을 구성합니다.
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **매개변수 설명**:
   - `setRightAngleAxes(true)`: 축이 수직인지 확인합니다.
   - 회전 값: 3D 보기의 각도와 깊이를 조정합니다.

### 차트에 시리즈 데이터 채우기

#### 개요
차트에 데이터 포인트를 채우는 것은 분석에 매우 중요합니다. 여기에서는 차트 내 계열에 특정 값을 추가해 보겠습니다.

**단계:**

1. **데이터 포인트 추가**

   ```java
   public static void populateSeriesData(IChart chart) {
       // 두 번째 차트 시리즈에 접속하세요
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // 지정된 값을 사용하여 막대 시리즈에 대한 데이터 포인트 추가
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
차트 모양을 미세 조정하면 가독성을 향상시킬 수 있습니다. 이 섹션에서는 더 나은 데이터 시각화를 위해 겹침 속성을 조정하는 방법을 설명합니다.

**단계:**

1. **시리즈 오버랩 설정**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // 차트에서 두 번째 시리즈를 가져와서 오버랩을 100으로 설정합니다.
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### 프레젠테이션 저장

#### 개요
프레젠테이션을 구성한 후 원하는 형식으로 디스크에 저장하세요. 이 단계를 수행하면 모든 변경 사항이 그대로 유지됩니다.

**단계:**

1. **프레젠테이션 저장**

   ```java
   public static void savePresentation(Presentation presentation) {
       // 수정된 프레젠테이션을 파일에 저장
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## 결론

이제 Aspose.Slides for Java를 사용하여 차트가 포함된 프레젠테이션을 만들고 구성하는 방법을 알아보았습니다. 이 가이드에서는 프레젠테이션 초기화, 3차원 누적 세로 막대형 차트 추가, 데이터 계열 및 범주 구성, 회전 속성 설정, 계열 데이터 채우기, 계열 겹침 조정, 최종 프레젠테이션 저장 방법을 다루었습니다.

더욱 고급 기능 및 사용자 정의 옵션은 다음을 참조하세요. [Java용 Aspose.Slides 문서](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
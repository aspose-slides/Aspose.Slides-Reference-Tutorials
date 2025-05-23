---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 원형 차트를 만들고 사용자 지정하는 방법을 알아보세요. 이 가이드에서는 설정, 구현 및 실제 적용 사례를 다룹니다."
"title": "Aspose.Slides를 사용하여 Java로 원형 차트 만들기 - 종합 가이드"
"url": "/ko/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java로 원형 차트 만들기: 종합 가이드

## 차트 및 그래프

### 소개

데이터 시각화에서 원형 차트는 데이터 세트 내 비율을 직관적으로 표현하는 방법입니다. 하지만 일부 세그먼트가 다른 세그먼트보다 훨씬 작은 복잡한 데이터 세트를 다룰 때, 기존 원형 차트는 복잡하고 해석하기 어려울 수 있습니다. 원형 차트는 작은 조각들을 별도의 차트로 분할하여 가독성을 높여 이러한 문제를 해결합니다.

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 원형 차트를 만들고 조작하는 방법을 배웁니다. 환경 설정, 차트 생성, 데이터 레이블 및 분할 위치와 같은 속성 사용자 지정, 그리고 PPTX 형식으로 프레젠테이션 저장 방법을 다룹니다. 튜토리얼을 마치면 실용적인 응용 프로그램과 성능 향상 팁을 통해 이러한 기능을 완벽하게 익힐 수 있습니다.

**배울 내용:**
- Java용 Aspose.Slides 설정
- 파이 차트 만들기
- 데이터 레이블 및 분할 구성과 같은 차트 속성 사용자 지정
- 프레젠테이션을 디스크에 저장

시작할 준비가 되셨나요? 먼저 필수 조건을 살펴보겠습니다!

## 필수 조건

원형 차트를 만들기 전에 다음 사항을 확인하세요.

### 필수 라이브러리, 버전 및 종속성:
- **Java용 Aspose.Slides**: PowerPoint 프레젠테이션을 프로그래밍 방식으로 관리하는 데 필수적입니다.

### 환경 설정 요구 사항:
- 컴퓨터에 Java Development Kit(JDK)가 설치되어 있어야 합니다. JDK 16 이상을 사용하는 것이 좋습니다.
- IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 통합 개발 환경(IDE).

### 지식 전제 조건:
- Java 프로그래밍에 대한 기본 이해
- 종속성 관리를 위한 Maven 또는 Gradle에 대한 지식

## Java용 Aspose.Slides 설정

### 설치 정보:

**메이븐:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그래들:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**직접 다운로드**: 최신 버전은 다음에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

### 라이센스 취득 단계:
- **무료 체험**: 모든 기능을 체험하려면 30일 체험판을 시작하세요.
- **임시 면허**장기 평가를 위해 임시 라이센스를 요청하세요.
- **구입**: Aspose.Slides가 귀하의 요구 사항을 충족한다면 라이선스 구매를 고려하세요.

### 기본 초기화 및 설정

프로젝트에 라이브러리를 설정한 후 인스턴스를 생성하여 초기화합니다. `Presentation` 수업:

```java
Presentation presentation = new Presentation();
```

이제 슬라이드에 다양한 차트를 추가할 수 있는 단계가 마련되었습니다. 다음으로, 원형 차트를 구현해 보겠습니다.

## 구현 가이드

### '원형 원형' 차트 만들기

#### 개요
우리는 인스턴스를 생성하는 것으로 시작할 것입니다 `Presentation` 첫 번째 슬라이드에 원형 차트를 추가하세요. 이 차트는 작은 세그먼트들을 두 번째 원형 차트로 나누어 데이터를 효과적으로 시각화하고 가독성을 높여줍니다.

#### 1단계: 프레젠테이션 클래스 인스턴스 생성
```java
// 새로운 프레젠테이션을 만드세요
ePresentation presentation = new Presentation();
```
이 코드는 차트를 추가할 프레젠테이션을 초기화합니다.

#### 2단계: 첫 번째 슬라이드에 '원형 차트' 추가
```java
// 첫 번째 슬라이드에 위치(50, 50)에 크기(500x400)의 원형 차트를 추가합니다.
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
여기서 우리는 차트의 유형을 지정합니다(`PieOfPie`)과 슬라이드에서의 위치와 치수.

#### 3단계: 시리즈 값을 표시하도록 데이터 레이블 설정
```java
// 값을 표시하도록 데이터 레이블 구성
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
이 단계에서는 파이 차트의 각 세그먼트에 해당 값이 표시되도록 하여 데이터를 빠르게 해석하는 데 도움이 됩니다.

#### 4단계: 두 번째 파이 크기 구성 및 백분율로 분할
```java
// 보조 파이의 크기를 설정하세요
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// 파이를 백분율로 나누세요
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// 분할 위치 설정
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
이러한 구성을 사용하면 차트를 어떻게 나누고 작은 세그먼트를 표시하는지 사용자 정의하여 시청자의 명확성을 향상시킬 수 있습니다.

#### 5단계: PPTX 형식으로 프레젠테이션을 디스크에 저장
```java
// 출력 디렉토리 정의
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// 프레젠테이션을 저장합니다\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
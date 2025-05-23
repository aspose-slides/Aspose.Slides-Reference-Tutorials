---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 동적 분산형 차트를 만드는 방법을 알아보세요. 사용자 정의 가능한 차트 기능으로 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"title": "Aspose.Slides를 사용하여 Java로 분산형 차트 만들기 및 사용자 지정"
"url": "/ko/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides를 사용하여 Java로 분산형 차트 만들기 및 사용자 지정

Aspose.Slides와 Java를 사용하여 동적 분산형 차트를 추가하여 프레젠테이션을 더욱 풍성하게 만들어 보세요. 이 포괄적인 튜토리얼은 디렉터리 설정, 프레젠테이션 초기화, 분산형 차트 생성, 차트 데이터 관리, 시리즈 유형 및 마커 사용자 지정, 작업 저장 등의 과정을 모두 쉽게 안내합니다.

**배울 내용:**
- 프레젠테이션 파일을 저장할 디렉토리 설정
- Aspose.Slides를 사용하여 프레젠테이션 초기화 및 조작
- 슬라이드에 산점도 만들기
- 차트 시리즈에 데이터 관리 및 추가
- 차트 시리즈 유형 및 마커 사용자 지정
- 수정 사항을 적용하여 프레젠테이션 저장

먼저, 필요한 전제 조건이 충족되었는지 확인해 보겠습니다.

## 필수 조건

이 튜토리얼을 따르려면 다음 사항이 필요합니다.
- **Java용 Aspose.Slides**: 버전 25.4 이상이 필요합니다.
- **자바 개발 키트(JDK)**: JDK 8 이상이 필요합니다.
- Java 프로그래밍에 대한 기본 지식과 Maven 또는 Gradle 빌드 도구에 대한 익숙함이 필요합니다.

## Java용 Aspose.Slides 설정

코딩을 시작하기 전에 다음 방법 중 하나를 사용하여 Aspose.Slides를 프로젝트에 통합하세요.

### 메이븐
이 종속성을 다음에 포함하세요. `pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 그래들
이 줄을 추가하세요 `build.gradle` 파일:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

또는 Java용 최신 Aspose.Slides를 다운로드하세요. [Aspose 릴리스](https://releases.aspose.com/slides/java/).

#### 라이센스 취득
- **무료 체험**: 30일 무료 체험판을 통해 기능을 살펴보세요.
- **임시 면허**: 장기 테스트를 위해 임시 라이센스를 얻으세요.
- **구입**: 전체 액세스 및 지원을 받으려면 라이선스를 구매하세요.

이제 아래와 같이 필요한 가져오기를 추가하여 Java 애플리케이션에서 Aspose.Slides를 초기화합니다.

## 구현 가이드

### 디렉토리 설정
먼저, 프레젠테이션 파일을 저장할 디렉토리가 있는지 확인하세요. 이렇게 하면 파일 저장 중 오류가 발생하는 것을 방지할 수 있습니다.

#### 디렉토리가 없으면 생성하세요
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // 디렉토리를 생성하세요
    new File(dataDir).mkdirs();
}
```
이 스니펫은 지정된 디렉터리를 확인하고, 디렉터리가 없으면 디렉터리를 생성합니다. `File.exists()` 존재를 확인하고 `File.mkdirs()` 디렉토리를 생성합니다.

### 프레젠테이션 초기화

다음으로, 산점 차트를 추가할 프레젠테이션 객체를 초기화합니다.

#### 프레젠테이션 초기화
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
여기, `new Presentation()` 빈 프레젠테이션을 만듭니다. 첫 번째 슬라이드에 접근하여 직접 작업합니다.

### 차트 생성
초기화된 슬라이드에 산점도를 만드는 것은 다음 단계입니다.

#### 슬라이드에 분산형 차트 추가
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
이 코드 조각은 첫 번째 슬라이드에 부드러운 선이 있는 분산형 차트를 추가합니다. 매개변수는 차트의 위치와 크기를 정의합니다.

### 차트 데이터 관리
이제 기존 시리즈를 지우고 새 시리즈를 추가하여 차트 데이터를 관리해 보겠습니다.

#### 차트 시리즈 관리
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// 차트에 새로운 시리즈 추가
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
이 섹션에서는 기존 데이터를 지우고 산점도에 두 개의 새로운 시리즈를 추가합니다.

### 산점 시리즈에 대한 데이터 포인트 추가
데이터를 시각화하려면 산점도의 각 시리즈에 점을 추가합니다.

#### 데이터 포인트 추가
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
우리는 사용합니다 `addDataPointForScatterSeries()` 첫 번째 시리즈에 데이터 포인트를 추가합니다. 매개변수는 X와 Y 값을 정의합니다.

### 시리즈 유형 및 마커 수정
각 시리즈의 마커 유형과 스타일을 변경하여 차트의 모양을 사용자 정의합니다.

#### 시리즈 사용자 정의
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// 두 번째 시리즈 수정
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
이러한 변경 사항은 직선과 마커를 사용하도록 시리즈 유형을 조정합니다. 또한 시각적 구분을 위해 마커 크기와 기호도 설정합니다.

### 프레젠테이션 저장
마지막으로, 모든 수정 사항을 적용하여 프레젠테이션을 저장합니다.

#### 프레젠테이션 저장
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
사용 `SaveFormat.Pptx` 파일을 저장할 PowerPoint 형식을 지정합니다. 이 단계는 모든 변경 사항을 유지하는 데 매우 중요합니다.

## 실제 응용 프로그램
실제 사용 사례는 다음과 같습니다.
1. **재무 분석**: 분산형 차트를 사용하여 시간 경과에 따른 주식 추세를 표시합니다.
2. **과학 연구**: 분석을 위한 실험 데이터 포인트를 나타냅니다.
3. **프로젝트 관리**: 리소스 할당 및 진행률 측정 항목을 시각화합니다.

Aspose.Slides를 시스템에 통합하면 보고서 생성을 자동화하여 생산성과 정확성을 높일 수 있습니다.

## 성능 고려 사항
최적의 성능을 위해:
- 프레젠테이션을 저장한 후 삭제하여 메모리 사용량을 관리합니다.
- 대규모 데이터 세트의 경우 효율적인 데이터 구조를 사용하세요.
- 루프 내에서 리소스 집약적 작업을 최소화합니다.

모범 사례를 통해 복잡한 차트 조작에서도 원활한 실행이 보장됩니다.

## 결론
이 튜토리얼에서는 디렉터리 설정, Aspose.Slides 프레젠테이션 초기화, 분산형 차트 생성 및 사용자 지정, 시리즈 데이터 관리, 마커 수정, 작업 저장 방법을 알아보았습니다. Aspose.Slides의 기능을 더 자세히 알아보려면 애니메이션 및 슬라이드 전환과 같은 고급 기능을 살펴보세요.

**다음 단계**: 다양한 차트 유형을 실험하거나 이러한 기술을 더 큰 Java 프로젝트에 통합합니다.

## 자주 묻는 질문

### 마커의 색상을 어떻게 바꾸나요?
마커 색상을 변경하려면 다음을 사용하세요. `series.getMarker().getFillFormat().setFillColor(ColorObject)`, 어디 `ColorObject` 원하는 색상입니다.

### 산점 차트에 두 개 이상의 시리즈를 추가할 수 있나요?
네, 새로운 시리즈와 데이터 포인트를 추가하는 과정을 반복하여 필요한 만큼 시리즈를 추가할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
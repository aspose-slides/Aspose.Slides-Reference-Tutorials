---
date: '2026-02-06'
description: Aspose.Slides for Java를 사용하여 .NET에서 프레젠테이션 Aspose Slides를 초기화하고 클러스터형
  열 차트를 사용자 지정하는 방법을 배워보세요. 데이터 시각화를 향상시키기 위한 단계별 가이드를 따라보세요.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Aspose Slides로 프레젠테이션 초기화: .NET 차트'
url: /ko/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용한 .NET 프레젠테이션에서 차트 만들기

## 소개
이 튜토리얼에서는 **initialize presentation Aspose Slides**를 수행하고 .NET 슬라이드에 동적이고 사용자 정의 가능한 차트를 삽입하는 방법을 배웁니다. 클러스터형 컬럼 차트와 같은 시각 데이터는 청중이 트렌드를 즉시 파악하도록 도와주며, Aspose.Slides for Java는 .NET 환경을 대상으로 할 때도 완전한 프로그래밍 제어를 제공합니다. 라이브러리 설정, 새 프레젠테이션 생성, 차트 추가, 데이터 채우기, 음수 값을 색상으로 표시하는 포맷팅 트릭 등을 단계별로 안내합니다.

**배우게 될 내용**
- .NET 프로젝트에서 Aspose.Slides for Java를 설정하는 방법.  
- **initialize presentation Aspose Slides**를 수행하고 차트를 추가하는 방법.  
- **customize clustered column chart** 시리즈와 카테고리를 사용자 정의하는 방법.  
- 차트의 데이터 워크북을 관리하고 조건부 서식을 적용하는 방법.  

### 빠른 답변
- **첫 번째 단계는 무엇인가요?** `Presentation` 객체를 초기화합니다.  
- **예제에서 사용된 차트 유형은?** `ClusteredColumn`.  
- **음수 값을 다르게 포맷할 수 있나요?** 네, 조건부 채우기 색상을 사용합니다.  
- **테스트에 라이선스가 필요합니까?** 개발에는 무료 체험 라이선스로 충분합니다.  
- **필요한 Maven 아티팩트는?** `com.aspose:aspose-slides:25.4`와 `jdk16` classifier.

## “initialize presentation Aspose Slides”란 무엇인가요?
프레젠테이션을 초기화하면 저장하기 전에 조작할 수 있는 메모리 내 PPTX 파일이 생성됩니다. Aspose.Slides는 파일 형식을 추상화하여 저수준 OPC 구조를 직접 다루지 않고도 슬라이드, 도형 및 차트를 추가할 수 있게 해줍니다.

## 클러스터형 컬럼 차트를 사용자 정의해야 하는 이유
클러스터형 컬럼 차트는 카테고리별로 여러 데이터 시리즈를 비교하는 데 이상적입니다. 색상, 데이터 포인트 및 레이블을 사용자 정의하면 음수를 빨간색, 양수를 초록색으로 강조하는 등 핵심 인사이트를 부각시켜 슬라이드를 더욱 설득력 있게 만들 수 있습니다.

## 사전 요구 사항
- **Aspose.Slides for Java** ≥ 25.4  
- .NET 개발 환경 (Visual Studio, .NET 6+ 권장)  
- 기본 Java 지식 (JVM에서 실행되는 Java 코드를 작성하고 이를 .NET에서 JNI 또는 브리지 레이어를 통해 호출합니다.)  

### 필요 라이브러리 및 버전
- **Aspose.Slides for Java**: 버전 25.4 이상.

### 환경 설정 요구 사항
- .NET과 호환되는 Java 런타임 (예: AdoptOpenJDK 16).  
- 의존성 관리를 위한 Maven 또는 Gradle.

### 지식 사전 요구 사항
- .NET 환경에서 프레젠테이션을 만드는 경험.  
- Java 프로젝트 설정 (Maven/Gradle) 이해.

## Aspose.Slides for Java 설정
선호하는 빌드 도구를 사용해 프로젝트에 라이브러리를 추가합니다.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 직접 다운로드
공식 릴리스 페이지에서 최신 JAR 파일을 다운로드할 수도 있습니다: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### 라이선스 획득 단계
- **Free Trial** – 개발용 임시 라이선스 파일 생성.  
- **Purchase** – 프로덕션 배포를 위한 정식 라이선스 획득.

#### 기본 초기화 및 설정
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
`try/finally` 블록은 네이티브 리소스가 해제되도록 보장하여 메모리 누수를 방지합니다.

## 프레젠테이션 초기화 방법 (initialize presentation Aspose Slides)
아래에서는 새 프레젠테이션을 만들고 차트 삽입을 위해 준비하는 구체적인 단계들을 살펴봅니다.

### 프레젠테이션 초기화
**개요:**  
프레젠테이션 인스턴스를 생성하면 이후 모든 작업의 기반이 마련됩니다.

#### 단계 1: 필요한 패키지 가져오기
```java
import com.aspose.slides.Presentation;
```

#### 단계 2: 새 Presentation 객체 생성
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*이 코드는 사용 후 프레젠테이션 객체가 적절히 해제되어 메모리 누수를 방지합니다.*

## 클러스터형 컬럼 차트 사용자 정의 방법
프레젠테이션이 준비되었으니, 이제 클러스터형 컬럼 차트를 추가하고 맞춤 설정해 보겠습니다.

### 슬라이드에 차트 추가
**개요:**  
차트를 추가하면 슬라이드에 데이터가 살아납니다.

#### 단계 1: 필요한 패키지 가져오기
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 단계 2: 프레젠테이션 초기화 및 차트 추가
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*여기서는 지정된 좌표와 크기로 첫 번째 슬라이드에 클러스터형 컬럼 차트를 추가합니다.*

### 차트 데이터 워크북 관리
**개요:**  
차트의 데이터 워크북을 효율적으로 관리하면 시리즈와 카테고리를 원활하게 조작할 수 있습니다.

#### 단계 1: 필요한 패키지 가져오기
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 단계 2: 데이터 워크북 접근 및 초기화
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*새 시리즈와 카테고리를 추가하기 전에 워크북을 초기화하는 것이 중요합니다.*

### 차트에 시리즈 및 카테고리 추가
**개요:**  
이 단계에서는 시리즈와 카테고리를 관리하여 의미 있는 데이터 포인트를 추가하는 방법을 보여줍니다.

#### 단계 1: 시리즈 및 카테고리 추가
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*시리즈와 카테고리를 추가하면 데이터가 보다 체계적으로 표시됩니다.*

### 시리즈 데이터 채우기 및 포맷팅
**개요:**  
차트에 데이터 포인트를 채우고 외관을 포맷팅하여 가독성을 높이세요. 특히 음수 값을 다룰 때 유용합니다.

#### 단계 1: 시리즈 데이터 채우기
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*이 섹션에서는 데이터를 채우고 색상 포맷팅을 적용해 시각화를 개선하는 방법을 보여줍니다.*

## 일반적인 문제와 해결책
- **Memory leaks** – `Presentation` 객체를 항상 `try/finally` 블록으로 감싸서 해제를 보장합니다.  
- **Incorrect cell coordinates** – 행과 열은 0부터 시작한다는 점을 기억하세요; 인덱스 불일치 시 `NullPointerException`이 발생합니다.  
- **License not found** – 라이선스 파일을 애플리케이션 작업 디렉터리에 두거나 `License.setLicense("Aspose.Slides.Java.lic")` 로 경로를 명시적으로 설정합니다.

## 자주 묻는 질문

**Q: 이 방법을 .NET Core에서도 사용할 수 있나요?**  
A: 네. Aspose.Slides for Java는 모든 JVM에서 실행되며, IKVM이나 JNI와 같은 브리지를 사용해 .NET Core에서 Java 코드를 호출할 수 있습니다.

**Q: 개발에 유료 라이선스가 필요합니까?**  
A: 개발 및 테스트에는 무료 체험 라이선스로 충분합니다. 프로덕션 배포에는 구매한 라이선스가 필요합니다.

**Q: 차트를 만든 후 차트 유형을 변경하려면 어떻게 해야 하나요?**  
A: `chart.getChartData().setChartType(ChartType.Pie)` 를 호출해 다른 차트 유형으로 전환할 수 있습니다.

**Q: 프로그래밍으로 데이터 레이블을 추가할 수 있나요?**  
A: 네. `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` 를 사용해 차트에 값을 표시할 수 있습니다.

**Q: 프레젠테이션을 어떤 형식으로 저장할 수 있나요?**  
A: Aspose.Slides는 PPTX, PPT, PDF, XPS 및 PNG, JPEG 등 여러 이미지 형식을 지원합니다.

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
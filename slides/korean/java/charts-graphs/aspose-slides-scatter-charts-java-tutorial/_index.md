---
date: '2026-02-24'
description: Aspose.Slides for Java를 사용하여 산점도를 사용자 정의하는 방법을 배웁니다. 이 가이드는 프레젠테이션에서
  동적 산점도를 만들고, 스타일을 적용하며, 저장하는 과정을 단계별로 안내합니다.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Java에서 Aspose를 이용한 산점도 차트 사용자 정의
url: /ko/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java에서 Aspose 산점도 차트 사용자 지정

이 튜토리얼에서는 강력한 Aspose.Slides for Java 라이브러리를 사용하여 **customize scatter chart aspose**를 배우게 됩니다. 프로젝트 설정, 산점도 차트 생성, 시리즈 유형 및 마커 조정, 마지막으로 프레젠테이션 저장까지 단계별로 안내합니다. 끝까지 따라오면 프로페셔널한 산점도 차트를 프로그래밍으로 생성하고, 브랜드나 보고 요구에 맞게 모든 시각적 세부 사항을 맞춤 설정할 수 있습니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Slides for Java (v25.4+).  
- **지원되는 Java 버전은?** JDK 8 이상.  
- **마커 모양을 변경할 수 있나요?** 예 – `MarkerStyleType`을 사용하여 별, 원 등 선택합니다.  
- **파일을 어떻게 저장하나요?** `pres.save("output.pptx", SaveFormat.Pptx)` 호출.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.

## “customize scatter chart aspose”란 무엇인가요?
Aspose를 사용하여 산점도 차트를 사용자 지정한다는 것은 PowerPoint를 직접 열지 않고도 차트의 데이터, 외관 및 동작을 프로그래밍 방식으로 정의하는 것을 의미합니다—점 좌표부터 마커 기호까지 모든 것을 포함합니다. 이 방법은 자동화된 보고, 데이터 기반 프레젠테이션, 또는 반복 가능하고 고품질 시각화가 필요한 모든 상황에 이상적입니다.

## Aspose.Slides로 산점도 차트를 사용자 지정하는 이유
- **전체 제어** – Java 코드를 통해 시리즈 유형, 마커 스타일, 색상 등을 수정합니다.  
- **자동화** – 대시보드나 일괄 보고서를 위해 실시간으로 수십 개의 차트를 생성합니다.  
- **크로스 플랫폼** – Java를 지원하는 모든 OS에서 동작하며 Office 설치가 필요 없습니다.  
- **성능** – 대용량 데이터 세트를 효율적으로 처리하는 경량 API입니다.

## 사전 요구 사항

따라 하려면 다음이 준비되어 있어야 합니다:

- **Aspose.Slides for Java** (v25.4 이상).  
- **Java Development Kit (JDK)** 8 이상이 설치되어 있어야 합니다.  
- 의존성 관리를 위한 Maven 또는 Gradle (또는 JAR을 직접 다운로드할 수도 있습니다).  
- 기본 Java 지식과 선택한 빌드 도구에 대한 이해.

## Aspose.Slides for Java 설정

아래 방법 중 하나를 사용하여 라이브러리를 프로젝트에 통합합니다.

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

또는 최신 릴리스를 [Aspose Releases](https://releases.aspose.com/slides/java/)에서 다운로드하십시오.

#### 라이선스 획득
- **무료 체험** – 30일 평가.  
- **임시 라이선스** – 연장된 테스트 기간.  
- **정식 라이선스** – 프러덕션 사용 및 프리미엄 지원.

## Aspose로 산점도 차트 사용자 지정 단계별 가이드

### 1️⃣ 프레젠테이션 파일을 위한 폴더 준비
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*왜 중요한가:* 출력 폴더가 존재하도록 하면 나중에 PPTX를 저장할 때 `FileNotFoundException` 발생을 방지할 수 있습니다.

### 2️⃣ 새 프레젠테이션을 만들고 첫 슬라이드를 가져오기
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
새로운 `Presentation`은 깨끗한 캔버스를 제공하며, 차트를 배치할 첫 슬라이드가 됩니다.

### 3️⃣ 부드러운 선이 있는 산점도 차트 추가
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines`는 추세 시각화에 적합한 부드러운 선 산점도 차트를 생성합니다.

### 4️⃣ 기본 시리즈를 모두 지우고 사용자 정의 시리즈 추가
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
기본 시리즈를 제거하면 표시할 데이터에 대한 완전한 제어가 가능합니다.

### 5️⃣ 첫 번째 시리즈에 데이터 포인트 채우기
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries`는 X값 셀과 Y값 셀을 받아 점진적으로 산점도를 구성합니다.

### 6️⃣ 시리즈 유형 및 마커 모양 사용자 지정
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
여기서는 직선으로 전환하고, 마커를 확대하며, 시각적 명확성을 위해 별과 원 같은 구별된 기호를 선택하여 **customize scatter chart aspose**를 수행합니다.

### 7️⃣ 프레젠테이션 저장
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
`Pptx` 형식으로 저장하면 모든 차트 사용자 지정이 보존되고 파일을 공유하거나 추가 편집할 수 있습니다.

## 맞춤형 산점도 차트의 일반적인 사용 사례
- **재무 대시보드** – 주가와 거래량을 플롯합니다.  
- **과학 연구** – 오류 마커와 함께 실험 측정값을 표시합니다.  
- **프로젝트 관리** – 작업별 계획 대비 실제 노력을 비교합니다.  

## 성능 팁
- 저장 후 `Presentation` 객체(`pres.dispose()`)를 해제하여 네이티브 리소스를 해제합니다.  
- 대용량 데이터 세트의 경우 먼저 워크북을 채운 뒤 시리즈를 바인딩하여 UI 새로 고침을 반복하는 것을 방지합니다.  
- 다수의 시리즈를 추가할 때는 단일 `IChartDataWorkbook` 인스턴스를 재사용합니다.

## 자주 묻는 질문

### 마커 색상을 어떻게 변경하나요?
`series.getMarker().getFillFormat().setFillColor(Color)`를 사용합니다. 여기서 `Color`는 `java.awt.Color` 인스턴스이며 (예: `Color.RED`).

### 산점도 차트에 두 개 이상의 시리즈를 추가할 수 있나요?
물론 가능합니다. 추가 시리즈마다 `chart.getChartData().getSeries().add(...)` 호출을 반복하고 해당 데이터 포인트를 채워 넣으면 됩니다.

### 각 시리즈에 사용자 정의 범례를 설정할 수 있나요?
예. 시리즈를 만든 후 `series.getLegend().setText("Your Legend Text")`를 호출하여 기본 이름을 교체합니다.

### 차트를 PPTX가 아니라 이미지로 내보내려면?
차트를 구성한 뒤 `chart.getImage().save("chart.png", ImageFormat.Png)`를 호출합니다. 이렇게 하면 독립적인 PNG 파일을 얻을 수 있습니다.

### 산점도 포인트에 애니메이션을 추가하려면?
Aspose.Slides는 애니메이션 효과를 지원합니다. `chart.getTimeline().getMainSequence().addEffect(...)`를 사용하여 차트 또는 개별 시리즈에 입장 또는 강조 애니메이션을 추가합니다.

---

**마지막 업데이트:** 2026-02-24  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
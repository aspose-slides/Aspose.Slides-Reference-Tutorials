---
"date": "2025-04-17"
"description": "Aspose.Slides for Java를 사용하여 차트를 만들고 서식을 지정하는 방법을 알아보세요. 이 가이드에서는 설정, 차트 생성, 서식 지정 및 프레젠테이션 저장 방법을 다룹니다."
"title": "Aspose.Slides를 사용하여 Java로 차트 만들기 및 서식 지정하기 - 포괄적인 가이드"
"url": "/ko/java/charts-graphs/create-format-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java에서 Aspose.Slides를 사용하여 차트 만들기 및 서식 지정

## Aspose.Slides를 사용하여 Java에서 차트를 만들고 서식을 지정하는 방법

### 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 효과적인 소통에 필수적입니다. 비즈니스 전문가든 교육자든, 데이터 시각화 자료를 유익하면서도 미적으로 보기 좋게 만드는 것은 쉽지 않습니다. 이 튜토리얼은 **Java용 Aspose.Slides** PowerPoint 프레젠테이션에서 차트를 원활하게 만들고 서식을 지정하는 방법.

이 가이드는 환경 설정, 차트 생성, 제목, 축 서식, 눈금선, 레이블, 범례 설정 등의 속성 구성, 프레젠테이션 저장에 중점을 둡니다. 이 튜토리얼을 따라 하면 다음 작업을 수행하는 방법을 배우게 됩니다.
- Aspose.Slides for Java로 환경 설정
- Java에서 프로그래밍 방식으로 디렉토리 확인 및 생성
- Aspose.Slides를 사용하여 차트를 만들고 구성합니다.
- 차트 제목, 축, 격자선, 레이블, 범례 및 배경 서식 지정
- 서식이 지정된 차트로 프레젠테이션을 저장합니다.

코딩을 시작하기 전에 모든 것이 설정되어 있는지 확인해 보겠습니다.

### 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. **자바 개발 키트(JDK)**: 시스템에 JDK 8 이상이 설치되어 있는지 확인하세요.
2. **통합 개발 환경(IDE)**: IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java 호환 IDE를 사용하세요.
3. **Java용 Aspose.Slides**: 이 라이브러리는 튜토리얼의 핵심이 될 것입니다.

#### 필수 라이브러리 및 종속성
프로젝트에서 Aspose.Slides를 사용하려면 Maven이나 Gradle을 통해 추가하세요.

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

또는 다음에서 최신 JAR을 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

#### 환경 설정 요구 사항
- 최신 버전의 JDK를 설치하세요.
- IDE를 설정하고 선택에 따라 Maven이나 Gradle을 사용하도록 구성되었는지 확인하세요.
  
### 지식 전제 조건
Java 프로그래밍에 대한 기본적인 이해가 필요합니다. 객체 지향 원리에 대한 지식이 있으면 도움이 될 것입니다.

## Java용 Aspose.Slides 설정
Aspose.Slides를 사용하려면 프로젝트에 라이브러리를 포함하세요.
1. **종속성 추가**: 위에 표시된 대로 필요한 Maven 또는 Gradle 종속성을 포함합니다.
2. **라이센스 취득**:
   - 획득하다 [무료 체험판 라이센스](https://purchase.aspose.com/temporary-license/) 테스트 목적으로.
   - 생산용으로 사용하려면 다음에서 전체 라이센스를 구매하는 것을 고려하세요. [Aspose 공식 사이트](https://purchase.aspose.com/buy).

### 기본 초기화 및 설정
Java 애플리케이션에서 Aspose.Slides를 초기화하려면:
```java
import com.aspose.slides.Presentation;
// Presentation 객체를 초기화합니다
Presentation pres = new Presentation();
```

## 구현 가이드
이 섹션에서는 명확성을 위해 논리적인 하위 제목을 사용하여 각 기능을 단계별로 설명합니다.

### 디렉토리 설정
**개요**: 프레젠테이션에 차트를 저장하기 전에 디렉토리 구조가 제대로 되어 있는지 확인하세요.

#### 디렉토리 확인 및 생성
```java
import java.io.File;
// 대상 디렉토리 정의
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// 디렉토리가 존재하는지 확인하고, 존재하지 않으면 생성합니다.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // 재귀적으로 디렉토리 생성
}
```
**설명**: 이 스니펫은 지정된 디렉터리가 존재하는지 확인합니다. 디렉터리가 없으면 필요한 폴더를 생성합니다.

### 차트 생성 및 구성
**개요**: Aspose.Slides를 사용하여 PowerPoint에서 차트를 만들고, 모양을 사용자 지정한 다음 파일에 저장합니다.

#### 차트를 사용하여 프레젠테이션 슬라이드 만들기
```java
import com.aspose.slides.*;
// 새로운 프레젠테이션을 만드세요
Presentation pres = new Presentation();
try {
    // 첫 번째 슬라이드에 접근하세요
    ISlide slide = pres.getSlides().get_Item(0);

    // 슬라이드에 차트 추가
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
**설명**새로운 프레젠테이션을 초기화하고 특정 좌표에 마커가 있는 선형 차트를 추가합니다.

#### 차트 제목 설정
```java
// 제목을 활성화하고 서식을 지정합니다.
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
**설명**: 이 코드는 차트 제목을 설정하고 스타일을 지정합니다. 텍스트 속성을 사용자 지정하면 가독성이 향상됩니다.

#### 축 서식
##### 세로 축 서식
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// 주요 격자선 형식 지정
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// 축 속성 구성
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```
**설명**: 명확성을 위해 수직축 격자선을 사용자 지정하고 숫자 형식을 설정합니다.

##### 수평 축 서식
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// 주요 격자선 형식 지정
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// 레이블 위치 및 회전 설정
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
**설명**: 수평 축은 비슷한 형식으로 지정되었으며, 라벨 위치를 위한 추가 조정이 이루어졌습니다.

#### 범례 사용자 정의
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// 차트 영역과 겹치지 않도록 방지
chart.getLegend().setOverlay(true);
```
**설명**: 범례 속성을 설정하면 명확성이 보장되고 시각적 혼란을 피할 수 있습니다.

#### 배경 구성
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```
**설명**: 배경색은 미적인 매력을 위해 설정되어 차트의 전반적인 모습을 향상시킵니다.

### 프레젠테이션 저장
```java
// 프레젠테이션을 디스크에 저장
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // 자원 정리
}
```
**설명**: 이렇게 하면 모든 변경 사항이 저장되고 리소스가 적절하게 관리됩니다.

## 실제 응용 프로그램
1. **사업 보고서**: 서식이 지정된 차트로 자세한 보고서를 작성하여 분기별 결과를 제시합니다.
2. **교육 자료**: 데이터 기반 시각 자료를 활용하여 학생들을 위한 매력적인 프레젠테이션을 개발합니다.
3. **프로젝트 제안**: 주요 지표를 강조하는 시각적으로 매력적인 차트를 통합하여 제안을 더욱 강화합니다.
4. **마케팅 분석**: 마케팅 자료에 차트를 활용하여 추세와 캠페인 결과를 효과적으로 보여줍니다.
5. **대시보드 통합**: 대시보드에 차트를 삽입하여 실시간 데이터 시각화를 구현합니다.

## 성능 고려 사항
- **메모리 관리**: 항상 프레젠테이션 객체를 삭제하여 리소스를 신속하게 해제하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
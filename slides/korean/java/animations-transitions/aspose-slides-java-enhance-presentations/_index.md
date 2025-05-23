---
"date": "2025-04-18"
"description": "Aspose.Slides for Java를 사용하여 표와 프레임을 조작하여 프레젠테이션을 더욱 풍성하게 만드는 방법을 알아보세요. 이 가이드에서는 표 만들기, 텍스트 프레임 추가, 특정 콘텐츠 주위에 프레임 그리기를 다룹니다."
"title": "Aspose.Slides for Java를 활용한 프레젠테이션의 테이블 및 프레임 조작 마스터링"
"url": "/ko/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java용 Aspose.Slides를 사용하여 프레젠테이션에서 테이블 및 프레임 조작 마스터하기

## 소개

PowerPoint에서 데이터를 효과적으로 표현하는 것은 어려울 수 있습니다. 소프트웨어 개발자든 프레젠테이션 디자이너든 시각적으로 매력적인 표를 사용하고 텍스트 프레임을 추가하면 슬라이드를 더욱 매력적으로 만들 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 표 셀에 텍스트를 추가하고 '0'과 같은 특정 문자가 포함된 단락이나 부분에 프레임을 그리는 방법을 살펴봅니다. 이러한 기법을 숙달하면 프레젠테이션을 더욱 정확하고 스타일리시하게 만들 수 있습니다.

### 배울 내용:
- 슬라이드에 표를 만들고 텍스트로 채웁니다.
- 더 나은 표현을 위해 자동 모양 내에서 텍스트를 정렬합니다.
- 내용을 강조하기 위해 문단과 부분 주위에 프레임을 그립니다.
- 실제 상황에서 이러한 기능을 실용적으로 적용하는 방법.

프레젠테이션을 혁신할 준비가 되셨나요? 시작해 볼까요!

## 필수 조건

코드를 살펴보기 전에 다음 사항이 있는지 확인하세요.

### 필수 라이브러리
Java용 Aspose.Slides가 필요합니다. Maven이나 Gradle을 사용하여 포함하는 방법은 다음과 같습니다.

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

### 환경 설정
이 예제에서는 JDK 16 이상을 사용하는 것이 좋으므로 Java Development Kit(JDK)가 설치되어 있는지 확인하십시오. `jdk16` 분류기.

### 지식 전제 조건
- Java 프로그래밍에 대한 기본적인 이해.
- PowerPoint와 같은 프레젠테이션 소프트웨어에 익숙함.
- IntelliJ IDEA나 Eclipse와 같은 통합 개발 환경(IDE)을 사용한 경험이 있습니다.

## Java용 Aspose.Slides 설정

Aspose.Slides를 사용하려면 다음 단계를 따르세요.

1. **라이브러리 설치**: Maven 또는 Gradle을 사용하여 종속성을 관리하거나 직접 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

2. **라이센스 취득**:
   - 임시 라이센스를 다운로드하여 무료 평가판을 시작하세요. [임시 면허](https://purchase.aspose.com/temporary-license/).
   - 전체 액세스를 위해서는 라이선스 구매를 고려하세요. [Aspose.Slides 구매](https://purchase.aspose.com/buy).

3. **기본 초기화**:
다음 코드 조각으로 프레젠테이션 환경을 초기화하세요.
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // 여기에 코드를 입력하세요
} finally {
    if (pres != null) pres.dispose();
}
```

## 구현 가이드

이 섹션에서는 Java용 Aspose.Slides를 사용하여 구현할 수 있는 다양한 기능에 대해 설명합니다.

### 기능 1: 표 만들기 및 셀에 텍스트 추가

#### 개요
이 기능은 첫 번째 슬라이드에 표를 만들고 특정 셀에 텍스트를 채우는 방법을 보여줍니다. 

##### 단계:
**1. 테이블 만들기**
먼저, 프레젠테이션을 초기화하고 지정된 열 너비와 행 높이를 가진 표를 위치 (50, 50)에 추가합니다.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. 셀에 텍스트 추가**
텍스트의 일부를 선택하여 문단을 만들고 특정 셀에 추가합니다.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```
**3. 프레젠테이션 저장**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 기능 2: 자동 모양에 텍스트 프레임 추가 및 정렬 설정

#### 개요
자동 모양에 특정 정렬을 적용한 텍스트 프레임을 추가하는 방법을 알아보세요.

##### 단계:
**1. 자동 모양 추가**
지정된 치수로 위치 (400, 100)에 사각형을 자동 모양으로 추가합니다.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2. 텍스트 정렬 설정**
텍스트를 "모양 안의 텍스트"로 설정하고 왼쪽에 맞춥니다.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3. 프레젠테이션 저장**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 기능 3: 표 셀의 단락 및 부분 주위에 프레임 그리기

#### 개요
이 기능은 표 셀 내에서 '0'을 포함하는 문단과 부분 주위에 프레임을 그리는 데 중점을 둡니다.

##### 단계:
**1. 테이블 만들기**
초기 설정에는 "표 만들기 및 셀에 텍스트 추가"의 코드를 재사용합니다.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. 문단 추가**
이전 기능의 문단 생성 코드를 재사용합니다.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```
**3. 프레임 그리기**
문단과 부분을 반복하여 그 주위에 프레임을 그립니다.
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```
**4. 프레젠테이션 저장**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## 결론
이 가이드를 따라 하면 Aspose.Slides for Java를 사용하여 프레젠테이션을 효과적으로 개선할 수 있습니다. 표와 프레임 조작을 마스터하면 더욱 매력적이고 시각적으로 매력적인 슬라이드를 만들 수 있습니다. 더 자세히 알아보려면 Aspose.Slides의 추가 기능을 살펴보거나 다른 Java 애플리케이션과 통합해 보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
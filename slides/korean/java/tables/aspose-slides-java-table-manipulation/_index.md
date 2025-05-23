---
"date": "2025-04-18"
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 표를 만들고 조작하는 방법을 알아보세요. 동적이고 데이터가 풍부한 표를 사용하여 슬라이드를 손쉽게 꾸며보세요."
"title": "Aspose.Slides for Java를 활용한 Java 프레젠테이션의 마스터 테이블 조작"
"url": "/ko/java/tables/aspose-slides-java-table-manipulation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 활용한 Java 프레젠테이션의 마스터 테이블 조작
## Aspose.Slides for Java를 사용하여 프레젠테이션에서 테이블을 만들고 조작하는 방법
오늘날처럼 빠르게 변화하는 디지털 세상에서 역동적인 프레젠테이션을 만드는 것은 그 어느 때보다 중요합니다. Aspose.Slides for Java를 사용하면 몇 줄의 코드만으로 PowerPoint 슬라이드에서 표를 원활하게 만들고 조작할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 설정하고 프레젠테이션을 더욱 향상시켜 줄 다양한 기능을 구현하는 과정을 안내합니다.

### 소개
시각적으로 매력적이면서도 데이터가 풍부한 PowerPoint 프레젠테이션 표를 만드는 데 어려움을 겪어 보신 적이 있으신가요? Aspose.Slides for Java를 사용하면 이러한 어려움은 과거의 일이 됩니다. 이 강력한 라이브러리를 사용하면 프레젠테이션 인스턴스 생성, 슬라이드 접근, 표 크기 정의, 표 추가 및 사용자 지정, 셀 내 텍스트 설정, 텍스트 프레임 수정, 텍스트 세로 정렬, 작업 내용 저장 등 다양한 작업을 효율적으로 수행할 수 있습니다.

**배울 내용:**
- Java용 Aspose.Slides 설정
- 새로운 프레젠테이션 인스턴스 생성
- 프레젠테이션에서 슬라이드에 액세스하기
- 테이블 크기 정의 및 슬라이드에 추가
- 셀 텍스트 설정 및 텍스트 프레임 수정을 통한 테이블 사용자 지정
- 표 셀 내에서 텍스트를 세로로 정렬
- 수정된 프레젠테이션 저장
이 튜토리얼을 이해하는 데 필요한 전제 조건을 살펴보겠습니다.

### 필수 조건
구현에 들어가기 전에 다음 사항이 있는지 확인하세요.
- **라이브러리 및 종속성:** Java 버전 25.4 이상용 Aspose.Slides.
- **환경 설정:** 호환되는 JDK(예시대로라면 JDK16이 바람직함).
- **지식 전제 조건:** Java 프로그래밍에 대한 기본적인 이해와 Maven 또는 Gradle 빌드 도구 사용에 대한 익숙함이 필요합니다.

### Java용 Aspose.Slides 설정
시작하려면 프로젝트에 필요한 종속성을 추가해야 합니다. 방법은 다음과 같습니다.

#### 메이븐
다음 종속성을 추가하세요. `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### 그래들
Gradle 사용자의 경우 다음을 포함합니다. `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
또는 다음에서 최신 JAR을 다운로드할 수 있습니다. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

**라이센스 취득:** Aspose는 기능을 체험해 볼 수 있도록 무료 체험판 라이선스를 제공합니다. 임시 라이선스를 신청하거나 필요한 경우 구매할 수 있습니다.

### 기본 초기화
프로젝트를 설정한 후 초기화하세요. `Presentation` 아래와 같이 클래스가 표시됩니다.
```java
import com.aspose.slides.Presentation;
// Presentation 인스턴스를 생성합니다
Presentation presentation = new Presentation();
try {
    // 여기에 코드를 입력하세요
} finally {
    if (presentation != null) presentation.dispose();
}
```

## 구현 가이드
이제 환경이 준비되었으니 구현 과정을 자세히 살펴보겠습니다. 명확성을 위해 기능별로 나누어 설명하겠습니다.

### 프레젠테이션 인스턴스 생성
이 기능은 초기화를 보여줍니다. `Presentation` 사례:
```java
import com.aspose.slides.Presentation;
// 새로운 프레젠테이션을 초기화합니다
global slide;
presentation = new Presentation();
try {
    // 슬라이드와 모양을 조작하는 코드
} finally {
    if (presentation != null) presentation.dispose();
}
```
**목적:** 적절한 자원 관리를 보장합니다. `dispose()` 방법 `finally` 차단하다.

### 프레젠테이션에서 슬라이드 가져오기
첫 번째 슬라이드에 접근하는 것은 간단합니다.
```java
import com.aspose.slides.Presentation;
global slide;
presentation = new Presentation();
try {
    // 첫 번째 슬라이드에 접근하세요
    ISlide slide = presentation.getSlides().get_Item(0);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**설명:** `get_Item(0)` 0에서 인덱싱된 첫 번째 슬라이드를 검색합니다.

### 표 크기 정의 및 슬라이드에 표 추가
표를 추가하기 전에 열 너비와 행 높이를 정의하세요.
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120}; // 열 너비
double[] dblRows = {100, 100, 100, 100}; // 행 높이

    // 슬라이드의 위치 (x: 100, y: 50)에 표를 추가합니다.
    ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**키 구성:** 열과 행에 대한 배열을 사용하여 차원을 지정합니다.

### 표 셀에 텍스트 설정
셀 내에 텍스트를 설정하여 표를 사용자 지정하세요.
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // 특정 셀에 대한 텍스트 설정
    tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
} finally {
    if (presentation != null) presentation.dispose();
}
```
**메모:** 사용 `getTextFrame().setText()` 셀 내용을 설정합니다.

### 셀의 텍스트 프레임에 액세스하고 수정하기
텍스트 프레임에 액세스하면 더욱 세부적으로 사용자 정의할 수 있습니다.
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // 텍스트 프레임에 접근하여 콘텐츠를 수정합니다.
    ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);

portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**설명:** 다음을 사용하여 텍스트 및 색상과 같은 속성을 수정합니다. `Portion` 사물.

### 셀에서 텍스트를 세로로 정렬
텍스트를 세로로 정렬하면 가독성이 향상됩니다.
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    ISlide slide = presentation.getSlides().get_Item(0);
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};

ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);

    // 텍스트를 세로로 정렬
    ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center); // 중앙 정렬
cell.setTextVerticalType(TextVerticalType.Vertical270);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**메모:** 사용 `setTextVerticalType()` 텍스트를 수직으로 정렬합니다.

### 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 저장합니다.
```java
import com.aspose.slides.*;
global slide;
presentation = new Presentation();
try {
    // 테이블 조작을 위한 코드
    
    // 프레젠테이션을 PPTX 파일로 저장합니다.
    presentation.save("ModifiedPresentation.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```
**설명:** 그만큼 `save()` 이 방법은 지정된 형식으로 디스크에 변경 사항을 기록합니다.

### 결론
이제 Java용 Aspose.Slides 설정, PowerPoint 슬라이드 내에서 표 생성 및 조작, 셀 텍스트 사용자 지정, 텍스트 세로 정렬, 프레젠테이션 저장 방법을 알아보았습니다. 이러한 기술을 익히면 동적이고 데이터가 풍부한 표로 프레젠테이션을 더욱 풍성하게 만들 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
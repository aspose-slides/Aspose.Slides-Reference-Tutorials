---
date: '2026-06-23'
description: PowerPoint에서 표를 만들고, 표 셀에 텍스트를 추가하고, 텍스트 주위에 프레임을 그리며, Aspose.Slides
  for Java를 사용하여 프레젠테이션을 pptx 형식으로 저장하는 방법을 배웁니다.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
title: PowerPoint에서 표를 만들고 Aspose.Slides for Java로 프레임을 그리는 방법
url: /ko/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# PowerPoint에서 표를 만들고 Aspose.Slides for Java로 프레임 그리기

## 소개

프로그래밍 방식으로 **create table in PowerPoint**를 만들면 수동 서식 작업에 소요되는 시간을 크게 절감할 수 있습니다. 특히 핵심 수치를 강조하거나 설명 노트를 추가해야 할 때 유용합니다. 이 튜토리얼에서는 표 셀에 텍스트를 추가하고, 특정 단락 주위에 프레임을 그리며, 정확한 텍스트 정렬을 설정하고, 마지막으로 **save presentation as pptx**를 수행하는 방법을 강력한 Aspose.Slides for Java API와 함께 배웁니다. 튜토리얼을 마치면 깔끔하고 읽기 쉬우며 가장 중요한 데이터를 즉시 강조하는 슬라이드를 만들 수 있습니다.

## 빠른 답변
- **“add text to table”이(가) 의미하는 바는 무엇인가요?** 프로그래밍으로 개별 표 셀의 텍스트 내용을 삽입하거나 업데이트하는 것을 의미합니다.  
- **파일을 저장하는 메서드는 무엇인가요?** `pres.save("output.pptx", SaveFormat.Pptx)` – 이 **save presentation as pptx** 단계가 변경 사항을 최종 저장합니다.  
- **도형 내부의 텍스트를 어떻게 정렬하나요?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`와 같이 `TextAlignment.Left`(또는 Center/Right)를 사용합니다.  
- **단락 주위에 사각형을 그릴 수 있나요?** 예 – 단락을 순회하면서 경계 사각형을 얻고, 채우기 없이 검은 선을 가진 `IAutoShape`를 추가합니다.  
- **라이선스가 필요합니까?** 평가용 임시 라이선스로 테스트할 수 있지만, 실제 운영에서는 정식 라이선스가 필요합니다.  

## 왜 텍스트 주위에 프레임을 그리나요?

단락이나 특정 부분(예: 문자 **'0'**이 포함된 텍스트) 주위에 프레임(또는 사각형)을 그리면 청중의 시선을 즉시 해당 내용으로 끌어올 수 있습니다. 텍스트 자체를 변경하지 않고 명확한 시각적 신호를 제공하므로 핵심 수치, 경고, 또는 슬라이드 내 섹션 구분에 이상적입니다.

## 전제 조건

코드 작성을 시작하기 전에 다음 항목을 준비하십시오:

### 필수 라이브러리
Maven 또는 Gradle을 사용하여 Aspose.Slides for Java를 포함하는 방법은 다음과 같습니다:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

### 환경 설정
Java Development Kit(JDK)가 설치되어 있는지 확인하십시오. 이 예제는 `jdk16` 분류자를 사용하므로 JDK 16 이상을 권장합니다.

### 지식 전제 조건
- Java 프로그래밍에 대한 기본 이해.  
- PowerPoint와 같은 프레젠테이션 소프트웨어에 익숙함.  
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE) 사용 경험.

## Aspose.Slides for Java 설정

`Presentation`은 Aspose.Slides의 핵심 클래스이며 메모리 내에서 PowerPoint 파일을 나타내고 슬라이드, 도형 및 표에 대한 접근을 제공합니다. Aspose.Slides 사용을 시작하려면 다음 단계를 따르세요:

1. **라이브러리 설치**: Maven 또는 Gradle로 종속성을 관리하거나 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 직접 다운로드하십시오.

2. **라이선스 획득**:
   - [Temporary License](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 다운로드하여 무료 평가판을 시작하십시오.
   - 전체 기능이 필요하면 [Purchase Aspose.Slides](https://purchase.aspose.com/buy)에서 라이선스를 구매하십시오.

3. **기본 초기화**:  
   다음 코드 스니펫으로 프레젠테이션 환경을 초기화합니다:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Aspose.Slides for Java에서 표에 텍스트를 추가하는 방법은?

새 `Presentation`을 로드하고 원하는 좌표에 표를 만든 뒤, `TextFrame` 객체로 셀을 채우고 마지막으로 `pres.save("output.pptx", SaveFormat.Pptx)`를 호출합니다. 이 흐름은 **create table in PowerPoint**를 수행하고 각 셀에 사용자 정의 텍스트를 삽입한 뒤, 효율적인 단일 워크플로우로 PPTX 파일에 결과를 기록합니다.

### 기능 1: 표 만들기 및 셀에 텍스트 추가

#### 개요
이 기능은 **create table**을 만든 뒤 **add text to table** 셀에 텍스트를 삽입하고, 최종적으로 **save presentation as pptx**를 수행하는 과정을 보여줍니다.

#### 단계

**1. 표 만들기**  
먼저 프레젠테이션을 초기화하고 (50, 50) 위치에 지정된 열 너비와 행 높이로 표를 추가합니다.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 셀에 텍스트 추가**  
단락을 생성하고 텍스트 조각을 포함시킨 뒤 특정 셀에 추가합니다.  
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

### 기능 2: AutoShape에 TextFrame 추가 및 정렬 설정

#### 개요
특정 정렬이 적용된 텍스트 프레임을 AutoShape에 추가하는 방법을 배웁니다—**set text alignment java**의 예시입니다.

#### 단계

AutoShape은 텍스트와 그래픽을 담을 수 있는 도형입니다.

**1. AutoShape 추가**  
(400, 100) 위치에 지정된 크기로 사각형을 AutoShape로 추가합니다.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` 열거형은 도형 내부 텍스트의 수평 정렬 옵션을 정의합니다.

**2. 텍스트 정렬 설정**  
텍스트를 “Text in shape”으로 설정하고 왼쪽 정렬합니다.  
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
이 기능은 **draw frames around text**와 문자 ‘0’이 포함된 부분에 대해 **draw rectangle around paragraph**를 수행하는 방법에 중점을 둡니다.

#### 단계

`IAutoShape`은 슬라이드에 그릴 수 있는 도형 객체를 나타내며, 프레임용 사각형으로 사용됩니다.

**1. 표 만들기**  
“표 만들기 및 셀에 텍스트 추가”에서 사용한 코드를 재사용하여 초기 설정을 진행합니다.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 단락 추가**  
이전 기능에서 만든 단락 생성 코드를 재사용합니다.  
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
단락과 텍스트 조각을 순회하면서 프레임을 그립니다.  
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

## 일반적인 함정 및 팁

- **Null 체크** – `Presentation` 사용을 `try‑finally` 블록으로 감싸 `pres.dispose()`가 실행되어 네이티브 리소스를 해제하도록 하십시오.  
- **경계 사각형 정확도** – `para.getRect()`가 반환하는 사각형은 현재 레이아웃을 반영합니다. 글꼴 크기나 여백을 변경하면 프레임을 그리기 전에 사각형을 다시 계산하십시오.  
- **성능** – 매우 큰 표를 다룰 때는 도형 추가를 배치 처리하거나, 업데이트된 기하 정보를 사용해 단일 `IAutoShape` 인스턴스를 재사용하여 메모리 오버헤드를 줄이는 것이 좋습니다.  

## 자주 묻는 질문

**Q: 오래된 JDK 버전에서도 이 API를 사용할 수 있나요?**  
A: 라이브러리는 JDK 8 이상을 지원하지만, 최신 런타임에서는 `jdk16` 분류자가 최고의 성능을 제공합니다.

**Q: 프레임 색상을 어떻게 변경하나요?**  
A: 선 형식의 채우기 색을 수정하면 됩니다. 예: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: 최종 슬라이드를 이미지로 내보낼 수 있나요?**  
A: 예—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`를 사용한 뒤 바이트 배열을 저장하면 됩니다.

**Q: 셀 안에서 “Total”이라는 단어만 강조하려면 어떻게 해야 하나요?**  
A: `cell.getTextFrame().getParagraphs()`를 순회하면서 “Total”이 포함된 조각을 찾아 해당 조각의 경계 상자를 기준으로 사각형을 그립니다.

**Q: Aspose.Slides가 대용량 프레젠테이션을 효율적으로 처리하나요?**  
A: API는 데이터를 스트리밍하고 `pres.dispose()` 호출 시 리소스를 해제하므로 대용량 파일의 메모리 관리에 도움이 됩니다.

---

**마지막 업데이트:** 2026-06-23  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Slides for Java: PowerPoint 프레젠테이션에서 PPTX 표 및 텍스트 조작 마스터](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 텍스트 프레임 만들기](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java를 사용하여 텍스트 프레임에 열 추가](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
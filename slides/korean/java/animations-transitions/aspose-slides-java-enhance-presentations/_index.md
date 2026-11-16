---
date: '2026-11-16'
description: Aspose.Slides for Java를 사용하여 PowerPoint 표에서 텍스트 주위에 프레임을 그립니다 – 표 만들기,
  셀에 텍스트 추가, 셀 강조, 파일을 PPTX로 내보내는 방법을 배웁니다.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Aspose.Slides for Java를 사용하여 PowerPoint 표에서 텍스트 주위에 프레임을 그립니다. 이 가이드는
  표 만들기, 텍스트 추가 및 정렬, 셀 강조, 슬라이드를 PNG로 내보내는 방법을 보여줍니다.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Aspose.Slides for Java와 함께 PowerPoint에서 텍스트 주위에 프레임을 그리고 표를 만드는 방법
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
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
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Aspose.Slides for Java와 함께 PowerPoint에서 텍스트 주위에 프레임을 그리고 표를 만드는 방법
url: /ko/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 텍스트 주위에 프레임을 그리고 테이블을 만들기 (Aspose.Slides for Java)

## 소개

PowerPoint 슬라이드에 **draw frame around text**를 그리면 기본 내용을 변경하지 않고 핵심 수치를 강조할 수 있습니다. 이 튜토리얼에서는 프로그래밍 방식으로 테이블을 만들고, 셀 안에 텍스트를 삽입·정렬하며, 특정 단어나 전체 셀을 강조하고, 마지막으로 프레젠테이션을 PPTX 파일로 저장하는 방법을 배웁니다. 완료하면 청중의 시선을 정확히 원하는 위치로 끌어오는 깔끔한 슬라이드를 얻을 수 있습니다.

## 빠른 답변
- **“add text to table”**은 무엇을 의미하나요? 프로그래밍 방식으로 개별 테이블 셀의 텍스트 내용을 삽입하거나 업데이트하는 것을 의미합니다.  
- **파일을 저장하는 메서드는 무엇인가요?** `pres.save("output.pptx", SaveFormat.Pptx)` – 이 **save presentation as pptx** 단계가 변경 사항을 최종 저장합니다.  
- **쉐이프 내부의 텍스트를 어떻게 정렬하나요?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`을 통해 `TextAlignment.Left`(또는 Center/Right)를 사용합니다.  
- **단락 주위에 사각형을 그릴 수 있나요?** 예 — 단락을 반복하면서 경계 사각형을 얻고, 채우기 없이 검은 선을 가진 `IAutoShape`를 추가합니다.  
- **라이선스가 필요합니까?** 평가용으로는 임시 라이선스로 동작하지만, 실제 사용을 위해서는 정식 라이선스가 필요합니다.  

## 텍스트 주위에 프레임을 그리는 이유

텍스트 주위에 프레임을 그리면 중요한 숫자, 경고, 제목 등을 즉시 강조할 수 있습니다. 원본 서식을 그대로 유지하면서 시각적 신호를 제공하므로 재무 보고서, KPI 대시보드 또는 강조가 필요한 모든 슬라이드에 적합합니다.

## draw frame around text란 무엇인가요?

`draw frame around text`는 프로그래밍 방식으로 단락이나 텍스트 부분의 정확한 경계에 맞는 사각형 쉐이프를 추가하는 기술이며, 내부를 채우지 않고 선 서식만 사용합니다. 이 방법을 통해 텍스트 자체를 변경하지 않고도 내용을 강조할 수 있습니다.

## 사전 요구 사항

시작하기 전에 다음이 준비되어 있는지 확인하십시오:

### 필수 라이브러리
Java용 Aspose.Slides가 필요합니다. 패키지 관리자 중 하나를 사용해 포함하십시오:

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

또한 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 릴리스를 확인할 수 있습니다.

### 환경 설정
예제에서 `jdk16` 분류자를 사용하므로 Java Development Kit (JDK) 16 이상을 권장합니다. IntelliJ IDEA나 Eclipse와 같은 IDE라면 모두 사용할 수 있습니다.

### 사전 지식
- 기본 Java 프로그래밍 기술.  
- PowerPoint 개념(슬라이드, 쉐이프, 테이블)에 대한 친숙함.  
- Maven/Gradle가 종속성을 관리하는 방식에 대한 이해.

## Aspose.Slides for Java 설정

`Presentation`은 메모리 내에서 PowerPoint 파일을 나타내는 Aspose.Slides의 핵심 클래스이며 슬라이드, 쉐이프, 테이블에 접근할 수 있습니다. 최대 **10,000 슬라이드**까지 처리하면서 메모리 사용량을 **500 MB** 이하로 유지하므로 대규모 자동화에 적합합니다.

1. **라이브러리 설치** – Maven 또는 Gradle를 사용하거나 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 직접 다운로드합니다.  
2. **라이선스 획득** – [Temporary License](https://purchase.aspose.com/temporary-license/)에서 무료 체험을 시작하고, 실제 작업을 위해서는 [Purchase Aspose.Slides](https://purchase.aspose.com/buy)에서 정식 라이선스로 업그레이드합니다.  
3. **기본 초기화** – 새 `Presentation` 객체를 생성하고 필요에 따라 슬라이드를 로드하거나 생성합니다.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Aspose.Slides for Java에서 테이블에 텍스트 추가 방법

`Presentation`은 메모리 내에서 PowerPoint 파일을 나타내는 주요 클래스입니다.
새 `Presentation`을 로드하고 원하는 좌표에 테이블을 만든 뒤, `TextFrame` 객체로 셀을 채우고 마지막으로 `pres.save("output.pptx", SaveFormat.Pptx)`를 호출합니다. 이 순서는 **create table in PowerPoint**를 수행하고 각 셀에 사용자 정의 텍스트를 삽입하여 단일 효율적인 워크플로우로 PPTX 파일에 기록합니다.

### 직접 답변
`slide.getShapes().addTable(...)`을 호출해 테이블을 만든 뒤, 각 셀에 대해 `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`를 사용합니다. 모든 셀을 채운 후 `pres.save("output.pptx", SaveFormat.Pptx)`를 호출해 파일을 저장합니다. 이 방법으로 각 셀의 내용과 스타일을 프로그래밍 방식으로 제어할 수 있습니다.

#### 기능 1: 테이블 생성 및 셀에 텍스트 추가

**1. 테이블 생성** – 프레젠테이션을 초기화하고 슬라이드를 추가한 뒤, (50, 50) 위치에 지정된 열 너비와 행 높이로 테이블을 배치합니다.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 셀에 텍스트 추가** – 각 셀에 대해 `Paragraph`를 생성하고 원하는 문자열을 가진 `Portion`을 추가한 뒤, 해당 `Paragraph`를 셀의 `TextFrame`에 할당합니다.  
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

**3. 프레젠테이션 저장** – `pres.save("output.pptx", SaveFormat.Pptx)`를 호출합니다.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## PowerPoint 슬라이드에서 텍스트 주위에 프레임을 그리는 방법

`Rectangle2D`는 2차원 좌표 공간에서 사각형 영역을 나타냅니다.
슬라이드를 로드하고 강조하려는 단락이나 부분을 찾은 뒤, `getRect()`를 통해 경계 사각형을 가져오고, 채우기 없이 색상 선이 있는 `IAutoShape` 사각형을 추가합니다. 이 방법은 전체 단락과 개별 단어 부분 모두에 적용됩니다.

### 직접 답변
텍스트 주위에 프레임을 그리려면 먼저 단락의 사각형을 얻습니다(`Rectangle2D rect = paragraph.getRect();`). 그런 다음 `IAutoShape` 사각형을 생성합니다(`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`로 선 색상을 설정하고, 채우기를 비활성화합니다(`shape.getFillFormat().setFillType(FillType.NoFill)`). 이렇게 하면 쉐이프가 텍스트를 정확히 둘러싸게 됩니다.

#### 기능 3: 테이블 셀의 단락 및 부분 주위에 프레임 그리기

**1. 테이블 생성** – 기능 1의 코드를 재사용해 초기 테이블을 설정합니다.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. 단락 추가** – 기능 1의 단락 생성 코드를 재사용합니다.  
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

**3. 프레임 그리기** – 각 단락을 반복하면서 경계 사각형을 얻고 위에서 설명한 대로 사각형 쉐이프를 추가합니다. 문자 ‘0’이 포함된 부분에 대해서는 추가 프레임을 그려 해당 숫자를 강조합니다.  
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

**4. 프레젠테이션 저장** – 이전과 동일한 최종 단계입니다.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## AutoShape에 텍스트 프레임을 추가하고 정렬 설정하는 방법

`AutoShape`는 텍스트, 이미지 또는 기타 콘텐츠를 포함할 수 있는 쉐이프입니다.
`AutoShape`는 `TextFrame`을 보유할 수 있으며, `ParagraphFormat` 열거형을 사용해 수평 정렬을 제어할 수 있습니다.

### 직접 답변
사각형 AutoShape를 생성합니다(`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), 해당 `TextFrame`에 접근해 `shape.getTextFrame().setText("Text in shape")`로 텍스트를 설정한 뒤, `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`를 호출합니다. 이렇게 하면 쉐이프 내부의 텍스트가 왼쪽으로 정렬됩니다.

**1. AutoShape 추가** – 원하는 위치에 사각형을 배치합니다.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. 텍스트 정렬 설정** – 위와 같이 왼쪽 정렬을 적용합니다.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. 프레젠테이션 저장** – 동일한 최종 단계입니다.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## 일반적인 함정 및 팁

- **항상 dispose 호출** – `Presentation` 사용을 try‑finally 블록으로 감싸고 `pres.dispose()`를 호출해 네이티브 리소스를 해제합니다.  
- **경계 사각형 재계산** – 프레임을 그린 후 글꼴 크기, 여백 또는 셀 패딩을 변경하면 쉐이프를 추가하기 전에 `paragraph.getRect()`를 다시 호출합니다.  
- **대형 테이블을 위한 배치 쉐이프 생성** – 단일 `IAutoShape` 인스턴스를 재사용하고 기하학을 업데이트하면 수백 행 테이블을 처리할 때 메모리 부담을 줄일 수 있습니다.  
- **성능 수치** – 일반적인 4코어 서버에서 Aspose.Slides는 200페이지 PPTX를 2 초 미만에 생성할 수 있으며, 1,000개의 단락에 프레임을 그리는 데는 150 ms 미만의 오버헤드만 추가됩니다.

## 자주 묻는 질문

**Q: 오래된 JDK 버전에서도 이 API를 사용할 수 있나요?**  
A: 라이브러리는 JDK 8 이상을 지원하지만, `jdk16` 분류자를 사용하면 최신 런타임에서 최고의 성능을 제공합니다.

**Q: 프레임 색상을 어떻게 변경하나요?**  
A: 선 서식의 채우기 색상을 수정하면 됩니다. 예: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: 최종 슬라이드를 이미지로 내보낼 수 있나요?**  
A: 예—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`를 사용한 뒤 바이트 배열을 저장하면 됩니다.

**Q: 셀 안에서 단어 “Total”만 강조하려면 어떻게 하나요?**  
A: `cell.getTextFrame().getParagraphs()`를 반복하여 “Total”이 포함된 부분을 찾고, 해당 부분의 경계 상자 주위에 사각형을 그립니다.

**Q: Aspose.Slides는 대용량 프레젠테이션을 효율적으로 처리하나요?**  
A: API는 데이터를 스트리밍하고 `pres.dispose()` 호출 시 리소스를 해제하므로 대형 파일의 메모리 관리에 도움이 됩니다.

---

**마지막 업데이트:** 2026-11-16  
**테스트 대상:** Aspose.Slides for Java 25.4 (jdk16)  
**작성자:** Aspose  

## 관련 튜토리얼

- [Aspose.Slides for Java: PowerPoint 프레젠테이션에서 PPTX 테이블 및 텍스트 조작 마스터](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Aspose.Slides for Java를 사용하여 PowerPoint에서 동적 텍스트 프레임 만들기](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aspose.Slides for Java를 사용한 텍스트 프레임에 열 추가](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
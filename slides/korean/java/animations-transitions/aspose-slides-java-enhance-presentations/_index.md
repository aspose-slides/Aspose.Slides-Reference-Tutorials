---
date: '2026-02-09'
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 텍스트 주위에 테두리를 그리는 방법과 표 셀에 텍스트를
  추가하는 방법을 배웁니다. 이 튜토리얼에서는 표 만들기, 텍스트 정렬 설정 및 프레젠테이션을 pptx 형식으로 저장하는 내용을 다룹니다.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java를 사용하여 프레임을 그리하고 테이블에 텍스트를 추가하는 방법
url: /ko/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용하여 프레젠테이션에서 프레임을 그리고 테이블에 텍스트를 추가하는 방법

## 소개

PowerPoint에서 데이터를 강조하게 표시하는 것은 특히 **표에 텍스트를 추가**가 필요하고 요소의 중요한 값을 강조해야 할 때 중요할 수 있습니다. 이 가이드에서는 특정 주변에 ** 프레임을 따르는 방법**, 도형 내부의 방향을 선택하고 마지막으로 **프레젠테이션을 pptx로 저장**하는 방법을 Aspose.Slides for Java를 다루는 배우게 만듭니다. 방향을 바꾸면 방향을 정하고 원하는 곳으로 끌어올 수 있는 다양한 슬라이드를 만들 수 있습니다.

슬라이드를 돋보이게 할 준비가 되셨나요? 과정을 살펴보겠습니다.

## 빠른 답변
- **“표에 텍스트 추가”가 무엇을 의미하는지?** 개인 테이블 셀의 텍스트 내용을 삽입하거나 업데이트하는 것을 프로그래밍 방식으로 의미합니다.
- **파일을 저장하는 방법은 무엇입니까?** `pres.save("output.pptx", SaveFormat.Pptx)` – 이 **프레젠테이션을 pptx로 저장** 단계가 변경된 내용을 최종적으로 말합니다.
- **도형 내부의 텍스트를 어쩌고 있나요?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`를 통해 `TextAlignment.Left`(또는 Center/Right)를 사용합니다.
- **단락 주변에 커터를 그릴 수 있나요?** 예 — 단락을 순회하면서 경계를 이루고 있고, 온전히 검은 선으로 `IAutoShape`를 추가하면 됩니다.
- **라이선스가 필요합니까?** 평가용으로는 임시 능력으로 충분하지만, 실제 운영에서는 능력이 필요합니다.

## 텍스트 주위에 프레임을 그리는 이유는 무엇입니까?

단락이나 특정 부분(예: 문자 **'0'**이 포함된 텍스트) 주변에 프레임(또는 섹션)을 그리고 즉시 관심을 끌 수 있습니다. 이 규정은 다음과 같습니다:

- 표에서 중요한 부분을 강조하기.
- 슬라이드에서 중요한 메모를 강조하기.
- 추가 도형을 매뉴얼로 구성하는 인원을 생성합니다.

## 전제 조건

코드에 있기 때문에 다음 사항을 준비하시기 바랍니다:

### 필수 라이브러리
Aspose.Slides for Java가 필요합니다. Maven 또는 Gradle을 실행하는 방법은 다음과 같습니다:

**메이븐:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**그레이들:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 환경 설정
Java Development Kit(JDK)가 설치되어 있는지 확인하십시오. 가능하다면 JDK16 이상을 권장합니다. 이 예는 `jdk16`을 구분하여 사용합니다.

### 지식 전제조건
- Java 프로그래밍에 대한 기본 이해.
- PowerPoint와 같은 프레젠테이션 소프트웨어에 포인터가 있습니다.
- IntelliJ IDEA 또는 Eclipse와 동일한 통합 개발 환경(IDE) 사용 환경.

## Java용 Aspose.Slides 설정

Aspose.Slides 사용을 시작하려면 다음 단계를 따르세요:

1. **라이브러리 설치**: Maven 또는 Gradle로 종속성을 관리하거나 [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)에서 직접 다운로드하십시오.

2. **라이선스 획득**:
   - [Temporary License](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 다운로드하여 무료 체험을 시작하십시오.
   - 전체 기능을 사용하려면 [Purchase Aspose.Slides](https://purchase.aspose.com/buy)에서 라이선스를 구매하십시오.

3. **기본 초기화**:
다음 코드 스니펫으로 프레젠테이션 환경을 초기화하십시오:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Aspose.Slides for Java에서 표에 텍스트 추가하는 방법

### 기능 1: 표 생성 및 셀에 텍스트 추가

#### 개요
이 방법은 **표 생성** 후 **표에 텍스트 추가**를 실행하고 **프레젠테이션을 pptx로 저장**하는 방법을 설명합니다.

#### 단계

**1. 표 생성**
먼저 프레젠테이션을 초기화하고 (50,50) 위치에 지정된 열 너비와 행 높이로 표를 추가합니다.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. 셀에 텍스트 추가**
텍스트의 일부를 포함하는 단락을 생성하고 특정 셀에 추가합니다.
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

### 기능 2: 도형에 TextFrame 추가 및 정렬 설정

#### 개요
자동 모양을 설정하려면 **텍스트 정렬 java를 설정하세요**.

#### 단계

**1. 도형 추가**
지정된 치수를 사용하여 위치(400,100)에 도형으로 직사각형을 추가합니다.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

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

### 기능 3: 표 셀의 단락 및 텍스트 주위에 프레임 그리기

#### 개요
이 기능은 **텍스트 주위에 프레임 그리기**와 **단락 주위에 사각형 그리기**를 통해 '0' 셀의 단락 및 텍스트 주위에 프레임을 그리는 기능을 포함합니다.

#### 단계

**1. 표 생성**  
초기 설정을 위해 “표 생성 및 셀에 텍스트 추가” 코드를 재사용합니다.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. 단락 추가**  
이전 기능에서 사용한 단락 생성 코드를 재사용합니다.
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
단락과 부분을 순회하면서 각각에 프레임을 그립니다.
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

- **Null 검사** – `Presentation` 사용을 활성화하기 위해 try‑finally 블록으로 감싸기 `pres.dispose()`가 실행되도록 합니다.
- **경계 제자리에서** – `para.getRect()`가 반환되는 부분은 현재 독립적으로 사용됩니다; 크기를 조정하고 프레임을 변경하면 프레임을 다시 사용하기 시작해야 합니다.
- ** 프로세서** – 매우 큰 단일 테이블을 사용하고 도형 추가를 처리하거나 업데이트된 기하 정보를 포함하는 `IAutoShape`를 재사용하여 메모리 오버헤드를 줄이는 것을 고려하십시오.

## 자주 묻는 질문

**Q: 오래된 JDK 버전에서도 이 API를 사용할 수 있나요?**  
A: 라이브러리는 JDK 8 이상을 지원하지만, `jdk16` 분류자를 사용하면 최신 런타임에서 최고의 성능을 제공합니다.

**Q: 프레임 색상을 어떻게 변경하나요?**  
A: 라인 포맷의 채우기 색을 수정합니다. 예: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: 최종 슬라이드를 이미지로 내보낼 수 있나요?**  
A: 예—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`를 사용한 뒤 바이트 배열을 저장하면 됩니다.

**Q: 셀 안에서 단어 “Total”만 강조하려면 어떻게 해야 하나요?**  
A: `cell.getTextFrame().getParagraphs()`를 순회하여 “Total”이 포함된 부분을 찾고, 해당 부분의 경계 상자 주위에 사각형을 그립니다.

**Q: Aspose.Slides가 대용량 프레젠테이션을 효율적으로 처리하나요?**  
A: API는 데이터를 스트리밍하고 `pres.dispose()` 호출 시 리소스를 해제하므로 대용량 파일의 메모리 관리에 도움이 됩니다.

---

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

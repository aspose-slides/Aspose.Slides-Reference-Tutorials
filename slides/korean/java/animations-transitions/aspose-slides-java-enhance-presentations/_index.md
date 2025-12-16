---
date: '2025-12-10'
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 표에 텍스트를 추가하고 텍스트 주위에 프레ーム를
  그리는 방법을 배웁니다. 이 가이드는 표 만들기, 텍스트 정렬 설정 및 콘텐츠에 프레임을 적용하는 내용을 다룹니다.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java – 테이블에 텍스트 추가 및 프레임 조작
url: /ko/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java를 사용한 프레젠테이션의 표 및 프레임 조작 마스터하기

## 소개

PowerPoint에서 데이터를 효과적으로 보여주는 것은 어려울 수 있습니다. 소프트웨어 개발자이든 프레젠테이션 디자이너이든, **표에 텍스트 추가**와 핵심 문단 주위에 프레임을 그려 슬라이드를 돋보이게 만들 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용해 표에 텍스트를 추가하고 정렬하며 텍스트 주위에 프레임을 그리는 방법을 정확히 보여줍니다. 끝까지 따라오면 적절한 시점에 올바른 정보를 강조하는 깔끔한 프레젠테이션을 만들 수 있습니다.

프레젠테이션을 변신시킬 준비가 되셨나요? 시작해봅시다!

## 빠른 답변
- **“표에 텍스트 추가”는 무엇을 의미하나요?** 개별 표 셀의 텍스트 내용을 프로그래밍 방식으로 삽입하거나 업데이트하는 것을 의미합니다.  
- **파일을 저장하는 메서드는 무엇인가요?** `pres.save("output.pptx", SaveFormat.Pptx)` – 이 **프레젠테이션을 pptx로 저장** 단계가 변경 사항을 최종 적용합니다.  
- **도형 내부의 텍스트를 어떻게 정렬하나요?** `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` 로 `TextAlignment.Left`(또는 Center/Right)를 사용합니다.  
- **문단 주위에 사각형을 그릴 수 있나요?** 예 – 문단을 순회하면서 경계 사각형을 얻고, 채우기 없이 검은 선만 있는 `IAutoShape`를 추가합니다.  
- **라이선스가 필요합니까?** 평가용 임시 라이선스는 사용할 수 있지만, 실제 운영 환경에서는 정식 라이선스가 필요합니다.

## 사전 요구 사항

코드에 들어가기 전에 다음을 준비하십시오:

### 필수 라이브러리
Aspose.Slides for Java가 필요합니다. Maven 또는 Gradle을 사용해 포함하는 방법은 다음과 같습니다:

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
Java Development Kit(JDK)이 설치되어 있어야 하며, 이 예제는 `jdk16` 분류자를 사용하므로 JDK 16 이상을 권장합니다.

### 지식 사전 조건
- Java 프로그래밍에 대한 기본 이해  
- PowerPoint와 같은 프레젠테이션 소프트웨어에 대한 친숙함  
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE) 사용 경험

## Aspose.Slides for Java 설정하기

Aspose.Slides 사용을 시작하려면 다음 단계를 따르세요:

1. **라이브러리 설치**: Maven 또는 Gradle로 의존성을 관리하거나 [Aspose.Slides for Java 릴리스](https://releases.aspose.com/slides/java/)에서 직접 다운로드합니다.

2. **라이선스 획득**:
   - [임시 라이선스](https://purchase.aspose.com/temporary-license/)를 다운로드해 무료 체험을 시작합니다.
   - 전체 기능을 사용하려면 [Aspose.Slides 구매](https://purchase.aspose.com/buy) 페이지에서 라이선스를 구매하세요.

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

## 왜 표에 텍스트를 추가하고 프레임을 그릴까요?

표에 텍스트를 추가하면 구조화된 데이터를 명확히 제시할 수 있고, 문단이나 특정 부분(예: 문자 **'0'**이 포함된 부분) 주위에 프레임을 그리면 청중의 시선을 중요한 값으로 유도합니다. 이 조합은 재무 보고서, 대시보드, 혹은 핵심 숫자를 강조해야 하는 모든 슬라이드에 최적입니다.

## Aspose.Slides for Java에서 표에 텍스트를 추가하는 방법

### 기능 1: 표 만들기 및 셀에 텍스트 추가

#### 개요
이 기능은 **표 만들기**, **표에 텍스트 추가** 그리고 **프레젠테이션을 pptx로 저장**하는 과정을 보여줍니다.

#### 단계

**1. 표 만들기**  
프레젠테이션을 초기화하고 (50, 50) 위치에 지정된 열 너비와 행 높이로 표를 추가합니다.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. 셀에 텍스트 추가**  
문단을 생성하고 텍스트 조각을 추가한 뒤 특정 셀에 삽입합니다.
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
AutoShape에 특정 정렬이 적용된 텍스트 프레임을 추가하는 방법을 배웁니다—**set text alignment java** 예시입니다.

#### 단계

**1. AutoShape 추가**  
(400, 100) 위치에 지정된 크기로 사각형 AutoShape를 추가합니다.
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

### 기능 3: 표 셀의 문단 및 텍스트 조각 주위에 프레임 그리기

#### 개요
이 기능은 **텍스트 주위에 프레임 그리기**와 문자 ‘0’이 포함된 조각에 대해 **문단 주위에 사각형 그리기**를 중점적으로 다룹니다.

#### 단계

**1. 표 만들기**  
“표 만들기 및 셀에 텍스트 추가” 단계의 코드를 재사용합니다.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. 문단 추가**  
이전 기능에서 사용한 문단 생성 코드를 재사용합니다.
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
문단과 조각을 순회하면서 프레임을 그립니다.
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
이 가이드를 따르면 **표에 텍스트 추가**, 도형 내부 텍스트 정렬, 그리고 **텍스트 주위에 프레임 그리기**를 통해 중요한 정보를 강조할 수 있습니다. 이러한 기술을 마스터하면 Aspose.Slides for Java를 사용해 고품질의 데이터 기반 프레젠테이션을 만들 수 있습니다. 차후에는 차트, 애니메이션, PDF 내보내기와 결합해 보세요.

## 자주 묻는 질문

**Q: 오래된 JDK 버전에서도 이 API를 사용할 수 있나요?**  
A: 라이브러리는 JDK 8 이상을 지원하지만, `jdk16` 분류자를 사용하면 최신 런타임에서 최고의 성능을 얻을 수 있습니다.

**Q: 프레임 색상을 어떻게 변경하나요?**  
A: 선 형식의 채우기 색상을 수정하면 됩니다. 예: `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: 최종 슬라이드를 이미지로 내보낼 수 있나요?**  
A: 예—`pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`을 사용한 뒤 바이트 배열을 저장하면 됩니다.

**Q: 셀 안에서 “Total”이라는 단어만 강조하고 싶다면?**  
A: `cell.getTextFrame().getParagraphs()`를 순회하면서 “Total”이 포함된 조각을 찾고, 해당 조각의 경계 상자 주위에 사각형을 그립니다.

**Q: Aspose.Slides가 대용량 프레젠테이션을 효율적으로 처리하나요?**  
A: API는 데이터를 스트리밍하고 `pres.dispose()` 호출 시 리소스를 해제하므로 대용량 파일의 메모리 관리에 도움이 됩니다.

---

{{< blocks/products/products-backtop-button >}}

**마지막 업데이트:** 2025-12-10  
**테스트 환경:** Aspose.Slides for Java 25.4 (jdk16)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}
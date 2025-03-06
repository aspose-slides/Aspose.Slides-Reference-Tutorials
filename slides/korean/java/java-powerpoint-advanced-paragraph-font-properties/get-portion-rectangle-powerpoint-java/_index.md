---
title: Java를 사용하여 PowerPoint에서 부분 사각형 가져오기
linktitle: Java를 사용하여 PowerPoint에서 부분 사각형 가져오기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 상세한 단계별 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 PowerPoint에서 직사각형 부분을 얻는 방법을 알아보세요. Java 개발자에게 적합합니다.
weight: 12
url: /ko/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
Aspose.Slides for Java를 사용하면 Java로 동적 프레젠테이션을 만드는 것이 매우 쉽습니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 PowerPoint에서 직사각형 부분을 가져오는 핵심을 살펴보겠습니다. 환경 설정부터 코드 분석까지 단계별로 모든 것을 다룰 것입니다. 자, 시작해 봅시다!
## 전제 조건
코드를 시작하기 전에 원활하게 따라가는 데 필요한 모든 것이 있는지 확인하겠습니다.
1. JDK(Java Development Kit): 컴퓨터에 JDK 8 이상이 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): Eclipse, IntelliJ IDEA 또는 원하는 기타 Java IDE.
4. Java 기본 지식: Java 프로그래밍에 대한 이해가 필수적입니다.
## 패키지 가져오기
먼저 필요한 패키지를 가져오겠습니다. 여기에는 작업을 효율적으로 처리하기 위한 Aspose.Slides 및 기타 몇 가지가 포함됩니다.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## 1단계: 프레젠테이션 설정
첫 번째 단계는 새 프레젠테이션을 만드는 것입니다. 이것이 우리가 작업할 캔버스가 될 것입니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 테이블 생성
이제 프레젠테이션의 첫 번째 슬라이드에 표를 추가해 보겠습니다. 이 테이블에는 텍스트를 추가할 셀이 포함됩니다.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## 3단계: 셀에 단락 추가
다음으로 단락을 만들어 표의 특정 셀에 추가하겠습니다. 여기에는 기존 텍스트를 지우고 새 단락을 추가하는 작업이 포함됩니다.
```java
// 단락 만들기
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// 표 셀에 텍스트 추가
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## 4단계: 도형에 텍스트 프레임 추가
프레젠테이션을 더욱 동적으로 만들기 위해 도형에 텍스트 프레임을 추가하고 정렬을 설정하겠습니다.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## 5단계: 좌표 계산
테이블 셀의 왼쪽 상단 모서리의 좌표를 가져와야 합니다. 이렇게 하면 모양을 정확하게 배치하는 데 도움이 됩니다.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## 6단계: 단락 및 부분에 프레임 추가
 사용하여`IParagraph.getRect()` 그리고`IPortion.getRect()`메서드를 사용하면 단락과 부분에 프레임을 추가할 수 있습니다. 여기에는 단락과 부분을 반복하고, 주위에 모양을 만들고, 모양을 사용자 정의하는 작업이 포함됩니다.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## 7단계: 도형 단락에 프레임 추가
마찬가지로 프레젠테이션의 시각적 매력을 향상시키기 위해 AutoShape의 단락에 프레임을 추가하겠습니다.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## 8단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 지정된 경로에 저장하겠습니다.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## 9단계: 정리
리소스를 확보하려면 프레젠테이션 개체를 삭제하는 것이 좋습니다.
```java
if (pres != null) pres.dispose();
```
## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint에서 직사각형 부분을 얻는 방법을 성공적으로 배웠습니다. 이 강력한 라이브러리는 프로그래밍 방식으로 역동적이고 시각적으로 매력적인 프레젠테이션을 만들 수 있는 가능성의 세계를 열어줍니다. Aspose.Slides에 대해 더 자세히 알아보고 프레젠테이션을 더욱 향상시킬 수 있는 더 많은 기능을 살펴보세요.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 조작할 수 있는 강력한 라이브러리입니다.
### 상용 프로젝트에서 Java용 Aspose.Slides를 사용할 수 있나요?
 예, Java용 Aspose.Slides는 상용 프로젝트에서 사용할 수 있습니다. 다음에서 라이센스를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 설명서는 어디에서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 Aspose 포럼에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

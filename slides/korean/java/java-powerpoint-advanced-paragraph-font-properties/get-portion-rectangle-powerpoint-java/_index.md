---
"description": "이 자세하고 단계별 튜토리얼을 통해 Aspose.Slides for Java를 사용하여 PowerPoint에서 부분 사각형을 만드는 방법을 알아보세요. Java 개발자에게 안성맞춤입니다."
"linktitle": "Java를 사용하여 PowerPoint에서 부분 사각형 가져오기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java를 사용하여 PowerPoint에서 부분 사각형 가져오기"
"url": "/ko/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 PowerPoint에서 부분 사각형 가져오기

## 소개
Aspose.Slides for Java를 사용하면 Java에서 동적 프레젠테이션을 손쉽게 만들 수 있습니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 PowerPoint에서 부분 사각형을 만드는 방법을 자세히 살펴보겠습니다. 환경 설정부터 코드 단계별 분석까지 모든 것을 다룹니다. 자, 시작해 볼까요!
## 필수 조건
코드로 들어가기 전에, 원활하게 따라갈 수 있도록 필요한 모든 것이 있는지 확인해 보겠습니다.
1. Java Development Kit(JDK): 컴퓨터에 JDK 8 이상이 설치되어 있는지 확인하세요.
2. Java용 Aspose.Slides: 최신 버전을 다운로드하세요. [여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): Eclipse, IntelliJ IDEA 또는 선택한 다른 Java IDE.
4. Java에 대한 기본 지식: Java 프로그래밍에 대한 이해가 필수적입니다.
## 패키지 가져오기
먼저 필요한 패키지를 임포트해 보겠습니다. 여기에는 Aspose.Slides를 비롯하여 작업을 효율적으로 처리하는 데 필요한 몇 가지 패키지가 포함됩니다.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## 1단계: 프레젠테이션 설정
첫 번째 단계는 새로운 프레젠테이션을 만드는 것입니다. 이 프레젠테이션이 우리가 작업할 캔버스가 될 것입니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 테이블 만들기
이제 프레젠테이션의 첫 번째 슬라이드에 표를 추가해 보겠습니다. 이 표에는 텍스트를 추가할 셀이 포함됩니다.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## 3단계: 셀에 단락 추가
다음으로, 단락을 만들어 표의 특정 셀에 추가해 보겠습니다. 기존 텍스트를 지우고 새 단락을 추가하는 과정이 포함됩니다.
```java
// 문단 만들기
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
## 4단계: 자동 모양에 텍스트 프레임 추가
프레젠테이션을 더욱 역동적으로 만들기 위해 자동 도형에 텍스트 프레임을 추가하고 정렬을 설정하겠습니다.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## 5단계: 좌표 계산
표 셀의 왼쪽 상단 모서리 좌표를 알아야 합니다. 이를 통해 도형을 정확하게 배치할 수 있습니다.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## 6단계: 문단 및 부분에 프레임 추가
를 사용하여 `IParagraph.getRect()` 그리고 `IPortion.getRect()` 메서드를 사용하여 단락과 부분에 프레임을 추가할 수 있습니다. 여기에는 단락과 부분을 반복하고, 그 주변에 모양을 만들고, 모양을 사용자 지정하는 작업이 포함됩니다.
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
## 7단계: 자동 모양 단락에 프레임 추가
마찬가지로, 자동 모양의 문단에 프레임을 추가하여 프레젠테이션의 시각적 매력을 향상시켜 보겠습니다.
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
마지막으로, 프레젠테이션을 지정된 경로에 저장합니다.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## 9단계: 정리
리소스를 확보하려면 프레젠테이션 객체를 삭제하는 것이 좋습니다.
```java
if (pres != null) pres.dispose();
```
## 결론
축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint에서 부분 사각형을 만드는 방법을 성공적으로 배우셨습니다. 이 강력한 라이브러리는 역동적이고 시각적으로 매력적인 프레젠테이션을 프로그래밍 방식으로 제작할 수 있는 무한한 가능성을 열어줍니다. Aspose.Slides를 더 자세히 살펴보고 프레젠테이션을 더욱 향상시켜 줄 다양한 기능을 살펴보세요.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 수정하고, 조작할 수 있는 강력한 라이브러리입니다.
### 상업용 프로젝트에서 Aspose.Slides for Java를 사용할 수 있나요?
네, Aspose.Slides for Java는 상업용 프로젝트에서 사용할 수 있습니다. 라이선스는 다음에서 구매하실 수 있습니다. [여기](https://purchase.aspose.com/buy).
### Aspose.Slides for Java에 대한 무료 평가판이 있나요?
네, 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 문서는 어디에서 찾을 수 있나요?
문서가 제공됩니다 [여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides에 대한 지원은 어떻게 받을 수 있나요?
Aspose 포럼에서 지원을 받을 수 있습니다. [여기](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
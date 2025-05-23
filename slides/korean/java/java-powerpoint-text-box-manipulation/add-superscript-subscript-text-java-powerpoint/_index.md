---
"description": "Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에 위 첨자 및 아래 첨자 텍스트를 추가하는 방법을 알아보세요. 슬라이드를 더욱 돋보이게 하는 데 적합합니다."
"linktitle": "Java PowerPoint에서 상위 첨자 및 하위 첨자 텍스트 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java PowerPoint에서 상위 첨자 및 하위 첨자 텍스트 추가"
"url": "/ko/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 상위 첨자 및 하위 첨자 텍스트 추가

## 소개
매력적이고 유익한 파워포인트 프레젠테이션을 만들려면 위첨자 및 아래첨자 텍스트와 같은 서식 기능을 사용해야 하는 경우가 많습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 파워포인트 프레젠테이션에 위첨자 및 아래첨자 텍스트를 삽입하는 과정을 안내합니다.
## 필수 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Java용 Aspose.Slides 라이브러리입니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA나 Eclipse와 같은 통합 개발 환경(IDE)을 Java 개발에 맞게 설정합니다.
- Java 프로그래밍과 PowerPoint 프레젠테이션에 대한 기본적인 지식이 필요합니다.

## 패키지 가져오기
먼저, Aspose.Slides for Java에서 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 설정
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2단계: 슬라이드에 액세스
```java
// 첫 번째 슬라이드를 받으세요
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3단계: 텍스트 상자 만들기
```java
// 텍스트 상자 역할을 하는 자동 도형 만들기
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## 4단계: 상위 첨자 텍스트 추가
```java
// 본문에 대한 문단을 작성하세요
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// 상위 첨자 텍스트에 대한 부분을 만듭니다.
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // 상위 첨자에 대한 이스케이프먼트 설정
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// 텍스트 상자에 상위 첨자로 주요 문단을 추가합니다.
textFrame.getParagraphs().add(mainParagraph);
```
## 5단계: 아래 첨자 텍스트 추가
```java
// 아래 첨자 텍스트에 대한 다른 문단을 만듭니다.
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// 아래 첨자 텍스트에 대한 부분을 만듭니다.
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // 아래 첨자에 대한 이스케이프먼트 설정
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// 텍스트 상자에 아래 첨자 문단을 추가합니다.
textFrame.getParagraphs().add(subscriptParagraph);
```
## 6단계: 프레젠테이션 저장
```java
// 프레젠테이션을 저장하세요
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 위첨자 및 아래첨자 텍스트를 사용하여 Java PowerPoint 프레젠테이션을 개선하는 방법을 살펴보았습니다. 이 단계를 따라 하면 시각적으로 매력적이고 유익한 슬라이드를 제작하여 콘텐츠를 효과적으로 전달할 수 있습니다.

## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 조작하고, 변환할 수 있는 강력한 라이브러리입니다.
### Java용 Aspose.Slides에 대한 추가 문서는 어디에서 찾을 수 있나요?
자세한 문서는 여기에서 찾을 수 있습니다. [여기](https://reference.aspose.com/slides/java/).
### Java용 Aspose.Slides에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
임시면허를 받을 수 있습니다 [여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java를 무료로 사용해 볼 수 있나요?
네, 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디에서 받을 수 있나요?
지원 및 토론을 위해 다음을 방문하세요. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: Java PowerPoint의 끝 단락 속성
linktitle: Java PowerPoint의 끝 단락 속성
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 프로그래밍 방식으로 Java로 PowerPoint 프레젠테이션을 만들고 사용자 정의하는 방법을 알아보세요. 원활한 통합을 위한 튜토리얼과 필수 팁을 살펴보세요.
weight: 11
url: /ko/java/java-powerpoint-text-alignment-formatting/end-paragraph-properties-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
프로그래밍 방식으로 PowerPoint 프레젠테이션을 만들고 조작하면 비즈니스 프레젠테이션부터 교육 자료에 이르기까지 다양한 영역에서 워크플로를 간소화하고 생산성을 향상시킬 수 있습니다. Aspose.Slides for Java는 개발자가 슬라이드 추가, 텍스트 삽입, 콘텐츠 서식 지정, 다양한 형식으로 프레젠테이션 내보내기 등의 작업을 자동화할 수 있는 강력한 API를 제공합니다. 이 튜토리얼은 Aspose.Slides for Java를 시작하기 위한 필수 단계를 안내하고 해당 기능을 효과적으로 활용하는 방법을 보여줍니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
- JDK(Java Development Kit): JDK 8 이상이 시스템에 설치되어 있는지 확인하세요.
-  Java 라이브러리용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요.[Java 다운로드용 Aspose.Slides](https://releases.aspose.com/slides/java/).
- 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 Java 개발용으로 구성된 다른 IDE를 사용하세요.
- 기본 Java 프로그래밍 기술: Java 구문 및 객체 지향 프로그래밍 개념에 익숙하면 도움이 됩니다.

## 패키지 가져오기
Aspose.Slides for Java에서 필요한 패키지를 가져오는 것부터 시작하세요. 이러한 패키지는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업하는 데 필요한 기능에 대한 액세스를 제공합니다.
```java
import com.aspose.slides.*;
```
## 1단계: 문서 디렉토리 설정
PowerPoint 파일이 저장될 디렉터리 경로를 정의합니다.
```java
String dataDir = "Your Document Directory/";
```
## 2단계: 프리젠테이션 개체 만들기
 인스턴스화`Presentation` PowerPoint 프레젠테이션을 나타내는 개체입니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 및 도형 추가
프레젠테이션에 새 슬라이드를 추가하고 그 위에 직사각형 모양을 삽입합니다.
```java
ISlide slide = pres.getSlides().addEmptySlide(pres.getLayoutSlides().getByType(SlideLayoutType.Blank));
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 10, 10, 200, 250);
```
## 4단계: 도형에 텍스트 추가
단락과 부분을 만들어 도형에 텍스트를 추가합니다.
```java
Paragraph para1 = new Paragraph();
para1.getPortions().add(new Portion("Sample text"));
Paragraph para2 = new Paragraph();
para2.getPortions().add(new Portion("Sample text 2"));
shape.getTextFrame().getParagraphs().add(para1);
shape.getTextFrame().getParagraphs().add(para2);
```
## 5단계: 텍스트 서식 지정
글꼴 크기와 스타일을 지정하여 도형 내의 텍스트 서식을 지정합니다.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(24);
portionFormat.setFontBold(NullableBool.True);
para1.getPortions().get_Item(0).setPortionFormat(portionFormat);
PortionFormat endParagraphPortionFormat = new PortionFormat();
endParagraphPortionFormat.setFontHeight(48);
endParagraphPortionFormat.setLatinFont(new FontData("Times New Roman"));
para2.setEndParagraphPortionFormat(endParagraphPortionFormat);
```
## 6단계: 프레젠테이션 저장
수정된 프레젠테이션을 지정된 출력 디렉터리에 저장합니다.
```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```
## 7단계: 프레젠테이션 개체 삭제
 반드시 폐기하세요.`Presentation` 자원을 해제하는 개체입니다.
```java
if (pres != null) {
    pres.dispose();
}
```

## 결론
결론적으로 Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작할 수 있는 강력한 기능을 제공합니다. 이 가이드를 따르면 이러한 기능을 Java 애플리케이션에 신속하게 통합하여 작업을 자동화하고 프레젠테이션 작성 및 수정의 효율성을 높일 수 있습니다.
## FAQ
### Java용 Aspose.Slides가 기존 PowerPoint 파일과 작동할 수 있나요?
예, 기존 PowerPoint 파일을 로드하고 Aspose.Slides for Java를 사용하여 수정할 수 있습니다.
### Aspose.Slides는 프레젠테이션을 PDF로 내보내기를 지원합니까?
예, Aspose.Slides는 PDF를 포함한 다양한 형식으로 프레젠테이션 내보내기를 지원합니다.
### Aspose.Slides는 차트와 표가 포함된 보고서를 생성하는 데 적합합니까?
물론 Aspose.Slides는 프레젠테이션의 차트, 표 및 기타 요소를 추가하고 조작할 수 있는 API를 제공합니다.
### Aspose.Slides를 사용하여 프로그래밍 방식으로 슬라이드에 애니메이션을 추가할 수 있나요?
예, Aspose.Slides API를 통해 슬라이드에 애니메이션과 전환을 추가할 수 있습니다.
### 문제가 발생하거나 질문이 있는 경우 어디서 지원을 받을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 지원 및 커뮤니티 토론을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

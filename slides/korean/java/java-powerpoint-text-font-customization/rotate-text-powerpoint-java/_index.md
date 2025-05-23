---
"description": "Aspose.Slides를 사용하여 Java로 PowerPoint에서 텍스트를 회전하는 방법을 알아보세요. 초보자부터 고급 사용자까지 누구나 쉽게 따라 할 수 있는 단계별 튜토리얼입니다."
"linktitle": "Java를 사용하여 PowerPoint에서 텍스트 회전"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java를 사용하여 PowerPoint에서 텍스트 회전"
"url": "/ko/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 PowerPoint에서 텍스트 회전

## 소개
이 튜토리얼에서는 Java와 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션의 텍스트를 프로그래밍 방식으로 회전하는 방법을 살펴보겠습니다. 텍스트 회전은 시각적으로 매력적인 프레젠테이션을 만들기 위해 슬라이드를 디자인할 때 유용한 기능입니다.
## 필수 조건
시작하기에 앞서 다음 사항이 있는지 확인하세요.
- Java 프로그래밍 언어에 대한 기본 지식.
- 시스템에 JDK가 설치되어 있습니다.
- Java용 Aspose.Slides 라이브러리입니다. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA나 Eclipse와 같은 IDE(통합 개발 환경)를 컴퓨터에 설치합니다.
## 패키지 가져오기
먼저, Java에서 PowerPoint 파일을 다루기 위해 필요한 Aspose.Slides 클래스를 가져와야 합니다.
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 1단계: 프로젝트 설정
IDE에서 새 Java 프로젝트를 만들고 Aspose.Slides JAR 파일을 프로젝트의 빌드 경로에 추가하여 시작하세요.
## 2단계: 프레젠테이션 및 슬라이드 개체 초기화
```java
// 프레젠테이션을 저장할 디렉토리 경로
String dataDir = "Your_Document_Directory/";
// Presentation 클래스의 인스턴스를 생성합니다.
Presentation presentation = new Presentation();
// 첫 번째 슬라이드를 받으세요 
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3단계: 사각형 모양 추가
```java
// 사각형 유형의 자동 도형 추가
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## 4단계: 사각형 모양에 텍스트 추가
```java
// 사각형에 TextFrame 추가
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// 텍스트 프레임에 접근하기
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## 5단계: 텍스트 콘텐츠 및 스타일 설정
```java
// 텍스트 프레임에 대한 단락 개체 만들기
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// 문단에 대한 부분 객체 생성
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## 6단계: 프레젠테이션 저장
```java
// 프레젠테이션 저장
presentation.save(dataDir + "RotateText_out.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Java와 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 텍스트를 회전하는 방법을 알아보았습니다. 이 단계를 따라 하면 슬라이드의 텍스트 방향을 동적으로 조정하여 시각적 효과를 향상시킬 수 있습니다.
## 자주 묻는 질문
### Java용 Aspose.Slides를 사용하여 PowerPoint에서 텍스트를 원하는 각도로 회전할 수 있나요?
네, 프로그래밍 방식으로 원하는 텍스트 회전 각도를 지정할 수 있습니다.
### Aspose.Slides는 글꼴 크기 및 정렬과 같은 다른 텍스트 서식 옵션을 지원합니까?
물론입니다. Aspose.Slides는 다양한 텍스트 서식 요구 사항을 처리하기 위한 포괄적인 API를 제공합니다.
### Java용 Aspose.Slides를 시작하려면 어떻게 해야 하나요?
Aspose.Slides의 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/) 그 특징을 알아보세요.
### Aspose.Slides에 대한 추가 문서와 지원은 어디에서 찾을 수 있나요?
자세한 문서는 다음을 방문하세요. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/). 또한 커뮤니티에서 지원을 받을 수도 있습니다. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### Aspose.Slides에 대한 임시 라이선스를 얻으려면 어떻게 해야 하나요?
임시면허를 취득할 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/) 제한 없이 Aspose.Slides를 평가해보세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
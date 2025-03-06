---
title: Java를 사용하여 PowerPoint에서 텍스트 회전
linktitle: Java를 사용하여 PowerPoint에서 텍스트 회전
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 PowerPoint에서 텍스트를 회전하는 방법을 알아보세요. 초보자부터 고급 사용자까지 위한 단계별 튜토리얼입니다.
weight: 10
url: /ko/java/java-powerpoint-text-font-customization/rotate-text-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Java 및 Aspose.Slides를 사용하여 프로그래밍 방식으로 PowerPoint 프레젠테이션의 텍스트를 회전하는 방법을 살펴보겠습니다. 시각적으로 매력적인 프레젠테이션을 만들기 위해 슬라이드를 디자인할 때 텍스트 회전은 유용한 기능이 될 수 있습니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- Java 프로그래밍 언어에 대한 기본 지식.
- 시스템에 JDK가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(통합 개발 환경)가 컴퓨터에 설정되어 있습니다.
## 패키지 가져오기
먼저, Java에서 PowerPoint 파일을 사용하려면 필요한 Aspose.Slides 클래스를 가져와야 합니다.
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 1단계: 프로젝트 설정
IDE에서 새 Java 프로젝트를 생성하고 Aspose.Slides JAR 파일을 프로젝트의 빌드 경로에 추가하여 시작하세요.
## 2단계: 프레젠테이션 및 슬라이드 개체 초기화
```java
// 프레젠테이션을 저장하려는 디렉터리의 경로
String dataDir = "Your_Document_Directory/";
// 프레젠테이션 클래스의 인스턴스 만들기
Presentation presentation = new Presentation();
// 첫 번째 슬라이드 가져오기
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3단계: 직사각형 모양 추가
```java
// 직사각형 유형의 도형 추가
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## 4단계: 직사각형 모양에 텍스트 추가
```java
// 직사각형에 TextFrame 추가
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
// 텍스트 프레임에 액세스하기
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setTextVerticalType(TextVerticalType.Vertical270);
```
## 5단계: 텍스트 내용 및 스타일 설정
```java
// 텍스트 프레임용 단락 개체 만들기
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// 단락에 대한 부분 개체 만들기
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
이 튜토리얼에서는 Java 및 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 텍스트를 회전하는 방법을 배웠습니다. 다음 단계를 수행하면 슬라이드의 텍스트 방향을 동적으로 조작하여 시각적 효과를 향상할 수 있습니다.
## FAQ
### Aspose.Slides for Java를 사용하여 PowerPoint에서 텍스트를 원하는 각도로 회전할 수 있나요?
예, 프로그래밍 방식으로 텍스트 회전에 대해 원하는 각도를 지정할 수 있습니다.
### Aspose.Slides는 글꼴 크기 및 정렬과 같은 다른 텍스트 서식 옵션을 지원합니까?
물론 Aspose.Slides는 다양한 텍스트 서식 요구 사항을 처리할 수 있는 포괄적인 API를 제공합니다.
### Java용 Aspose.Slides를 어떻게 시작하나요?
 Aspose.Slides의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/) 그 특징을 탐구합니다.
### Aspose.Slides에 대한 추가 문서와 지원은 어디서 찾을 수 있나요?
 자세한 문서를 보려면 다음을 방문하세요.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/) . 다음 커뮤니티에서 지원을 받을 수도 있습니다.[Aspose.슬라이드 포럼](https://forum.aspose.com/c/slides/11).
### Aspose.Slides에 대한 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시면허를 취득하실 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/)Aspose.Slides를 제한 없이 평가합니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
title: Java PowerPoint에서 사용자 정의 글머리 기호 번호 설정
linktitle: Java PowerPoint에서 사용자 정의 글머리 기호 번호 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java PowerPoint에서 사용자 정의 글머리 기호 번호를 설정하여 프로그래밍 방식으로 프레젠테이션 명확성과 구조를 향상시키는 방법을 알아보세요.
type: docs
weight: 15
url: /ko/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---
## 소개
오늘날의 디지털 시대에 역동적인 프레젠테이션을 만드는 것은 아이디어와 데이터를 효과적으로 전달하는 데 매우 중요합니다. Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작할 수 있는 강력한 도구 키트를 제공하여 프레젠테이션 작성 프로세스를 향상시키는 광범위한 기능을 제공합니다. 이 기사에서는 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에서 사용자 정의 글머리 기호 번호를 설정하는 방법을 살펴봅니다. 숙련된 개발자이든 초보자이든 이 튜토리얼은 프로세스를 단계별로 안내하여 이 기능을 효율적으로 활용할 수 있도록 해줍니다.
## 전제 조건
튜토리얼을 시작하기 전에 개발 환경에 다음과 같은 필수 구성 요소가 설정되어 있는지 확인하세요.
- JDK(Java 개발 키트)가 설치되었습니다.
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE)
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/)
- Java 프로그래밍 언어 및 객체지향 개념에 대한 기본 이해

## 패키지 가져오기
먼저 필요한 Aspose.Slides 클래스와 기타 Java 표준 라이브러리를 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프리젠테이션 개체 만들기
Aspose.Slides를 사용하여 새 PowerPoint 프레젠테이션을 만드는 것부터 시작하세요.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2단계: 텍스트가 포함된 도형 추가
슬라이드에 도형(사각형)을 삽입하고 해당 텍스트 프레임에 액세스합니다.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## 3단계: 기본 단락 제거
텍스트 프레임에서 기본 기존 단락을 제거합니다.
```java
textFrame.getParagraphs().removeAt(0);
```
## 4단계: 번호가 매겨진 글머리 기호 추가
특정 번호부터 시작하는 사용자 정의 번호가 매겨진 글머리 기호로 단락을 추가합니다.
```java
// 2부터 시작하는 글머리 기호가 있는 예제 단락
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// 3부터 시작하는 글머리 기호가 있는 예제 단락
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// 7부터 시작하는 글머리 기호가 있는 예제 단락
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## 5단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 원하는 위치에 저장합니다.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## 결론
결론적으로, Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션에서 사용자 정의 글머리 기호 번호를 설정하는 프로세스를 단순화합니다. 이 튜토리얼에 설명된 단계를 따르면 프레젠테이션의 시각적 명확성과 구조를 효율적으로 향상시킬 수 있습니다.
## FAQ
### 글머리 기호 모양을 추가로 사용자 정의할 수 있나요?
예, Aspose.Slides는 글머리 기호 유형, 크기, 색상 등을 사용자 정의할 수 있는 광범위한 옵션을 제공합니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 97-2003부터 최신 버전까지 PowerPoint 형식을 지원합니다.
### Aspose.Slides에 대한 기술 지원은 어떻게 받을 수 있나요?
 방문하다[Aspose.슬라이드 포럼](https://forum.aspose.com/c/slides/11) 기술 지원을 위해.
### 구매하기 전에 Aspose.Slides를 사용해 볼 수 있나요?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Slides는 어디서 구입할 수 있나요?
 Aspose.Slides는 다음에서 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).
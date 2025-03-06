---
title: Java를 사용하는 PowerPoint의 글꼴 속성
linktitle: Java를 사용하는 PowerPoint의 글꼴 속성
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java와 함께 Java를 사용하여 PowerPoint 프레젠테이션에서 글꼴 속성을 조작하는 방법을 알아보세요. 이 단계별 가이드를 통해 글꼴을 쉽게 사용자 정의하세요.
weight: 11
url: /ko/java/java-powerpoint-font-management/font-properties-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하는 PowerPoint의 글꼴 속성

## 소개
이 튜토리얼에서는 Java, 특히 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 글꼴 속성을 조작하는 방법을 살펴보겠습니다. 필요한 패키지를 가져오는 것부터 수정된 프리젠테이션을 저장하는 것까지 각 단계를 안내해 드립니다. 뛰어들어보자!
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Java JAR용 Aspose.Slides: 다음 위치에서 Java용 Aspose.Slides 라이브러리를 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse, NetBeans 등 원하는 Java IDE를 사용할 수 있습니다.

## 패키지 가져오기
먼저 Aspose.Slides for Java를 사용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
import java.awt.*;
```
## 1단계: 프레젠테이션 개체 인스턴스화
 다음을 생성하여 시작하세요.`Presentation` PowerPoint 파일을 나타내는 개체:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "FontProperties.pptx");
```
## 2단계: 슬라이드 및 자리표시자 액세스
이제 프레젠테이션의 슬라이드와 자리 표시자에 액세스해 보겠습니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## 3단계: 단락 및 부분에 액세스
다음으로 텍스트 프레임 내의 단락과 부분에 액세스하겠습니다.
```java
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## 4단계: 새 글꼴 정의
부분에 사용할 글꼴을 정의합니다.
```java
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## 5단계: 글꼴 속성 설정
굵게, 기울임꼴, 색상 등 다양한 글꼴 속성을 설정합니다.
```java
port1.getPortionFormat().setLatinFont(fd1);
port2.getPortionFormat().setLatinFont(fd2);
port1.getPortionFormat().setFontBold(NullableBool.True);
port2.getPortionFormat().setFontBold(NullableBool.True);
port1.getPortionFormat().setFontItalic(NullableBool.True);
port2.getPortionFormat().setFontItalic(NullableBool.True);
port1.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port1.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
port2.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port2.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Peru));
```
## 6단계: 수정된 프리젠테이션 저장
마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.
```java
pres.save(dataDir + "WelcomeFont_out.pptx", SaveFormat.Pptx);
```

## 결론
Aspose.Slides for Java를 사용하면 Java를 사용하여 PowerPoint 프레젠테이션의 글꼴 속성을 쉽게 조작할 수 있습니다. 이 튜토리얼에 설명된 단계를 따르면 글꼴을 사용자 정의하여 슬라이드의 시각적 매력을 향상시킬 수 있습니다.
## FAQ
### Java용 Aspose.Slides에서 사용자 정의 글꼴을 사용할 수 있나요?
 예, 글꼴을 정의하는 동안 글꼴 이름을 지정하여 사용자 정의 글꼴을 사용할 수 있습니다.`FontData`.
### PowerPoint 슬라이드의 텍스트 글꼴 크기를 어떻게 변경합니까?
 설정을 통해 글꼴 크기를 조정할 수 있습니다.`FontHeight` 의 재산`PortionFormat`.
### Java용 Aspose.Slides는 텍스트 효과 추가를 지원합니까?
예, Aspose.Slides for Java는 프레젠테이션을 향상시키기 위한 다양한 텍스트 효과 옵션을 제공합니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Slides for Java에 대한 추가 지원과 리소스는 어디서 찾을 수 있나요?
 Aspose.Slides 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/slides/11) 지원 및 문서화를 위해[여기](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

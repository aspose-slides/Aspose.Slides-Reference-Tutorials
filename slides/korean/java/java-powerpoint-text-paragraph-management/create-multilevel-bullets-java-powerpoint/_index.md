---
title: Java PowerPoint에서 다단계 글머리 기호 만들기
linktitle: Java PowerPoint에서 다단계 글머리 기호 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 다단계 글머리 기호를 만드는 방법을 알아보세요. 코드 예제와 FAQ가 포함된 단계별 가이드입니다.
weight: 14
url: /ko/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 다단계 글머리 기호 만들기

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 다단계 글머리 기호를 만드는 방법을 살펴보겠습니다. 주요 항목을 추가하는 것은 프레젠테이션에서 체계적이고 시각적으로 매력적인 콘텐츠를 만들기 위한 일반적인 요구 사항입니다. 우리는 이 가이드가 끝날 때쯤에는 여러 수준에서 구조화된 주요 항목을 사용하여 프레젠테이션을 향상시킬 수 있도록 프로세스를 단계별로 진행해 보겠습니다.
## 전제 조건
시작하기 전에 다음이 설정되어 있는지 확인하세요.
- Java 개발 환경: JDK(Java Development Kit)가 시스템에 설치되어 있는지 확인하십시오.
-  Java 라이브러리용 Aspose.Slides: 다음에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/java/).
- IDE: IntelliJ IDEA, Eclipse 등 선호하는 Java 통합 개발 환경(IDE)을 사용하세요.
- 기본 지식: Java 프로그래밍 및 기본 PowerPoint 개념에 익숙하면 도움이 됩니다.

## 패키지 가져오기
튜토리얼을 시작하기 전에 튜토리얼 전체에서 사용할 Aspose.Slides for Java에서 필요한 패키지를 가져와 보겠습니다.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1단계: 프로젝트 설정
먼저 IDE에서 새 Java 프로젝트를 만들고 프로젝트 종속성에 Aspose.Slides for Java를 추가하세요. 필요한 Aspose.Slides JAR 파일이 프로젝트의 빌드 경로에 포함되어 있는지 확인하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 2단계: 프레젠테이션 개체 초기화
새 프레젠테이션 인스턴스를 만드는 것부터 시작하세요. 이는 슬라이드와 콘텐츠를 추가할 PowerPoint 문서로 사용됩니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드에 액세스
다음으로, 다단계 글머리 기호를 추가하려는 슬라이드에 액세스합니다. 이 예에서는 첫 번째 슬라이드(`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 4단계: 텍스트 프레임이 포함된 도형 추가
다단계 글머리 기호가 있는 텍스트를 배치할 슬라이드에 도형을 추가합니다.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## 5단계: 텍스트 프레임에 액세스
글머리 기호가 있는 단락을 추가할 도형 내의 텍스트 프레임에 액세스합니다.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //기본 단락 지우기
```
## 6단계: 글머리 기호가 있는 단락 추가
글머리 기호 수준이 다른 단락을 추가합니다. 다단계 글머리 기호를 추가하는 방법은 다음과 같습니다.
```java
// 첫 번째 수준
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// 두 번째 수준
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// 세 번째 수준
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// 네 번째 수준
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## 7단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 원하는 디렉터리에 PPTX 파일로 저장합니다.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 다단계 글머리 기호를 만드는 방법을 다루었습니다. 이러한 단계를 수행하면 다양한 수준에서 정리된 글머리 기호로 콘텐츠를 효과적으로 구성하여 프레젠테이션의 명확성과 시각적 매력을 향상시킬 수 있습니다.
## FAQ
### 글머리 기호 기호를 추가로 사용자 정의할 수 있나요?
예, 유니코드 문자를 조정하거나 다른 모양을 사용하여 글머리 기호 기호를 사용자 정의할 수 있습니다.
### Aspose.Slides는 다른 글머리 기호 유형을 지원합니까?
예, Aspose.Slides는 기호, 숫자, 사용자 정의 이미지를 포함한 다양한 글머리 기호 유형을 지원합니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 Microsoft PowerPoint 2007 이상 버전과 호환되는 프레젠테이션을 생성합니다.
### Aspose.Slides를 사용하여 슬라이드 생성을 자동화할 수 있나요?
예, Aspose.Slides는 PowerPoint 프레젠테이션의 생성, 수정 및 조작을 자동화하는 API를 제공합니다.
### Java용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 Aspose.Slides 커뮤니티와 전문가로부터 지원을 받을 수 있습니다.[Aspose.슬라이드 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

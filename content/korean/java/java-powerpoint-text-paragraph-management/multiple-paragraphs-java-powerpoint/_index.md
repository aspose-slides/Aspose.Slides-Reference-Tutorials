---
title: Java PowerPoint의 여러 단락
linktitle: Java PowerPoint의 여러 단락
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 여러 단락을 만드는 방법을 알아보세요. 코드 예제가 포함된 완전한 가이드입니다.
type: docs
weight: 13
url: /ko/java/java-powerpoint-text-paragraph-management/multiple-paragraphs-java-powerpoint/
---
## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java에서 여러 단락으로 슬라이드를 만드는 방법을 살펴보겠습니다. Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작할 수 있도록 하는 강력한 라이브러리로, 슬라이드 생성 및 서식 지정과 관련된 작업을 자동화하는 데 이상적입니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- JDK(Java Development Kit)가 설치되었습니다.
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(통합 개발 환경)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
## 패키지 가져오기
필요한 Aspose.Slides 클래스를 Java 파일로 가져오는 것부터 시작하세요.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1단계: 프로젝트 설정
먼저, 선호하는 IDE에서 새 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 프로젝트의 빌드 경로에 추가하세요.
## 2단계: 프레젠테이션 초기화
 인스턴스화`Presentation` PowerPoint 파일을 나타내는 개체:
```java
// 프레젠테이션을 저장하려는 디렉터리의 경로
String dataDir = "Your_Document_Directory/";
// 프레젠테이션 개체 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 액세스 및 도형 추가
프레젠테이션의 첫 번째 슬라이드에 액세스하여 직사각형 모양(`IAutoShape`) 그것에:
```java
// 첫 번째 슬라이드에 액세스
ISlide slide = pres.getSlides().get_Item(0);
// 슬라이드에 도형(사각형) 추가
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 300, 150);
```
## 4단계: TextFrame에 액세스하고 단락 만들기
 액세스`TextFrame` ~의`AutoShape` 여러 단락을 생성합니다(`IParagraph`) 그 안에 :
```java
// 도형의 TextFrame에 액세스
ITextFrame tf = ashp.getTextFrame();
// 다양한 텍스트 형식으로 단락 및 부분 만들기
IParagraph para0 = tf.getParagraphs().get_Item(0);
IPortion port01 = new Portion();
IPortion port02 = new Portion();
para0.getPortions().add(port01);
para0.getPortions().add(port02);
// 추가 단락 만들기
IParagraph para1 = new Paragraph();
tf.getParagraphs().add(para1);
IPortion port10 = new Portion();
IPortion port11 = new Portion();
IPortion port12 = new Portion();
para1.getPortions().add(port10);
para1.getPortions().add(port11);
para1.getPortions().add(port12);
IParagraph para2 = new Paragraph();
tf.getParagraphs().add(para2);
IPortion port20 = new Portion();
IPortion port21 = new Portion();
IPortion port22 = new Portion();
para2.getPortions().add(port20);
para2.getPortions().add(port21);
para2.getPortions().add(port22);
```
## 5단계: 텍스트 및 단락 서식 지정
단락 내 텍스트의 각 부분에 서식을 지정합니다.
```java
// 단락과 부분을 반복하여 텍스트와 서식을 설정합니다.
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 3; j++) {
        tf.getParagraphs().get_Item(i).getPortions().get_Item(j).setText("Portion0" + j);
        if (j == 0) {
            // 각 단락의 첫 번째 부분 형식
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontBold(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(15);
        } else if (j == 1) {
            // 각 단락의 두 번째 부분 형식
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontItalic(NullableBool.True);
            tf.getParagraphs().get_Item(i).getPortions().get_Item(j).getPortionFormat().setFontHeight(18);
        }
    }
}
```
## 6단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 디스크에 저장합니다.
```java
// PPTX를 디스크에 저장
pres.save(dataDir + "multiParaPort_out.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 여러 단락이 포함된 PowerPoint 프레젠테이션을 만드는 방법을 다루었습니다. 이 접근 방식을 사용하면 Java 코드에서 직접 동적 콘텐츠 생성 및 사용자 정의가 가능합니다.

## FAQ
### 나중에 단락을 더 추가하거나 서식을 변경할 수 있나요?
예, Aspose.Slides의 API 메소드를 사용하여 원하는 만큼 단락을 추가하고 서식을 사용자 정의할 수 있습니다.
### 더 많은 예제와 문서는 어디에서 찾을 수 있나요?
더 많은 예제와 자세한 문서를 탐색할 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 PowerPoint 형식을 지원하여 다양한 버전 간의 호환성을 보장합니다.
### 구매하기 전에 Aspose.Slides를 무료로 사용해 볼 수 있나요?
 예, 무료 평가판을 다운로드할 수 있습니다[여기](https://releases.aspose.com/).
### 필요한 경우 기술 지원을 어떻게 받을 수 있나요?
 Aspose.Slides 커뮤니티에서 지원을 받을 수 있습니다.[여기](https://forum.aspose.com/c/slides/11).
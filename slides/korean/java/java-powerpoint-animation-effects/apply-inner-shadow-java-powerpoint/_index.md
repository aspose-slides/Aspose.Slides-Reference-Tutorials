---
title: Java PowerPoint 프레젠테이션에 내부 그림자 적용
linktitle: Java PowerPoint 프레젠테이션에 내부 그림자 적용
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 모양에 내부 그림자 효과를 적용하는 방법을 알아보세요. 이 단계별 가이드를 통해 슬라이드를 향상해 보세요.
weight: 12
url: /ko/java/java-powerpoint-animation-effects/apply-inner-shadow-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint 프레젠테이션에 내부 그림자 적용

## 소개
시각적으로 매력적인 프레젠테이션을 만드는 것은 아이디어를 효과적으로 전달하는 데 중요합니다. 프레젠테이션을 크게 향상시킬 수 있는 도구 중 하나는 내부 그림자를 사용하는 것입니다. 이 튜토리얼은 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양에 내부 그림자를 적용하는 과정을 안내합니다. 이 튜토리얼을 마치면 슬라이드 요소를 조작하여 놀라운 효과를 만드는 방법을 포괄적으로 이해하게 될 것입니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[자바 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: 다음에서 최신 버전을 다운로드하세요.[Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE는 프로젝트를 보다 효율적으로 관리하는 데 도움이 됩니다.
4.  Aspose.Slides 라이선스: 임시 라이선스를 받으려면 다음을 방문하세요.[임시 라이센스 제공](https://purchase.aspose.com/temporary-license/) . 구매 옵션을 확인하세요.[구매 페이지 제안](https://purchase.aspose.com/buy).
## 패키지 가져오기
먼저 필요한 패키지를 가져와야 합니다. 이를 통해 Aspose.Slides에서 제공하는 클래스와 메서드를 사용할 수 있습니다.
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1단계: 프로젝트 디렉터리 설정
먼저 프로젝트 디렉터리를 설정합니다. 여기에는 PowerPoint 파일과 Java 클래스가 위치합니다.
```java
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
이 단계에서는 프로젝트 파일용 디렉터리가 있는지 확인합니다. 그렇지 않다면 우리가 만듭니다.
## 2단계: 프레젠테이션 초기화
 다음으로, 다음의 인스턴스를 생성해야 합니다.`Presentation` 수업. 이 개체는 PowerPoint 프레젠테이션을 조작하기 위한 기본 인터페이스가 됩니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드에 액세스
이제 프레젠테이션의 첫 번째 슬라이드에 액세스하세요. 슬라이드는 컬렉션에 저장되며 해당 인덱스를 사용하여 첫 번째 슬라이드를 검색할 수 있습니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 슬라이드에 도형 추가
슬라이드에 직사각형 모양을 추가하겠습니다. 이 모양에는 나중에 텍스트와 내부 그림자가 적용됩니다.
```java
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## 5단계: 도형에 텍스트 추가
### TextFrame 생성 및 액세스
 도형에 텍스트를 추가하려면`TextFrame`.
```java
ashp.addTextFrame(" ");
ITextFrame txtFrame = ashp.getTextFrame();
```
### 텍스트 설정
액세스하여 직사각형 모양에 텍스트를 추가합니다.`Paragraph` 그리고`Portion` 사물.
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## 6단계: 내부 그림자 적용
이 단계에는 내부 그림자 효과를 만들고 이를 모양에 적용하는 작업이 포함됩니다.
```java
IEffectFormat effectFormat = ashp.getEffectFormat();
effectFormat.enableInnerShadowEffect();
IInnerShadowEffect innerShadow = effectFormat.getInnerShadowEffect();
innerShadow.setBlurRadius(5.0);
innerShadow.setDirection(45.0);
innerShadow.setDistance(4.0);
innerShadow.getShadowColor().setColor(java.awt.Color.BLACK);
```
## 7단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 지정된 디렉터리에 저장합니다. 이 단계를 수행하면 변경 사항이 파일에 기록됩니다.
```java
pres.save(dataDir + "ApplyInnerShadow_out.pptx", SaveFormat.Pptx);
```
## 8단계: 리소스 정리
 메모리 누수를 방지하려면 항상`Presentation` 작업이 끝난 후 이의를 제기하세요.
```java
if (pres != null) pres.dispose();
```
## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양에 내부 그림자를 성공적으로 적용했습니다. 이 튜토리얼에서는 프로젝트 설정부터 최종 프레젠테이션 저장까지의 필수 단계를 다루었습니다. 이러한 기술을 사용하면 이제 다양한 효과로 프레젠테이션을 더욱 매력적이고 시각적으로 매력적으로 만들 수 있습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성하고 조작하기 위한 강력한 API입니다. 이를 통해 개발자는 Microsoft PowerPoint 없이도 프레젠테이션 작업을 할 수 있습니다.
### 라이선스 없이 Aspose.Slides를 사용할 수 있나요?
 Aspose.Slides는 다음에서 다운로드할 수 있는 무료 평가판을 제공합니다.[Aspose 무료 평가판 페이지](https://releases.aspose.com/). 그러나 전체 기능을 사용하려면 라이센스가 필요합니다.
### 슬라이드에 다른 도형을 어떻게 추가하나요?
 다음을 사용하여 다양한 모양을 추가할 수 있습니다.`addAutoShape` 방법을 지정하고 다음과 같은 모양 유형을 지정합니다.`ShapeType.Rectangle`, `ShapeType.Ellipse`, 등.
### 그림자 효과를 추가로 사용자 정의할 수 있나요?
예. 흐림 반경, 방향, 거리, 색상 등 그림자 효과의 다양한 매개변수를 필요에 맞게 사용자 정의할 수 있습니다.
### 더 자세한 문서는 어디서 찾을 수 있나요?
 당신은[Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 자세한 정보와 예시를 확인하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

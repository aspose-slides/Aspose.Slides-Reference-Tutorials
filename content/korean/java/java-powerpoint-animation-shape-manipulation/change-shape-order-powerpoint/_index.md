---
title: PowerPoint에서 도형 순서 변경
linktitle: PowerPoint에서 도형 순서 변경
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 단계별 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 PowerPoint에서 모양 순서를 변경하는 방법을 알아보세요. 손쉽게 프레젠테이션 기술을 향상시켜 보세요.
type: docs
weight: 15
url: /ko/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---
## 소개
시각적으로 매력적이고 잘 구성된 프레젠테이션을 만드는 것은 어려운 작업일 수 있습니다. 그러나 올바른 도구와 기술을 사용하면 훨씬 쉽게 만들 수 있습니다. Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하고 관리하는 데 도움이 되는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 모양 순서를 변경하는 단계를 안내합니다.
## 전제조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Java 라이브러리용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요.[Aspose.Slides for Java 다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용하여 코딩합니다.
4. 프레젠테이션 파일: 조작하려는 PowerPoint 파일을 준비합니다.
## 패키지 가져오기
시작하려면 Aspose.Slides 라이브러리에서 필요한 패키지를 가져와야 합니다. 이러한 가져오기를 사용하면 프레젠테이션, 슬라이드, 도형 작업을 할 수 있습니다.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
이 가이드에서는 더 나은 이해와 구현 용이성을 위해 모양 순서를 변경하는 과정을 여러 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 로드
 먼저 작업하려는 PowerPoint 프레젠테이션 파일을 로드해야 합니다. 이 단계에는`Presentation` PowerPoint 파일 경로가 포함된 클래스입니다.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## 2단계: 원하는 슬라이드에 액세스
프레젠테이션이 로드되면 모양을 재정렬하려는 슬라이드에 액세스합니다. 슬라이드의 색인은 0부터 시작하므로 첫 번째 슬라이드에 액세스하려면 색인 0을 사용하세요.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## 3단계: 슬라이드에 도형 추가
다음으로 슬라이드에 셰이프를 추가합니다. 데모를 위해 슬라이드에 직사각형과 삼각형 모양을 추가하겠습니다.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## 4단계: 모양 재정렬
 이제 슬라이드의 셰이프 순서를 변경합니다. 그만큼`reorder` 메서드를 사용하면 슬라이드의 모양 컬렉션 내에서 모양의 새 위치를 지정할 수 있습니다.
```java
slide.getShapes().reorder(2, shp3);
```
## 5단계: 수정된 프레젠테이션 저장
모양의 순서를 바꾼 후 수정된 프레젠테이션을 새 파일에 저장합니다. 이렇게 하면 원본 파일이 변경되지 않은 상태로 유지됩니다.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## 6단계: 리소스 정리
마지막으로 프레젠테이션 개체를 삭제하여 리소스를 확보합니다.
```java
if (presentation1 != null) presentation1.dispose();
```
## 결론
다음 단계를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 모양 순서를 쉽게 변경할 수 있습니다. 이 강력한 라이브러리는 PowerPoint 프레젠테이션과 관련된 많은 작업을 단순화하여 프로그래밍 방식으로 슬라이드를 만들고 조작할 수 있게 해줍니다. 프레젠테이션 생성을 자동화하거나 대량 변경이 필요한 경우 Aspose.Slides for Java는 매우 귀중한 도구입니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Microsoft PowerPoint를 사용하지 않고 PowerPoint 프레젠테이션을 만들고 조작하기 위한 Java API입니다.
### 다른 Java IDE와 함께 Aspose.Slides for Java를 사용할 수 있나요?
예, IntelliJ IDEA, Eclipse, NetBeans 등 모든 Java IDE와 함께 사용할 수 있습니다.
### Aspose.Slides for Java는 모든 PowerPoint 형식과 호환됩니까?
예, Aspose.Slides for Java는 PPT, PPTX 및 기타 PowerPoint 형식을 지원합니다.
### Aspose.Slides for Java의 무료 평가판을 받으려면 어떻게 해야 합니까?
 다음에서 무료 평가판을 다운로드할 수 있습니다.[Aspose.Slides for Java 다운로드 페이지](https://releases.aspose.com/).
### Aspose.Slides for Java에 대한 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서는 다음에서 찾을 수 있습니다.[Java 문서 페이지용 Aspose.Slides](https://reference.aspose.com/slides/java/).
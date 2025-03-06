---
title: Java PowerPoint의 SmartArt 노드에서 텍스트 가져오기
linktitle: Java PowerPoint의 SmartArt 노드에서 텍스트 가져오기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt 노드에서 텍스트를 추출하는 방법을 알아보세요. 개발자를 위한 쉽고 단계별 가이드입니다.
type: docs
weight: 14
url: /ko/java/java-powerpoint-text-alignment-formatting/get-text-from-smartart-node-java-powerpoint/
---
## 소개
이 튜토리얼에서는 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt 노드에서 텍스트를 추출하는 방법을 살펴보겠습니다. Aspose.Slides는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 조작 및 변환할 수 있는 강력한 Java 라이브러리입니다. SmartArt 노드에서 텍스트를 추출하면 데이터 추출, 콘텐츠 분석 등과 같은 다양한 응용 프로그램에 유용할 수 있습니다. 이 가이드를 마치면 Java에서 Aspose.Slides를 사용하여 SmartArt 노드에서 텍스트를 효율적으로 검색하는 방법을 명확하게 이해하게 될 것입니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): Java용 Aspose.Slides에는 JDK 8 이상이 필요합니다.
2.  Java 라이브러리용 Aspose.Slides: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 Java 지원이 포함된 원하는 IDE를 사용하세요.
4. 프레젠테이션 파일: 텍스트를 추출하려는 SmartArt가 포함된 PowerPoint 파일(.pptx)이 있습니다.
## 패키지 가져오기
시작하려면 필요한 Aspose.Slides 클래스를 Java 파일로 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프로젝트 설정
먼저 Java 프로젝트를 설정하고 프로젝트 종속성에 Aspose.Slides for Java를 포함하세요. Aspose.Slides JAR 파일을 빌드 경로 또는 Maven/Gradle 종속성에 추가했는지 확인하세요.
## 2단계: 프레젠테이션 로드
Aspose.Slides를 사용하여 PowerPoint 프레젠테이션 파일을 로드합니다.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Presentation.pptx");
```
## 3단계: 슬라이드에서 SmartArt에 액세스
프레젠테이션에서 첫 번째 슬라이드를 검색하고 SmartArt 개체에 액세스합니다.
```java
ISlide slide = presentation.getSlides().get_Item(0);
ISmartArt smartArt = (ISmartArt) slide.getShapes().get_Item(0);
```
## 4단계: SmartArt 노드 검색
SmartArt 내의 모든 노드에 액세스하여 각 노드의 모양을 반복합니다.
```java
ISmartArtNodeCollection smartArtNodes = smartArt.getAllNodes();
for (ISmartArtNode smartArtNode : (Iterable<ISmartArtNode>) smartArtNodes) {
    for (ISmartArtShape nodeShape : smartArtNode.getShapes()) {
        if (nodeShape.getTextFrame() != null)
            System.out.println(nodeShape.getTextFrame().getText());
    }
}
```
## 5단계: 프레젠테이션 개체 삭제
프레젠테이션 개체 사용을 마친 후에는 해당 개체를 삭제하는 것이 좋습니다.
```java
finally {
    if (presentation != null) presentation.dispose();
}
```
## 결론
이 튜토리얼에서는 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt 노드에서 텍스트를 추출하는 방법을 다루었습니다. 이러한 단계를 수행하면 프로그래밍 방식으로 SmartArt 개체에서 텍스트 콘텐츠를 효과적으로 검색하여 Java 응용 프로그램의 다양한 문서 처리 작업을 용이하게 할 수 있습니다.

## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 Java를 사용하여 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 조작 및 변환할 수 있도록 하는 강력한 API입니다.
### Java용 Aspose.Slides를 어떻게 다운로드할 수 있나요?
 Java용 Aspose.Slides를 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
### Aspose.Slides for Java는 상업용으로 적합합니까?
 예, Aspose.Slides for Java는 상업적으로 사용할 수 있습니다. 라이센스를 구매할 수 있습니다[여기](https://purchase.aspose.com/buy).
### Aspose.Slides for Java는 무료 평가판을 제공합니까?
 예, Aspose.Slides for Java의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디서 찾을 수 있나요?
 기술 지원 및 커뮤니티 지원을 받으려면 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
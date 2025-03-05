---
title: PowerPoint의 복제 모양
linktitle: PowerPoint의 복제 모양
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양을 복제하는 방법을 알아보세요. 따라하기 쉬운 튜토리얼을 통해 작업 흐름을 간소화하세요.
type: docs
weight: 16
url: /ko/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---
## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양을 복제하는 방법을 살펴보겠습니다. 모양 복제를 사용하면 프레젠테이션 내에서 기존 모양을 복제할 수 있습니다. 이는 일관된 레이아웃을 만들거나 슬라이드 전체에서 요소를 반복하는 데 특히 유용할 수 있습니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 Java Development Kit가 설치되어 있는지 확인하십시오. 최신 버전을 다운로드하여 설치할 수 있습니다.[웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java 라이브러리: Aspose.Slides for Java 라이브러리를 다운로드하여 Java 프로젝트에 포함하세요. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져와야 합니다. 이 패키지는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 작업에 필요한 기능을 제공합니다.
```java
import com.aspose.slides.*;

```
## 1단계: 프레젠테이션 로드
 먼저 복제하려는 모양이 포함된 PowerPoint 프레젠테이션을 로드해야 합니다. 사용`Presentation` 소스 프레젠테이션을 로드하는 클래스입니다.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## 2단계: 모양 복제
다음으로 소스 프레젠테이션에서 도형을 복제하여 동일한 프레젠테이션의 새 슬라이드에 추가합니다. 여기에는 소스 모양에 액세스하고 새 슬라이드를 만든 다음 복제된 모양을 새 슬라이드에 추가하는 작업이 포함됩니다.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## 3단계: 프레젠테이션 저장
마지막으로 복제된 모양이 포함된 수정된 프레젠테이션을 새 파일에 저장합니다.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양을 복제하는 것은 프레젠테이션 생성 워크플로를 간소화하는 데 도움이 될 수 있는 간단한 프로세스입니다. 이 튜토리얼에 설명된 단계를 따르면 기존 모양을 쉽게 복제하고 필요에 따라 사용자 정의할 수 있습니다.

## FAQ
### 여러 슬라이드에서 모양을 복제할 수 있나요?
예, Aspose.Slides for Java를 사용하여 프레젠테이션의 모든 슬라이드에서 모양을 복제하고 다른 슬라이드에 추가할 수 있습니다.
### 모양 복제에 제한이 있나요?
Aspose.Slides for Java는 강력한 복제 기능을 제공하지만 복잡한 모양이나 애니메이션은 완벽하게 복제되지 않을 수 있습니다.
### 복제된 도형을 슬라이드에 추가한 후 수정할 수 있나요?
물론, 모양이 복제되어 슬라이드에 추가되면 필요에 따라 해당 속성, 스타일 및 콘텐츠를 수정할 수 있습니다.
### Aspose.Slides for Java는 모양 외의 다른 요소 복제를 지원합니까?
예, Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션 내의 슬라이드, 텍스트, 이미지 및 기타 요소를 복제할 수 있습니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 Java용 Aspose.Slides의 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/java/).
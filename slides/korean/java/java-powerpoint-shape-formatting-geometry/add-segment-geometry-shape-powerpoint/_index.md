---
title: PowerPoint의 기하학 모양에 세그먼트 추가
linktitle: PowerPoint의 기하학 모양에 세그먼트 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 상세한 단계별 가이드를 통해 Java용 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션의 기하학적 모양에 세그먼트를 추가하는 방법을 알아보세요.
weight: 19
url: /ko/java/java-powerpoint-shape-formatting-geometry/add-segment-geometry-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
매력적이고 역동적인 프레젠테이션을 만드는 것은 어려울 수 있으며, 특히 사용자 정의 모양과 디자인을 추가하려는 경우 더욱 그렇습니다. 이것이 바로 Java용 Aspose.Slides가 유용한 곳입니다. 이 강력한 API를 사용하면 프로그래밍 방식으로 PowerPoint 파일을 조작할 수 있으므로 복잡한 기하학적 모양과 세그먼트를 쉽게 추가할 수 있는 유연성을 얻을 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기하학적 모양에 세그먼트를 추가하는 방법을 안내합니다. 프레젠테이션 작성을 자동화하려는 개발자이거나 코딩을 좋아하는 사람이라면 이 가이드가 포괄적인 리소스가 될 것입니다.
## 전제 조건
단계별 가이드를 시작하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java 라이브러리를 다운로드해야 합니다. 에서 받으실 수 있습니다.[웹사이트](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 IDE를 사용하면 코딩이 더욱 쉽고 효율적으로 수행됩니다.
4. Java에 대한 기본 지식: 이 튜토리얼을 따르려면 Java 프로그래밍에 대한 지식이 필수적입니다.
## 패키지 가져오기
먼저 Aspose.Slides에서 필요한 패키지를 가져와야 합니다. 이를 통해 PowerPoint 프레젠테이션을 만들고 조작하는 데 필요한 모든 기능에 액세스할 수 있습니다.
```java
import com.aspose.slides.*;

```
명확성과 이해의 용이성을 보장하기 위해 기하학적 형태에 세그먼트를 추가하는 과정을 세부 단계로 나누어 보겠습니다.
## 1단계: 새 프레젠테이션 만들기
이 단계에서는 Aspose.Slides를 사용하여 새로운 PowerPoint 프레젠테이션을 만듭니다.
```java
Presentation pres = new Presentation();
try {
    // 여기에 귀하의 코드가 있습니다
} finally {
    if (pres != null) pres.dispose();
}
```
 새 프레젠테이션을 만드는 것은`Presentation` 수업. 이렇게 하면 조작할 수 있는 메모리의 새 PowerPoint 파일이 초기화됩니다.
## 2단계: 기하학 모양 추가
다음으로 프레젠테이션의 첫 번째 슬라이드에 새 도형을 추가하겠습니다. 이 예에서는 직사각형을 추가하겠습니다.
```java
GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
여기서는 좌표 (100, 100)에 너비가 200, 높이가 100인 직사각형 모양을 추가합니다.
## 3단계: 모양의 형상 경로 가져오기
이제 방금 추가한 모양의 기하학 경로를 가져와야 합니다. 이 경로는 모양의 윤곽을 나타냅니다.
```java
IGeometryPath geometryPath = shape.getGeometryPaths()[0];
```
 그만큼`getGeometryPaths` 메소드는 모양과 연관된 경로의 배열을 반환합니다. 단순한 모양을 다루고 있으므로 첫 번째 경로에 직접 액세스할 수 있습니다.
## 4단계: 형상 경로에 세그먼트 추가
모양을 수정하려면 형상 경로에 새 세그먼트를 추가하면 됩니다. 이 경우 두 개의 선분을 추가하겠습니다.
```java
geometryPath.lineTo(100, 50, 1);
geometryPath.lineTo(100, 50, 4);
```
 그만큼`lineTo` 메소드는 형상 경로에 선분을 추가합니다. 매개변수는 선의 끝점과 세그먼트 유형을 지정합니다.
## 5단계: 편집된 형상 경로를 모양에 다시 할당
형상 경로를 수정한 후 이를 모양에 다시 할당해야 합니다.
```java
shape.setGeometryPath(geometryPath);
```
그러면 변경 사항이 반영되어 모양이 새 형상 경로로 업데이트됩니다.
## 6단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 파일로 저장합니다.
```java
String resultPath = "GeometryShapeAddSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
프레젠테이션을 저장할 경로와 형식(이 경우 PPTX)을 지정합니다.
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기하학 모양에 세그먼트를 추가하는 것은 슬라이드의 시각적 매력을 크게 향상시킬 수 있는 간단한 프로세스입니다. 이 튜토리얼에 설명된 단계를 따르면 프로그래밍 방식으로 사용자 정의 모양을 만들고 프리젠테이션에 복잡한 세부 정보를 추가할 수 있습니다. 프레젠테이션 생성을 자동화하든, 코드를 실험하든 상관없이 Aspose.Slides for Java는 작업을 효율적으로 완료하는 데 필요한 도구를 제공합니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 생성, 수정 및 조작하기 위한 강력한 API입니다.
### 다른 프로그래밍 언어와 함께 Java용 Aspose.Slides를 사용할 수 있나요?
아니요, Aspose.Slides for Java는 Java와 함께 사용하도록 특별히 설계되었습니다. 그러나 Aspose는 .NET 및 Python과 같은 다른 언어에 대해 유사한 API를 제공합니다.
### Aspose.Slides for Java는 무료인가요?
 Aspose.Slides for Java는 유료 라이브러리이지만 다운로드할 수 있습니다.[무료 시험판](https://releases.aspose.com/) 기능을 테스트합니다.
### Aspose.Slides를 사용하여 프레젠테이션에 어떤 유형의 도형을 추가할 수 있나요?
직사각형, 타원, 선, 사용자 정의 기하학 모양을 포함한 다양한 모양을 추가할 수 있습니다.
### Java용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티와 개발자에게 질문하고 도움을 받을 수 있는 곳입니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

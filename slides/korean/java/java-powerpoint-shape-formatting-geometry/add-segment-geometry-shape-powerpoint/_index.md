---
"description": "이 자세하고 단계별 가이드를 통해 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 기하학적 모양에 세그먼트를 추가하는 방법을 알아보세요."
"linktitle": "PowerPoint에서 기하 도형에 세그먼트 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 기하 도형에 세그먼트 추가"
"url": "/ko/java/java-powerpoint-shape-formatting-geometry/add-segment-geometry-shape-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 기하 도형에 세그먼트 추가

## 소개
매력적이고 역동적인 프레젠테이션을 만드는 것은 어려울 수 있습니다. 특히 사용자 지정 도형과 디자인을 추가하려는 경우에는 더욱 그렇습니다. 바로 이럴 때 Aspose.Slides for Java가 유용합니다. 이 강력한 API를 사용하면 PowerPoint 파일을 프로그래밍 방식으로 조작할 수 있어 복잡한 도형과 세그먼트를 손쉽게 추가할 수 있는 유연성을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 세그먼트를 추가하는 방법을 안내합니다. 프레젠테이션 제작 자동화를 원하는 개발자든, 코딩에 푹 빠져 있는 개발자든, 이 가이드는 여러분에게 유용한 종합적인 자료가 될 것입니다.
## 필수 조건
단계별 가이드를 살펴보기 전에 꼭 갖춰야 할 몇 가지 전제 조건이 있습니다.
1. Java Development Kit(JDK): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides for Java: Aspose.Slides for Java 라이브러리를 다운로드해야 합니다. 다음에서 다운로드할 수 있습니다. [웹사이트](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse, NetBeans와 같은 IDE를 사용하면 코딩이 더 쉽고 효율적입니다.
4. Java에 대한 기본 지식: 이 튜토리얼을 따라가려면 Java 프로그래밍에 대한 지식이 필수입니다.
## 패키지 가져오기
먼저 Aspose.Slides에서 필요한 패키지를 가져와야 합니다. 이렇게 하면 PowerPoint 프레젠테이션을 만들고 편집하는 데 필요한 모든 기능을 사용할 수 있습니다.
```java
import com.aspose.slides.*;

```
명확성과 이해의 용이성을 보장하기 위해 기하학적 모양에 세그먼트를 추가하는 과정을 자세한 단계로 나누어 보겠습니다.
## 1단계: 새 프레젠테이션 만들기
이 단계에서는 Aspose.Slides를 사용하여 새로운 PowerPoint 프레젠테이션을 만들어 보겠습니다.
```java
Presentation pres = new Presentation();
try {
    // 여기에 코드를 입력하세요
} finally {
    if (pres != null) pres.dispose();
}
```
새로운 프레젠테이션을 만드는 것은 인스턴스화하는 것만큼 간단합니다. `Presentation` 클래스입니다. 이렇게 하면 메모리에 새 PowerPoint 파일이 초기화되어 조작할 수 있습니다.
## 2단계: 기하 도형 추가
다음으로, 프레젠테이션의 첫 번째 슬라이드에 새 도형을 추가해 보겠습니다. 이 예시에서는 사각형을 추가해 보겠습니다.
```java
GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
여기서는 (100, 100) 좌표에 너비가 200, 높이가 100인 사각형 모양을 추가합니다.
## 3단계: 모양의 기하학 경로 가져오기
이제 방금 추가한 도형의 지오메트리 경로를 구해야 합니다. 이 경로는 도형의 윤곽선을 나타냅니다.
```java
IGeometryPath geometryPath = shape.getGeometryPaths()[0];
```
그만큼 `getGeometryPaths` 메서드는 도형과 연결된 경로 배열을 반환합니다. 간단한 도형을 다루고 있으므로 첫 번째 경로에 직접 접근할 수 있습니다.
## 4단계: 기하학 경로에 세그먼트 추가
모양을 수정하려면 기하 경로에 새 선분을 추가할 수 있습니다. 이 경우에는 두 개의 선분을 추가합니다.
```java
geometryPath.lineTo(100, 50, 1);
geometryPath.lineTo(100, 50, 4);
```
그만큼 `lineTo` 이 메서드는 기하 경로에 선분을 추가합니다. 매개변수는 선의 끝점과 선분의 유형을 지정합니다.
## 5단계: 편집된 기하 경로를 다시 도형에 할당
기하 경로를 수정한 후에는 해당 경로를 다시 모양에 할당해야 합니다.
```java
shape.setGeometryPath(geometryPath);
```
이렇게 하면 우리가 만든 변경 사항이 반영되어 새로운 기하 경로로 모양이 업데이트됩니다.
## 6단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 파일로 저장합니다.
```java
String resultPath = "GeometryShapeAddSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
프레젠테이션을 저장할 경로와 형식(이 경우 PPTX)을 지정합니다.
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 도형에 세그먼트를 추가하는 것은 슬라이드의 시각적 매력을 크게 향상시킬 수 있는 간단한 과정입니다. 이 튜토리얼에 설명된 단계를 따라 하면 사용자 지정 도형을 만들고 프레젠테이션에 정교한 세부 정보를 프로그래밍 방식으로 추가할 수 있습니다. 프레젠테이션 제작을 자동화하거나 코드를 실험하는 경우, Aspose.Slides for Java는 작업을 효율적으로 수행하는 데 필요한 도구를 제공합니다.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 수정하고, 조작하기 위한 강력한 API입니다.
### Aspose.Slides for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
아니요, Aspose.Slides for Java는 Java용으로 특별히 설계되었습니다. 하지만 Aspose는 .NET 및 Python과 같은 다른 언어에도 유사한 API를 제공합니다.
### Aspose.Slides for Java는 무료인가요?
Aspose.Slides for Java는 유료 라이브러리이지만 다운로드할 수 있습니다. [무료 체험](https://releases.aspose.com/) 기능을 테스트해 보세요.
### Aspose.Slides를 사용하여 프레젠테이션에 어떤 유형의 도형을 추가할 수 있나요?
사각형, 타원, 선, 사용자 정의 기하학적 모양 등 다양한 모양을 추가할 수 있습니다.
### Java용 Aspose.Slides에 대한 지원은 어떻게 받을 수 있나요?
당신은에서 지원을 받을 수 있습니다 [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티와 개발자에게 질문을 하고 도움을 받을 수 있는 곳입니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
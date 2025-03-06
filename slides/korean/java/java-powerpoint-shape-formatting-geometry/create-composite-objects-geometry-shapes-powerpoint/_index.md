---
title: 기하학 모양에 복합 개체 만들기
linktitle: 기하학 모양에 복합 개체 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 포괄적인 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 기하학적 형태로 복합 개체를 만드는 방법을 알아보세요. Java 개발자에게 적합합니다.
weight: 20
url: /ko/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 기하학 모양에 복합 개체 만들기

## 소개
안녕하세요! Java를 사용하여 PowerPoint 프레젠테이션에서 멋지고 복잡한 모양을 만들고 싶었던 적이 있습니까? 글쎄, 당신은 바로 이곳에 있습니다. 이 튜토리얼에서는 강력한 Aspose.Slides for Java 라이브러리에 대해 자세히 알아보고 기하학적 형태로 복합 객체를 생성합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 단계별 가이드는 인상적인 결과를 즉시 달성하는 데 도움이 될 것입니다. 시작할 준비가 되셨나요? 뛰어들어보자!
## 전제 조건
코드를 시작하기 전에 필요한 몇 가지 사항이 있습니다.
- JDK(Java Development Kit): 컴퓨터에 JDK 1.8 이상이 설치되어 있는지 확인하십시오.
- 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE는 여러분의 삶을 더 쉽게 만들어줄 것입니다.
-  Java용 Aspose.Slides: 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/) 또는 Maven을 사용하여 프로젝트에 포함시키세요.
- Java 기본 지식: 이 튜토리얼에서는 사용자가 Java에 대한 기본 지식을 가지고 있다고 가정합니다.
## 패키지 가져오기
먼저 Aspose.Slides for Java를 시작하는 데 필요한 패키지를 가져오겠습니다.
```java
import com.aspose.slides.*;

```

복합 개체를 만드는 것은 복잡해 보일 수 있지만 관리 가능한 단계로 나누어 보면 생각보다 쉽다는 것을 알게 될 것입니다. PowerPoint 프리젠테이션을 만들고 모양을 추가한 다음 여러 지오메트리 경로를 정의 및 적용하여 복합 모양을 만듭니다.
## 1단계: 프로젝트 설정
 코드를 작성하기 전에 Java 프로젝트를 설정하십시오. IDE에서 새 프로젝트를 만들고 Aspose.Slides for Java를 포함하세요. Maven을 사용하여 라이브러리를 추가하거나 다음에서 JAR 파일을 다운로드할 수 있습니다.[Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/).
### Maven을 사용하여 프로젝트에 Aspose.Slides 추가하기
 Maven을 사용하는 경우 다음 종속성을 추가하십시오.`pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## 2단계: 프레젠테이션 초기화
이제 새로운 PowerPoint 프레젠테이션을 만들어 보겠습니다. 초기화부터 시작하겠습니다.`Presentation` 수업.
```java
// 출력 파일 이름
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## 3단계: 새 모양 만들기
다음으로 프레젠테이션의 첫 번째 슬라이드에 새로운 직사각형 모양을 추가하겠습니다.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## 4단계: 첫 번째 형상 경로 정의
 다음을 생성하여 복합 모양의 첫 번째 부분을 정의하겠습니다.`GeometryPath` 그리고 거기에 포인트를 더해줍니다.
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## 5단계: 두 번째 형상 경로 정의
마찬가지로 복합 모양의 두 번째 부분을 정의합니다.
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## 6단계: 형상 경로 결합
두 개의 지오메트리 경로를 결합하고 모양으로 설정합니다.
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## 7단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 파일에 저장합니다.
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## 8단계: 리소스 정리
프레젠테이션에 사용된 리소스를 모두 해제했는지 확인하세요.
```java
if (pres != null) pres.dispose();
```
## 결론
그리고 거기에 있습니다! Aspose.Slides for Java를 사용하여 복합 모양을 성공적으로 만들었습니다. 프로세스를 간단한 단계로 나누면 복잡한 모양을 쉽게 만들고 프레젠테이션을 향상시킬 수 있습니다. 독특한 디자인을 만들기 위해 다양한 지오메트리 경로를 계속 실험해 보세요.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java로 PowerPoint 프레젠테이션을 생성, 조작 및 변환하기 위한 강력한 라이브러리입니다.
### Java용 Aspose.Slides를 어떻게 설치하나요?
 Maven을 사용하여 설치하거나 다음에서 JAR 파일을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/java/).
### 상용 프로젝트에서 Java용 Aspose.Slides를 사용할 수 있나요?
 예, 하지만 라이센스를 구입해야 합니다. 자세한 내용은 다음에서 확인할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).
### 무료 평가판이 제공되나요?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### 추가 문서와 지원은 어디서 찾을 수 있나요?
 확인해 보세요[선적 서류 비치](https://reference.aspose.com/slides/java/) 그리고[지원 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint에서 사용자 지정 도형을 만들어 보세요. 단계별 가이드를 따라 프레젠테이션을 더욱 멋지게 만들어 보세요."
"linktitle": "PowerPoint에서 ShapeUtil을 사용하여 기하 도형을 만들어 보세요."
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 ShapeUtil을 사용하여 기하 도형을 만들어 보세요."
"url": "/ko/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 ShapeUtil을 사용하여 기하 도형을 만들어 보세요.

## 소개
시각적으로 매력적인 파워포인트 프레젠테이션을 만들려면 표준 도형과 텍스트만으로는 부족할 때가 많습니다. 슬라이드에 사용자 지정 도형과 텍스트 경로를 직접 추가하여 프레젠테이션의 시각적 효과를 강화할 수 있다고 상상해 보세요. Java용 Aspose.Slides를 사용하면 이러한 작업을 쉽게 수행할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides 사용 방법을 안내합니다. `ShapeUtil` PowerPoint 프레젠테이션에서 도형을 만드는 방법을 배우는 강좌입니다. 숙련된 개발자든 초보자든, 이 단계별 가이드는 Aspose.Slides for Java의 강력한 기능을 활용하여 멋지고 개성 넘치는 콘텐츠를 제작하는 데 도움을 드립니다.
## 필수 조건
튜토리얼을 시작하기 전에 몇 가지 필요한 것이 있습니다.
1. Java Development Kit(JDK): 컴퓨터에 JDK 8 이상이 설치되어 있는지 확인하세요.
2. Java용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요. [다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 개발 환경: IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java IDE를 사용하세요.
4. 임시 면허: 무료 임시 면허를 받으세요. [Aspose의 임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/) Java용 Aspose.Slides의 모든 기능을 활용하세요.
## 패키지 가져오기
시작하려면 Aspose.Slides와 Java AWT(Abstract Window Toolkit) 작업에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## 1단계: 프로젝트 설정
먼저 Java 프로젝트를 설정하고 Aspose.Slides for Java를 프로젝트 종속성에 추가하세요. JAR 파일을 직접 추가하거나 Maven이나 Gradle과 같은 빌드 도구를 사용하여 추가할 수 있습니다.
## 2단계: 새 프레젠테이션 만들기
먼저 새 PowerPoint 프레젠테이션 개체를 만듭니다. 이 개체는 사용자 지정 도형을 추가할 캔버스가 됩니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 사각형 모양 추가
다음으로, 프레젠테이션의 첫 번째 슬라이드에 기본 사각형 도형을 추가합니다. 이 도형은 나중에 사용자 지정 기하 경로를 포함하도록 수정됩니다.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## 4단계: 기하 경로 검색 및 수정
사각형 모양의 기하 경로를 검색하고 채우기 모드를 수정합니다. `None`이 단계는 이 경로를 다른 사용자 정의 지오메트리 경로와 결합할 수 있으므로 매우 중요합니다.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## 5단계: 텍스트에서 사용자 지정 기하 경로 만들기
이제 텍스트를 기반으로 사용자 지정 지오메트리 경로를 만듭니다. 이 과정에서는 텍스트 문자열을 그래픽 경로로 변환한 후, 다시 해당 경로를 지오메트리 경로로 변환합니다.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## 6단계: 기하학 경로 결합
원래의 기하 경로와 새로운 텍스트 기반 기하 경로를 결합하고 이 조합을 모양으로 설정합니다.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## 7단계: 프레젠테이션 저장
마지막으로, 수정된 프레젠테이션을 파일로 저장합니다. 이렇게 하면 사용자 지정 도형이 포함된 PowerPoint 파일이 생성됩니다.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## 결론
축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 사용자 지정 도형을 만들었습니다. 이 튜토리얼에서는 프로젝트 설정부터 도형 경로 생성 및 결합까지 모든 단계를 안내해 드렸습니다. 이러한 기법을 숙달하면 프레젠테이션에 독특하고 눈길을 끄는 요소를 추가하여 더욱 돋보이게 만들 수 있습니다.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Aspose.Slides for Java는 Java에서 PowerPoint 파일을 다루는 강력한 API입니다. 프로그래밍 방식으로 프레젠테이션을 만들고, 수정하고, 변환할 수 있습니다.
### Java용 Aspose.Slides를 어떻게 설치합니까?
최신 버전은 다음에서 다운로드할 수 있습니다. [다운로드 페이지](https://releases.aspose.com/slides/java/) 그리고 프로젝트에 JAR 파일을 추가합니다.
### Aspose.Slides를 무료로 사용할 수 있나요?
Aspose.Slides는 다음에서 다운로드할 수 있는 무료 평가판 버전을 제공합니다. [여기](https://releases.aspose.com/)모든 기능을 사용하려면 라이선스를 구매해야 합니다.
### ShapeUtil 클래스의 용도는 무엇인가요?
그만큼 `ShapeUtil` Aspose.Slides의 클래스는 그래픽 경로를 기하학적 경로로 변환하는 등 도형 작업에 필요한 유틸리티 메서드를 제공합니다.
### Aspose.Slides에 대한 지원은 어디에서 받을 수 있나요?
당신은에서 지원을 받을 수 있습니다 [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
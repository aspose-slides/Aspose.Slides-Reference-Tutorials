---
title: PowerPoint에서 기하학 모양에 ShapeUtil 사용
linktitle: PowerPoint에서 기하학 모양에 ShapeUtil 사용
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java용 Aspose.Slides를 사용하여 PowerPoint에서 사용자 정의 모양을 만듭니다. 프레젠테이션을 향상하려면 이 단계별 가이드를 따르세요.
weight: 23
url: /ko/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
시각적으로 매력적인 PowerPoint 프레젠테이션을 만들려면 표준 모양과 텍스트를 사용하는 것 이상이 필요한 경우가 많습니다. 사용자 정의된 모양과 텍스트 경로를 슬라이드에 직접 추가하여 프레젠테이션의 시각적 효과를 향상시킬 수 있다고 상상해 보십시오. Aspose.Slides for Java를 사용하면 이를 쉽게 달성할 수 있습니다. 이 튜토리얼에서는 다음을 사용하는 과정을 안내합니다.`ShapeUtil` PowerPoint 프레젠테이션에서 기하학적 모양을 만드는 클래스입니다. 숙련된 개발자이든 이제 막 시작하든 이 단계별 가이드는 Aspose.Slides for Java의 강력한 기능을 활용하여 멋진 맞춤형 콘텐츠를 만드는 데 도움이 될 것입니다.
## 전제 조건
튜토리얼을 시작하기 전에 필요한 몇 가지 사항이 있습니다.
1. JDK(Java Development Kit): 컴퓨터에 JDK 8 이상이 설치되어 있는지 확인하세요.
2.  Aspose.Slides for Java: 다음에서 최신 버전을 다운로드하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 개발 환경: IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java IDE를 사용합니다.
4.  임시 라이센스: 다음에서 무료 임시 라이센스를 받으세요.[Aspose의 임시 라이센스 페이지](https://purchase.aspose.com/temporary-license/) Java용 Aspose.Slides의 전체 기능을 잠금 해제합니다.
## 패키지 가져오기
시작하려면 Aspose.Slides 및 Java AWT(Abstract Window Toolkit) 작업에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## 1단계: 프로젝트 설정
먼저 Java 프로젝트를 설정하고 프로젝트 종속성에 Aspose.Slides for Java를 추가하세요. JAR 파일을 직접 추가하거나 Maven 또는 Gradle과 같은 빌드 도구를 사용하여 이를 수행할 수 있습니다.
## 2단계: 새 프레젠테이션 만들기
새 PowerPoint 프리젠테이션 개체를 만드는 것부터 시작하세요. 이 개체는 사용자 정의 모양을 추가할 캔버스가 됩니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 직사각형 모양 추가
다음으로 프레젠테이션의 첫 번째 슬라이드에 기본 직사각형 모양을 추가합니다. 이 모양은 나중에 사용자 정의 형상 경로를 포함하도록 수정됩니다.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## 4단계: 형상 경로 검색 및 수정
 직사각형 모양의 기하학 경로를 검색하고 채우기 모드를 다음과 같이 수정합니다.`None`. 이 단계는 이 경로를 다른 사용자 정의 형상 경로와 결합할 수 있으므로 매우 중요합니다.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## 5단계: 텍스트에서 사용자 정의 형상 경로 만들기
이제 텍스트를 기반으로 사용자 정의 형상 경로를 만듭니다. 여기에는 텍스트 문자열을 그래픽 경로로 변환한 다음 해당 경로를 형상 경로로 변환하는 작업이 포함됩니다.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## 6단계: 형상 경로 결합
원래 형상 경로를 새로운 텍스트 기반 형상 경로와 결합하고 이 조합을 모양에 설정합니다.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## 7단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 파일에 저장합니다. 그러면 사용자 정의 모양이 포함된 PowerPoint 파일이 출력됩니다.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## 결론
축하해요! 방금 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 사용자 정의 기하학 모양을 만들었습니다. 이 튜토리얼에서는 프로젝트 설정부터 지오메트리 경로 생성 및 결합까지 각 단계를 안내했습니다. 이러한 기술을 익히면 프레젠테이션에 독특하고 눈길을 끄는 요소를 추가하여 프레젠테이션을 돋보이게 만들 수 있습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java에서 PowerPoint 파일을 작업하기 위한 강력한 API입니다. 이를 통해 프로그래밍 방식으로 프레젠테이션을 생성, 수정 및 변환할 수 있습니다.
### Java용 Aspose.Slides를 어떻게 설치하나요?
 최신 버전은 다음 사이트에서 다운로드할 수 있습니다.[다운로드 페이지](https://releases.aspose.com/slides/java/) JAR 파일을 프로젝트에 추가하십시오.
### Aspose.Slides를 무료로 사용할 수 있나요?
Aspose.Slides는 다음에서 다운로드할 수 있는 무료 평가판을 제공합니다.[여기](https://releases.aspose.com/)전체 기능을 사용하려면 라이센스를 구매해야 합니다.
### ShapeUtil 클래스의 용도는 무엇입니까?
 그만큼`ShapeUtil` Aspose.Slides의 클래스는 그래픽 경로를 지오메트리 경로로 변환하는 등 모양 작업을 위한 유틸리티 메서드를 제공합니다.
### Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

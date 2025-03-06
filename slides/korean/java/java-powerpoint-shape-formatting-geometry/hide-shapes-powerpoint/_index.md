---
title: PowerPoint에서 도형 숨기기
linktitle: PowerPoint에서 도형 숨기기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 자세한 단계별 가이드를 통해 Java용 Aspose.Slides를 사용하여 PowerPoint에서 모양을 숨기는 방법을 알아보세요. 모든 수준의 Java 개발자에게 적합합니다.
weight: 27
url: /ko/java/java-powerpoint-shape-formatting-geometry/hide-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
Java용 Aspose.Slides를 사용하여 PowerPoint에서 모양을 숨기는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다! 프로그래밍 방식으로 PowerPoint 프레젠테이션에서 특정 모양을 숨겨야 했던 적이 있다면 잘 찾아오셨습니다. 이 가이드는 간단한 대화 스타일로 각 단계를 안내합니다. 노련한 개발자이든 이제 막 Java를 시작하는 개발자이든 상관없이 저희가 도와드리겠습니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Java 라이브러리용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요.[Java 릴리스용 Aspose.Slides](https://releases.aspose.com/slides/java/).
- 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 모든 Java IDE.
- Java의 기본 이해: 이 튜토리얼은 초보자에게 적합하지만 Java에 대한 기본 이해가 도움이 될 것입니다.
## 패키지 가져오기
시작하려면 Aspose.Slides에 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

```
이 섹션에서는 PowerPoint에서 도형을 숨기는 과정을 따라하기 쉬운 단계로 나누어 보겠습니다. 각 단계에는 제목과 자세한 설명이 포함되어 있습니다.
## 1단계: 프로젝트 설정
먼저, Java 프로젝트를 설정하고 Aspose.Slides를 종속성으로 포함해야 합니다. 방법은 다음과 같습니다.
### 새 Java 프로젝트 생성
 IDE를 열고 새 Java 프로젝트를 만듭니다. 다음과 같이 관련 있는 이름을 지정하세요.`HideShapesInPowerPoint`.
### Aspose.Slides 라이브러리 추가
 Aspose.Slides JAR 파일을 다음에서 다운로드하세요.[다운로드 링크](https://releases.aspose.com/slides/java/) 프로젝트의 클래스 경로에 추가하세요. 이 단계는 IDE에 따라 약간 다를 수 있습니다.
## 2단계: 프레젠테이션 초기화
이제 코딩을 시작해 보겠습니다. PowerPoint 파일을 나타내는 프리젠테이션 개체를 초기화해야 합니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PPTX를 나타내는 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```

## 3단계: 첫 번째 슬라이드에 액세스
다음으로 프레젠테이션의 첫 번째 슬라이드에 액세스하려고 합니다.
```java
// 첫 번째 슬라이드 가져오기
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 슬라이드에 도형 추가
이 예에서는 직사각형과 달 모양이라는 두 가지 모양을 슬라이드에 추가합니다.
```java
// 직사각형 형태의 자동모양 추가
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## 5단계: 대체 텍스트 정의 및 도형 숨기기
숨기려는 도형을 식별하려면 해당 도형에 대한 대체 텍스트를 설정하세요. 그런 다음 모든 도형을 반복하고 대체 텍스트와 일치하는 도형을 숨깁니다.
```java
String alttext = "User Defined";
int iCount = sld.getShapes().size();
for (int i = 0; i < iCount; i++) {
    AutoShape ashp = (AutoShape) sld.getShapes().get_Item(i);
    if (ashp.getAlternativeText().equals(alttext)) {
        ashp.setHidden(true);
    }
}
```
## 6단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 원하는 위치에 저장합니다.
```java
// 프레젠테이션을 디스크에 저장
pres.save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 모양을 숨기는 방법을 성공적으로 배웠습니다. 이 단계별 가이드에서는 프로젝트 설정부터 최종 프레젠테이션 저장까지 모든 것을 다루었습니다. 이러한 기술을 사용하면 이제 PowerPoint 프레젠테이션을 보다 효율적으로 자동화하고 사용자 지정할 수 있습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 파일을 조작하기 위한 강력한 API입니다. 이를 통해 개발자는 Microsoft PowerPoint 없이도 프레젠테이션을 생성, 수정 및 관리할 수 있습니다.
### Java를 사용하여 PowerPoint에서 도형을 숨기려면 어떻게 하나요?
 설정하여 도형을 숨길 수 있습니다.`setHidden` 재산`true`. 여기에는 대체 텍스트로 모양을 식별하고 슬라이드의 모양을 반복하는 작업이 포함됩니다.
### 다른 프로그래밍 언어와 함께 Java용 Aspose.Slides를 사용할 수 있나요?
Aspose.Slides는 .NET, Python, C를 포함한 다양한 프로그래밍 언어에서 사용할 수 있습니다.++. 그러나 이 가이드에서는 특히 Java를 다룹니다.
### Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Slides 지원 포럼](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: PowerPoint에서 그룹 모양 만들기
linktitle: PowerPoint에서 그룹 모양 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 그룹 모양을 만드는 방법을 알아보세요. 정리와 시각적 매력을 쉽게 개선할 수 있습니다.
type: docs
weight: 11
url: /ko/java/java-powerpoint-shape-thumbnail-creation/create-group-shape-powerpoint/
---
## 소개
현대 프레젠테이션에서는 시각적으로 매력적이고 잘 구성된 요소를 통합하는 것이 정보를 효과적으로 전달하는 데 중요합니다. PowerPoint의 그룹 도형을 사용하면 여러 도형을 단일 단위로 구성하여 더 쉽게 조작하고 서식을 지정할 수 있습니다. Aspose.Slides for Java는 프로그래밍 방식으로 그룹 모양을 생성하고 조작할 수 있는 강력한 기능을 제공하여 프레젠테이션 디자인에 대한 유연성과 제어 기능을 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2. Aspose.Slides for Java 라이브러리: 프로젝트에 Aspose.Slides for Java 라이브러리를 다운로드하고 포함하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse 등 원하는 Java IDE를 선택하세요.

## 패키지 가져오기
시작하려면 Aspose.Slides for Java 기능을 사용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;

```
## 1단계: 환경 설정
 PowerPoint 프레젠테이션을 만들고 저장할 수 있는 프로젝트 디렉터리가 설정되어 있는지 확인하세요. 바꾸다`"Your Document Directory"` 원하는 디렉토리의 경로로.
```java
String dataDir = "Your Document Directory";
```
## 2단계: 프레젠테이션 클래스 인스턴스화
 인스턴스를 생성합니다.`Presentation` 새 PowerPoint 프레젠테이션을 초기화하는 클래스입니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 및 도형 컬렉션 가져오기
프레젠테이션에서 첫 번째 슬라이드를 검색하고 해당 모양 컬렉션에 액세스합니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
IShapeCollection slideShapes = sld.getShapes();
```
## 4단계: 그룹 셰이프 추가
 다음을 사용하여 슬라이드에 그룹 도형을 추가합니다.`addGroupShape()` 방법.
```java
IGroupShape groupShape = slideShapes.addGroupShape();
```
## 5단계: 그룹 도형 내부에 도형 추가
내부에 개별 셰이프를 추가하여 그룹 셰이프를 채웁니다.
```java
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```
## 6단계: 그룹 모양 프레임 사용자 정의
선택적으로 원하는 대로 그룹 모양의 프레임을 사용자 정의합니다.
```java
groupShape.setFrame(new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0));
```
## 7단계: 프레젠테이션 저장
PowerPoint 프레젠테이션을 지정된 디렉터리에 저장합니다.
```java
pres.save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 그룹 모양을 만들면 콘텐츠를 구성하고 구조화하는 간소화된 접근 방식을 제공합니다. 위에 설명된 단계별 가이드를 따르면 그룹 모양을 프레젠테이션에 효율적으로 통합하여 시각적 매력을 강화하고 정보를 효과적으로 전달할 수 있습니다.

## FAQ
### 다른 그룹 도형 내에 그룹 도형을 중첩할 수 있나요?
예, Aspose.Slides for Java를 사용하면 그룹 모양을 서로 중첩하여 복잡한 계층 구조를 만들 수 있습니다.
### Aspose.Slides for Java는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for Java는 다양한 버전과 호환되는 PowerPoint 프레젠테이션을 생성하여 상호 호환성을 보장합니다.
### Java용 Aspose.Slides는 그룹 모양에 이미지 추가를 지원합니까?
물론, Aspose.Slides for Java를 사용하여 다른 모양과 함께 이미지를 그룹 모양에 추가할 수 있습니다.
### 그룹 도형 내의 도형 수에 제한이 있나요?
Aspose.Slides for Java는 그룹 도형에 추가할 수 있는 도형의 수에 엄격한 제한을 두지 않습니다.
### Aspose.Slides for Java를 사용하여 그룹 모양에 애니메이션을 적용할 수 있나요?
예, Aspose.Slides for Java는 그룹 모양에 애니메이션을 적용하여 동적 프레젠테이션을 가능하게 하는 포괄적인 지원을 제공합니다.
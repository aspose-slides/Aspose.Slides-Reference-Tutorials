---
title: PowerPoint에서 커넥터를 사용하여 도형 연결
linktitle: PowerPoint에서 커넥터를 사용하여 도형 연결
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 커넥터를 사용하여 모양을 연결하는 방법을 알아보세요. 초보자를 위한 단계별 튜토리얼입니다.
weight: 18
url: /ko/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java의 도움으로 PowerPoint 프레젠테이션에서 커넥터를 사용하여 모양을 연결하는 방법을 살펴보겠습니다. 효율적으로 모양을 연결하고 시각적으로 매력적인 슬라이드를 만들려면 다음 단계별 지침을 따르세요.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍 언어에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)를 설치했습니다.
-  Java용 Aspose.Slides를 다운로드하고 설정했습니다. 아직 설치하지 않으셨다면 아래에서 다운로드 받으실 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- Eclipse 또는 IntelliJ IDEA와 같은 코드 편집기.

## 패키지 가져오기
먼저 Java 프로젝트에서 Aspose.Slides 작업에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;

```
## 1단계: 프레젠테이션 클래스 인스턴스화
 인스턴스화`Presentation`작업 중인 PPTX 파일을 나타내는 클래스입니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## 2단계: 셰이프 컬렉션에 액세스
도형과 연결선을 추가하려는 선택한 슬라이드의 도형 컬렉션에 액세스하세요.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## 3단계: 도형 추가
슬라이드에 필요한 도형을 추가합니다. 이 예에서는 타원과 직사각형을 추가하겠습니다.
```java
// 자동 모양 타원 추가
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// 자동 모양 직사각형 추가
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4단계: 커넥터 추가
슬라이드 모양 컬렉션에 연결선 모양을 추가합니다.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5단계: 커넥터에 셰이프 결합
셰이프를 커넥터에 연결합니다.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 6단계: 커넥터 경로 재지정
셰이프 간의 자동 최단 경로를 설정하려면 reroute를 호출하세요.
```java
connector.reroute();
```
## 7단계: 프레젠테이션 저장
커넥터를 사용하여 도형을 연결한 후 프레젠테이션을 저장합니다.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
마지막으로 프레젠테이션 개체를 삭제하는 것을 잊지 마세요.
```java
if (input != null) input.dispose();
```
이제 Aspose.Slides for Java를 사용하여 PowerPoint의 커넥터를 사용하여 모양을 성공적으로 연결했습니다.

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 커넥터를 사용하여 모양을 연결하는 방법을 배웠습니다. 이러한 간단한 단계를 따르면 시각적으로 매력적인 다이어그램과 순서도를 사용하여 프레젠테이션을 향상시킬 수 있습니다.
## FAQ
### Aspose.Slides for Java에서 커넥터 모양을 사용자 정의할 수 있나요?
예, 프레젠테이션 요구 사항에 맞게 색상, 선 스타일, 두께 등 커넥터의 다양한 속성을 사용자 정의할 수 있습니다.
### Aspose.Slides for Java는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for Java는 PPTX, PPT, ODP를 포함한 다양한 PowerPoint 형식을 지원합니다.
### 단일 연결선으로 두 개 이상의 셰이프를 연결할 수 있나요?
예, Aspose.Slides for Java에서 제공하는 복잡한 커넥터를 사용하여 여러 모양을 연결할 수 있습니다.
### Aspose.Slides for Java는 도형에 텍스트를 추가하는 기능을 지원합니까?
물론, Aspose.Slides for Java를 사용하면 프로그래밍 방식으로 모양과 연결선에 텍스트를 쉽게 추가할 수 있습니다.
### Java 사용자를 위한 Aspose.Slides에 사용할 수 있는 커뮤니티 포럼이나 지원 채널이 있습니까?
 예, Aspose.Slides 포럼에서 유용한 리소스를 찾고, 질문하고, 다른 사용자와 소통할 수 있습니다.[여기](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

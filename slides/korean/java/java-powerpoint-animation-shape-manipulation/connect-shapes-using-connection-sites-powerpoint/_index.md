---
title: PowerPoint에서 연결 사이트를 사용하여 셰이프 연결
linktitle: PowerPoint에서 연결 사이트를 사용하여 셰이프 연결
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 도형을 연결하는 방법을 알아보세요. 프레젠테이션을 손쉽게 자동화하세요.
weight: 19
url: /ko/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint의 연결 사이트를 사용하여 도형을 연결하는 방법을 살펴보겠습니다. 이 강력한 라이브러리를 사용하면 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작하여 모양 연결과 같은 작업을 원활하고 효율적으로 만들 수 있습니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요. 에서 다운로드하여 설치할 수 있습니다.[웹사이트](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Java용 Aspose.Slides: 다음 사이트에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse, NetBeans 등 Java 개발용 IDE를 선택합니다.

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.*;

```
## 1단계: Shapes 컬렉션에 접근하기
선택한 슬라이드의 모양 컬렉션에 액세스합니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PPTX 파일을 나타내는 프레젠테이션 클래스 인스턴스화
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## 2단계: 커넥터 모양 추가
슬라이드 모양 컬렉션에 연결선 모양을 추가합니다.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## 3단계: 도형 추가하기
타원 및 직사각형과 같은 자동 모양을 추가합니다.
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## 4단계: 모양을 연결선에 결합
연결선에 셰이프를 결합합니다.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 5단계: 연결 사이트 색인 설정
셰이프에 대해 원하는 연결 사이트 인덱스를 설정합니다.
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint의 연결 사이트를 사용하여 도형을 연결하는 방법을 배웠습니다. 이러한 지식을 바탕으로 이제 PowerPoint 프레젠테이션을 쉽게 자동화하고 사용자 지정할 수 있습니다.
## FAQ
### Aspose.Slides for Java를 다른 PowerPoint 조작 작업에 사용할 수 있습니까?
예, Aspose.Slides for Java는 PowerPoint 프레젠테이션 생성, 편집 및 변환을 위한 광범위한 기능을 제공합니다.
### Aspose.Slides for Java는 무료로 사용할 수 있나요?
 Aspose.Slides for Java는 상용 라이브러리이지만 무료 평가판을 통해 해당 기능을 탐색할 수 있습니다. 방문하다[여기](https://releases.aspose.com/) 시작하려면.
### Aspose.Slides for Java를 사용하는 동안 문제가 발생하면 지원을 받을 수 있나요?
 예, Aspose 커뮤니티 포럼에서 지원을 받을 수 있습니다[여기](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java에 임시 라이선스를 사용할 수 있나요?
 예, 테스트 및 평가 목적으로 임시 라이선스를 사용할 수 있습니다. 하나를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java 라이선스는 어디서 구매할 수 있나요?
Aspose 웹사이트에서 라이선스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint에서 도형을 연결하는 방법을 알아보세요. 프레젠테이션을 손쉽게 자동화하세요."
"linktitle": "PowerPoint에서 연결 사이트를 사용하여 도형 연결"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 연결 사이트를 사용하여 도형 연결"
"url": "/ko/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 연결 사이트를 사용하여 도형 연결

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint에서 연결 사이트를 사용하여 도형을 연결하는 방법을 살펴보겠습니다. 이 강력한 라이브러리를 사용하면 PowerPoint 프레젠테이션을 프로그래밍 방식으로 조작하여 도형 연결과 같은 작업을 원활하고 효율적으로 수행할 수 있습니다.
## 필수 조건
시작하기에 앞서 다음 사항이 있는지 확인하세요.
1. Java Development Kit(JDK): 시스템에 Java가 설치되어 있는지 확인하세요. 다음에서 다운로드하여 설치할 수 있습니다. [웹사이트](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Java용 Aspose.Slides: 다음에서 Java용 Aspose.Slides를 다운로드하여 설치하세요. [다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java 개발을 위한 IDE를 선택하세요.

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져오세요.
```java
import com.aspose.slides.*;

```
## 1단계: Shapes 컬렉션에 액세스
선택한 슬라이드의 모양 컬렉션에 액세스하세요.
```java
// 문서 디렉토리의 경로입니다.                    
String dataDir = "Your Document Directory";
// PPTX 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## 2단계: 커넥터 모양 추가
슬라이드 모양 컬렉션에 커넥터 모양을 추가합니다.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## 3단계: 자동 모양 추가
타원, 사각형 등 자동 모양을 추가합니다.
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## 4단계: 모양을 커넥터에 연결
모양을 커넥터에 연결하세요.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 5단계: 연결 사이트 인덱스 설정
모양에 대해 원하는 연결 사이트 인덱스를 설정합니다.
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint에서 연결 사이트를 사용하여 도형을 연결하는 방법을 알아보았습니다. 이 지식을 바탕으로 이제 PowerPoint 프레젠테이션을 쉽게 자동화하고 사용자 지정할 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides for Java를 다른 PowerPoint 조작 작업에도 사용할 수 있나요?
네, Aspose.Slides for Java는 PowerPoint 프레젠테이션을 만들고, 편집하고, 변환하기 위한 다양한 기능을 제공합니다.
### Aspose.Slides for Java는 무료로 사용할 수 있나요?
Aspose.Slides for Java는 상용 라이브러리이지만, 무료 평가판을 통해 기능을 체험해 볼 수 있습니다. 방문하세요. [여기](https://releases.aspose.com/) 시작하려면.
### Java용 Aspose.Slides를 사용하는 동안 문제가 발생하면 지원을 받을 수 있나요?
네, Aspose 커뮤니티 포럼에서 지원을 받을 수 있습니다. [여기](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java에 대한 임시 라이선스를 이용할 수 있나요?
네, 테스트 및 평가 목적으로 임시 면허를 발급받을 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java 라이선스는 어디에서 구매할 수 있나요?
Aspose 웹사이트에서 라이센스를 구매할 수 있습니다. [여기](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
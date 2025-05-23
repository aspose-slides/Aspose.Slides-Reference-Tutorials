---
"description": "이 포괄적인 튜토리얼을 통해 Aspose.Slides for Java를 사용하여 기하 도형에서 복합 객체를 만드는 방법을 알아보세요. Java 개발자에게 안성맞춤입니다."
"linktitle": "기하 도형에서 복합 객체 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "기하 도형에서 복합 객체 만들기"
"url": "/ko/java/java-powerpoint-shape-formatting-geometry/create-composite-objects-geometry-shapes-powerpoint/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 기하 도형에서 복합 객체 만들기

## 소개
안녕하세요! Java를 사용하여 PowerPoint 프레젠테이션에 멋지고 정교한 도형을 만들고 싶으신가요? 잘 찾아오셨습니다. 이 튜토리얼에서는 강력한 Aspose.Slides for Java 라이브러리를 사용하여 기하 도형으로 복합 객체를 만드는 방법을 자세히 알아보겠습니다. 숙련된 개발자든 초보자든, 이 단계별 가이드를 따라 하면 금방 멋진 결과물을 얻을 수 있습니다. 시작할 준비가 되셨나요? 시작해 볼까요!
## 필수 조건
코드로 들어가기 전에 필요한 몇 가지 사항이 있습니다.
- Java Development Kit(JDK): 컴퓨터에 JDK 1.8 이상이 설치되어 있는지 확인하세요.
- 통합 개발 환경(IDE): IntelliJ IDEA나 Eclipse와 같은 IDE는 여러분의 삶을 더욱 편리하게 만들어 줄 것입니다.
- Java용 Aspose.Slides: 여기에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/) 또는 Maven을 사용하여 프로젝트에 포함하세요.
- Java에 대한 기본 지식: 이 튜토리얼은 독자가 Java에 대한 기본적인 지식을 가지고 있다고 가정합니다.
## 패키지 가져오기
우선, Java용 Aspose.Slides를 시작하는 데 필요한 패키지를 가져오겠습니다.
```java
import com.aspose.slides.*;

```

합성 객체를 만드는 것은 복잡하게 들릴 수 있지만, 단계별로 나누어 보면 생각보다 훨씬 쉽습니다. PowerPoint 프레젠테이션을 만들고 도형을 추가한 다음, 여러 개의 지오메트리 경로를 정의하고 적용하여 합성 도형을 만들어 보겠습니다.
## 1단계: 프로젝트 설정
코드를 작성하기 전에 Java 프로젝트를 설정하세요. IDE에서 새 프로젝트를 생성하고 Java용 Aspose.Slides를 포함하세요. Maven을 사용하여 라이브러리를 추가하거나 다음에서 JAR 파일을 다운로드할 수 있습니다. [Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/).
### Maven을 사용하여 프로젝트에 Aspose.Slides 추가
Maven을 사용하는 경우 다음 종속성을 추가하세요. `pom.xml` 파일:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace with the latest version -->
</dependency>
```
## 2단계: 프레젠테이션 초기화
이제 새 PowerPoint 프레젠테이션을 만들어 보겠습니다. 먼저 다음을 초기화합니다. `Presentation` 수업.
```java
// 출력 파일 이름
String resultPath = "Your Output Directory" +  "GeometryShapeCompositeObjects.pptx";
Presentation pres = new Presentation();
```
## 3단계: 새 모양 만들기
다음으로, 프레젠테이션의 첫 번째 슬라이드에 새로운 사각형 모양을 추가해 보겠습니다.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## 4단계: 첫 번째 기하학 경로 정의
우리는 합성 모양의 첫 번째 부분을 정의합니다. `GeometryPath` 그리고 거기에 포인트를 추가합니다.
```java
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.moveTo(0, 0);
geometryPath0.lineTo(shape.getWidth(), 0);
geometryPath0.lineTo(shape.getWidth(), shape.getHeight() / 3);
geometryPath0.lineTo(0, shape.getHeight() / 3);
geometryPath0.closeFigure();
```
## 5단계: 두 번째 기하학 경로 정의
마찬가지로 합성 모양의 두 번째 부분을 정의합니다.
```java
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.moveTo(0, shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight() / 3 * 2);
geometryPath1.lineTo(shape.getWidth(), shape.getHeight());
geometryPath1.lineTo(0, shape.getHeight());
geometryPath1.closeFigure();
```
## 6단계: 기하학 경로 결합
두 개의 기하학적 경로를 결합하고 모양으로 설정합니다.
```java
shape.setGeometryPaths(new GeometryPath[]{geometryPath0, geometryPath1});
```
## 7단계: 프레젠테이션 저장
마지막으로, 프레젠테이션을 파일로 저장합니다.
```java
String resultPath = "Your Output Directory" + "GeometryShapeCompositeObjects.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## 8단계: 리소스 정리
프레젠테이션에 사용된 모든 리소스를 해제하세요.
```java
if (pres != null) pres.dispose();
```
## 결론
자, 이제 완성했습니다! Aspose.Slides for Java를 사용하여 합성 도형을 성공적으로 만들었습니다. 이 과정을 간단한 단계로 나누어 복잡한 도형을 쉽게 만들고 프레젠테이션을 더욱 돋보이게 할 수 있습니다. 다양한 지오메트리 경로를 계속 실험하여 독특한 디자인을 만들어 보세요.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 Java로 PowerPoint 프레젠테이션을 만들고, 조작하고, 변환하기 위한 강력한 라이브러리입니다.
### Java용 Aspose.Slides를 어떻게 설치합니까?
Maven을 사용하여 설치하거나 JAR 파일을 다운로드할 수 있습니다. [웹사이트](https://releases.aspose.com/slides/java/).
### 상업용 프로젝트에서 Aspose.Slides for Java를 사용할 수 있나요?
네, 하지만 라이선스를 구매해야 합니다. 자세한 내용은 [구매 페이지](https://purchase.aspose.com/buy).
### 무료 체험판이 있나요?
네, 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/).
### 더 많은 문서와 지원은 어디에서 찾을 수 있나요?
확인해 보세요 [선적 서류 비치](https://reference.aspose.com/slides/java/) 그리고 [지원 포럼](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
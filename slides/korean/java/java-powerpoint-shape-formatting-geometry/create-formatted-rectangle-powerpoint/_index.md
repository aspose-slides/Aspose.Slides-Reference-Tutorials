---
"description": "이 단계별 가이드를 통해 Aspose.Slides for Java를 사용하여 PowerPoint에서 사각형을 만들고 서식을 지정하는 방법을 알아보세요."
"linktitle": "PowerPoint에서 서식 있는 사각형 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 서식 있는 사각형 만들기"
"url": "/ko/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 서식 있는 사각형 만들기

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에 서식이 적용된 사각형을 만드는 과정을 안내합니다. 각 단계를 자세히 설명하여 여러분이 직접 프로젝트에 적용하고 따라 할 수 있도록 도와드리겠습니다.
## 필수 조건
코드를 살펴보기 전에 전제 조건을 살펴보겠습니다. 다음이 필요합니다.
1. Java Development Kit(JDK): 시스템에 JDK가 설치되어 있는지 확인하세요.
2. Java용 Aspose.Slides 라이브러리: Java용 Aspose.Slides 라이브러리를 다운로드하여 프로젝트에 포함하세요.
3. 통합 개발 환경(IDE): IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하면 코딩 경험이 더 원활해집니다.
4. Java에 대한 기본 지식: Java 프로그래밍에 대한 지식이 있으면 이 튜토리얼을 따라가는 데 도움이 됩니다.
## 패키지 가져오기
시작하려면 Aspose.Slides 라이브러리에서 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
이러한 가져오기는 PowerPoint 프레젠테이션에서 모양을 만들고 서식을 지정하는 데 필요한 클래스를 가져오기 때문에 중요합니다.
## 1단계: 프로젝트 디렉토리 설정
먼저, 프로젝트 디렉터리를 만들어야 합니다. 이 디렉터리에는 PowerPoint 파일이 저장됩니다.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
이 코드는 디렉터리가 있는지 확인하고 없으면 새로 만듭니다. 프로젝트 파일을 체계적으로 정리하는 것이 좋습니다.
## 2단계: 프레젠테이션 클래스 인스턴스화
다음으로 인스턴스화합니다. `Presentation` PowerPoint 파일을 나타내는 클래스입니다.
```java
Presentation pres = new Presentation();
```
이 코드 줄은 콘텐츠를 추가할 수 있는 새롭고 빈 프레젠테이션을 만듭니다.
## 3단계: 프레젠테이션에 슬라이드 추가
이제 프레젠테이션에 슬라이드를 추가해 보겠습니다. 기본적으로 새 프레젠테이션에는 슬라이드 하나가 포함되므로, 이 슬라이드를 기준으로 작업하겠습니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
이 코드 조각은 프레젠테이션의 첫 번째 슬라이드를 가져옵니다.
## 4단계: 사각형 모양 추가
이제 슬라이드에 사각형을 추가해보겠습니다.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
여기서는 지정된 크기(너비, 높이)와 위치(x, y)를 갖는 사각형을 슬라이드에 추가합니다.
## 5단계: 사각형 서식 지정
사각형을 시각적으로 매력적으로 만들기 위해 몇 가지 서식을 적용해 보겠습니다.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
이 코드는 채우기 유형을 단색으로, 채우기 색상을 초콜릿으로 설정합니다.
## 사각형 테두리 서식 지정
다음으로 사각형의 테두리를 서식화하겠습니다.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
이 코드는 테두리 색상을 검은색으로, 테두리 너비를 5로 설정합니다.
## 6단계: 프레젠테이션 저장
마지막으로, 프레젠테이션을 프로젝트 디렉토리에 저장해 보겠습니다.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
이 코드 줄은 프레젠테이션을 지정된 디렉토리에 PPTX 파일로 저장합니다.
## 7단계: 리소스 정리
폐기하는 것이 좋은 관행입니다. `Presentation` 리소스를 확보하기 위해 반대합니다.
```java
if (pres != null) pres.dispose();
```
이렇게 하면 모든 리소스가 적절하게 해제됩니다.
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 도형을 만들고 서식을 지정하는 것은 매우 간단한 과정입니다. 이 튜토리얼에 설명된 단계를 따라 하면 시각적으로 매력적인 슬라이드를 손쉽게 자동으로 만들 수 있습니다. 비즈니스 보고서, 교육 콘텐츠 또는 동적 프레젠테이션용 애플리케이션을 개발하는 경우, Aspose.Slides for Java는 성공에 필요한 도구를 제공합니다.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 수정하고, 변환할 수 있는 라이브러리입니다.
### 모든 IDE에서 Aspose.Slides for Java를 사용할 수 있나요?
네, IntelliJ IDEA, Eclipse, NetBeans 등 Java 호환 IDE에서 Aspose.Slides for Java를 사용할 수 있습니다.
### Java용 Aspose.Slides의 무료 평가판을 받으려면 어떻게 해야 하나요?
Aspose.Slides for Java의 무료 평가판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/).
### 폐기가 필요한가요? `Presentation` 물체?
네, 폐기합니다 `Presentation` 객체는 리소스를 확보하고 메모리 누수를 방지하는 데 도움이 됩니다.
### Java용 Aspose.Slides에 대한 문서는 어디에서 찾을 수 있나요?
문서가 제공됩니다 [여기](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
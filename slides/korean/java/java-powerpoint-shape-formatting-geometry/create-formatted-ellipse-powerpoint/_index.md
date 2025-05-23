---
"description": "자세한 단계별 가이드를 통해 Aspose.Slides for Java를 사용하여 PowerPoint에서 서식 있는 타원을 만드는 방법을 알아보세요."
"linktitle": "PowerPoint에서 서식 있는 타원 만들기"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 서식 있는 타원 만들기"
"url": "/ko/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 서식 있는 타원 만들기

## 소개
Java용 Aspose.Slides를 사용하여 PowerPoint에서 서식 있는 타원을 만드는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Slides는 개발자가 PowerPoint 파일을 프로그래밍 방식으로 조작할 수 있도록 지원하는 강력한 라이브러리입니다. 슬라이드 생성을 자동화하거나 사용자 지정 도형으로 프레젠테이션을 개선하는 등, 이 가이드는 모든 단계를 안내하여 슬라이드에 완벽하게 서식 있는 타원을 쉽게 추가할 수 있도록 도와드립니다. 자, 이제 본격적으로 이 작업을 수행하는 방법을 알아보겠습니다!
## 필수 조건
시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.
1. Java Development Kit(JDK): JDK 1.6 이상이 설치되어 있는지 확인하세요.
2. Java용 Aspose.Slides: 최신 버전을 다운로드하세요. [Java용 Aspose.Slides](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA나 Eclipse와 같은 IDE를 사용하세요.
4. Java에 대한 기본 지식: Java 프로그래밍에 대한 지식이 필요합니다.
## 패키지 가져오기
Aspose.Slides를 사용하려면 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## 1단계: 프로젝트 디렉토리 설정
먼저, PowerPoint 파일을 저장할 디렉토리가 필요합니다.
### 디렉토리 생성
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉토리가 없으면 새로 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
교체해야 합니다 `"Your Document Directory"` 파일을 저장하려는 실제 경로를 입력합니다.
## 2단계: 프레젠테이션 초기화
이제 PowerPoint 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
```java
// PPTX를 나타내는 Presentation 클래스를 인스턴스화합니다.
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드 가져오기
다음으로, 타원을 추가할 프레젠테이션의 첫 번째 슬라이드를 가져옵니다.
```java
// 첫 번째 슬라이드를 받으세요
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 타원 모양 추가
슬라이드에 타원 유형의 자동 모양을 추가합니다.
```java
// 타원 유형의 자동 모양 추가
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
여기, `50, 150, 150, 50` 타원의 좌표와 크기(x 위치, y 위치, 너비, 높이)입니다.
## 5단계: 타원에 서식 적용
이제 타원에 서식을 적용해 보겠습니다. 단색 채우기 색과 선 색을 설정해 보겠습니다.
### 채우기 색상 설정
```java
// 타원 모양에 일부 서식 적용
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### 선 색상 및 너비 설정
```java
// 타원 선에 일부 서식을 적용합니다.
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## 6단계: 프레젠테이션 저장
마지막으로, 프레젠테이션을 지정된 디렉토리에 저장합니다.
```java
// PPTX 파일을 디스크에 쓰기
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## 7단계: 프레젠테이션 객체 폐기
프레젠테이션 객체를 삭제하여 리소스를 확보합니다.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## 결론
축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 서식이 적용된 타원을 성공적으로 만들었습니다. 이 튜토리얼에서는 프로젝트 설정, 타원 추가, 서식 적용, 프레젠테이션 저장 방법을 안내해 드렸습니다. 이 기술을 활용하면 이제 PowerPoint 슬라이드를 프로그래밍 방식으로 개선하여 더욱 역동적이고 시각적으로 매력적인 프레젠테이션을 만들 수 있습니다.
## 자주 묻는 질문
### Java용 Aspose.Slides란 무엇인가요?
Java용 Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고, 수정하고, 관리할 수 있는 강력한 라이브러리입니다.
### 모든 IDE에서 Aspose.Slides for Java를 사용할 수 있나요?
네, IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 모든 Java IDE에서 Aspose.Slides for Java를 사용할 수 있습니다.
### Aspose.Slides를 사용하려면 라이선스가 필요합니까?
네, Aspose.Slides는 상용 제품이므로 모든 기능을 사용하려면 라이선스가 필요합니다. 임시 라이선스를 구매하실 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Slides에 대한 추가 문서는 어디에서 찾을 수 있나요?
Java용 Aspose.Slides에 대한 자세한 설명서를 찾을 수 있습니다. [문서 페이지](https://reference.aspose.com/slides/java/).
### Aspose.Slides에 대한 지원이 있나요?
예, Aspose는 다음을 통해 지원을 제공합니다. [법정](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
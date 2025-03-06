---
title: PowerPoint에서 서식 있는 타원 만들기
linktitle: PowerPoint에서 서식 있는 타원 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 자세한 단계별 가이드를 통해 Java용 Aspose.Slides를 사용하여 PowerPoint에서 형식화된 타원을 만드는 방법을 알아보세요.
type: docs
weight: 17
url: /ko/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---
## 소개
Aspose.Slides for Java를 사용하여 PowerPoint에서 형식화된 타원을 만드는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Slides는 개발자가 PowerPoint 파일을 프로그래밍 방식으로 조작할 수 있는 강력한 라이브러리입니다. 슬라이드 생성을 자동화하든 사용자 정의 모양으로 프레젠테이션을 향상시키든 이 가이드는 모든 단계를 안내하여 완벽하게 서식이 지정된 타원을 슬라이드에 쉽게 추가할 수 있도록 도와줍니다. 자세히 알아보고 이를 어떻게 달성할 수 있는지 살펴보겠습니다!
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): JDK 1.6 이상이 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요.[Java용 Aspose.Slides](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE를 사용합니다.
4. Java 기본 지식: Java 프로그래밍에 대한 지식이 필요합니다.
## 패키지 가져오기
Aspose.Slides 사용을 시작하려면 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## 1단계: 프로젝트 디렉터리 설정
먼저 PowerPoint 파일을 저장할 디렉터리가 필요합니다.
### 디렉토리 생성
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 꼭 교체하세요`"Your Document Directory"` 파일을 저장하려는 실제 경로를 사용하세요.
## 2단계: 프레젠테이션 초기화
이제 PowerPoint 파일을 나타내는 Presentation 클래스를 인스턴스화합니다.
```java
// PPTX를 나타내는 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 첫 번째 슬라이드 가져오기
다음으로, 타원을 추가할 프레젠테이션의 첫 번째 슬라이드를 가져옵니다.
```java
// 첫 번째 슬라이드 가져오기
ISlide sld = pres.getSlides().get_Item(0);
```
## 4단계: 타원 모양 추가
슬라이드에 타원 유형의 자동 모양을 추가합니다.
```java
// 타원형 자동모양 추가
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 여기,`50, 150, 150, 50` 타원의 좌표와 크기(x 위치, y 위치, 너비, 높이)입니다.
## 5단계: 타원에 서식 적용
이제 타원에 일부 서식을 적용합니다. 단색 채우기 색상과 선 색상을 설정하겠습니다.
### 채우기 색상 설정
```java
// 타원 모양에 일부 서식 적용
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### 선 색상 및 너비 설정
```java
// Ellipse 라인에 일부 서식 적용
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## 6단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 지정된 디렉터리에 저장합니다.
```java
// PPTX 파일을 디스크에 쓰기
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## 7단계: 프레젠테이션 개체 삭제
프리젠테이션 개체를 삭제하여 리소스를 확보합니다.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 형식화된 타원을 성공적으로 만들었습니다. 이 튜토리얼에서는 프로젝트 설정, 타원 추가, 서식 적용 및 프레젠테이션 저장 과정을 안내했습니다. 이러한 기술을 사용하면 이제 프로그래밍 방식으로 PowerPoint 슬라이드를 향상시켜 프레젠테이션을 더욱 역동적이고 시각적으로 매력적으로 만들 수 있습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 관리할 수 있는 강력한 라이브러리입니다.
### 모든 IDE에서 Aspose.Slides for Java를 사용할 수 있나요?
예, IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java IDE에서 Aspose.Slides for Java를 사용할 수 있습니다.
### Aspose.Slides에 대한 라이선스가 필요합니까?
예, Aspose.Slides는 상업용 제품이므로 전체 기능을 사용하려면 라이선스가 필요합니다. 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java에 대한 추가 문서는 어디서 찾을 수 있나요?
 Aspose.Slides for Java에서 자세한 문서를 찾을 수 있습니다.[문서 페이지](https://reference.aspose.com/slides/java/).
### Aspose.Slides에 대한 지원이 제공됩니까?
 예, Aspose는 다음을 통해 지원을 제공합니다.[법정](https://forum.aspose.com/c/slides/11).
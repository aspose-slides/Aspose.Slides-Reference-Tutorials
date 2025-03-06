---
title: PowerPoint에서 조인 스타일 서식 지정
linktitle: PowerPoint에서 조인 스타일 서식 지정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 모양에 대해 다양한 선 결합 스타일을 설정하여 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요. 단계별 가이드를 따르세요.
weight: 15
url: /ko/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 조인 스타일 서식 지정

## 소개
시각적으로 매력적인 PowerPoint 프레젠테이션을 만드는 것은 어려운 작업이 될 수 있으며, 특히 모든 세부 사항을 완벽하게 만들고 싶을 때 더욱 그렇습니다. 이것이 바로 Java용 Aspose.Slides가 유용한 곳입니다. 프로그래밍 방식으로 프레젠테이션을 생성, 조작 및 관리할 수 있는 강력한 API입니다. 활용할 수 있는 기능 중 하나는 모양에 대해 다양한 선 결합 스타일을 설정하는 것입니다. 이는 슬라이드의 미학을 크게 향상시킬 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 모양에 대한 조인 스타일을 설정하는 방법을 살펴보겠습니다. 
## 전제 조건
시작하기 전에 갖춰야 할 몇 가지 전제 조건이 있습니다.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클의 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java 라이브러리: 프로젝트에 Aspose.Slides for Java를 다운로드하여 포함해야 합니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 IDE를 사용하여 Java 코드를 작성하고 실행합니다.
4. Java의 기본 지식: Java 프로그래밍에 대한 기본적인 이해는 튜토리얼을 따라가는 데 도움이 됩니다.
## 패키지 가져오기
먼저 Aspose.Slides에 필요한 패키지를 가져와야 합니다. 이는 프레젠테이션 조작에 필요한 클래스와 메서드에 액세스하는 데 필수적입니다.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## 1단계: 프로젝트 디렉토리 설정
프레젠테이션 파일을 저장할 디렉터리를 만드는 것부터 시작해 보겠습니다. 이렇게 하면 모든 파일이 정리되고 쉽게 액세스할 수 있습니다.
```java
String dataDir = "Your Document Directory";
// 디렉터리가 아직 없으면 만듭니다.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
이 단계에서는 디렉터리 경로를 정의하고 해당 경로가 존재하는지 확인합니다. 그렇지 않은 경우 디렉터리를 만듭니다. 이는 파일을 체계적으로 정리하는 간단하면서도 효과적인 방법입니다.
## 2단계: 프레젠테이션 초기화
 다음으로 인스턴스화합니다.`Presentation` PowerPoint 파일을 나타내는 클래스입니다. 이것이 슬라이드와 모양을 만드는 기초입니다.
```java
Presentation pres = new Presentation();
```
이 코드 줄은 새로운 프레젠테이션을 만듭니다. 모든 콘텐츠를 추가할 빈 PowerPoint 파일을 여는 것과 같다고 생각하세요.
## 3단계: 슬라이드에 도형 추가
### 첫 번째 슬라이드 받기
도형을 추가하기 전에 프레젠테이션의 첫 번째 슬라이드에 대한 참조를 가져와야 합니다. 기본적으로 새 프레젠테이션에는 빈 슬라이드가 하나 포함됩니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### 직사각형 모양 추가
이제 슬라이드에 세 개의 직사각형 모양을 추가해 보겠습니다. 이 모양은 다양한 선 결합 스타일을 보여줍니다.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
이 단계에서는 슬라이드의 지정된 위치에 세 개의 직사각형을 추가합니다. 각 직사각형은 나중에 다양한 결합 스타일을 보여주기 위해 다르게 스타일이 지정됩니다.
## 4단계: 도형 스타일 지정
### 채우기 색상 설정
우리는 직사각형이 단색으로 채워지기를 원합니다. 여기서는 채우기 색상으로 검정색을 선택합니다.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### 선 너비 및 색상 설정
다음으로 각 직사각형의 선 너비와 색상을 정의합니다. 이는 조인 스타일을 시각적으로 구별하는 데 도움이 됩니다.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## 5단계: 조인 스타일 적용
이 튜토리얼의 하이라이트는 선 결합 스타일을 설정하는 것입니다. 마이터(Miter), 베벨(Bevel), 라운드(Round)의 세 가지 스타일을 사용하겠습니다.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
각 선 결합 스타일은 선이 만나는 모서리의 모양에 고유한 모양을 제공합니다. 이는 시각적으로 구별되는 다이어그램이나 그림을 만드는 데 특히 유용할 수 있습니다.
## 6단계: 도형에 텍스트 추가
각 모양이 무엇을 나타내는지 명확하게 하기 위해 사용된 결합 스타일을 설명하는 텍스트를 각 직사각형에 추가합니다.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
텍스트를 추가하면 슬라이드를 발표하거나 공유할 때 다양한 스타일을 식별하는 데 도움이 됩니다.
## 7단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 지정된 디렉터리에 저장합니다.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
이 명령은 프레젠테이션을 Microsoft PowerPoint 또는 기타 호환 소프트웨어로 열 수 있는 PPTX 파일에 기록합니다.
## 결론
그리고 거기에 있습니다! 방금 Aspose.Slides for Java를 사용하여 각기 다른 선 결합 스타일을 보여주는 세 개의 직사각형이 있는 PowerPoint 슬라이드를 만들었습니다. 이 튜토리얼은 Aspose.Slides의 기본 사항을 이해하는 데 도움이 될 뿐만 아니라 독특한 스타일로 프레젠테이션을 향상시키는 방법도 보여줍니다. 발표를 즐기세요!
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 생성, 조작 및 관리하기 위한 강력한 API입니다.
### 모든 IDE에서 Java용 Aspose.Slides를 사용할 수 있나요?
예, IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 Java 지원 IDE에서 Aspose.Slides for Java를 사용할 수 있습니다.
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### PowerPoint의 선 결합 스타일이란 무엇입니까?
선 결합 스타일은 두 선이 만나는 모서리의 모양을 나타냅니다. 일반적인 스타일에는 마이터(Miter), 베벨(Bevel) 및 라운드(Round)가 있습니다.
### Aspose.Slides for Java에 대한 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

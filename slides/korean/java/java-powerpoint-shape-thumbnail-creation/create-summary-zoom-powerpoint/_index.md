---
title: PowerPoint에서 요약 확대/축소 만들기
linktitle: PowerPoint에서 요약 확대/축소 만들기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 이 포괄적인 단계별 튜토리얼을 통해 Java용 Aspose.Slides를 사용하여 PowerPoint에서 요약 확대/축소를 만드는 방법을 알아보세요.
weight: 16
url: /ko/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
Aspose.Slides for Java를 사용하여 PowerPoint에서 요약 확대/축소를 만드는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. 프레젠테이션에 동적인 대화형 요소를 추가하려는 경우 요약 확대/축소가 환상적인 기능입니다. 프레젠테이션의 다양한 섹션을 확대할 수 있는 단일 슬라이드를 만들어 청중에게 더욱 매력적이고 탐색 가능한 경험을 제공할 수 있습니다.
이 단계별 가이드에서는 개발 환경 설정부터 요약 확대/축소 프레임 생성 및 사용자 정의까지 전체 프로세스를 안내합니다. 노련한 Java 개발자이든 이제 막 시작하는 개발자이든 관계없이 이 가이드는 쉽게 따라할 수 있고 귀중한 통찰력으로 가득 차 있다는 것을 알게 될 것입니다.
## 전제 조건
코드를 살펴보기 전에 시작하는 데 필요한 모든 것이 갖추어져 있는지 확인하십시오.
1.  JDK(Java Development Kit): 컴퓨터에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Java용 Aspose.Slides: 다음에서 라이브러리를 다운로드하세요.[Aspose 릴리스 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): 보다 원활한 개발 환경을 위해 IntelliJ IDEA, Eclipse 또는 NetBeans와 같은 IDE를 사용하세요.
4. Java에 대한 기본 지식: Java 프로그래밍 개념에 익숙하면 이 가이드의 단계를 이해하고 구현하는 데 도움이 됩니다.
## 패키지 가져오기
시작하기 전에 필요한 패키지를 가져와야 합니다. 프로젝트 종속성에 Java용 Aspose.Slides가 포함되어 있는지 확인하세요.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## 1단계: 프로젝트 설정
먼저 개발 환경이 올바르게 설정되었는지 확인하세요. 프로젝트를 구성하려면 다음 단계를 따르세요.
### 새 프로젝트 만들기
1. IDE를 엽니다.
2. 새로운 자바 프로젝트를 생성합니다.
3.  프로젝트의 빌드 경로에 Aspose.Slides for Java 라이브러리를 추가하세요. JAR 파일은 다음에서 다운로드할 수 있습니다.[Aspose 릴리스 페이지](https://releases.aspose.com/slides/java/) 프로젝트에 포함시키세요.
### 프레젠테이션 초기화
다음으로 슬라이드와 섹션을 추가할 새 프리젠테이션 개체를 초기화합니다.
```java
Presentation pres = new Presentation();
```
## 2단계: 슬라이드 및 섹션 추가
이 단계에서는 프레젠테이션에 슬라이드를 추가하고 섹션으로 구성해 보겠습니다. 이 구성은 요약 확대/축소를 만드는 데 중요합니다.
### 새 슬라이드 및 섹션 추가
1. 빈 슬라이드 추가: 프레젠테이션에 새 슬라이드를 추가합니다.
2. 슬라이드 배경 사용자 정의: 슬라이드 배경에 단색 채우기 색상을 설정합니다.
3. 섹션 추가: 슬라이드를 섹션으로 그룹화합니다.
이를 달성하기 위한 코드는 다음과 같습니다.
```java
// 첫 번째 슬라이드 추가
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// 첫 번째 섹션 추가
pres.getSections().addSection("Section 1", slide);
```
### 추가 섹션에 대해 반복
슬라이드와 섹션을 더 추가하려면 이 과정을 반복하세요.
```java
// 두 번째 슬라이드 및 섹션 추가
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// 세 번째 슬라이드와 섹션 추가
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// 네 번째 슬라이드 및 섹션 추가
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## 3단계: 요약 확대/축소 프레임 만들기
이제 첫 번째 슬라이드에 요약 확대/축소 프레임을 만들어 보겠습니다. 이 프레임은 사용자가 다른 섹션을 확대할 수 있는 대화형 요소 역할을 합니다.

1. 첫 번째 슬라이드 찾기: 요약 확대/축소 프레임을 추가할 첫 번째 슬라이드를 검색합니다.
2.  요약 확대/축소 프레임 추가:`addSummaryZoomFrame` 프레임을 추가하는 방법.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## 4단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 원하는 위치에 저장합니다. 이 단계를 수행하면 모든 변경 사항이 파일에 기록됩니다.
### 파일 저장
1. 출력 경로 정의: 프레젠테이션을 저장할 경로를 지정합니다.
2.  프리젠테이션 저장:`save` 파일을 PPTX 형식으로 저장하는 방법.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### 프레젠테이션 개체 삭제
사용 중인 리소스를 해제하려면 프레젠테이션 개체를 삭제하세요.
```java
if (pres != null) pres.dispose();
```
## 결론
 축하해요! Aspose.Slides for Java를 사용하여 PowerPoint에서 요약 확대/축소를 성공적으로 만들었습니다. 이 기능은 프레젠테이션을 더욱 상호 작용적이고 매력적으로 만들어 프레젠테이션을 향상시킵니다. 이 가이드를 따르면 이제 자신의 프로젝트에서 이 기능을 구현하는 기술을 갖게 됩니다. 탐험하는 것을 잊지 마세요[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/)고급 기능과 사용자 정의 옵션을 확인하세요.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 Java를 사용하여 프로그래밍 방식으로 PowerPoint 프레젠테이션을 생성, 수정 및 조작할 수 있는 강력한 라이브러리입니다.
### Aspose.Slides for Java를 사용하여 PowerPoint에서 다른 유형의 콘텐츠를 만들 수 있나요?
예, Aspose.Slides for Java는 슬라이드 생성, 도형, 차트, 표 추가 등 다양한 기능을 지원합니다.
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
예, 다음에서 Aspose.Slides for Java 무료 평가판을 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/).
### Aspose.Slides for Java의 임시 라이선스를 받으려면 어떻게 해야 합니까?
 임시면허를 취득할 수 있습니다.[구매 페이지 제안](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Slides에 대한 추가 예제와 지원은 어디서 찾을 수 있나요?
 더 많은 사례를 찾아보고 지원을 요청할 수 있습니다.[Aspose.Slides 지원 포럼](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

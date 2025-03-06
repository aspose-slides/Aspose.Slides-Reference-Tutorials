---
title: Java를 사용하여 SmartArt에서 차트 레이아웃 유형 구성
linktitle: Java를 사용하여 SmartArt에서 차트 레이아웃 유형 구성
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 SmartArt에서 차트 레이아웃 유형을 정리하여 프레젠테이션 시각적 요소를 쉽게 향상시킵니다.
weight: 13
url: /ko/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Java를 사용하고 특히 Aspose.Slides 라이브러리를 활용하여 SmartArt에서 차트 레이아웃 유형을 구성하는 프로세스를 안내합니다. 프레젠테이션의 SmartArt는 데이터의 시각적 매력과 명확성을 크게 향상시켜 데이터 조작을 마스터하는 데 필수적입니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Aspose.Slides 라이브러리를 다운로드하고 설정했습니다. 아직 다운로드하지 않았다면 다음에서 다운로드하세요.[여기](https://releases.aspose.com/slides/java/).
3. Java 프로그래밍에 대한 기본 이해.

## 패키지 가져오기
먼저 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
제공된 예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 개체 초기화
```java
Presentation presentation = new Presentation();
```
새 프리젠테이션 개체를 만듭니다.
## 2단계: 슬라이드에 SmartArt 추가
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
지정된 크기와 레이아웃 유형으로 원하는 슬라이드에 SmartArt를 추가합니다.
## 3단계: 조직도 레이아웃 설정
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
조직도 레이아웃 유형을 설정합니다. 이 예에서는 왼쪽 걸기 레이아웃을 사용하고 있습니다.
## 4단계: 프레젠테이션 저장
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
정리된 차트 레이아웃으로 프레젠테이션을 저장하세요.

## 결론
Java를 사용하여 SmartArt에서 차트 레이아웃 유형의 구성을 마스터하면 시각적으로 매력적인 프레젠테이션을 쉽게 만들 수 있습니다. Aspose.Slides를 사용하면 프로세스가 간소화되고 효율적이 되어 영향력 있는 콘텐츠 제작에 집중할 수 있습니다.
## FAQ
### Aspose.Slides는 다른 Java 개발 환경과 호환됩니까?
예, Aspose.Slides는 다양한 Java 개발 환경과 호환되어 개발자에게 유연성을 보장합니다.
### Aspose.Slides를 사용하여 SmartArt 요소의 모양을 사용자 지정할 수 있나요?
물론 Aspose.Slides는 SmartArt 요소에 대한 광범위한 사용자 정의 옵션을 제공하므로 이를 특정 요구 사항에 맞게 조정할 수 있습니다.
### Aspose.Slides는 개발자를 위한 포괄적인 문서를 제공합니까?
예, 개발자는 Aspose.Slides for Java에서 제공하는 자세한 문서를 참조하여 기능과 사용법에 대한 통찰력을 얻을 수 있습니다.
### Aspose.Slides에 사용할 수 있는 평가판이 있습니까?
예, Aspose.Slides의 무료 평가판에 액세스하여 구매 결정을 내리기 전에 해당 기능을 살펴볼 수 있습니다.
### Aspose.Slides 관련 쿼리에 대한 지원은 어디서 구할 수 있나요?
 Aspose.Slides에 관한 도움이나 질문이 있는 경우 지원 포럼을 방문하세요.[여기](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

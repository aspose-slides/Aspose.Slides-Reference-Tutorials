---
title: Java를 사용하여 SmartArt에 사용자 지정 하위 노드 추가
linktitle: Java를 사용하여 SmartArt에 사용자 지정 하위 노드 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 PowerPoint 프레젠테이션의 SmartArt에 사용자 지정 하위 노드를 추가하는 방법을 알아보세요. 전문적인 그래픽으로 손쉽게 슬라이드를 향상시켜 보세요.
weight: 11
url: /ko/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
SmartArt는 사용자가 전문가 수준의 그래픽을 빠르고 쉽게 만들 수 있게 해주는 PowerPoint의 강력한 기능입니다. 이 튜토리얼에서는 Aspose.Slides와 함께 Java를 사용하여 SmartArt에 사용자 지정 하위 노드를 추가하는 방법을 알아봅니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Slides: 다음에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 로드
SmartArt에 사용자 지정 하위 노드를 추가하려는 PowerPoint 프레젠테이션을 로드합니다.
```java
String dataDir = "Your Document Directory";
// 원하는 프레젠테이션을 로드하세요.
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## 2단계: 슬라이드에 SmartArt 추가
이제 슬라이드에 SmartArt를 추가해 보겠습니다.
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## 3단계: SmartArt 도형 이동
SmartArt 도형을 새 위치로 이동합니다.
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## 4단계: 도형 너비 변경
SmartArt 도형의 너비를 변경합니다.
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## 5단계: 도형 높이 변경
SmartArt 도형의 높이를 변경합니다.
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## 6단계: 도형 회전
SmartArt 도형 회전:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## 7단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 저장합니다.
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides와 함께 Java를 사용하여 SmartArt에 사용자 지정 하위 노드를 추가하는 방법을 배웠습니다. 다음 단계를 따르면 맞춤형 그래픽으로 프레젠테이션을 더욱 매력적이고 전문적으로 만들 수 있습니다.
## FAQ
### Aspose.Slides for Java를 사용하여 다양한 유형의 SmartArt 레이아웃을 추가할 수 있나요?
예, Aspose.Slides for Java는 다양한 SmartArt 레이아웃을 지원하므로 프레젠테이션 요구 사항에 가장 적합한 레이아웃을 선택할 수 있습니다.
### Aspose.Slides for Java는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for Java는 다양한 버전의 PowerPoint와 원활하게 작동하도록 설계되어 플랫폼 간 호환성과 일관성을 보장합니다.
### SmartArt 도형의 모양을 프로그래밍 방식으로 사용자 지정할 수 있나요?
전적으로! Aspose.Slides for Java를 사용하면 SmartArt 모양의 모양, 크기, 색상 및 레이아웃을 프로그래밍 방식으로 사용자 정의하여 디자인 기본 설정에 맞출 수 있습니다.
### Aspose.Slides for Java는 문서와 지원을 제공합니까?
예, Aspose 웹사이트에서 포괄적인 문서와 커뮤니티 지원 포럼에 대한 액세스를 찾을 수 있습니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 웹사이트에서 Aspose.Slides for Java의 무료 평가판을 다운로드하여 구매하기 전에 해당 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: Java를 사용하여 SmartArt의 특정 위치에 노드 추가
linktitle: Java를 사용하여 SmartArt의 특정 위치에 노드 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 SmartArt의 특정 위치에 노드를 추가하는 방법을 알아보세요. 손쉽게 동적 프레젠테이션을 만들어 보세요.
weight: 16
url: /ko/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Aspose.Slides와 함께 Java를 사용하여 SmartArt의 특정 위치에 노드를 추가하는 과정을 안내합니다. SmartArt는 시각적으로 매력적인 다이어그램과 차트를 만들 수 있는 PowerPoint의 기능입니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
2.  Java 라이브러리용 Aspose.Slides가 다운로드되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
3. Java 프로그래밍 언어에 대한 기본 지식.

## 패키지 가져오기
먼저 Java 코드에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1단계: 프레젠테이션 인스턴스 생성
Presentation 클래스의 인스턴스를 생성하여 시작하십시오.
```java
Presentation pres = new Presentation();
```
## 2단계: 프레젠테이션 슬라이드에 액세스
SmartArt를 추가하려는 슬라이드에 액세스합니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3단계: SmartArt 모양 추가
슬라이드에 SmartArt 모양을 추가합니다.
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## 4단계: SmartArt 노드에 액세스
원하는 인덱스에서 SmartArt 노드에 액세스합니다.
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## 5단계: 특정 위치에 하위 노드 추가
상위 노드의 특정 위치에 새 하위 노드를 추가합니다.
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## 6단계: 노드에 텍스트 추가
새로 추가된 노드의 텍스트를 설정합니다.
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## 7단계: 프레젠테이션 저장
수정된 프레젠테이션을 저장합니다.
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides와 함께 Java를 사용하여 SmartArt의 특정 위치에 노드를 추가하는 방법을 배웠습니다. 다음 단계를 수행하면 프로그래밍 방식으로 SmartArt 도형을 조작하여 동적 프레젠테이션을 만들 수 있습니다.
## FAQ
### 한 번에 여러 노드를 추가할 수 있나요?
예, 원하는 위치를 반복하여 프로그래밍 방식으로 여러 노드를 추가할 수 있습니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 PowerPoint 형식을 지원하여 대부분의 버전과의 호환성을 보장합니다.
### SmartArt 노드의 모양을 사용자 지정할 수 있나요?
예, 크기, 색상, 스타일을 포함하여 노드의 모양을 사용자 정의할 수 있습니다.
### Aspose.Slides는 다른 프로그래밍 언어를 지원합니까?
예, Aspose.Slides는 .NET 및 Python을 포함한 여러 프로그래밍 언어에 대한 라이브러리를 제공합니다.
### Aspose.Slides에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

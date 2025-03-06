---
title: Java를 사용하여 SmartArt 노드의 텍스트 변경
linktitle: Java를 사용하여 SmartArt 노드의 텍스트 변경
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 PowerPoint에서 SmartArt 노드 텍스트를 업데이트하여 프레젠테이션 사용자 정의를 향상시키는 방법을 알아보세요.
weight: 22
url: /ko/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
PowerPoint의 SmartArt는 시각적으로 매력적인 다이어그램을 만들기 위한 강력한 기능입니다. Aspose.Slides for Java는 SmartArt 요소를 프로그래밍 방식으로 조작할 수 있는 포괄적인 지원을 제공합니다. 이 자습서에서는 Java를 사용하여 SmartArt 노드에서 텍스트를 변경하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
- Java 프로젝트에서 다운로드하고 참조하는 Java 라이브러리용 Aspose.Slides입니다.
- Java 프로그래밍에 대한 기본 이해.

## 패키지 가져오기
먼저 Java 코드 내에서 Aspose.Slides 기능에 액세스하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
예제를 여러 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 개체 초기화
```java
Presentation presentation = new Presentation();
```
 새 인스턴스를 생성합니다.`Presentation` 파워포인트 프레젠테이션 작업을 위한 수업입니다.
## 2단계: 슬라이드에 SmartArt 추가
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 첫 번째 슬라이드에 SmartArt를 추가합니다. 이 예에서는`BasicCycle` 공들여 나열한 것.
## 3단계: SmartArt 노드에 액세스
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
SmartArt의 두 번째 루트 노드에 대한 참조를 가져옵니다.
## 4단계: 노드에 텍스트 설정
```java
node.getTextFrame().setText("Second root node");
```
선택한 SmartArt 노드의 텍스트를 설정합니다.
## 5단계: 프레젠테이션 저장
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
수정된 프레젠테이션을 지정된 위치에 저장합니다.

## 결론
이 튜토리얼에서는 Java 및 Aspose.Slides를 사용하여 SmartArt 노드에서 텍스트를 변경하는 방법을 시연했습니다. 이러한 지식을 바탕으로 PowerPoint 프레젠테이션에서 SmartArt 요소를 동적으로 조작하여 시각적 매력과 명확성을 향상시킬 수 있습니다.
## FAQ
### SmartArt를 슬라이드에 추가한 후 레이아웃을 변경할 수 있나요?
 예, 다음 페이지에 액세스하여 레이아웃을 변경할 수 있습니다.`SmartArt.setAllNodes(LayoutType)` 방법.
### Aspose.Slides는 Java 11과 호환됩니까?
예, Java용 Aspose.Slides는 Java 11 및 최신 버전과 호환됩니다.
### SmartArt 노드의 모양을 프로그래밍 방식으로 사용자 지정할 수 있나요?
물론 Aspose.Slides API를 사용하면 색상, 크기, 모양과 같은 다양한 속성을 수정할 수 있습니다.
### Aspose.Slides는 다른 유형의 SmartArt 레이아웃을 지원합니까?
예, Aspose.Slides는 다양한 SmartArt 레이아웃을 지원하므로 프레젠테이션 요구 사항에 가장 적합한 레이아웃을 선택할 수 있습니다.
### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 자세한 API 참조 및 튜토리얼을 확인하세요. 또한, 귀하는 다음 기관으로부터 도움을 구할 수 있습니다.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 아니면 구매를 고려해 보세요.[임시면허](https://purchase.aspose.com/temporary-license/) 전문적인 지원을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

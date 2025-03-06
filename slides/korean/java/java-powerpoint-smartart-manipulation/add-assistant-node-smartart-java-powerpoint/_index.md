---
title: Java PowerPoint의 SmartArt에 보조 노드 추가
linktitle: Java PowerPoint의 SmartArt에 보조 노드 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt에 보조 노드를 추가하는 방법을 알아보세요. PowerPoint 편집 기술을 향상시켜 보세요.
weight: 17
url: /ko/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt에 보조 노드를 추가하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요. 최신 JDK를 다운로드하여 설치할 수 있습니다.[여기](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: 다음에서 Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요.[이 링크](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
시작하려면 Java 코드에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 설정
PowerPoint 파일의 경로를 사용하여 프레젠테이션 인스턴스를 만드는 것부터 시작하세요.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## 2단계: 모양 탐색
프레젠테이션의 첫 번째 슬라이드 내부의 모든 모양을 탐색합니다.
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## 3단계: SmartArt 도형 확인
도형이 SmartArt 유형인지 확인하세요.
```java
if (shape instanceof ISmartArt)
```
## 4단계: SmartArt 노드 통과
SmartArt 모양의 모든 노드를 통과합니다.
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## 5단계: 보조 노드 확인
노드가 보조 노드인지 확인하십시오.
```java
if (node.isAssistant())
```
## 6단계: 보조 노드를 일반으로 설정
노드가 보조 노드인 경우 일반 노드로 설정합니다.
```java
node.setAssistant(false);
```
## 7단계: 프레젠테이션 저장
수정된 프레젠테이션을 저장합니다.
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## 결론
축하해요! Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt에 보조 노드를 성공적으로 추가했습니다.

## FAQ
### 프레젠테이션의 SmartArt에 여러 보조 노드를 추가할 수 있나요?
예, 각 노드에 대해 프로세스를 반복하여 여러 보조 노드를 추가할 수 있습니다.
### 이 튜토리얼은 PowerPoint와 PowerPoint 템플릿 모두에 적용됩니까?
예, 이 튜토리얼을 PowerPoint 프레젠테이션과 템플릿 모두에 적용할 수 있습니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 97-2003의 PowerPoint 버전부터 최신 버전까지 지원합니다.
### 보조 노드의 모양을 사용자 정의할 수 있나요?
예, Aspose.Slides에서 제공하는 다양한 속성과 메서드를 사용하여 모양을 맞춤 설정할 수 있습니다.
### SmartArt의 노드 수에 제한이 있나요?
PowerPoint의 SmartArt는 많은 수의 노드를 지원하지만 더 나은 가독성을 위해 합리적으로 유지하는 것이 좋습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

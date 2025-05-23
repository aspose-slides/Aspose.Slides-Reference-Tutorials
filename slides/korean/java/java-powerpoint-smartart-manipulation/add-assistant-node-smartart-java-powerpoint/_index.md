---
"description": "Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt에 보조 노드를 추가하는 방법을 알아보세요. PowerPoint 편집 실력을 향상시켜 보세요."
"linktitle": "Java PowerPoint에서 SmartArt에 보조 노드 추가"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java PowerPoint에서 SmartArt에 보조 노드 추가"
"url": "/ko/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 SmartArt에 보조 노드 추가

## 소개
이 튜토리얼에서는 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt에 보조 노드를 추가하는 과정을 안내합니다.
## 필수 조건
시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.
1. Java Development Kit(JDK): 시스템에 Java가 설치되어 있는지 확인하세요. 최신 JDK는 다음에서 다운로드하여 설치할 수 있습니다. [여기](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Java용 Aspose.Slides: Java용 Aspose.Slides 라이브러리를 다운로드하여 설치하세요. [이 링크](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
시작하려면 Java 코드에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 설정
PowerPoint 파일 경로를 사용하여 프레젠테이션 인스턴스를 만들어 시작하세요.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## 2단계: 모양 탐색
프레젠테이션의 첫 번째 슬라이드 안에 있는 모든 모양을 탐색합니다.
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## 3단계: SmartArt 모양 확인
모양이 SmartArt 유형인지 확인하세요.
```java
if (shape instanceof ISmartArt)
```
## 4단계: SmartArt 노드 탐색
SmartArt 도형의 모든 노드를 탐색합니다.
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## 5단계: 보조 노드 확인
노드가 보조 노드인지 확인하세요.
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
축하합니다! Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 SmartArt에 보조 노드를 성공적으로 추가했습니다.

## 자주 묻는 질문
### 프레젠테이션의 SmartArt에 여러 개의 보조 노드를 추가할 수 있나요?
네, 각 노드에 대해 이 과정을 반복하여 여러 개의 보조 노드를 추가할 수 있습니다.
### 이 튜토리얼은 PowerPoint와 PowerPoint 템플릿 모두에 적용되나요?
네, 이 튜토리얼은 PowerPoint 프레젠테이션과 템플릿 모두에 적용할 수 있습니다.
### Aspose.Slides는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 97-2003부터 최신 버전까지의 PowerPoint 버전을 지원합니다.
### 보조 노드의 모양을 사용자 정의할 수 있나요?
네, Aspose.Slides가 제공하는 다양한 속성과 메서드를 사용하여 모양을 사용자 지정할 수 있습니다.
### SmartArt의 노드 수에 제한이 있나요?
PowerPoint의 SmartArt는 많은 수의 노드를 지원하지만 가독성을 높이려면 적당한 수를 유지하는 것이 좋습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
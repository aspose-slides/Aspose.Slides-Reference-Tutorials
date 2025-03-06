---
title: Java를 사용하여 PowerPoint에서 SmartArt 모양 스타일 변경
linktitle: Java를 사용하여 PowerPoint에서 SmartArt 모양 스타일 변경
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java용 Aspose.Slides와 함께 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 스타일을 변경하는 방법을 알아보세요. 프레젠테이션을 향상시키세요.
weight: 23
url: /ko/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
Java 개발 세계에서는 강력한 프레젠테이션을 만드는 것이 필수 사항인 경우가 많습니다. 비즈니스 홍보, 교육 목적 또는 단순한 정보 공유 등 PowerPoint 프레젠테이션은 일반적인 매체입니다. 그러나 때로는 PowerPoint에서 제공하는 기본 스타일과 형식이 우리의 요구 사항을 완전히 충족하지 못할 수도 있습니다. 이것이 Java용 Aspose.Slides가 작동하는 곳입니다.
Aspose.Slides for Java는 Java 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 작업할 수 있게 해주는 강력한 라이브러리입니다. 모양, 스타일, 애니메이션 등을 조작하는 기능을 포함하여 광범위한 기능을 제공합니다. 이 튜토리얼에서는 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 모양 스타일을 변경하는 특정 작업에 중점을 둡니다.
## 전제 조건
튜토리얼을 시작하기 전에 준비해야 할 몇 가지 전제 조건이 있습니다.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하십시오. Oracle 웹사이트에서 최신 버전을 다운로드하여 설치할 수 있습니다.
2. Aspose.Slides for Java 라이브러리: 프로젝트에 Aspose.Slides for Java 라이브러리를 다운로드하고 포함해야 합니다. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): Java 개발을 위해 선호하는 IDE를 선택하세요. IntelliJ IDEA, Eclipse 또는 NetBeans가 널리 사용됩니다.

## 패키지 가져오기
코딩을 시작하기 전에 필요한 패키지를 Java 프로젝트로 가져오겠습니다. 이 패키지를 사용하면 Aspose.Slides 기능을 원활하게 사용할 수 있습니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 로드
먼저 수정하려는 PowerPoint 프레젠테이션을 로드해야 합니다.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## 2단계: 모양 탐색
다음으로 프레젠테이션의 첫 번째 슬라이드 내부의 모든 모양을 살펴보겠습니다.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## 3단계: SmartArt 유형 확인
각 도형에 대해 SmartArt 도형인지 확인하겠습니다.
```java
if (shape instanceof ISmartArt)
```
## 4단계: SmartArt로 전송
 도형이 SmartArt인 경우 이를`ISmartArt` 상호 작용.
```java
ISmartArt smart = (ISmartArt) shape;
```
## 5단계: 스타일 확인 및 변경
그런 다음 SmartArt의 현재 스타일을 확인하고 필요한 경우 변경합니다.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## 6단계: 프레젠테이션 저장
마지막으로 수정된 프레젠테이션을 새 파일에 저장하겠습니다.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Java 및 Aspose.Slides for Java 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 모양 스타일을 변경하는 방법을 배웠습니다. 단계별 가이드에 따라 프레젠테이션 요구 사항에 맞게 SmartArt 모양의 모양을 쉽게 사용자 지정할 수 있습니다.
## FAQ
### 다른 Java 라이브러리와 함께 Java용 Aspose.Slides를 사용할 수 있나요?
예, Aspose.Slides for Java는 다른 Java 라이브러리와 원활하게 통합되어 애플리케이션의 기능을 향상시킬 수 있습니다.
### Aspose.Slides for Java에 대한 무료 평가판이 있습니까?
 예, 다음에서 Aspose.Slides for Java의 무료 평가판을 이용할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 다음을 방문하여 Java용 Aspose.Slides에 대한 지원을 받을 수 있습니다.[법정](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java의 임시 라이선스를 구매할 수 있나요?
 예, 다음에서 Aspose.Slides for Java의 임시 라이선스를 구매할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 Aspose.Slides for Java에 대한 자세한 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

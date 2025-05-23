---
"description": "Aspose.Slides for Java를 사용하여 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 레이아웃을 조작하는 방법을 알아보세요."
"linktitle": "Java를 사용하여 PowerPoint에서 SmartArt 레이아웃 변경"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java를 사용하여 PowerPoint에서 SmartArt 레이아웃 변경"
"url": "/ko/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 PowerPoint에서 SmartArt 레이아웃 변경

## 소개
이 튜토리얼에서는 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 레이아웃을 조작하는 방법을 살펴보겠습니다. SmartArt는 PowerPoint의 강력한 기능으로, 프로세스, 계층 구조, 관계 등을 표현하는 등 다양한 목적으로 시각적으로 매력적인 그래픽을 만들 수 있도록 해줍니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
1. Java 개발 환경: 시스템에 Java Development Kit(JDK)가 설치되어 있는지 확인하세요.
2. Aspose.Slides 라이브러리: Java용 Aspose.Slides 라이브러리를 다운로드하여 설치하세요. [여기](https://releases.aspose.com/slides/java/).
3. Java에 대한 기본 이해: Java 프로그래밍 언어의 기본 사항을 알고 있으면 도움이 됩니다.
4. 통합 개발 환경(IDE): Eclipse나 IntelliJ IDEA 등 원하는 IDE를 선택하세요.

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져오세요.
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## 1단계: Java 프로젝트 환경 설정
선택한 IDE에서 Java 프로젝트가 제대로 설정되었는지 확인하세요. 새 Java 프로젝트를 생성하고 Aspose.Slides 라이브러리를 프로젝트 종속성에 포함하세요.
## 2단계: 새 프레젠테이션 만들기
새로운 Presentation 객체를 인스턴스화하여 새로운 PowerPoint 프레젠테이션을 만듭니다.
```java
Presentation presentation = new Presentation();
```
## 3단계: SmartArt 그래픽 추가
프레젠테이션에 SmartArt 그래픽을 추가하세요. 슬라이드에서 SmartArt 그래픽의 위치와 크기를 지정하세요.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## 4단계: SmartArt 레이아웃 변경
SmartArt 그래픽의 레이아웃을 원하는 레이아웃 유형으로 변경합니다.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## 5단계: 프레젠테이션 저장
수정된 프레젠테이션을 시스템의 지정된 디렉토리에 저장합니다.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## 결론
Aspose.Slides for Java를 사용하면 Java를 사용하여 PowerPoint 프레젠테이션의 SmartArt 레이아웃을 손쉽게 조작할 수 있습니다. 이 튜토리얼을 따라 하면 프레젠테이션의 필요에 맞게 SmartArt 그래픽을 쉽게 수정할 수 있습니다.
## 자주 묻는 질문
### Java용 Aspose.Slides를 사용하여 SmartArt 그래픽의 모양을 사용자 정의할 수 있나요?
네, SmartArt 그래픽의 색상, 스타일, 효과 등 다양한 측면을 사용자 지정할 수 있습니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 버전의 PowerPoint에서 만든 PowerPoint 프레젠테이션을 지원하여 다양한 플랫폼 간의 호환성을 보장합니다.
### Aspose.Slides는 다른 프로그래밍 언어에 대한 지원을 제공합니까?
네, Aspose.Slides는 .NET, Python, JavaScript를 포함한 여러 프로그래밍 언어로 제공됩니다.
### Aspose.Slides를 사용하여 SmartArt 그래픽을 처음부터 만들 수 있나요?
물론입니다. SmartArt 그래픽을 프로그래밍 방식으로 만들거나 기존 그래픽을 수정하여 요구 사항을 충족할 수 있습니다.
### Aspose.Slides와 관련하여 도움을 구할 수 있는 커뮤니티 포럼이 있나요?
네, Aspose.Slides 포럼을 방문하실 수 있습니다. [여기](https://forum.aspose.com/c/slides/11) 질문을 하고 커뮤니티에 참여하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
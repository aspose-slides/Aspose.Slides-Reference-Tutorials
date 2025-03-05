---
title: Java를 사용하여 PowerPoint에서 SmartArt 레이아웃 변경
linktitle: Java를 사용하여 PowerPoint에서 SmartArt 레이아웃 변경
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java용 Aspose.Slides와 함께 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 레이아웃을 조작하는 방법을 알아보세요.
type: docs
weight: 19
url: /ko/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---
## 소개
이 튜토리얼에서는 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 레이아웃을 조작하는 방법을 살펴보겠습니다. SmartArt는 사용자가 프로세스, 계층, 관계 등을 보여주는 등 다양한 목적을 위해 시각적으로 매력적인 그래픽을 만들 수 있도록 하는 PowerPoint의 강력한 기능입니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
1. Java 개발 환경: 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.
2.  Aspose.Slides 라이브러리: 다음에서 Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/java/).
3. Java에 대한 기본 이해: Java 프로그래밍 언어 기본 사항에 익숙하면 도움이 됩니다.
4. 통합 개발 환경(IDE): Eclipse, IntelliJ IDEA 등 원하는 IDE를 선택하세요.

## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## 1단계: Java 프로젝트 환경 설정
선택한 IDE에서 Java 프로젝트가 올바르게 설정되었는지 확인하세요. 새 Java 프로젝트를 만들고 프로젝트 종속성에 Aspose.Slides 라이브러리를 포함합니다.
## 2단계: 새 프레젠테이션 만들기
새 프레젠테이션 개체를 인스턴스화하여 새 PowerPoint 프레젠테이션을 만듭니다.
```java
Presentation presentation = new Presentation();
```
## 3단계: SmartArt 그래픽 추가
프레젠테이션에 SmartArt 그래픽을 추가하세요. 슬라이드에서 SmartArt 그래픽의 위치와 크기를 지정합니다.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## 4단계: SmartArt 레이아웃 변경
SmartArt 그래픽의 레이아웃을 원하는 레이아웃 유형으로 변경합니다.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## 5단계: 프레젠테이션 저장
수정된 프레젠테이션을 시스템의 지정된 디렉터리에 저장합니다.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## 결론
Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 레이아웃을 조작하는 것은 Aspose.Slides for Java를 사용하면 간단한 프로세스입니다. 이 튜토리얼을 따르면 프레젠테이션 요구 사항에 맞게 SmartArt 그래픽을 쉽게 수정할 수 있습니다.
## FAQ
### Java용 Aspose.Slides를 사용하여 SmartArt 그래픽의 모양을 사용자 지정할 수 있나요?
예, 색상, 스타일, 효과 등 SmartArt 그래픽의 다양한 측면을 사용자 지정할 수 있습니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 버전의 PowerPoint에서 작성된 PowerPoint 프레젠테이션을 지원하여 다양한 플랫폼 간의 호환성을 보장합니다.
### Aspose.Slides는 다른 프로그래밍 언어를 지원합니까?
예, Aspose.Slides는 .NET, Python 및 JavaScript를 포함한 여러 프로그래밍 언어에서 사용할 수 있습니다.
### Aspose.Slides를 사용하여 처음부터 SmartArt 그래픽을 만들 수 있나요?
물론 프로그래밍 방식으로 SmartArt 그래픽을 만들거나 요구 사항에 맞게 기존 그래픽을 수정할 수 있습니다.
### Aspose.Slides에 관해 도움을 구할 수 있는 커뮤니티 포럼이 있습니까?
 예, Aspose.Slides 포럼을 방문하실 수 있습니다[여기](https://forum.aspose.com/c/slides/11) 질문을 하고 커뮤니티에 참여합니다.
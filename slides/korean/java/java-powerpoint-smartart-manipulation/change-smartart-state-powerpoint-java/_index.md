---
title: Java를 사용하여 PowerPoint에서 SmartArt 상태 변경
linktitle: Java를 사용하여 PowerPoint에서 SmartArt 상태 변경
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java 및 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 상태를 변경하는 방법을 알아보세요. 프레젠테이션 자동화 기술을 향상시키세요.
weight: 21
url: /ko/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
이 튜토리얼에서는 Aspose.Slides 라이브러리와 Java를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 개체를 조작하는 방법을 배웁니다. SmartArt는 시각적으로 매력적인 다이어그램과 그래픽을 만들 수 있는 PowerPoint의 강력한 기능입니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1.  JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하십시오. 다음에서 다운로드할 수 있습니다.[오라클 웹사이트](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: 다음에서 Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
Java 프로젝트에서 Aspose.Slides 작업을 시작하려면 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
이제 제공된 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 개체 초기화
```java
Presentation presentation = new Presentation();
```
 여기서는 새 항목을 만듭니다.`Presentation` PowerPoint 프레젠테이션을 나타내는 개체입니다.
## 2단계: SmartArt 개체 추가
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 이 단계에서는 프레젠테이션의 첫 번째 슬라이드에 SmartArt 개체를 추가합니다. SmartArt 개체의 위치와 크기는 물론 레이아웃 유형(이 경우`BasicProcess`).
## 3단계: SmartArt 상태 설정
```java
smart.setReversed(true);
```
여기서는 SmartArt 개체의 상태를 설정합니다. 이 예에서는 SmartArt의 방향을 반대로 바꿉니다.
## 4단계: SmartArt 상태 확인
```java
boolean flag = smart.isReversed();
```
 SmartArt 개체의 현재 상태도 확인할 수 있습니다. 이 줄은 SmartArt가 반전되었는지 여부를 검색하여`flag` 변하기 쉬운.
## 5단계: 프레젠테이션 저장
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
마지막으로 수정된 프레젠테이션을 디스크의 지정된 위치에 저장합니다.

## 결론
이 튜토리얼에서는 Java 및 Aspose.Slides 라이브러리를 사용하여 PowerPoint 프레젠테이션에서 SmartArt 개체의 상태를 변경하는 방법을 배웠습니다. 이러한 지식을 바탕으로 프로그래밍 방식으로 역동적이고 매력적인 프레젠테이션을 만들 수 있습니다.
## FAQ
### Aspose.Slides for Java를 사용하여 SmartArt의 다른 속성을 수정할 수 있나요?
예, Aspose.Slides를 사용하여 색상, 스타일, 레이아웃 등 SmartArt 개체의 다양한 측면을 수정할 수 있습니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
예, Aspose.Slides는 다양한 버전의 PowerPoint 프레젠테이션을 지원하여 호환성과 원활한 통합을 보장합니다.
### Aspose.Slides를 사용하여 사용자 정의 SmartArt 레이아웃을 만들 수 있나요?
전적으로! Aspose.Slides는 특정 요구 사항에 맞는 맞춤형 SmartArt 레이아웃을 생성할 수 있는 API를 제공합니다.
### Aspose.Slides는 PowerPoint 외에 다른 파일 형식을 지원합니까?
예, Aspose.Slides는 PPTX, PPT, PDF 등을 포함한 광범위한 파일 형식을 지원합니다.
### Aspose.Slides 관련 질문에 대해 도움을 받을 수 있는 커뮤니티 포럼이 있나요?
 예, Aspose.Slides 포럼을 방문하실 수 있습니다.[여기](https://forum.aspose.com/c/slides/11) 도움과 토론을 위해.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

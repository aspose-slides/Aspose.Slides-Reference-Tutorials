---
title: PowerPoint에서 Shape Bevel 효과적인 데이터 가져오기
linktitle: PowerPoint에서 Shape Bevel 효과적인 데이터 가져오기
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint에서 형상 베벨 유효 데이터를 검색하는 방법을 알아보세요. 놀라운 시각 효과로 프레젠테이션을 향상시켜 보세요.
type: docs
weight: 26
url: /ko/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---
## 소개
현대 비즈니스 프레젠테이션에서 시각적 매력은 정보를 효과적으로 전달하는 데 중요한 역할을 합니다. PowerPoint 프레젠테이션에서 도형의 시각적 효과를 향상시킬 수 있는 요소 중 하나는 경사 효과입니다. Aspose.Slides for Java는 베벨 효과를 포함하여 도형의 다양한 속성에 액세스하고 조작할 수 있는 강력한 도구를 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 형상 베벨 유효 데이터를 검색하는 과정을 안내합니다.
## 전제조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 프로그래밍 언어에 대한 기본 이해.
2. 시스템에 JDK(Java Development Kit)를 설치했습니다.
3.  Java용 Aspose.Slides를 다운로드하여 설치했습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져오는 것부터 시작하세요.
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
```
## 1단계: 문서 디렉터리 설정
PowerPoint 프레젠테이션이 있는 문서 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Document Directory";
```
## 2단계: 프레젠테이션 로드
Aspose.Slides 라이브러리를 사용하여 PowerPoint 프레젠테이션을 로드합니다.
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## 3단계: 베벨 유효 데이터 검색
모양의 효과적인 베벨 데이터에 액세스합니다.
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## 4단계: 베벨 속성 인쇄
효과적인 모양의 윗면 릴리프 속성을 인쇄합니다.
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## 결론
이 튜토리얼에서는 Java용 Aspose.Slides를 사용하여 PowerPoint에서 형상 베벨 유효 데이터를 검색하는 방법을 시연했습니다. 다음 단계를 따르면 도형의 다양한 속성에 쉽게 액세스하고 조작하여 프레젠테이션의 시각적 매력을 향상시킬 수 있습니다.
## FAQ
### 여러 모양에 동시에 경사 효과를 적용할 수 있나요?
예, 슬라이드의 모양을 반복하고 필요에 따라 경사 효과를 적용할 수 있습니다.
### Aspose.Slides는 경사 외에 다른 3D 효과를 지원합니까?
예, Aspose.Slides는 PowerPoint 프레젠테이션의 모양에 적용할 수 있는 광범위한 3D 효과를 제공합니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 버전의 PowerPoint와의 호환성을 보장하므로 다양한 환경에서 원활하게 작업할 수 있습니다.
### 경사 효과 속성을 추가로 사용자 정의할 수 있나요?
물론, 경사 효과 속성을 완전히 제어할 수 있으며 요구 사항에 따라 사용자 정의할 수 있습니다.
### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 질문, 지원 또는 추가 리소스가 필요합니다.
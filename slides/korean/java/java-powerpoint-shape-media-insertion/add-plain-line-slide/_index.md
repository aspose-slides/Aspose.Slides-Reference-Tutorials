---
title: 슬라이드에 일반 선 추가
linktitle: 슬라이드에 일반 선 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 PowerPoint 슬라이드에 일반 선을 추가하는 방법을 알아보세요. 이 단계별 가이드를 통해 생산성을 높이십시오.
weight: 14
url: /ko/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
Aspose.Slides for Java는 Java 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 작업할 수 있게 해주는 강력한 라이브러리입니다. Aspose.Slides를 사용하면 PowerPoint 파일을 쉽게 생성, 수정 및 변환하여 시간과 노력을 절약할 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 슬라이드에 일반 선을 추가하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
- 시스템에 설치된 JDK(Java Development Kit)
- Java 라이브러리용 Aspose.Slides가 다운로드되어 Java 프로젝트에 추가되었습니다.
- Java 프로그래밍 언어에 대한 기본 지식

## 패키지 가져오기
시작하려면 Java 코드에 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## 1단계: 환경 설정
 먼저, 새로운 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 프로젝트의 클래스 경로에 추가하세요. 다음에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
## 2단계: 새 프레젠테이션 만들기
 다음으로 인스턴스화`Presentation` 새로운 PowerPoint 프레젠테이션을 만드는 수업입니다.
```java
Presentation pres = new Presentation();
```
## 3단계: 슬라이드 추가
프레젠테이션의 첫 번째 슬라이드를 가져와 변수에 저장합니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 4단계: 선 모양 추가
이제 슬라이드에 선 유형의 자동 모양을 추가합니다.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## 5단계: 프레젠테이션 저장
마지막으로 프레젠테이션을 디스크에 저장합니다.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 슬라이드에 일반 줄을 성공적으로 추가했습니다. Aspose.Slides를 사용하면 PowerPoint 파일을 프로그래밍 방식으로 쉽게 조작하여 Java 애플리케이션에 대한 가능성의 세계를 열어줄 수 있습니다.

## FAQ
### 선 모양의 속성을 사용자 정의할 수 있나요?
예, Aspose.Slides API를 사용하여 선 색상, 너비, 스타일 등과 같은 다양한 속성을 사용자 정의할 수 있습니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
예, Aspose.Slides는 PPT, PPTX 등을 포함한 다양한 PowerPoint 형식을 지원하여 다양한 버전 간의 호환성을 보장합니다.
### Aspose.Slides는 선 외에 다른 모양을 추가하는 기능을 제공합니까?
전적으로! Aspose.Slides는 직사각형, 원, 화살표 등을 포함한 다양한 모양 유형을 제공합니다.
### 슬라이드에 선 모양과 함께 텍스트를 추가할 수 있나요?
예, Aspose.Slides API를 사용하여 슬라이드에 텍스트, 이미지 및 기타 콘텐츠를 추가할 수 있습니다.
### Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 다음에서 Aspose.Slides의 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

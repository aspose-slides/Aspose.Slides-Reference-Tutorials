---
title: Java에서 프리젠테이션 언어 및 도형 텍스트 설정
linktitle: Java에서 프리젠테이션 언어 및 도형 텍스트 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 자동화하는 방법을 알아보세요. 프로그래밍 방식으로 쉽게 슬라이드를 생성, 수정 및 향상할 수 있습니다.
type: docs
weight: 19
url: /ko/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---
## 소개
Java에서 프로그래밍 방식으로 PowerPoint 프레젠테이션을 만들고 조작하면 워크플로 자동화를 간소화하고 생산성을 높일 수 있습니다. Aspose.Slides for Java는 이러한 작업을 효율적으로 수행할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼은 Aspose.Slides for Java를 사용하여 프레젠테이션 언어를 설정하고 텍스트를 구성하는 필수 단계를 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- JDK(Java 개발 키트)가 설치되었습니다.
-  Aspose.Slides for Java 라이브러리는 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/)
- 시스템에 설치된 IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE)
- Java 프로그래밍 언어에 대한 기본 지식
## 패키지 가져오기
시작하려면 필요한 Aspose.Slides 패키지를 Java 파일로 가져옵니다.
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## 1단계: 프리젠테이션 개체 만들기
 초기화부터 시작하세요.`Presentation` 물체:
```java
Presentation pres = new Presentation();
```
그러면 새로운 PowerPoint 프레젠테이션이 만들어집니다.
## 2단계: 도형 추가 및 구성
다음으로 첫 번째 슬라이드에 도형을 추가하고 해당 속성을 구성합니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
여기서는 200x50 픽셀 크기의 좌표 (50, 50)에 직사각형 도형을 추가합니다.
## 3단계: 텍스트 및 언어 설정
텍스트 내용을 설정하고 맞춤법 검사를 위한 언어를 지정합니다.
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 바꾸다`"Text to apply spellcheck language"` 원하는 텍스트로. 언어 ID`"en-EN"`영어(미국)를 지정합니다.
## 4단계: 프레젠테이션 저장
수정된 프레젠테이션을 지정된 출력 디렉터리에 저장합니다.
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 반드시 교체하세요`"Your Output Directory"` 파일을 저장하려는 실제 디렉터리 경로를 사용하세요.
## 5단계: 리소스 폐기
 올바르게 폐기하십시오.`Presentation` 자원을 해제할 객체:
```java
pres.dispose();
```
이 단계는 메모리 누수를 방지하는 데 중요합니다.

## 결론
결론적으로 Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 생성하고 조작하는 프로세스를 단순화합니다. 다음 단계를 수행하면 요구 사항에 따라 프레젠테이션 언어를 효율적으로 설정하고 텍스트 속성을 구성할 수 있습니다.
## FAQ
### Aspose.Slides for Java를 사용하여 처음부터 PowerPoint 프레젠테이션을 만들 수 있나요?
예, Aspose.Slides는 완전히 프로그래밍 방식으로 프레젠테이션을 생성할 수 있는 포괄적인 API를 제공합니다.
### Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 텍스트에 다양한 글꼴을 적용하려면 어떻게 해야 합니까?
 다음을 통해 글꼴 속성을 설정할 수 있습니다.`IPortionFormat` 텍스트 부분과 관련된 개체.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 문서는 어디서 찾을 수 있나요?
 자세한 문서가 제공됩니다.[여기](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java에는 어떤 지원 옵션을 사용할 수 있나요?
 Aspose.Slides 포럼을 방문할 수 있습니다.[여기](https://forum.aspose.com/c/slides/11) 지역 사회 지원을 위해.
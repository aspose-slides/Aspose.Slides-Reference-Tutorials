---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 자동화하는 방법을 알아보세요. 프로그래밍 방식으로 슬라이드를 쉽게 만들고, 수정하고, 개선할 수 있습니다."
"linktitle": "Java에서 프레젠테이션 언어 및 모양 텍스트 설정"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java에서 프레젠테이션 언어 및 모양 텍스트 설정"
"url": "/ko/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 프레젠테이션 언어 및 모양 텍스트 설정

## 소개
Java에서 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고 조작하면 워크플로 자동화를 간소화하고 생산성을 향상시킬 수 있습니다. Aspose.Slides for Java는 이러한 작업을 효율적으로 수행할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프레젠테이션 언어와 모양 텍스트를 설정하는 필수 단계를 안내합니다.
## 필수 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
- Java Development Kit(JDK) 설치됨
- Aspose.Slides for Java 라이브러리는 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/)
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE)이 시스템에 설정되어 있습니다.
- Java 프로그래밍 언어에 대한 기본 지식
## 패키지 가져오기
시작하려면 Java 파일에 필요한 Aspose.Slides 패키지를 가져옵니다.
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## 1단계: 프레젠테이션 개체 만들기
초기화로 시작하세요 `Presentation` 물체:
```java
Presentation pres = new Presentation();
```
이렇게 하면 새로운 PowerPoint 프레젠테이션이 생성됩니다.
## 2단계: 자동 모양 추가 및 구성
다음으로, 첫 번째 슬라이드에 자동 모양을 추가하고 해당 속성을 구성합니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
여기서는 좌표 (50, 50)에 200x50픽셀 크기의 사각형 자동 모양을 추가합니다.
## 3단계: 텍스트 및 언어 설정
텍스트 내용을 설정하고 맞춤법 검사를 위한 언어를 지정합니다.
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
바꾸다 `"Text to apply spellcheck language"` 원하는 텍스트와 함께 언어 ID를 입력하세요. `"en-EN"` 영어(미국)를 지정합니다.
## 4단계: 프레젠테이션 저장
수정된 프레젠테이션을 지정된 출력 디렉토리에 저장합니다.
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
교체를 확인하세요 `"Your Output Directory"` 파일을 저장하려는 실제 디렉토리 경로를 입력하세요.
## 5단계: 리소스 폐기
적절하게 폐기하십시오 `Presentation` 리소스 해제에 대한 객체:
```java
pres.dispose();
```
이 단계는 메모리 누수를 방지하는 데 중요합니다.

## 결론
결론적으로, Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 만들고 조작하는 과정을 간소화합니다. 다음 단계를 따라 하면 프레젠테이션 언어를 효율적으로 설정하고 요구 사항에 맞게 텍스트 속성을 구성할 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 처음부터 만들 수 있나요?
네, Aspose.Slides는 완전히 프로그래밍 방식으로 프레젠테이션을 만들 수 있는 포괄적인 API를 제공합니다.
### Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드의 텍스트에 다른 글꼴을 적용하려면 어떻게 해야 합니까?
다음을 통해 글꼴 속성을 설정할 수 있습니다. `IPortionFormat` 텍스트 부분과 연관된 객체.
### Java용 Aspose.Slides의 평가판이 있나요?
네, 무료 체험판을 받으실 수 있습니다. [여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 문서는 어디에서 찾을 수 있나요?
자세한 문서가 제공됩니다. [여기](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java에는 어떤 지원 옵션이 있나요?
Aspose.Slides 포럼을 방문할 수 있습니다. [여기](https://forum.aspose.com/c/slides/11) 지역사회 지원을 위해.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
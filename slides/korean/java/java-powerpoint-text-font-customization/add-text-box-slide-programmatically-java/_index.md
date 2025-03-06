---
title: Java를 사용하여 프로그래밍 방식으로 슬라이드에 텍스트 상자 추가
linktitle: Java를 사용하여 프로그래밍 방식으로 슬라이드에 텍스트 상자 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 PowerPoint 슬라이드에 텍스트 상자를 추가하는 방법을 알아보세요. 이 단계별 가이드를 통해 생산성을 향상하세요.
weight: 24
url: /ko/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 프로그래밍 방식으로 슬라이드에 텍스트 상자 추가

## 소개
프로그래밍 방식으로 PowerPoint 프레젠테이션을 만들고 조작하면 보고서 생성에서 프레젠테이션 자동화에 이르기까지 다양한 작업 흐름을 간소화할 수 있습니다. Aspose.Slides for Java는 개발자가 이러한 작업을 효율적으로 수행할 수 있는 강력한 API를 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 슬라이드에 텍스트 상자를 추가하는 방법을 안내합니다. 이 튜토리얼이 끝나면 이 기능을 Java 애플리케이션에 통합하는 방법을 명확하게 이해하게 될 것입니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- JDK(Java 개발 키트)가 설치되었습니다.
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(통합 개발 환경)
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/)
- Java 프로그래밍에 대한 기본 지식
## 패키지 가져오기
먼저 Aspose.Slides 및 Java 코어 라이브러리에서 필요한 패키지를 가져와 코딩을 시작합니다.
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1단계: 프로젝트 설정
IDE에서 새 Java 프로젝트를 만들고 프로젝트의 빌드 경로에 Aspose.Slides for Java 라이브러리를 추가하세요. 아직 다운로드하지 않으셨다면, 아래에서 다운로드 받으세요.[여기](https://releases.aspose.com/slides/java/).
## 2단계: 프레젠테이션 개체 초기화
 초기화`Presentation` PowerPoint 파일을 나타내는 개체입니다.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 3단계: 슬라이드에 액세스하고 도형 추가
프레젠테이션에서 첫 번째 슬라이드를 가져와 여기에 AutoShape(사각형)를 추가합니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## 4단계: 도형에 텍스트 프레임 추가
텍스트를 포함할 도형에 텍스트 프레임을 추가합니다.
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## 5단계: 텍스트 내용 설정
텍스트 프레임 내부에 텍스트 내용을 설정합니다.
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## 6단계: 프레젠테이션 저장
수정된 프레젠테이션을 파일에 저장합니다.
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 슬라이드에 텍스트 상자를 추가하는 방법을 살펴보았습니다. 이 기능을 통해 개발자는 PowerPoint 프레젠테이션의 생성 및 사용자 정의를 자동화하여 다양한 응용 프로그램의 생산성과 효율성을 향상시킬 수 있습니다.
## FAQ
### Aspose.Slides for Java는 직사각형 외에 다른 모양도 처리할 수 있나요?
예, Aspose.Slides는 원, 선 등과 같은 다양한 모양을 지원합니다.
### Aspose.Slides for Java는 대규모 엔터프라이즈 애플리케이션에 적합합니까?
물론 복잡한 작업을 효율적으로 처리하도록 설계되었습니다.
### Aspose.Slides에 대한 추가 예제와 문서는 어디서 찾을 수 있나요?
 방문하다[Aspose.Slides 문서](https://reference.aspose.com/slides/java/) 포괄적인 가이드와 예시를 보려면
### 테스트용 임시 라이센스를 어떻게 얻을 수 있나요?
 당신은 얻을 수 있습니다[임시면허](https://purchase.aspose.com/temporary-license/) Aspose에서.
### Aspose.Slides는 프레젠테이션을 다른 형식으로 변환하는 것을 지원합니까?
예, PDF, 이미지 등 다양한 형식을 지원합니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

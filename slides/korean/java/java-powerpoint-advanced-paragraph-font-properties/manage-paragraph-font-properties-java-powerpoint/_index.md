---
title: Java PowerPoint에서 단락 글꼴 속성 관리
linktitle: Java PowerPoint에서 단락 글꼴 속성 관리
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 따라하기 쉬운 단계별 가이드를 통해 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션의 단락 글꼴 속성을 관리하고 사용자 정의하는 방법을 알아보세요.
weight: 10
url: /ko/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-font-properties-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 단락 글꼴 속성 관리

## 소개
시각적으로 매력적인 PowerPoint 프레젠테이션을 만드는 것은 효과적인 의사소통에 매우 중요합니다. 사업 제안서를 준비하든 학교 프로젝트를 준비하든 올바른 글꼴 속성을 사용하면 슬라이드를 더욱 매력적으로 만들 수 있습니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 단락 글꼴 속성을 관리하는 방법을 안내합니다. 다이빙할 준비가 되셨나요? 시작하자!
## 전제 조건
시작하기 전에 다음이 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK 8 이상이 설치되어 있는지 확인하십시오.
2.  Java용 Aspose.Slides: 다운로드 및 설치[Aspose.Slides for Java](https://releases.aspose.com/slides/java/) 도서관.
3. 통합 개발 환경(IDE): 더 나은 코드 관리를 위해 Eclipse 또는 IntelliJ IDEA와 같은 IDE를 사용합니다.
4. 프리젠테이션 파일: 글꼴 변경 사항을 적용하기 위한 파워포인트 파일(PPTX)입니다. 샘플 파일이 없으면 샘플 파일을 만듭니다.

## 패키지 가져오기
먼저 Java 프로그램에 필요한 패키지를 가져옵니다.
```java
import com.aspose.slides.*;
import java.awt.*;
```
프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 프레젠테이션 로드
먼저 Aspose.Slides를 사용하여 PowerPoint 프레젠테이션을 로드하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 인스턴스화
Presentation presentation = new Presentation(dataDir + "DefaultFonts.pptx");
```
## 2단계: 슬라이드 및 셰이프에 액세스
그런 다음 글꼴 속성을 수정하려는 특정 슬라이드와 도형에 액세스합니다.
```java
// 슬라이드 위치를 사용하여 슬라이드에 액세스
ISlide slide = presentation.getSlides().get_Item(0);
// 슬라이드의 첫 번째 및 두 번째 자리 표시자에 액세스하고 이를 도형으로 유형 변환
ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();
```
## 3단계: 단락 및 부분에 액세스
이제 텍스트 프레임 내의 단락과 부분에 액세스하여 글꼴 속성을 변경합니다.
```java
// 첫 번째 단락에 액세스하기
IParagraph para1 = tf1.getParagraphs().get_Item(0);
IParagraph para2 = tf2.getParagraphs().get_Item(0);
// 첫 번째 부분에 접근하기
IPortion port1 = para1.getPortions().get_Item(0);
IPortion port2 = para2.getPortions().get_Item(0);
```
## 4단계: 단락 정렬 설정
필요에 따라 단락 정렬을 조정합니다. 여기서는 두 번째 단락을 정당화하겠습니다.
```java
// 단락 정렬
para2.getParagraphFormat().setAlignment(TextAlignment.JustifyLow);
```
## 5단계: 새 글꼴 정의
텍스트 부분에 사용할 새 글꼴을 지정합니다.
```java
// 새 글꼴 정의
FontData fd1 = new FontData("Elephant");
FontData fd2 = new FontData("Castellar");
```
## 6단계: 부분에 글꼴 할당
해당 부분에 새 글꼴을 적용합니다.
```java
//부분에 새 글꼴 할당
port1.getPortionFormat().setLatinFont(fd1);
port2.getPortionFormat().setLatinFont(fd2);
```
## 7단계: 글꼴 스타일 설정
글꼴을 볼드체와 이탤릭체로 설정할 수도 있습니다.
```java
// 글꼴을 굵게 설정
port1.getPortionFormat().setFontBold(NullableBool.True);
port2.getPortionFormat().setFontBold(NullableBool.True);
// 글꼴을 기울임꼴로 설정
port1.getPortionFormat().setFontItalic(NullableBool.True);
port2.getPortionFormat().setFontItalic(NullableBool.True);
```
## 8단계: 글꼴 색상 변경
마지막으로 글꼴 색상을 변경하여 텍스트를 시각적으로 매력적으로 만드세요.
```java
// 글꼴 색상 설정
port1.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port1.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
port2.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
port2.getPortionFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Peru));
```
## 9단계: 프레젠테이션 저장
모든 변경을 완료한 후 프레젠테이션을 저장하세요.
```java
// PPTX를 디스크에 쓰기
presentation.save(dataDir + "ManagParagraphFontProperties_out.pptx", SaveFormat.Pptx);
```
## 10단계: 정리
리소스를 확보하려면 프레젠테이션 개체를 삭제하는 것을 잊지 마세요.
```java
if (presentation != null) presentation.dispose();
```
## 결론
거기 있어요! 다음 단계를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 단락 글꼴 속성을 쉽게 관리할 수 있습니다. 이는 시각적 매력을 향상시킬 뿐만 아니라 콘텐츠가 매력적이고 전문적이라는 것을 보장합니다. 즐거운 코딩하세요!
## FAQ
### Java용 Aspose.Slides에서 사용자 정의 글꼴을 사용할 수 있나요?
예, 코드에서 글꼴 데이터를 지정하여 사용자 정의 글꼴을 사용할 수 있습니다.
### 단락의 글꼴 크기를 어떻게 변경합니까?
다음을 사용하여 글꼴 크기를 설정할 수 있습니다.`setFontHeight` 부분의 형식에 대한 메소드입니다.
### 같은 문단의 다른 부분에 다른 글꼴을 적용할 수 있나요?
예, 단락의 각 부분은 고유한 글꼴 속성을 가질 수 있습니다.
### 텍스트에 그라데이션 색상을 적용할 수 있나요?
예, Java용 Aspose.Slides는 텍스트에 대한 그라데이션 채우기를 지원합니다.
### 변경 사항을 취소하고 싶으면 어떻게 하나요?
변경하기 전에 원본 프레젠테이션을 다시 로드하거나 백업을 보관하세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

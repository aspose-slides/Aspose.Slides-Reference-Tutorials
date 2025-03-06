---
title: Java PowerPoint에서 대체 글꼴을 사용하여 렌더링
linktitle: Java PowerPoint에서 대체 글꼴을 사용하여 렌더링
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에서 대체 글꼴로 텍스트를 렌더링하는 방법을 알아보세요. 원활한 구현을 위해 이 단계별 가이드를 따르세요.
weight: 13
url: /ko/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
Java로 PowerPoint 프레젠테이션을 만들고 조작하는 것은 어려울 수 있지만 Aspose.Slides를 사용하면 이 작업을 효율적으로 수행할 수 있습니다. 중요한 기능 중 하나는 대체 글꼴을 사용하여 텍스트를 렌더링하는 기능입니다. 이 문서에서는 Aspose.Slides for Java를 사용하여 PowerPoint 슬라이드에 대체 글꼴을 구현하는 방법에 대한 자세한 단계별 가이드를 제공합니다.
## 전제 조건
구현을 시작하기 전에 필요한 모든 것이 갖추어져 있는지 확인하십시오.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Slides for Java: 다음에서 다운로드할 수 있습니다.[Aspose.Slides for Java 다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 IDE는 개발 프로세스를 더욱 원활하게 만들어줍니다.
4. 종속성: 프로젝트 종속성에 Aspose.Slides를 포함합니다.
## 패키지 가져오기
먼저 Java 프로그램에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
프로세스를 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
 코드를 작성하기 전에 프로젝트가 올바르게 설정되었는지 확인하세요. 여기에는 프로젝트에 Aspose.Slides 라이브러리를 추가하는 것이 포함됩니다. 다음에서 라이브러리를 다운로드하면 됩니다.[Java용 Aspose.Slides](https://releases.aspose.com/slides/java/) 빌드 경로에 추가합니다.
## 2단계: 글꼴 대체 규칙 초기화
 다음의 인스턴스를 생성해야 합니다.`IFontFallBackRulesCollection` 클래스를 만들고 규칙을 추가합니다. 이러한 규칙은 특정 유니코드 범위에 대한 글꼴 대체를 정의합니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 규칙 컬렉션의 새 인스턴스 만들기
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// 여러 가지 규칙을 만들어 보세요
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## 3단계: 대체 규칙 수정
이 단계에서는 기존 대체 글꼴을 제거하고 특정 유니코드 범위에 대한 규칙을 업데이트하여 대체 규칙을 수정합니다.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // 로드된 규칙에서 FallBack 글꼴 "Tahoma"를 제거하려고 합니다.
    fallBackRule.remove("Tahoma");
    // 지정된 범위에 대한 업데이트 규칙
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//목록에서 기존 규칙을 제거합니다.
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## 4단계: 프레젠테이션 로드
수정하려는 PowerPoint 프레젠테이션을 로드합니다.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## 5단계: 프레젠테이션에 대체 규칙 할당
프레젠테이션의 글꼴 관리자에 준비된 대체 규칙을 할당합니다.
```java
try {
    // 사용을 위해 준비된 규칙 목록 할당
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // 초기화된 규칙 컬렉션을 사용하여 썸네일 렌더링 및 PNG에 저장
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 6단계: 저장 및 테스트
마지막으로 작업을 저장하고 구현을 테스트하여 모든 것이 예상대로 작동하는지 확인합니다. 문제가 발생하면 설정을 다시 확인하고 모든 종속성이 올바르게 추가되었는지 확인하세요.
## 결론
이 가이드를 따르면 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 대체 글꼴로 텍스트를 효율적으로 렌더링할 수 있습니다. 이 프로세스를 통해 기본 글꼴을 사용할 수 없는 경우에도 프레젠테이션의 서식이 일관되게 유지됩니다. 즐거운 코딩하세요!
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 개발자가 Java 애플리케이션에서 PowerPoint 프레젠테이션을 생성, 수정 및 렌더링할 수 있는 라이브러리입니다.
### 내 프로젝트에 Aspose.Slides를 어떻게 추가하나요?
 라이브러리는 다음에서 다운로드할 수 있습니다.[Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/) 프로젝트의 빌드 경로에 추가하세요.
### 대체 글꼴이란 무엇입니까?
대체 글꼴은 지정된 글꼴을 사용할 수 없거나 특정 문자를 지원하지 않을 때 사용되는 대체 글꼴입니다.
### 여러 대체 규칙을 사용할 수 있나요?
예, 여러 대체 규칙을 추가하여 다양한 유니코드 범위 및 글꼴을 처리할 수 있습니다.
### Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Slides 지원 포럼](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

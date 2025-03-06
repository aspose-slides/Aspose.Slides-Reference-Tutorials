---
title: Java를 사용하여 PowerPoint에 포함된 글꼴 추가
linktitle: Java를 사용하여 PowerPoint에 포함된 글꼴 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java와 함께 Java를 사용하여 PowerPoint 프레젠테이션에 포함된 글꼴을 추가하는 방법을 알아보세요. 여러 장치에서 일관된 디스플레이를 보장합니다.
type: docs
weight: 10
url: /ko/java/java-powerpoint-font-management/add-embedded-fonts-powerpoint-java/
---
## 소개
이 튜토리얼에서는 Java를 사용하고 특히 Aspose.Slides for Java를 활용하여 PowerPoint 프레젠테이션에 포함된 글꼴을 추가하는 과정을 안내합니다. 포함된 글꼴을 사용하면 원본 글꼴을 사용할 수 없는 경우에도 프레젠테이션이 다양한 장치에서 일관되게 표시됩니다. 다음 단계를 살펴보겠습니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요.
2.  Aspose.Slides for Java 라이브러리: Aspose.Slides for Java 라이브러리를 다운로드하고 설치하세요. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/slides/java/).

## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져옵니다.
```java
import com.aspose.slides.*;
```
## 1단계: 프레젠테이션 로드
먼저 포함된 글꼴을 추가하려는 PowerPoint 프레젠테이션을 로드합니다.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Fonts.pptx");
```
## 2단계: 소스 글꼴 로드
다음으로 프레젠테이션에 포함하려는 글꼴을 로드합니다. 여기서는 Arial을 예로 사용합니다.
```java
IFontData sourceFont = new FontData("Arial");
```
## 3단계: 포함된 글꼴 추가
프레젠테이션에 사용된 모든 글꼴을 반복하고 포함되지 않은 글꼴을 추가합니다.
```java
IFontData[] allFonts = presentation.getFontsManager().getFonts();
IFontData[] embeddedFonts = presentation.getFontsManager().getEmbeddedFonts();
for (IFontData font : allFonts) {
    boolean embeddedFontsContainsFont = false;
    for (int i = 0; i < embeddedFonts.length; i++) {
        if (embeddedFonts[i].equals(font)) {
            embeddedFontsContainsFont = true;
            break;
        }
    }
    if (!embeddedFontsContainsFont) {
        presentation.getFontsManager().addEmbeddedFont(font, EmbedFontCharacters.All);
        embeddedFonts = presentation.getFontsManager().getEmbeddedFonts();
    }
}
```
## 4단계: 프레젠테이션 저장
마지막으로 포함된 글꼴을 사용하여 프레젠테이션을 저장합니다.
```java
presentation.save(dataDir + "AddEmbeddedFont_out.pptx", SaveFormat.Pptx);
```
축하해요! Java를 사용하여 PowerPoint 프레젠테이션에 글꼴을 성공적으로 포함했습니다.

## 결론
PowerPoint 프레젠테이션에 포함된 글꼴을 추가하면 다양한 장치에서 일관된 표시가 보장되어 청중에게 원활한 보기 환경을 제공합니다. Aspose.Slides for Java를 사용하면 프로세스가 간단하고 효율적이 됩니다.
## FAQ
### PowerPoint 프레젠테이션에 포함된 글꼴이 중요한 이유는 무엇입니까?
포함된 글꼴을 사용하면 보기 장치에서 원본 글꼴을 사용할 수 없는 경우에도 프레젠테이션의 서식과 스타일이 유지됩니다.
### Aspose.Slides for Java를 사용하여 단일 프레젠테이션에 여러 글꼴을 포함할 수 있나요?
예, 프레젠테이션에 사용된 모든 글꼴을 반복하고 포함되지 않은 글꼴을 포함하여 여러 글꼴을 포함할 수 있습니다.
### 글꼴을 포함하면 프레젠테이션 파일 크기가 늘어나나요?
예, 글꼴을 포함하면 프레젠테이션의 파일 크기가 약간 늘어날 수 있지만 다양한 장치에서 일관된 표시가 보장됩니다.
### 포함할 수 있는 글꼴 유형에 제한이 있나요?
Aspose.Slides for Java는 프레젠테이션에 일반적으로 사용되는 광범위한 글꼴을 포함하는 트루타입 글꼴 포함을 지원합니다.
### Aspose.Slides for Java를 사용하여 프로그래밍 방식으로 글꼴을 포함할 수 있나요?
예, 이 튜토리얼에서 설명했듯이 Aspose.Slides for Java API를 사용하여 프로그래밍 방식으로 글꼴을 포함할 수 있습니다.
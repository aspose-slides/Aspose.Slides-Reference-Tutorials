---
title: Java PowerPoint에서 포함된 글꼴 관리
linktitle: Java PowerPoint에서 포함된 글꼴 관리
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에 포함된 글꼴을 손쉽게 관리하세요. 일관성을 위해 슬라이드를 최적화하기 위한 단계별 가이드입니다.
weight: 11
url: /ko/java/java-powerpoint-font-management-text-replacement/manage-embedded-fonts-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
끊임없이 진화하는 프레젠테이션 세계에서 글꼴을 효율적으로 관리하면 PowerPoint 파일의 품질과 호환성에 큰 변화를 가져올 수 있습니다. Aspose.Slides for Java는 포함된 글꼴을 관리하는 포괄적인 솔루션을 제공하여 프레젠테이션이 모든 장치에서 완벽하게 보이도록 보장합니다. 레거시 프레젠테이션을 다루든 새로운 프레젠테이션을 만들든 이 가이드는 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에 포함된 글꼴을 관리하는 과정을 안내합니다. 뛰어들어보자!
## 전제 조건
시작하기 전에 다음 설정이 있는지 확인하세요.
- JDK(Java Development Kit): 컴퓨터에 JDK 8 이상이 설치되어 있는지 확인하세요.
-  Java용 Aspose.Slides: 다음에서 라이브러리를 다운로드하세요.[Java용 Aspose.Slides](https://releases.aspose.com/slides/java/).
- IDE: IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경입니다.
- 프리젠테이션 파일: 글꼴이 포함된 샘플 PowerPoint 파일입니다. 이 튜토리얼에서는 "EmbeddedFonts.pptx"를 사용할 수 있습니다.
- 종속성: Java용 Aspose.Slides를 프로젝트 종속성에 추가합니다.
## 패키지 가져오기
먼저 Java 프로젝트에서 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.IFontData;
import com.aspose.slides.IFontsManager;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
예제를 자세한 단계별 가이드로 나누어 보겠습니다.
## 1단계: 프로젝트 디렉터리 설정
시작하기 전에 PowerPoint 파일과 출력 이미지를 저장할 프로젝트 디렉터리를 설정하세요.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 2단계: 프레젠테이션 로드
 인스턴스화`Presentation` PowerPoint 파일을 나타내는 개체입니다.
```java
Presentation presentation = new Presentation(dataDir + "EmbeddedFonts.pptx");
```
## 3단계: 포함된 글꼴을 사용하여 슬라이드 렌더링
포함된 글꼴을 사용하여 텍스트 프레임이 포함된 슬라이드를 렌더링하고 이미지로 저장합니다.
```java
try {
    // 첫 번째 슬라이드를 이미지로 렌더링
    BufferedImage image1 = presentation.getSlides().get_Item(0).getThumbnail(new Dimension(960, 720));
    ImageIO.write(image1, ".png", new File(dataDir + "picture1_out.png"));
```
## 4단계: 글꼴 관리자에 액세스
 받기`IFontsManager` 프레젠테이션에서 인스턴스를 가져와 글꼴을 관리합니다.
```java
    IFontsManager fontsManager = presentation.getFontsManager();
```
## 5단계: 포함된 글꼴 검색
프레젠테이션에 포함된 모든 글꼴을 가져옵니다.
```java
    // 모든 포함된 글꼴 가져오기
    IFontData[] embeddedFonts = fontsManager.getEmbeddedFonts();
```
## 6단계: 특정 포함된 글꼴 찾기 및 제거
프레젠테이션에서 특정 포함 글꼴(예: "Calibri")을 식별하고 제거합니다.
```java
    //"Calibri" 글꼴 찾기
    IFontData funSizedEmbeddedFont = null;
    for (IFontData embeddedFont : embeddedFonts) {
        if ("Calibri".equals(embeddedFont.getFontName())) {
            funSizedEmbeddedFont = embeddedFont;
            break;
        }
    }
    // "Calibri" 글꼴 제거
    if (funSizedEmbeddedFont != null) fontsManager.removeEmbeddedFont(funSizedEmbeddedFont);
```
## 7단계: 슬라이드 다시 렌더링
포함된 글꼴을 제거한 후 변경 사항을 확인하려면 슬라이드를 다시 렌더링하십시오.
```java
    // 첫 번째 슬라이드를 다시 렌더링하여 변경 사항 확인
    BufferedImage image2 = presentation.getSlides().get_Item(0).getThumbnail(new Dimension(960, 720));
    ImageIO.write(image2, ".png", new File(dataDir + "picture2_out.png"));
```
## 8단계: 업데이트된 프레젠테이션 저장
포함된 글꼴 없이 수정된 프리젠테이션 파일을 저장합니다.
```java
    // 포함된 "Calibri" 글꼴 없이 프레젠테이션을 저장합니다.
    presentation.save(dataDir + "WithoutManageEmbeddedFonts_out.ppt", SaveFormat.Ppt);
}
finally {
    if (presentation != null) presentation.dispose();
}
```
## 결론
PowerPoint 프레젠테이션에 포함된 글꼴을 관리하는 것은 다양한 장치와 플랫폼에서 일관성과 호환성을 유지하는 데 중요합니다. Aspose.Slides for Java를 사용하면 이 프로세스가 간단하고 효율적이 됩니다. 이 가이드에 설명된 단계를 따르면 프레젠테이션에 포함된 글꼴을 쉽게 제거하거나 관리하여 어디에서 보든 원하는 대로 정확하게 표시되도록 할 수 있습니다.
## FAQ
### Java용 Aspose.Slides란 무엇입니까?
Aspose.Slides for Java는 Java로 된 PowerPoint 프레젠테이션 작업을 위한 강력한 라이브러리입니다. 이를 통해 프로그래밍 방식으로 프레젠테이션을 생성, 수정 및 관리할 수 있습니다.
### 내 프로젝트에 Aspose.Slides를 어떻게 추가하나요?
 Aspose.Slides를 다운로드하여 프로젝트에 추가할 수 있습니다.[웹사이트](https://releases.aspose.com/slides/java/) 이를 프로젝트 종속성에 포함시킵니다.
### 모든 버전의 Java에서 Aspose.Slides for Java를 사용할 수 있나요?
Aspose.Slides for Java는 JDK 8 이상 버전과 호환됩니다.
### 프레젠테이션에 포함된 글꼴을 관리하면 어떤 이점이 있나요?
포함된 글꼴을 관리하면 프레젠테이션이 다양한 장치와 플랫폼에서 일관되게 표시되고 불필요한 글꼴을 제거하여 파일 크기를 줄이는 데 도움이 됩니다.
### Java용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 에서 지원을 받으실 수 있습니다.[Aspose.Slides 지원 포럼](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

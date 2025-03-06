---
title: Aspose.Slides for Java를 사용하는 PowerPoint의 기본 글꼴
linktitle: Aspose.Slides for Java를 사용하는 PowerPoint의 기본 글꼴
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 기본 글꼴을 설정하는 방법을 알아보세요. 일관성을 보장하고 시각적 매력을 쉽게 향상할 수 있습니다.
weight: 11
url: /ko/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java를 사용하는 PowerPoint의 기본 글꼴

## 소개
사용자 정의 글꼴을 사용하여 PowerPoint 프레젠테이션을 만드는 것은 많은 프로젝트에서 일반적인 요구 사항입니다. Aspose.Slides for Java는 기본 글꼴을 관리하는 원활한 솔루션을 제공하여 다양한 환경에서 일관성을 보장합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 기본 글꼴을 설정하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Java용 Aspose.Slides: 다음 사이트에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 기본 Java 지식: Java 프로그래밍 언어 기본 사항에 익숙합니다.

## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져오는 것부터 시작하세요.
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1단계: 기본 글꼴 설정
문서 디렉토리 경로를 정의하고 기본 일반 글꼴과 아시아 글꼴을 지정하는 로드 옵션을 만듭니다.
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## 2단계: 프레젠테이션 로드
정의된 로드 옵션을 사용하여 PowerPoint 프레젠테이션을 로드합니다.
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## 3단계: 출력 생성
슬라이드 축소판, PDF, XPS 파일과 같은 다양한 출력을 생성합니다.
```java
try {
    // 슬라이드 축소판 생성
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // PDF 생성
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // XPS 생성
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 기본 글꼴을 설정하는 것은 간단하고 효율적입니다. 이 튜토리얼에 설명된 단계를 따르면 다양한 플랫폼과 환경에서 글꼴 스타일의 일관성을 보장하여 프레젠테이션의 시각적 매력을 향상시킬 수 있습니다.
## FAQ
### Java용 Aspose.Slides에서 사용자 정의 글꼴을 사용할 수 있나요?
예, Aspose.Slides for Java를 사용하여 프레젠테이션에 사용자 정의 글꼴을 지정할 수 있습니다.
### Aspose.Slides for Java는 모든 버전의 PowerPoint와 호환됩니까?
Aspose.Slides for Java는 다양한 PowerPoint 버전을 지원하여 다양한 환경에서의 호환성을 보장합니다.
### Java용 Aspose.Slides에 대한 지원을 어떻게 받을 수 있나요?
 다음을 통해 Java용 Aspose.Slides에 대한 지원을 받을 수 있습니다.[포럼을 Aspose](https://forum.aspose.com/c/slides/11).
### 구매하기 전에 Java용 Aspose.Slides를 사용해 볼 수 있나요?
 예, 다음에서 제공되는 무료 평가판을 통해 Aspose.Slides for Java를 탐색할 수 있습니다.[releases.aspose.com](https://releases.aspose.com/).
### Aspose.Slides for Java의 임시 라이선스는 어디서 얻을 수 있나요?
 Aspose.Slides for Java에 대한 임시 라이선스는 다음 사이트에서 얻을 수 있습니다.[구매 페이지](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

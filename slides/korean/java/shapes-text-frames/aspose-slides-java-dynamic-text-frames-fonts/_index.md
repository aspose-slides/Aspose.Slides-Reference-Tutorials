---
"date": "2025-04-18"
"description": "Aspose.Slides for Java를 사용하여 프레젠테이션을 자동화하는 방법을 알아보세요. 텍스트 프레임과 글꼴 스타일을 동적으로 사용자 정의하여 비즈니스 프레젠테이션이나 교육 강의에 적합합니다."
"title": "Aspose.Slides for Java 동적 텍스트 프레임 및 글꼴 사용자 정의 가이드"
"url": "/ko/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java용 Aspose.Slides: 동적 텍스트 프레임 및 글꼴 스타일 마스터하기

오늘날의 디지털 환경에서 효과적인 커뮤니케이션을 위해서는 매력적인 프레젠테이션을 만드는 것이 필수적입니다. 비즈니스 프레젠테이션이든 학술 강연이든 마찬가지입니다. Java를 사용하여 이러한 작업을 자동화하고 맞춤 설정하면 생산성을 높일 수 있습니다. **Java용 Aspose.Slides**— 개발자가 프레젠테이션을 쉽게 만들고, 수정하고, 저장할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 프레젠테이션에서 동적 텍스트 프레임을 만들고 글꼴 스타일을 사용자 지정하는 방법을 안내합니다.

## 당신이 배울 것
- Java용 Aspose.Slides를 사용하여 환경 설정하기.
- 프레젠테이션을 만들고 텍스트 프레임으로 자동 모양을 추가합니다.
- 텍스트 프레임에 텍스트의 일부를 추가합니다.
- 기본 텍스트 스타일과 문단 글꼴 높이를 사용자 지정합니다.
- 특정 부분의 글꼴 높이를 설정합니다.
- 최종 프레젠테이션을 저장합니다.

이러한 기능을 효과적으로 활용하는 방법을 살펴보겠습니다!

### 필수 조건

시작하기 전에 개발 환경이 준비되었는지 확인하세요. 필요한 사항은 다음과 같습니다.

- **자바 개발 키트(JDK):** 버전 8 이상
- **Maven/Gradle:** 종속성 관리를 위해
- **선택한 IDE:** IntelliJ IDEA, Eclipse 또는 NetBeans와 같은
- Java 프로그래밍 개념에 대한 기본 이해

### Java용 Aspose.Slides 설정

Java용 Aspose.Slides를 사용하려면 프로젝트에 포함하세요. 방법은 다음과 같습니다.

#### Maven 설정

다음 종속성을 추가하세요. `pom.xml` 파일:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle 설정

Gradle의 경우 다음을 추가하세요. `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### 직접 다운로드

또는 다음에서 최신 릴리스를 다운로드하세요. [Java용 Aspose.Slides 릴리스](https://releases.aspose.com/slides/java/).

**라이센스 취득:** 무료 체험판을 이용하거나 임시 라이선스를 구매하여 제한 없이 모든 기능을 사용해 보세요. 구매하려면 여기를 방문하세요. [Aspose 구매 페이지](https://purchase.aspose.com/buy).

### 구현 가이드

#### 기능 1: 프레젠테이션 만들기 및 텍스트 프레임 추가

프레젠테이션을 만들고 텍스트 프레임이 있는 자동 모양을 추가하려면:

**개요:** 이 기능은 새로운 프레젠테이션을 초기화하고 첫 번째 슬라이드에 텍스트 프레임을 포함한 사각형 모양을 추가합니다.

```java
import com.aspose.slides.*;

public class Feature1 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            newShape.addTextFrame("");
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().clear();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:** 우리는 초기화합니다 `Presentation` 개체를 선택하고 첫 번째 슬라이드에 자동 모양을 추가합니다. 모양은 지정된 크기의 사각형으로 설정됩니다.

#### 기능 2: 텍스트 프레임에 부분 추가

문단에 텍스트 부분을 추가하려면:

**개요:** 이 기능은 텍스트 프레임의 문단 내에 여러 텍스트 부분을 추가하는 방법을 보여줍니다.

```java
import com.aspose.slides.*;

public class Feature2 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = (IAutoShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            
            IPortion portion0 = new Portion("Sample text with first portion");
            IPortion portion1 = new Portion(" and second portion.");

            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:** 텍스트 부분을 만들어 도형의 텍스트 프레임의 첫 번째 문단에 추가합니다.

#### 기능 3: 기본 텍스트 스타일 글꼴 높이 설정

모든 텍스트에 기본 글꼴 높이를 설정하려면:

**개요:** 이 기능은 프레젠테이션 전체의 기본 글꼴 크기를 수정합니다.

```java
import com.aspose.slides.*;

public class Feature3 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:** 기본 텍스트 스타일 글꼴 높이는 프레젠테이션 전체에 걸쳐 24포인트로 설정됩니다.

#### 기능 4: 문단 기본 글꼴 높이 설정

특정 문단 내에서 글꼴 높이를 사용자 지정하려면:

**개요:** 이 기능은 특정 문단의 기본 부분 형식에 사용자 지정 글꼴 크기를 적용합니다.

```java
import com.aspose.slides.*;

public class Feature4 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = (IAutoShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            
            newShape.getTextFrame().getParagraphs().get_Item(0)
                .getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:** 우리는 도형의 첫 번째 문단에 있는 모든 텍스트의 글꼴 높이를 40포인트로 설정했습니다.

#### 기능 5: 특정 부분 글꼴 높이 설정

개별 부분의 글꼴 높이를 조정하려면:

**개요:** 이 기능을 사용하면 문단 내 특정 부분의 글꼴 크기를 사용자 지정할 수 있습니다.

```java
import com.aspose.slides.*;

public class Feature5 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            IAutoShape newShape = (IAutoShape)pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle, 100, 100, 400, 75, false);
            
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0)
                .getPortionFormat().setFontHeight(55);
            
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1)
                .getPortionFormat().setFontHeight(18);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:** 문단 내 특정 텍스트 부분에 사용자 정의 글꼴 높이를 설정하여 시각적 계층 구조를 향상시킵니다.

#### 기능 6: 프레젠테이션 저장

프레젠테이션을 저장하려면:

**개요:** 이 기능은 프레젠테이션을 원하는 파일 형식과 위치에 저장하는 방법을 보여줍니다.

```java
import com.aspose.slides.*;

public class Feature6 {
    public static void main(String[] args) {
        Presentation pres = new Presentation();
        try {
            String outputDir = "YOUR_OUTPUT_DIRECTORY"; // 이것을 실제 디렉토리 경로로 바꿔야 합니다.
            pres.save(outputDir + "SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**설명:** 프레젠테이션은 지정된 디렉토리에 PPTX 형식으로 저장됩니다.

### 실제 응용 프로그램

1. **기업 프레젠테이션:** 분기별 보고서를 위해 동적 텍스트와 스타일을 적용한 슬라이드 생성을 자동화합니다.
2. **교육 강의:** 더 나은 가독성을 위해 글꼴 스타일과 크기를 사용자 정의하여 교육 자료를 개선하세요.
3. **사업 제안:** 청중의 참여를 효과적으로 유도하기 위해 텍스트 요소를 정밀하게 제어하여 인상적인 프레젠테이션을 만들어 보세요.

### 결론

Aspose.Slides for Java를 마스터하면 프레젠테이션 제작 프로세스를 크게 향상시킬 수 있습니다. 텍스트 프레임 사용자 지정을 자동화하면 시간을 절약할 수 있을 뿐만 아니라 다양한 슬라이드와 프로젝트에서 일관성을 유지할 수 있습니다. 이 튜토리얼에서 습득한 기술을 바탕으로 다양한 프레젠테이션 요구 사항을 쉽게 해결할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
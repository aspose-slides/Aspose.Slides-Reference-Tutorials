---
title: Java PowerPoint에서 글꼴 대체 설정
linktitle: Java PowerPoint에서 글꼴 대체 설정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: 일관된 텍스트 표시를 보장하기 위해 Java용 Aspose.Slides를 사용하여 Java PowerPoint에서 글꼴 대체를 설정하는 방법을 알아보세요.
weight: 16
url: /ko/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 글꼴 대체 설정의 복잡성을 자세히 살펴보겠습니다. 글꼴 대체는 필요한 글꼴을 사용할 수 없는 경우에도 프레젠테이션의 텍스트가 다양한 장치 및 운영 체제에서 올바르게 표시되도록 하는 데 중요합니다.
## 전제 조건
시작하기 전에 다음 사항이 있는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- Java 프로그래밍 언어에 대한 기본 이해.
- IntelliJ IDEA 또는 Eclipse와 같은 IDE(통합 개발 환경)

## 패키지 가져오기
먼저 Java 클래스에 필요한 Java용 Aspose.Slides 패키지를 포함합니다.
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## 1단계: 글꼴 대체 규칙 초기화
글꼴 대체를 설정하려면 유니코드 범위와 해당 대체 글꼴을 지정하는 규칙을 정의해야 합니다. 이러한 규칙을 초기화하는 방법은 다음과 같습니다.
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## 2단계: 글꼴 대체 규칙 적용
다음으로 글꼴 대체를 설정해야 하는 프레젠테이션이나 슬라이드에 이러한 규칙을 적용합니다. 다음은 PowerPoint 프레젠테이션의 슬라이드에 이러한 규칙을 적용하는 예입니다.
```java
// 슬라이드가 슬라이드 개체라고 가정
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## 결론
Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 글꼴 대체를 설정하는 것은 다양한 환경에서 일관된 텍스트 표시를 보장하는 데 필수적입니다. 이 튜토리얼에 설명된 대로 대체 규칙을 정의하면 특정 글꼴을 사용할 수 없는 상황을 처리하고 프레젠테이션의 무결성을 유지할 수 있습니다.

## FAQ
### PowerPoint 프레젠테이션의 글꼴 대체란 무엇입니까?
글꼴 대체는 설치되지 않은 글꼴을 사용 가능한 글꼴로 대체하여 텍스트가 올바르게 표시되도록 합니다.
### Java용 Aspose.Slides를 어떻게 다운로드할 수 있나요?
 Java용 Aspose.Slides를 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
### Aspose.Slides for Java는 모든 Java IDE와 호환됩니까?
예, Aspose.Slides for Java는 IntelliJ IDEA 및 Eclipse와 같은 널리 사용되는 Java IDE와 호환됩니다.
### Aspose 제품에 대한 임시 라이선스를 얻을 수 있나요?
예, Aspose 제품에 대한 임시 라이센스는 다음에서 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Slides에 대한 지원은 어디서 찾을 수 있나요?
 Java용 Aspose.Slides와 관련된 지원을 받으려면 다음을 방문하세요.[포럼을 Aspose](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

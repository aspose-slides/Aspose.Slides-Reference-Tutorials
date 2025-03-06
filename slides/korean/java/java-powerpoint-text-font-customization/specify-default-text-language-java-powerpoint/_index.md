---
title: Java PowerPoint에서 기본 텍스트 언어 지정
linktitle: Java PowerPoint에서 기본 텍스트 언어 지정
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java PowerPoint에서 기본 텍스트 언어를 지정하는 방법을 알아보세요. 프로그래밍 방식으로 텍스트 현지화를 원하는 개발자에게 적합합니다.
weight: 21
url: /ko/java/java-powerpoint-text-font-customization/specify-default-text-language-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint에서 기본 텍스트 언어 지정

## 소개
Java 애플리케이션 개발 영역에서는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 관리하고 조작하는 것이 일반적인 요구 사항입니다. Aspose.Slides for Java는 개발자가 Java 코드를 통해 PowerPoint 프레젠테이션을 원활하게 생성, 수정 및 향상할 수 있는 강력한 기능 세트를 제공합니다. 이 튜토리얼은 Aspose.Slides를 사용하여 Java PowerPoint 프레젠테이션에서 기본 텍스트 언어를 지정하는 필수 단계를 안내하는 것을 목표로 합니다.
## 전제 조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍 언어에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
- IntelliJ IDEA 또는 Eclipse와 같은 통합 개발 환경(IDE) 설정.
-  Java 라이브러리용 Aspose.Slides가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
-  찾을 수 있는 Java 문서용 Aspose.Slides에 액세스[여기](https://reference.aspose.com/slides/java/).

## 패키지 가져오기
코딩을 시작하기 전에 필요한 Aspose.Slides 클래스를 Java 파일로 가져와야 합니다.
```java
import com.aspose.slides.*;
```
## 1단계: 로드 옵션 설정
먼저 기본 텍스트 언어(`en-US` 이 경우).
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setDefaultTextLanguage("en-US");
```
## 2단계: 프레젠테이션 로드
 인스턴스화`Presentation` 구성된 로드 옵션을 사용하여 개체를 사용하여 기존 PowerPoint 프레젠테이션을 로드하거나 새 프레젠테이션을 만듭니다.
```java
Presentation pres = new Presentation(loadOptions);
```
## 3단계: 텍스트가 포함된 도형 추가
프레젠테이션의 첫 번째 슬라이드에 직사각형 모양을 추가하고 텍스트 내용을 설정합니다.
```java
IAutoShape shp = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 150, 50);
shp.getTextFrame().setText("New Text");
```
## 4단계: 텍스트 부분의 언어 확인
추가된 도형 내 텍스트 부분의 언어 설정을 검색하고 확인합니다.
```java
PortionFormat portionFormat = shp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat();
System.out.println(portionFormat.getLanguageId());
```
## 5단계: 프레젠테이션 개체 삭제
 적절한 폐기를 보장합니다.`Presentation` 사용 후 리소스를 해제하는 개체입니다.
```java
finally {
    if (pres != null) pres.dispose();
}
```

## 결론
이 튜토리얼에서는 프로그래밍 방식으로 PowerPoint 프레젠테이션의 기본 텍스트 언어를 지정하기 위해 Java용 Aspose.Slides를 활용하는 방법을 배웠습니다. 이 기능은 프레젠테이션의 텍스트 요소 전반에 걸쳐 일관된 언어 설정을 보장하고 가독성과 현지화 노력을 향상시키는 데 중요합니다.
## FAQ
### 기본 텍스트 언어를 프랑스어나 스페인어 등 다른 언어로 변경할 수 있나요?
예, Aspose.Slides for Java를 사용하여 기본 텍스트 언어를 설정할 때 지원되는 언어 코드를 지정할 수 있습니다.
### Aspose.Slides for Java는 엔터프라이즈급 애플리케이션에 적합합니까?
전적으로. Aspose.Slides for Java는 확장성과 성능을 고려하여 설계되어 기업 환경에 이상적입니다.
### Aspose.Slides for Java에 대한 추가 예제와 리소스는 어디에서 찾을 수 있나요?
 다음에서 포괄적인 문서와 추가 예제를 탐색할 수 있습니다.[Java 문서 페이지용 Aspose.Slides](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java는 클라우드 서비스와의 통합을 지원합니까?
예, Aspose.Slides for Java는 널리 사용되는 클라우드 플랫폼과의 통합을 지원하는 API를 제공합니다.
### 구매하기 전에 Java용 Aspose.Slides를 평가할 수 있나요?
 예, 다음에서 Aspose.Slides for Java의 무료 평가판을 얻을 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

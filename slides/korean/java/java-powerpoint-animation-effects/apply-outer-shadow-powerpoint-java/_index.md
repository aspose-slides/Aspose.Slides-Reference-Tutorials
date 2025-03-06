---
title: Java를 사용하는 PowerPoint에서 외부 그림자 적용
linktitle: Java를 사용하는 PowerPoint에서 외부 그림자 적용
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides와 함께 Java를 사용하여 PowerPoint에서 외부 그림자 효과를 적용하는 방법을 알아보세요. 깊이와 시각적 매력을 더해 프레젠테이션을 강화하세요.
weight: 13
url: /ko/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
시각적으로 매력적인 PowerPoint 프레젠테이션을 만들려면 도형과 텍스트에 다양한 효과를 추가해야 하는 경우가 많습니다. 그러한 효과 중 하나는 요소를 돋보이게 하고 슬라이드에 깊이를 더할 수 있는 외부 그림자입니다. 이 튜토리얼에서는 Aspose.Slides와 함께 Java를 사용하여 PowerPoint의 모양에 외부 그림자 효과를 적용하는 방법을 배웁니다.
## 전제 조건

이 튜토리얼을 시작하기 전에 다음 필수 구성 요소가 있는지 확인하세요.

1. JDK(Java Development Kit): 시스템에 Java가 설치되어 있는지 확인하세요. Oracle 웹사이트에서 최신 버전의 JDK를 다운로드하여 설치할 수 있습니다.

2.  Java용 Aspose.Slides: 다음 사이트에서 Java용 Aspose.Slides를 다운로드하고 설치하세요.[다운로드 페이지](https://releases.aspose.com/slides/java/).

3. IDE(통합 개발 환경): Java 애플리케이션 코딩 및 실행을 위해 Eclipse, IntelliJ IDEA, NetBeans 등 선호하는 Java IDE를 선택하세요.

4. 기본 Java 지식: Java 프로그래밍 언어 기본 사항 및 객체 지향 개념에 익숙하면 코드 예제를 이해하는 데 도움이 됩니다.

## 패키지 가져오기

먼저 Java 프로젝트에서 Aspose.Slides 및 관련 기능을 사용하는 데 필요한 패키지를 가져옵니다.

```java
import com.aspose.slides.*;
```

이제 Aspose.Slides와 함께 Java를 사용하여 PowerPoint의 모양에 외부 그림자 효과를 적용하기 위해 예제 코드를 여러 단계로 나누어 보겠습니다.

## 1단계: 프로젝트 환경 설정

원하는 IDE에서 새 Java 프로젝트를 생성하고 Aspose.Slides for Java 라이브러리를 프로젝트의 빌드 경로에 추가하세요.

## 2단계: 프레젠테이션 개체 초기화

 인스턴스를 생성합니다.`Presentation` PowerPoint 프레젠테이션 파일을 나타내는 클래스입니다.

```java
Presentation presentation = new Presentation();
```

## 3단계: 슬라이드 및 모양 추가

도형을 추가하려는 슬라이드에 대한 참조를 가져온 다음 슬라이드에 도형(예: 직사각형)을 추가합니다.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## 4단계: 모양 사용자 정의

도형의 채우기 유형을 'NoFill'로 설정하고 도형에 텍스트를 추가합니다.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## 5단계: 텍스트 사용자 정의

도형의 텍스트 속성에 액세스하고 글꼴 크기를 사용자 정의합니다.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## 6단계: 외부 그림자 효과 활성화

텍스트 부분에 외부 그림자 효과를 활성화합니다.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## 7단계: 그림자 매개변수 설정

흐림 반경, 방향, 거리, 그림자 색상 등 외부 그림자 효과에 대한 매개변수를 정의합니다.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## 8단계: 프레젠테이션 저장

도형에 외부 그림자 효과를 적용하여 수정된 프리젠테이션을 저장합니다.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## 결론

축하해요! Aspose.Slides와 함께 Java를 사용하여 PowerPoint의 모양에 외부 그림자 효과를 성공적으로 적용했습니다. 프레젠테이션에서 원하는 시각적 효과를 얻으려면 다양한 매개변수를 실험해 보세요.

## FAQ

### 직사각형 외의 다른 도형에도 외부 그림자 효과를 적용할 수 있나요?
예. 원, 삼각형, 사용자 정의 모양 등 Aspose.Slides가 지원하는 다양한 모양에 외부 그림자 효과를 적용할 수 있습니다.

### 그림자 색상과 강도를 맞춤 설정할 수 있나요?
전적으로! 색상, 흐림 반경, 방향, 거리 등 그림자 매개변수를 완벽하게 제어할 수 있습니다.

### 동일한 모양에 여러 효과를 적용할 수 있나요?
예. 외부 그림자, 내부 그림자, 광선, 반사 등 다양한 효과를 결합하여 프레젠테이션에서 모양과 텍스트의 시각적 매력을 향상할 수 있습니다.

### Aspose.Slides는 텍스트 요소에 효과 적용을 지원합니까?
예, 도형뿐만 아니라 도형 내의 개별 텍스트 부분에도 효과를 적용할 수 있으므로 슬라이드를 디자인할 때 광범위한 유연성이 제공됩니다.

### Aspose.Slides에 대한 추가 리소스와 지원은 어디서 찾을 수 있나요?
 당신은[선적 서류 비치](https://reference.aspose.com/slides/java/) 자세한 API 참조를 확인하고[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11) 커뮤니티 지원 및 토론을 위해.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

---
title: Java 슬라이드의 슬라이드 쇼 미디어 컨트롤
linktitle: Java 슬라이드의 슬라이드 쇼 미디어 컨트롤
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java 슬라이드에서 미디어 컨트롤을 활성화하고 사용하는 방법을 알아보세요. 미디어 컨트롤로 프레젠테이션을 향상하세요.
weight: 11
url: /ko/java/media-controls/slide-show-media-controls-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드의 슬라이드 쇼 미디어 컨트롤 소개

역동적이고 매력적인 프레젠테이션 영역에서 멀티미디어 요소는 청중의 관심을 사로잡는 데 중추적인 역할을 합니다. Java Slides는 Aspose.Slides for Java의 도움으로 개발자가 미디어 컨트롤을 원활하게 통합하는 매력적인 슬라이드 쇼를 만들 수 있도록 지원합니다. 교육 모듈, 판매 홍보 또는 교육 프리젠테이션을 디자인할 때 슬라이드쇼 중 미디어를 제어하는 기능은 판도를 바꾸는 기능입니다.

## 전제 조건

코드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Aspose.Slides for Java 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).
- IntelliJ IDEA 또는 Eclipse 등 원하는 통합 개발 환경(IDE).

## 1단계: 개발 환경 설정

코드를 살펴보기 전에 개발 환경을 올바르게 설정했는지 확인하세요. 다음과 같이하세요:

- 시스템에 JDK를 설치하십시오.
- 제공된 링크에서 Java용 Aspose.Slides를 다운로드하세요.
- 원하는 IDE를 설정하세요.

## 2단계: 새 프레젠테이션 만들기

새 프레젠테이션을 만드는 것부터 시작해 보겠습니다. Java Slides에서 이를 수행하는 방법은 다음과 같습니다.

```java
// PPTX 문서 경로
String outFilePath = "Your Output Directory" + "SlideShowMediaControl.pptx";
Presentation pres = new Presentation();
```

이 코드 조각에서는 새 프레젠테이션 개체를 만들고 프레젠테이션이 저장될 경로를 지정합니다.

## 3단계: 미디어 컨트롤 활성화

슬라이드쇼 모드에서 미디어 제어 표시를 활성화하려면 다음 코드를 사용하십시오.

```java
pres.getSlideShowSettings().setShowMediaControls(true);
```

이 코드 줄은 슬라이드쇼 중에 미디어 컨트롤을 표시하도록 Java 슬라이드에 지시합니다.

## 4단계: 슬라이드에 미디어 추가

이제 슬라이드에 미디어를 추가해 보겠습니다. Java Slides의 광범위한 기능을 사용하여 슬라이드에 오디오 또는 비디오 파일을 추가할 수 있습니다.

미디어 재생 사용자 정의
시작 및 종료 시간, 볼륨 등을 설정하는 등 미디어 재생을 추가로 사용자 정의하여 청중을 위한 맞춤형 멀티미디어 환경을 만들 수 있습니다.

## 5단계: 프레젠테이션 저장

미디어를 추가하고 재생을 사용자 정의한 후 다음 코드를 사용하여 프레젠테이션을 PPTX 형식으로 저장하십시오.

```java
pres.save(outFilePath, SaveFormat.Pptx);
```

이 코드는 미디어 컨트롤이 활성화된 상태로 프레젠테이션을 저장합니다.

## Java 슬라이드의 슬라이드 쇼 미디어 컨트롤을 위한 완전한 소스 코드

```java
// PPTX 문서 경로
String outFilePath = "Your Output Directory" + "SlideShowMediaControl.pptx";
Presentation pres = new Presentation();
try {
	// 슬라이드쇼 모드에서 미디어 제어 디스플레이를 활성화합니다.
	pres.getSlideShowSettings().setShowMediaControls(true);
	// 프레젠테이션을 PPTX 형식으로 저장합니다.
	pres.save(outFilePath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java 슬라이드에서 미디어 컨트롤을 활성화하고 활용하는 방법을 살펴보았습니다. 다음 단계를 따르면 청중을 사로잡는 대화형 멀티미디어 요소를 갖춘 매력적인 프레젠테이션을 만들 수 있습니다.

## FAQ

### 단일 슬라이드에 여러 미디어 파일을 추가하려면 어떻게 해야 합니까?

 단일 슬라이드에 여러 미디어 파일을 추가하려면`addMediaFrame`방법을 슬라이드에 적용하고 각 프레임에 대한 미디어 파일을 지정합니다. 그런 다음 각 프레임의 재생 설정을 개별적으로 사용자 정의할 수 있습니다.

### 프레젠테이션의 오디오 볼륨을 제어할 수 있나요?

 예, 다음을 설정하여 프레젠테이션의 오디오 볼륨을 제어할 수 있습니다.`Volume` 오디오 프레임의 속성입니다. 볼륨 레벨을 원하는 레벨로 조정할 수 있습니다.

### 슬라이드쇼 중에 비디오를 계속해서 반복할 수 있습니까?

 예, 설정할 수 있습니다`Looping` 비디오 프레임의 속성`true` 슬라이드쇼 중에 비디오가 계속 반복되도록 합니다.

### 슬라이드가 나타날 때 비디오를 자동으로 재생하려면 어떻게 해야 합니까?

 슬라이드가 나타날 때 비디오가 자동으로 재생되도록 하려면`PlayMode` 비디오 프레임의 속성`Auto`.

### Java Slides의 비디오에 자막을 추가하는 방법이 있습니까?

예, 비디오가 포함된 슬라이드에 텍스트 프레임이나 도형을 추가하여 Java Slides의 비디오에 자막이나 캡션을 추가할 수 있습니다. 그런 다음 타이밍 설정을 사용하여 텍스트를 비디오 재생과 동기화할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

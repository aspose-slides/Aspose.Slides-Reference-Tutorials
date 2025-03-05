---
title: Java 슬라이드의 읽기 전용 권장 속성
linktitle: Java 슬라이드의 읽기 전용 권장 속성
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java PowerPoint 프레젠테이션에서 읽기 전용 권장 속성을 활성화하는 방법을 알아보세요. 향상된 프레젠테이션 보안을 위해 소스 코드 예제가 포함된 단계별 가이드를 따르세요.
type: docs
weight: 17
url: /ko/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Java 슬라이드에서 읽기 전용 권장 속성 활성화 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 대한 읽기 전용 권장 속성을 활성화하는 방법을 살펴보겠습니다. 읽기 전용 권장 속성은 사용자가 변경하지 않고 프레젠테이션을 보도록 유도하려는 경우 유용할 수 있습니다. 이러한 속성은 프레젠테이션을 읽기 전용 모드로 열어야 함을 나타냅니다. 이를 달성하기 위해 Java 소스 코드와 함께 단계별 가이드를 제공합니다.

## 전제 조건

 시작하기 전에 프로젝트에 Aspose.Slides for Java 라이브러리가 설정되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Slides for Java 웹사이트](https://products.aspose.com/slides/java/).

## 1단계: 새 PowerPoint 프레젠테이션 만들기

Aspose.Slides for Java를 사용하여 새로운 PowerPoint 프레젠테이션을 만드는 것부터 시작하겠습니다. 이미 프레젠테이션이 있는 경우 이 단계를 건너뛸 수 있습니다.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

위 코드에서는 출력 PowerPoint 파일의 경로를 정의하고 새 프리젠테이션 개체를 만들었습니다.

## 2단계: 읽기 전용 권장 속성 활성화

이제 프레젠테이션에 대해 읽기 전용 권장 속성을 활성화하겠습니다.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 이 코드 조각에서는`getProtectionManager().setReadOnlyRecommended(true)` 읽기 전용 권장 속성을 설정하는 메서드`true`. 이렇게 하면 누군가 프레젠테이션을 열 때 읽기 전용 모드로 열라는 메시지가 표시됩니다.

## 3단계: 프레젠테이션 저장

마지막으로 읽기 전용 권장 속성을 활성화하여 프레젠테이션을 저장합니다.

## Java 슬라이드의 읽기 전용 권장 속성에 대한 전체 소스 코드

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 대한 읽기 전용 권장 속성을 활성화하는 방법을 배웠습니다. 이 기능은 편집을 제한하고 뷰어가 프레젠테이션을 읽기 전용 모드로 사용하도록 장려하려는 경우에 유용할 수 있습니다. 프레젠테이션에 비밀번호를 설정하면 보안을 더욱 강화할 수 있습니다.

## FAQ

### 읽기 전용 권장 속성을 비활성화하려면 어떻게 해야 합니까?

읽기 전용 권장 속성을 비활성화하려면 다음 코드를 사용하면 됩니다.

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### 읽기 전용 권장 프레젠테이션에 비밀번호를 설정할 수 있나요?

예, Aspose.Slides for Java를 사용하여 읽기 전용 권장 프레젠테이션에 대한 비밀번호를 설정할 수 있습니다. 당신은 사용할 수 있습니다`setPassword` 프레젠테이션의 비밀번호를 설정하는 방법입니다. 비밀번호가 설정되어 있으면 읽기 전용 모드에서도 프레젠테이션을 열려면 비밀번호를 입력해야 합니다.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 교체하는 것을 기억하세요`"YourPassword"` 원하는 비밀번호로
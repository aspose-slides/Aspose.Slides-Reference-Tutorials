---
title: Java 슬라이드에서 XPS 옵션 없이 변환
linktitle: Java 슬라이드에서 XPS 옵션 없이 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 XPS 형식으로 변환하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드입니다.
weight: 33
url: /ko/java/presentation-conversion/convert-without-xps-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드에서 XPS 옵션 없이 변환


## 소개 Java용 Aspose.Slides에서 XPS 옵션 없이 PowerPoint를 XPS로 변환

이 튜토리얼에서는 XPS 옵션을 지정하지 않고 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 XPS(XML Paper Spec) 문서로 변환하는 과정을 안내합니다. 우리는 이 작업을 달성하기 위한 단계별 지침과 Java 소스 코드를 제공할 것입니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  Java용 Aspose.Slides: Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 구성되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Slides for Java 웹사이트](https://downloads.aspose.com/slides/java).

2. Java 개발 환경: 컴퓨터에 Java 개발 환경이 설정되어 있어야 합니다.

## 1단계: Java용 Aspose.Slides 가져오기

Java 프로젝트에서 Java 파일 시작 부분에 필요한 Aspose.Slides for Java 클래스를 가져옵니다.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2단계: PowerPoint 프레젠테이션 로드

이제 XPS로 변환하려는 PowerPoint 프레젠테이션을 로드하겠습니다. 바꾸다`"Your Document Directory"` PowerPoint 프리젠테이션 파일의 실제 경로:

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// 프리젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
```

 교체했는지 확인하세요.`"Convert_XPS.pptx"` PowerPoint 파일의 실제 이름으로.

## 3단계: XPS 옵션 없이 XPS로 저장

Aspose.Slides for Java를 사용하면 XPS 옵션을 지정하지 않고도 로드된 프레젠테이션을 XPS 문서로 쉽게 저장할 수 있습니다. 방법은 다음과 같습니다.

```java
try {
    // 프레젠테이션을 XPS 문서에 저장
    pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
} finally {
    if (pres != null) pres.dispose();
}
```

 이 코드 블록은 프레젠테이션을 다음 이름의 XPS 문서로 저장합니다.`"XPS_Output_Without_XPSOption_out.xps"`. 필요에 따라 출력 파일 이름을 변경할 수 있습니다.

## Java 슬라이드에서 XPS 옵션 없이 변환하기 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프리젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "Convert_XPS.pptx");
try
{
	// 프레젠테이션을 XPS 문서에 저장
	pres.save(dataDir + "XPS_Output_Without_XPSOption_out.xps", SaveFormat.Xps);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 XPS 옵션을 지정하지 않고 PowerPoint 프레젠테이션을 XPS 문서로 변환하는 방법을 배웠습니다. Aspose.Slides for Java에서 제공하는 옵션을 탐색하여 변환 프로세스를 추가로 사용자 정의할 수 있습니다. 더 많은 고급 기능과 심층적인 문서를 보려면 다음을 방문하세요.[Java 문서용 Aspose.Slides](https://docs.aspose.com/slides/java/).

## FAQ

### 변환하는 동안 XPS 옵션을 어떻게 지정합니까?

 PowerPoint 프레젠테이션을 변환하는 동안 XPS 옵션을 지정하려면 다음을 사용할 수 있습니다.`XpsOptions` 클래스를 생성하고 이미지 압축, 글꼴 포함 등 다양한 속성을 설정합니다. XPS 변환에 대한 특정 요구 사항이 있는 경우 다음을 참조하세요.[Java 문서용 Aspose.Slides](https://docs.aspose.com/slides/java/) 상세 사항은.

### 다른 형식으로 저장하기 위한 추가 옵션이 있습니까?

 예, Aspose.Slides for Java는 XPS 외에도 PDF, TIFF, HTML 등 다양한 출력 형식을 제공합니다. 원하는 출력 형식을 변경하여 지정할 수 있습니다.`SaveFormat` 호출할 때 매개변수`save` 방법. 지원되는 형식의 전체 목록은 설명서를 참조하세요.

### 변환 프로세스 중에 예외를 어떻게 처리할 수 있나요?

 변환 프로세스 중에 발생할 수 있는 모든 오류를 정상적으로 처리하기 위해 예외 처리를 구현할 수 있습니다. 코드에 표시된 것처럼`try` 그리고`finally` 블록은 예외가 발생하더라도 적절한 리소스 처리를 보장하는 데 사용됩니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

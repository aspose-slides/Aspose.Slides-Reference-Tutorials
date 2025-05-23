---
"description": "Aspose.Slides의 단계별 튜토리얼을 통해 Java Slides에서 멋진 조직도를 만드는 방법을 알아보세요. 조직 구조를 손쉽게 맞춤 설정하고 시각화하세요."
"linktitle": "Java 슬라이드로 만든 조직도"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java 슬라이드로 만든 조직도"
"url": "/ko/java/chart-data-manipulation/organization-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 슬라이드로 만든 조직도


## Aspose.Slides를 사용하여 Java Slides에서 조직도 만들기 소개

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 조직도를 만드는 방법을 보여드리겠습니다. 조직도는 조직의 계층 구조를 시각적으로 표현한 것으로, 일반적으로 직원이나 부서 간의 관계와 계층 구조를 보여주는 데 사용됩니다.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- [Java용 Aspose.Slides](https://products.aspose.com/slides/java) Java 프로젝트에 설치된 라이브러리입니다.
- IntelliJ IDEA나 Eclipse와 같은 Java 통합 개발 환경(IDE).

## 1단계: Java 프로젝트 설정

1. 원하는 IDE에서 새로운 Java 프로젝트를 만듭니다.
2. 프로젝트에 Aspose.Slides for Java 라이브러리를 추가하세요. 라이브러리는 다음에서 다운로드할 수 있습니다. [Aspose 웹사이트](https://products.aspose.com/slides/java) 이를 종속성으로 포함합니다.

## 2단계: 필요한 라이브러리 가져오기
Java 클래스에서 Aspose.Slides 작업에 필요한 라이브러리를 가져옵니다.

```java
import com.aspose.slides.*;
```

## 3단계: 조직도 만들기

이제 Aspose.Slides를 사용하여 조직도를 만들어 보겠습니다. 다음 단계를 따르세요.

1. 문서 디렉토리의 경로를 지정하세요.
2. 기존 PowerPoint 프레젠테이션을 로드하거나 새 프레젠테이션을 만듭니다.
3. 슬라이드에 조직도 모양을 추가합니다.
4. 조직도와 함께 프레젠테이션을 저장하세요.

이를 달성하기 위한 코드는 다음과 같습니다.

```java
// 문서 디렉토리의 경로를 지정하세요.
String dataDir = "Your Document Directory";

// 기존 프레젠테이션을 로드하거나 새 프레젠테이션을 만듭니다.
Presentation pres = new Presentation(dataDir + "test.pptx");
try {
    // 첫 번째 슬라이드에 조직도 모양을 추가합니다.
    ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);

    // 조직도와 함께 프레젠테이션을 저장하세요.
    pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

바꾸다 `"Your Document Directory"` 문서 디렉토리의 실제 경로와 함께 `"test.pptx"` PowerPoint 프레젠테이션의 이름을 입력합니다.

## 4단계: 코드 실행

조직도를 만드는 코드를 추가했으니 이제 Java 애플리케이션을 실행하세요. Aspose.Slides 라이브러리가 프로젝트에 올바르게 추가되었고 필요한 종속성이 해결되었는지 확인하세요.

## Java 슬라이드로 만든 조직도의 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);
	pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java API를 사용하여 Java Slides에서 조직도를 만드는 방법을 알아보았습니다. 조직도의 모양과 내용은 특정 요구 사항에 맞게 사용자 지정할 수 있습니다. Aspose.Slides는 PowerPoint 프레젠테이션 작업에 필요한 다양한 기능을 제공하여 시각적 콘텐츠를 관리하고 제작하는 강력한 도구입니다.

## 자주 묻는 질문

### 조직도의 모양을 어떻게 사용자 지정할 수 있나요?

색, 스타일, 글꼴 등의 속성을 수정하여 조직도 모양을 사용자 지정할 수 있습니다. SmartArt 도형을 사용자 지정하는 방법에 대한 자세한 내용은 Aspose.Slides 설명서를 참조하세요.

### 조직도에 추가 도형이나 텍스트를 추가할 수 있나요?

네, 조직도에 도형, 텍스트, 연결선을 추가하여 조직 구조를 정확하게 표현할 수 있습니다. Aspose.Slides API를 사용하여 SmartArt 다이어그램에 도형을 추가하고 서식을 지정할 수 있습니다.

### 조직도를 PDF나 이미지 등 다른 형식으로 내보내려면 어떻게 해야 하나요?

Aspose.Slides를 사용하여 조직도가 포함된 프레젠테이션을 다양한 형식으로 내보낼 수 있습니다. 예를 들어 PDF로 내보내려면 다음을 사용하세요. `SaveFormat.Pdf` 프레젠테이션을 저장할 때 옵션을 사용할 수 있습니다. 마찬가지로 PNG나 JPEG와 같은 이미지 형식으로 내보낼 수도 있습니다.

### 여러 단계로 구성된 복잡한 조직 구조를 만드는 것이 가능할까요?

네, Aspose.Slides를 사용하면 조직도 내에 도형을 추가하고 배열하여 여러 단계의 복잡한 조직 구조를 만들 수 있습니다. 도형 간의 계층 관계를 정의하여 원하는 구조를 표현할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
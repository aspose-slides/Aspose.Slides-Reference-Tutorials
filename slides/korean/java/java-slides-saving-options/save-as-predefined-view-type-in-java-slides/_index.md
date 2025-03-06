---
title: Java 슬라이드에 사전 정의된 보기 유형으로 저장
linktitle: Java 슬라이드에 사전 정의된 보기 유형으로 저장
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 Java Slides에서 사전 정의된 보기 유형을 설정하는 방법을 알아보세요. 코드 예제와 FAQ가 포함된 단계별 가이드입니다.
weight: 10
url: /ko/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Java 슬라이드의 사전 정의된 보기 유형으로 저장 소개

이 단계별 가이드에서는 Aspose.Slides for Java를 사용하여 미리 정의된 보기 유형으로 프레젠테이션을 저장하는 방법을 살펴보겠습니다. 이 작업을 성공적으로 수행하는 데 필요한 코드와 설명을 제공하겠습니다.

## 전제 조건

시작하기 전에 다음 사항이 있는지 확인하세요.

- Java 프로그래밍에 대한 기본 지식.
- Java 라이브러리용 Aspose.Slides가 설치되었습니다.
- 원하는 통합 개발 환경(IDE).

## 환경 설정

시작하려면 다음 단계에 따라 개발 환경을 설정하세요.

1. IDE에서 새 Java 프로젝트를 만듭니다.
2. Aspose.Slides for Java 라이브러리를 프로젝트에 종속성으로 추가합니다.

이제 환경이 설정되었으므로 코드를 진행해 보겠습니다.

## 1단계: 프레젠테이션 만들기

미리 정의된 보기 유형으로 프레젠테이션을 저장하는 방법을 보여주기 위해 먼저 새 프레젠테이션을 만들어 보겠습니다. 프레젠테이션을 만드는 코드는 다음과 같습니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일 열기
Presentation presentation = new Presentation();
```

 이 코드에서는 새로운`Presentation` PowerPoint 프레젠테이션을 나타내는 개체입니다.

## 2단계: 보기 유형 설정

다음으로 프레젠테이션의 보기 유형을 설정하겠습니다. 보기 유형은 프레젠테이션을 열 때 표시되는 방식을 정의합니다. 이 예에서는 "슬라이드 마스터 보기"로 설정하겠습니다. 코드는 다음과 같습니다.

```java
// 보기 유형 설정
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 위의 코드에서는`setLastView` 의 방법`ViewProperties` 뷰 유형을 설정하는 클래스`SlideMasterView`. 필요에 따라 다른 보기 유형을 선택할 수 있습니다.

## 3단계: 프레젠테이션 저장

이제 프레젠테이션을 만들고 보기 유형을 설정했으므로 프레젠테이션을 저장할 차례입니다. PPTX 형식으로 저장하겠습니다. 코드는 다음과 같습니다.

```java
// 프레젠테이션 저장 중
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 이 코드에서는`save` 의 방법`Presentation` 지정된 파일 이름과 형식으로 프레젠테이션을 저장하는 클래스입니다.

## Java 슬라이드의 사전 정의된 보기 유형으로 저장을 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일 열기
Presentation presentation = new Presentation();
try
{
	// 보기 유형 설정
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// 프레젠테이션 저장 중
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java에서 미리 정의된 보기 유형으로 프레젠테이션을 저장하는 방법을 배웠습니다. 제공된 코드와 단계를 따르면 프레젠테이션의 보기 유형을 쉽게 설정하고 원하는 형식으로 저장할 수 있습니다.

## FAQ

### 보기 유형을 "슬라이드 마스터 보기"가 아닌 다른 것으로 어떻게 변경합니까?

 보기 유형을 "슬라이드 마스터 보기" 이외의 다른 것으로 변경하려면 간단히`ViewType.SlideMasterView` 다음과 같은 원하는 뷰 유형을 사용합니다.`ViewType.NormalView` 또는`ViewType.SlideSorterView`, 뷰 유형을 설정하는 코드에서.

### 프레젠테이션의 개별 슬라이드에 대한 보기 속성을 설정할 수 있나요?

예, Aspose.Slides for Java를 사용하여 개별 슬라이드에 대한 보기 속성을 설정할 수 있습니다. 프레젠테이션의 슬라이드를 반복하여 각 슬라이드의 속성에 개별적으로 액세스하고 조작할 수 있습니다.

### 프레젠테이션을 어떤 다른 형식으로 저장할 수 있나요?

Aspose.Slides for Java는 PPTX, PDF, TIFF, HTML 등을 포함한 다양한 출력 형식을 지원합니다. 프레젠테이션을 저장할 때 적절한 형식을 사용하여 원하는 형식을 지정할 수 있습니다.`SaveFormat` 열거형 값.

### Aspose.Slides for Java는 프레젠테이션 일괄 처리에 적합합니까?

예, Aspose.Slides for Java는 일괄 처리 작업에 적합합니다. 여러 프레젠테이션의 처리를 자동화하고, 변경 사항을 적용하고, Java 코드를 사용하여 대량으로 저장할 수 있습니다.

### Aspose.Slides for Java에 대한 자세한 정보와 문서는 어디서 찾을 수 있나요?

 Aspose.Slides for Java와 관련된 포괄적인 문서 및 참고 자료를 보려면 문서 웹사이트를 방문하세요.[Java 문서용 Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

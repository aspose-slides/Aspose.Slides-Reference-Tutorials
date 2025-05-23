---
"description": "Aspose.Slides for Java를 사용하여 Java Slides에서 미리 정의된 뷰 유형을 설정하는 방법을 알아보세요. 코드 예제와 FAQ가 포함된 단계별 가이드입니다."
"linktitle": "Java Slides에서 미리 정의된 뷰 유형으로 저장"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 미리 정의된 뷰 유형으로 저장"
"url": "/ko/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 미리 정의된 뷰 유형으로 저장


## Java Slides에서 미리 정의된 뷰 유형으로 저장 소개

이 단계별 가이드에서는 Aspose.Slides for Java를 사용하여 미리 정의된 뷰 유형으로 프레젠테이션을 저장하는 방법을 살펴보겠습니다. 이 작업을 성공적으로 수행하는 데 필요한 코드와 설명을 제공합니다.

## 필수 조건

시작하기에 앞서 다음 사항이 있는지 확인하세요.

- Java 프로그래밍에 대한 기본 지식.
- Java 라이브러리용 Aspose.Slides가 설치되었습니다.
- 귀하가 선택한 통합 개발 환경(IDE)

## 환경 설정

시작하려면 다음 단계에 따라 개발 환경을 설정하세요.

1. IDE에서 새로운 Java 프로젝트를 만듭니다.
2. 프로젝트에 종속성으로 Aspose.Slides for Java 라이브러리를 추가합니다.

이제 환경이 설정되었으니 코드 작업을 진행해 보겠습니다.

## 1단계: 프레젠테이션 만들기

미리 정의된 뷰 유형으로 프레젠테이션을 저장하는 방법을 보여주기 위해 먼저 새 프레젠테이션을 만들어 보겠습니다. 프레젠테이션을 만드는 코드는 다음과 같습니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일 열기
Presentation presentation = new Presentation();
```

이 코드에서 우리는 새로운 것을 생성합니다. `Presentation` PowerPoint 프레젠테이션을 나타내는 객체입니다.

## 2단계: 보기 유형 설정

다음으로 프레젠테이션의 보기 유형을 설정하겠습니다. 보기 유형은 프레젠테이션을 열었을 때 표시되는 방식을 정의합니다. 이 예시에서는 "슬라이드 마스터 보기"로 설정하겠습니다. 코드는 다음과 같습니다.

```java
// 뷰 유형 설정
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

위의 코드에서 우리는 다음을 사용합니다. `setLastView` 방법 `ViewProperties` 뷰 유형을 설정하는 클래스 `SlideMasterView`필요에 따라 다른 보기 유형을 선택할 수 있습니다.

## 3단계: 프레젠테이션 저장

프레젠테이션을 만들고 보기 유형을 설정했으니 이제 프레젠테이션을 저장할 차례입니다. PPTX 형식으로 저장하겠습니다. 코드는 다음과 같습니다.

```java
// 프레젠테이션 저장
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

이 코드에서는 다음을 사용합니다. `save` 방법 `Presentation` 지정된 파일 이름과 형식으로 프레젠테이션을 저장하는 클래스입니다.

## Java 슬라이드에서 미리 정의된 뷰 유형으로 저장하기 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일 열기
Presentation presentation = new Presentation();
try
{
	// 뷰 유형 설정
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// 프레젠테이션 저장
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 Java에서 미리 정의된 뷰 유형으로 프레젠테이션을 저장하는 방법을 알아보았습니다. 제공된 코드와 단계를 따라 프레젠테이션의 뷰 유형을 쉽게 설정하고 원하는 형식으로 저장할 수 있습니다.

## 자주 묻는 질문

### 보기 유형을 "슬라이드 마스터 보기"가 아닌 다른 것으로 변경하려면 어떻게 해야 하나요?

보기 유형을 "슬라이드 마스터 보기"가 아닌 다른 것으로 변경하려면 간단히 다음을 바꾸세요. `ViewType.SlideMasterView` 원하는 뷰 유형(예: `ViewType.N또는malView` or `ViewType.SlideSorterView`, 뷰 유형을 설정하는 코드에서.

### 프레젠테이션에서 개별 슬라이드의 보기 속성을 설정할 수 있나요?

네, Aspose.Slides for Java를 사용하여 개별 슬라이드의 뷰 속성을 설정할 수 있습니다. 프레젠테이션의 슬라이드를 반복하면서 각 슬라이드의 속성에 개별적으로 접근하고 조작할 수 있습니다.

### 프레젠테이션을 어떤 다른 형식으로 저장할 수 있나요?

Aspose.Slides for Java는 PPTX, PDF, TIFF, HTML 등 다양한 출력 형식을 지원합니다. 프레젠테이션을 저장할 때 적절한 형식을 사용하여 원하는 형식을 지정할 수 있습니다. `SaveFormat` 열거형 값.

### Java용 Aspose.Slides는 프레젠테이션의 일괄 처리에 적합합니까?

네, Aspose.Slides for Java는 일괄 처리 작업에 적합합니다. Java 코드를 사용하여 여러 프레젠테이션의 처리를 자동화하고, 변경 사항을 적용하고, 대량으로 저장할 수 있습니다.

### Aspose.Slides for Java에 대한 자세한 정보와 문서는 어디에서 찾을 수 있나요?

Aspose.Slides for Java와 관련된 포괄적인 문서와 참고 자료를 보려면 다음 문서 웹사이트를 방문하세요. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
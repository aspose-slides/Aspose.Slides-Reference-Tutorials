---
title: Java 슬라이드에 사용자 정의 문서 속성 추가
linktitle: Java 슬라이드에 사용자 정의 문서 속성 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Java Slides의 사용자 정의 문서 속성을 사용하여 PowerPoint 프레젠테이션을 향상시키는 방법을 알아보세요. Aspose.Slides for Java를 사용하는 코드 예제가 포함된 단계별 가이드입니다.
type: docs
weight: 13
url: /ko/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

## Java 슬라이드에 사용자 정의 문서 속성 추가 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 사용자 정의 문서 속성을 추가하는 과정을 안내합니다. 사용자 정의 문서 속성을 사용하면 참조 또는 분류를 위해 프레젠테이션에 대한 추가 정보를 저장할 수 있습니다.

## 전제조건

시작하기 전에 Java 프로젝트에 Aspose.Slides for Java 라이브러리가 설치 및 설정되어 있는지 확인하세요.

## 1단계: 필수 패키지 가져오기

```java
import com.aspose.slides.*;
```

## 2단계: 새 프레젠테이션 만들기

먼저, 새로운 프리젠테이션 개체를 만들어야 합니다. 다음과 같이 이 작업을 수행할 수 있습니다.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// 프레젠테이션 클래스 인스턴스화
Presentation presentation = new Presentation();
```

## 3단계: 문서 속성 가져오기

다음으로 프레젠테이션의 문서 속성을 검색합니다. 이러한 속성에는 제목, 작성자, 추가할 수 있는 사용자 정의 속성과 같은 기본 제공 속성이 포함됩니다.

```java
// 문서 속성 가져오기
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## 4단계: 사용자 정의 속성 추가

이제 프레젠테이션에 사용자 정의 속성을 추가해 보겠습니다. 사용자 정의 속성은 이름과 값으로 구성됩니다. 이를 사용하여 원하는 정보를 저장할 수 있습니다.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## 5단계: 특정 인덱스에서 속성 이름 가져오기

특정 인덱스에서 사용자 정의 속성의 이름을 검색할 수도 있습니다. 이는 특정 속성을 사용하여 작업해야 하는 경우 유용할 수 있습니다.

```java
// 특정 인덱스에서 속성 이름 가져오기
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## 6단계: 선택한 속성 제거

사용자 정의 속성을 제거하려면 해당 이름을 지정하면 됩니다. 여기서는 5단계에서 얻은 속성을 제거합니다.

```java
// 선택한 속성 제거
documentProperties.removeCustomProperty(getPropertyName);
```

## 7단계: 프레젠테이션 저장

마지막으로 추가 및 제거된 사용자 정의 속성이 포함된 프레젠테이션을 파일에 저장합니다.

```java
// 프레젠테이션 저장 중
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Java 슬라이드에 사용자 정의 문서 속성을 추가하기 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 클래스 인스턴스화
Presentation presentation = new Presentation();
// 문서 속성 가져오기
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// 사용자 정의 속성 추가
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// 특정 인덱스에서 속성 이름 가져오기
String getPropertyName = documentProperties.getCustomPropertyName(2);
// 선택한 속성 제거
documentProperties.removeCustomProperty(getPropertyName);
// 프레젠테이션 저장 중
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## 결론

Aspose.Slides를 사용하여 Java에서 PowerPoint 프레젠테이션에 사용자 정의 문서 속성을 추가하는 방법을 배웠습니다. 사용자 정의 속성은 프레젠테이션과 관련된 추가 정보를 저장하는 데 유용할 수 있습니다. 특정 사용 사례에 필요한 만큼 더 많은 사용자 정의 속성을 포함하도록 이 지식을 확장할 수 있습니다.

## FAQ

### 사용자 정의 속성 값을 어떻게 검색합니까?

 사용자 정의 속성의 값을 검색하려면 다음을 사용할 수 있습니다.`get_Item` 에 대한 방법`documentProperties` 물체. 예를 들어:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### 다양한 데이터 유형의 사용자 정의 속성을 추가할 수 있나요?

예, 예제에 표시된 대로 숫자, 문자열, 날짜 등을 포함한 다양한 데이터 유형의 사용자 정의 속성을 추가할 수 있습니다. Aspose.Slides for Java는 다양한 데이터 유형을 원활하게 처리합니다.

### 추가할 수 있는 사용자 정의 속성의 수에 제한이 있습니까?

추가할 수 있는 사용자 정의 속성의 수에는 엄격한 제한이 없습니다. 그러나 속성을 너무 많이 추가하면 프리젠테이션 파일의 성능과 크기에 영향을 미칠 수 있다는 점에 유의하세요.

### 프레젠테이션의 모든 사용자 정의 속성을 나열하려면 어떻게 해야 합니까?

모든 사용자 정의 속성을 반복하여 나열할 수 있습니다. 이를 수행하는 방법의 예는 다음과 같습니다.

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

이 코드는 프레젠테이션의 모든 사용자 정의 속성의 이름과 값을 표시합니다.
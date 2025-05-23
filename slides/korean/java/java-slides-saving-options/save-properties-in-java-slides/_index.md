---
"description": "Aspose.Slides for Java로 PowerPoint 프레젠테이션을 최적화하세요. 속성 설정, 암호화 해제, 암호 보호 추가, 저장 방법을 손쉽게 배워보세요."
"linktitle": "Java Slides에서 속성 저장"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 속성 저장"
"url": "/ko/java/saving-options/save-properties-in-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 속성 저장


## Java Slides에서 속성 저장 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 속성을 저장하는 과정을 안내합니다. 문서 속성을 설정하고, 문서 속성에 대한 암호화를 해제하고, 프레젠테이션을 보호하기 위한 비밀번호를 설정하고, 파일에 저장하는 방법을 배웁니다. 단계별 지침과 소스 코드 예제도 제공합니다.

## 필수 조건

시작하기 전에 Aspose.Slides for Java 라이브러리가 Java 프로젝트에 통합되어 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드할 수 있습니다. [여기](https://downloads.aspose.com/slides/java).

## 1단계: 필요한 라이브러리 가져오기

시작하려면 필요한 클래스와 라이브러리를 가져오세요.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2단계: 프레젠테이션 개체 만들기

PowerPoint 프레젠테이션을 나타내는 Presentation 객체를 인스턴스화합니다. 새 프레젠테이션을 만들거나 기존 프레젠테이션을 로드할 수 있습니다. 이 예제에서는 새 프레젠테이션을 만들어 보겠습니다.

```java
// 프레젠테이션을 저장할 디렉토리 경로
String dataDir = "Your Document Directory";

// 프레젠테이션 객체를 인스턴스화합니다
Presentation presentation = new Presentation();
```

## 3단계: 문서 속성 설정

제목, 작성자, 키워드 등 다양한 문서 속성을 설정할 수 있습니다. 여기서는 몇 가지 일반적인 속성을 설정해 보겠습니다.

```java
// 프레젠테이션의 제목을 설정하세요
presentation.getDocumentProperties().setTitle("My Presentation");

// 프레젠테이션 작성자를 설정하세요
presentation.getDocumentProperties().setAuthor("John Doe");

// 프레젠테이션을 위한 키워드 설정
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## 4단계: 문서 속성에 대한 암호화 비활성화

기본적으로 Aspose.Slides는 문서 속성을 암호화합니다. 문서 속성의 암호화를 비활성화하려면 다음 코드를 사용하세요.

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## 5단계: 프레젠테이션을 보호하기 위한 비밀번호 설정

프레젠테이션을 비밀번호로 보호하여 접근을 제한할 수 있습니다. 다음을 사용하세요. `encrypt` 비밀번호를 설정하는 방법:

```java
// 프레젠테이션을 보호하기 위해 비밀번호를 설정하세요
presentation.getProtectionManager().encrypt("your_password");
```

바꾸다 `"your_password"` 원하는 비밀번호를 입력하세요.

## 6단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 파일로 저장합니다. 이 예시에서는 PPTX 파일로 저장해 보겠습니다.

```java
// 프레젠테이션을 파일로 저장
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

바꾸다 `"Password_Protected_Presentation_out.pptx"` 원하는 파일 이름과 경로를 입력하세요.

## Java Slides에서 속성 저장을 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// PPT 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation presentation = new Presentation();
try
{
	//....여기서 일을 좀 하세요.....
	// 암호로 보호된 모드에서 문서 속성에 대한 액세스 설정
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// 비밀번호 설정
	presentation.getProtectionManager().encrypt("pass");
	// 프레젠테이션을 파일에 저장하세요
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 문서 속성을 저장하는 방법을 알아보았습니다. 다양한 속성을 설정하고, 문서 속성의 암호화를 비활성화하고, 보호를 위해 비밀번호를 설정하고, 원하는 형식으로 프레젠테이션을 저장할 수 있습니다.

## 자주 묻는 질문

### Java용 Aspose.Slides에서 문서 속성을 어떻게 설정할 수 있나요?

Java용 Aspose.Slides에서 문서 속성을 설정하려면 다음을 사용할 수 있습니다. `DocumentProperties` 클래스입니다. 제목, 작성자, 키워드와 같은 속성을 설정하는 방법의 예는 다음과 같습니다.

```java
// 프레젠테이션의 제목을 설정하세요
presentation.getDocumentProperties().setTitle("My Presentation");

// 프레젠테이션 작성자를 설정하세요
presentation.getDocumentProperties().setAuthor("John Doe");

// 프레젠테이션을 위한 키워드 설정
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### 문서 속성에 대한 암호화를 비활성화하는 목적은 무엇입니까?

문서 속성에 대한 암호화를 비활성화하면 암호화 없이 문서 메타데이터를 저장할 수 있습니다. 이는 비밀번호를 입력하지 않고도 문서 속성(예: 제목, 작성자 등)을 보고 접근할 수 있도록 하려는 경우 유용합니다.

다음 코드를 사용하여 암호화를 비활성화할 수 있습니다.

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### Aspose.Slides for Java를 사용하여 비밀번호로 PowerPoint 프레젠테이션을 보호하려면 어떻게 해야 합니까?

PowerPoint 프레젠테이션을 암호로 보호하려면 다음을 사용할 수 있습니다. `encrypt` 에서 제공하는 방법 `ProtectionManager` 클래스. 비밀번호를 설정하는 방법은 다음과 같습니다.

```java
// 프레젠테이션을 보호하기 위해 비밀번호를 설정하세요
presentation.getProtectionManager().encrypt("your_password");
```

바꾸다 `"your_password"` 원하는 비밀번호를 입력하세요.

### PPTX가 아닌 다른 형식으로 프레젠테이션을 저장할 수 있나요?

네, Aspose.Slides for Java에서 지원하는 PPT, PDF 등 다양한 형식으로 프레젠테이션을 저장할 수 있습니다. 다른 형식으로 저장하려면 `SaveFormat` 매개변수 `presentation.save` 방법. 예를 들어 PDF로 저장하려면 다음과 같이 하세요.

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### 저장 후 Presentation 객체를 삭제해야 합니까?

시스템 리소스를 해제하려면 Presentation 객체를 삭제하는 것이 좋습니다. 다음을 사용할 수 있습니다. `finally` 코드 예제에서 보여지는 것처럼 적절한 폐기를 보장하기 위한 블록:

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

이렇게 하면 애플리케이션에서 메모리 누수를 방지하는 데 도움이 됩니다.

### Aspose.Slides for Java와 그 기능에 대해 자세히 알아보려면 어떻게 해야 하나요?

Java용 Aspose.Slides 설명서를 다음에서 탐색할 수 있습니다. [여기](https://docs.aspose.com/slides/java/) 라이브러리 사용에 대한 자세한 정보, 튜토리얼, 예제를 확인하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
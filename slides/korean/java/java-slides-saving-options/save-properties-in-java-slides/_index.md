---
title: Java 슬라이드에 속성 저장
linktitle: Java 슬라이드에 속성 저장
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java로 PowerPoint 프레젠테이션을 최적화하세요. 속성 설정, 암호화 비활성화, 비밀번호 보호 추가 및 손쉽게 저장하는 방법을 알아보세요.
type: docs
weight: 12
url: /ko/java/saving-options/save-properties-in-java-slides/
---

## Java 슬라이드의 속성 저장 소개

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 속성을 저장하는 과정을 안내합니다. 문서 속성을 설정하고, 문서 속성에 대한 암호화를 비활성화하고, 프레젠테이션을 보호하기 위한 암호를 설정하고, 파일에 저장하는 방법을 배우게 됩니다. 단계별 지침과 소스 코드 예제를 제공합니다.

## 전제 조건

 시작하기 전에 Java 프로젝트에 통합된 Java용 Aspose.Slides 라이브러리가 있는지 확인하세요. Aspose 웹사이트에서 라이브러리를 다운로드할 수 있습니다.[여기](https://downloads.aspose.com/slides/java).

## 1단계: 필수 라이브러리 가져오기

시작하려면 필요한 클래스와 라이브러리를 가져옵니다.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2단계: 프리젠테이션 개체 만들기

PowerPoint 프레젠테이션을 나타내기 위해 프레젠테이션 개체를 인스턴스화합니다. 새 프레젠테이션을 만들거나 기존 프레젠테이션을 로드할 수 있습니다. 이 예에서는 새 프레젠테이션을 만들어 보겠습니다.

```java
// 프레젠테이션을 저장하려는 디렉터리의 경로
String dataDir = "Your Document Directory";

// 프레젠테이션 개체 인스턴스화
Presentation presentation = new Presentation();
```

## 3단계: 문서 속성 설정

제목, 작성자, 키워드 등 다양한 문서 속성을 설정할 수 있습니다. 여기서는 몇 가지 공통 속성을 설정하겠습니다.

```java
// 프레젠테이션 제목 설정
presentation.getDocumentProperties().setTitle("My Presentation");

//프레젠테이션 작성자 설정
presentation.getDocumentProperties().setAuthor("John Doe");

// 프레젠테이션의 키워드 설정
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

## 4단계: 문서 속성 암호화 비활성화

기본적으로 Aspose.Slides는 문서 속성을 암호화합니다. 문서 속성에 대한 암호화를 비활성화하려면 다음 코드를 사용하십시오.

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

## 5단계: 프레젠테이션을 보호하기 위한 비밀번호 설정

 액세스를 제한하는 비밀번호로 프레젠테이션을 보호할 수 있습니다. 사용`encrypt` 비밀번호를 설정하는 방법:

```java
// 프레젠테이션을 보호하려면 비밀번호를 설정하세요.
presentation.getProtectionManager().encrypt("your_password");
```

 바꾸다`"your_password"` 원하는 비밀번호로

## 6단계: 프레젠테이션 저장

마지막으로 프레젠테이션을 파일로 저장합니다. 이 예에서는 PPTX 파일로 저장합니다.

```java
// 프레젠테이션을 파일로 저장
presentation.save(dataDir + "Password_Protected_Presentation_out.pptx", SaveFormat.Pptx);
```

 바꾸다`"Password_Protected_Presentation_out.pptx"` 원하는 파일명과 경로로

## Java 슬라이드의 저장 속성에 대한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PPT 파일을 나타내는 Presentation 개체를 인스턴스화합니다.
Presentation presentation = new Presentation();
try
{
	//....여기서 일 좀 해라.....
	// 비밀번호 보호 모드에서 문서 속성에 대한 액세스 설정
	presentation.getProtectionManager().setEncryptDocumentProperties(false);
	// 비밀번호 설정
	presentation.getProtectionManager().encrypt("pass");
	// 프레젠테이션을 파일에 저장
	presentation.save(dataDir + "Password Protected Presentation_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 문서 속성을 저장하는 방법을 배웠습니다. 다양한 속성을 설정하고, 문서 속성에 대한 암호화를 비활성화하고, 보호를 위한 비밀번호를 설정하고, 프레젠테이션을 원하는 형식으로 저장할 수 있습니다.

## FAQ

### Aspose.Slides for Java에서 문서 속성을 어떻게 설정하나요?

 Aspose.Slides for Java에서 문서 속성을 설정하려면 다음을 사용할 수 있습니다.`DocumentProperties` 수업. 다음은 제목, 작성자, 키워드 등의 속성을 설정하는 방법에 대한 예입니다.

```java
// 프레젠테이션 제목 설정
presentation.getDocumentProperties().setTitle("My Presentation");

//프레젠테이션 작성자 설정
presentation.getDocumentProperties().setAuthor("John Doe");

// 프레젠테이션의 키워드 설정
presentation.getDocumentProperties().setKeywords("Aspose, Slides, Java, Tutorial");
```

### 문서 속성에 대한 암호화를 비활성화하는 목적은 무엇입니까?

문서 속성에 대한 암호화를 비활성화하면 암호화 없이 문서 메타데이터를 저장할 수 있습니다. 이는 암호를 입력하지 않고도 문서 속성(예: 제목, 작성자 등)을 보고 액세스할 수 있도록 하려는 경우 유용할 수 있습니다.

다음 코드를 사용하여 암호화를 비활성화할 수 있습니다.

```java
presentation.getProtectionManager().setEncryptDocumentProperties(false);
```

### Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 비밀번호로 보호하려면 어떻게 해야 합니까?

PowerPoint 프레젠테이션을 비밀번호로 보호하려면 다음을 사용할 수 있습니다.`encrypt` 에서 제공하는 방법`ProtectionManager` 수업. 비밀번호를 설정하는 방법은 다음과 같습니다.

```java
// 프레젠테이션을 보호하려면 비밀번호를 설정하세요.
presentation.getProtectionManager().encrypt("your_password");
```

 바꾸다`"your_password"` 원하는 비밀번호로

### 프레젠테이션을 PPTX가 아닌 다른 형식으로 저장할 수 있나요?

 예, Aspose.Slides for Java(예: PPT, PDF 등)가 지원하는 다양한 형식으로 프레젠테이션을 저장할 수 있습니다. 다른 형식으로 저장하려면`SaveFormat` 매개변수`presentation.save` 방법. 예를 들어 PDF로 저장하려면 다음을 수행하세요.

```java
presentation.save(dataDir + "Presentation.pdf", SaveFormat.Pdf);
```

### 저장 후 Presentation 객체를 폐기해야 합니까?

 시스템 리소스를 해제하려면 Presentation 개체를 삭제하는 것이 좋습니다. 당신은 사용할 수 있습니다`finally` 코드 예제에 표시된 대로 적절한 폐기를 보장하기 위해 블록을 차단합니다.

```java
finally {
    if (presentation != null) presentation.dispose();
}
```

이는 애플리케이션의 메모리 누수를 방지하는 데 도움이 됩니다.

### Aspose.Slides for Java 및 해당 기능에 대해 어떻게 더 알아볼 수 있나요?

 Java 문서용 Aspose.Slides를 탐색할 수 있습니다.[여기](https://docs.aspose.com/slides/java/) 라이브러리 사용에 대한 자세한 정보, 튜토리얼 및 예제를 확인하세요.
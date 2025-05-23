---
"description": "Aspose.Slides에서 Java 프레젠테이션의 루트 디렉터리 ClsId를 설정하는 방법을 알아보세요. CLSID를 사용하여 하이퍼링크 동작을 사용자 정의하세요."
"linktitle": "Java Slides의 루트 디렉토리 ClsId"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides의 루트 디렉토리 ClsId"
"url": "/ko/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides의 루트 디렉토리 ClsId


## Java용 Aspose.Slides에서 루트 디렉터리 ClsId 설정 소개

Java용 Aspose.Slides에서는 루트 디렉터리 ClsId를 설정할 수 있습니다. ClsId는 프레젠테이션의 하이퍼링크가 활성화될 때 루트 디렉터리로 사용될 애플리케이션을 지정하는 데 사용되는 CLSID(클래스 식별자)입니다. 이 가이드에서는 이 작업을 단계별로 안내합니다.

## 필수 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 시스템에 Java Development Kit(JDK)가 설치되어 있어야 합니다.
- Aspose.Slides for Java 라이브러리가 프로젝트에 추가되었습니다. 다음에서 다운로드할 수 있습니다. [Java용 Aspose.Slides 문서](https://reference.aspose.com/slides/java/).
- Java 개발을 위해 설정된 코드 편집기 또는 통합 개발 환경(IDE).

## 1단계: 새 프레젠테이션 만들기

먼저, Java용 Aspose.Slides를 사용하여 새 프레젠테이션을 만들어 보겠습니다. 이 예제에서는 빈 프레젠테이션을 만들어 보겠습니다.

```java
// 출력 파일 이름
String resultPath = "your_output_path/pres.ppt"; // "your_output_path"를 원하는 출력 디렉토리로 바꾸세요.
Presentation pres = new Presentation();
```

위 코드에서 출력 프레젠테이션 파일의 경로를 정의하고 새 파일을 만듭니다. `Presentation` 물체.

## 2단계: 루트 디렉터리 ClsId 설정

루트 디렉토리 ClsId를 설정하려면 인스턴스를 만들어야 합니다. `PptOptions` 원하는 CLSID를 설정하세요. CLSID는 하이퍼링크가 활성화될 때 루트 디렉터리로 사용될 응용 프로그램을 나타냅니다.

```java
PptOptions pptOptions = new PptOptions();
// CLSID를 'Microsoft Powerpoint.Show.8'로 설정합니다.
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

위의 코드에서 우리는 다음을 생성합니다. `PptOptions` 개체를 만들고 CLSID를 'Microsoft Powerpoint.Show.8'로 설정합니다. 루트 디렉터리로 사용할 응용 프로그램의 CLSID로 바꿀 수 있습니다.

## 3단계: 프레젠테이션 저장

이제 루트 디렉토리 ClsId를 설정하여 프레젠테이션을 저장해 보겠습니다.

```java
// 프레젠테이션 저장
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

이 단계에서는 지정된 위치에 프레젠테이션을 저장합니다. `resultPath` 와 함께 `PptOptions` 우리가 이전에 만든 것.

## 4단계: 정리

폐기하는 것을 잊지 마세요 `Presentation` 할당된 리소스를 해제하지 않습니다.

```java
if (pres != null) {
    pres.dispose();
}
```

## Java 슬라이드에서 루트 디렉토리 ClsId에 대한 전체 소스 코드

```java
// 출력 파일 이름
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// CLSID를 'Microsoft Powerpoint.Show.8'로 설정하세요
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// 프레젠테이션 저장
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## 결론

Aspose.Slides for Java에서 루트 디렉터리 ClsId를 성공적으로 설정했습니다. 이를 통해 프레젠테이션에서 하이퍼링크가 활성화될 때 루트 디렉터리로 사용될 애플리케이션을 지정할 수 있습니다. 특정 요구 사항에 따라 CLSID를 사용자 지정할 수 있습니다.

## 자주 묻는 질문

### 특정 애플리케이션의 CLSID를 어떻게 찾을 수 있나요?

특정 애플리케이션의 CLSID를 찾으려면 해당 애플리케이션 개발자가 제공하는 설명서나 자료를 참조하세요. CLSID는 COM 객체에 할당된 고유 식별자이며, 일반적으로 각 애플리케이션마다 고유합니다.

### 루트 디렉토리에 사용자 정의 CLSID를 설정할 수 있나요?

예, 원하는 CLSID 값을 지정하여 루트 디렉토리에 대한 사용자 정의 CLSID를 설정할 수 있습니다. `setRootDirectoryClsid` 코드 예제에서 볼 수 있듯이 이 메서드를 사용하면 프레젠테이션에서 하이퍼링크가 활성화될 때 특정 애플리케이션을 루트 디렉터리로 사용할 수 있습니다.

### 루트 디렉토리 ClsId를 설정하지 않으면 어떻게 되나요?

루트 디렉터리 ClsId를 설정하지 않으면 프레젠테이션을 여는 데 사용한 뷰어 또는 애플리케이션에 따라 기본 동작이 달라집니다. 하이퍼링크가 활성화되면 자체 기본 애플리케이션이 루트 디렉터리로 사용될 수 있습니다.

### 개별 하이퍼링크의 루트 디렉토리 ClsId를 변경할 수 있나요?

아니요, 루트 디렉터리 ClsId는 일반적으로 프레젠테이션 수준에서 설정되며 프레젠테이션 내의 모든 하이퍼링크에 적용됩니다. 각 하이퍼링크에 대해 서로 다른 적용 방식을 지정해야 하는 경우, 코드에서 해당 하이퍼링크를 별도로 처리해야 할 수 있습니다.

### 사용할 수 있는 CLSID에 제한이 있나요?

사용 가능한 CLSID는 일반적으로 시스템에 설치된 애플리케이션에 따라 결정됩니다. 하이퍼링크를 처리할 수 있는 유효한 애플리케이션에 해당하는 CLSID를 사용해야 합니다. 잘못된 CLSID를 사용하면 예기치 않은 동작이 발생할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
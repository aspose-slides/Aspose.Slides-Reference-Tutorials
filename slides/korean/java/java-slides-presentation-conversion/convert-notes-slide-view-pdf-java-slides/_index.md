---
"description": "Aspose.Slides for Java를 사용하여 노트가 포함된 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 알아보세요. 소스 코드와 함께 단계별 가이드를 따라해 보세요."
"linktitle": "Java Slides에서 Notes 슬라이드 뷰를 PDF로 변환"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 Notes 슬라이드 뷰를 PDF로 변환"
"url": "/ko/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 Notes 슬라이드 뷰를 PDF로 변환


## Java Slides에서 Notes 슬라이드 뷰를 PDF로 변환하는 방법 소개

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 노트 슬라이드 뷰가 포함된 PowerPoint 프레젠테이션을 PDF로 변환하는 과정을 안내합니다. 이 라이브러리는 Java에서 PowerPoint 프레젠테이션 작업을 위한 강력한 기능을 제공합니다.

## 필수 조건
1. Java Development Kit(JDK)가 설치되었습니다.
2. Java 라이브러리용 Aspose.Slides가 프로젝트에 추가되었습니다.

## 1단계: 필요한 클래스 가져오기
시작하려면 Aspose.Slides 라이브러리에서 필요한 클래스를 가져와야 합니다. 코드는 다음과 같습니다.

```java
import com.aspose.slides.*;
```

## 2단계: PowerPoint 프레젠테이션 로드
PowerPoint 프레젠테이션 파일을 준비하세요. `"Your Document Directory"` 프레젠테이션 파일이 있는 디렉터리 경로를 입력합니다. 프레젠테이션을 로드하는 코드는 다음과 같습니다.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## 3단계: PDF 옵션 구성
이제 PDF 내보내기 옵션을 설정해 보겠습니다. 구체적으로, PDF 슬라이드 아래에 노트가 표시되도록 노트 위치를 "BottomFull"로 설정합니다. 코드는 다음과 같습니다.

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

귀하의 요구 사항에 맞게 다른 PDF 옵션을 사용자 정의할 수 있습니다.

## 4단계: 노트와 함께 프레젠테이션을 PDF로 저장
마지막으로, 프레젠테이션을 노트를 포함한 PDF 파일로 저장해 보겠습니다. 출력 파일 이름을 지정할 수 있습니다(예: `"Pdf_Notes_out.pdf"`)을 선택하고 형식을 선택합니다.`SaveFormat.Pdf`). 이를 위한 코드는 다음과 같습니다.

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 5단계: 리소스 정리
프레젠테이션이 끝나면 리소스를 공개하는 것을 잊지 마세요.

```java
if (presentation != null) presentation.dispose();
```

## Java Slides에서 노트 슬라이드 뷰를 PDF로 변환하기 위한 완전한 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// 프레젠테이션을 PDF 노트로 저장
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 노트 슬라이드 뷰가 포함된 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 살펴보았습니다. 소스 코드를 포함한 단계별 가이드를 따라 변환 작업을 진행했습니다. 주요 내용은 다음과 같습니다.

## 자주 묻는 질문

### PDF에서 메모 위치를 어떻게 바꾸나요?

PDF에서 메모 위치를 변경하려면 다음을 수정하세요. `setNotesPosition` 메서드 인수입니다. 예를 들어 다음과 같이 설정할 수 있습니다. `NotesPositions.RightFull` 슬라이드의 오른쪽에 노트를 배치합니다.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### PDF 내보내기를 더욱 세부적으로 사용자 정의할 수 있나요?

예, 다양한 옵션을 조정하여 PDF 내보내기를 사용자 정의할 수 있습니다. `PdfOptions` 예를 들어, 필요에 따라 품질, 압축률 및 기타 매개변수를 설정할 수 있습니다.

### Java용 Aspose.Slides를 어떻게 구할 수 있나요?

Aspose.Slides for Java는 다음 웹사이트에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/java/).

### Aspose.Slides를 사용하는 데 라이선스 요구 사항이 있습니까?

네, Aspose.Slides는 상업적 용도로 유효한 라이선스가 필요합니다. Aspose 웹사이트에서 라이선스를 받으실 수 있습니다.

### 더 많은 문서와 예제는 어디에서 찾을 수 있나요?

Aspose.Slides for Java에 대한 포괄적인 설명서와 예제는 다음에서 찾을 수 있습니다. [여기](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
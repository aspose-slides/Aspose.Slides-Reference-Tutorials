---
title: Java 슬라이드에서 Notes 슬라이드 보기를 PDF로 변환
linktitle: Java 슬라이드에서 Notes 슬라이드 보기를 PDF로 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 노트가 포함된 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 알아보세요. 소스 코드가 포함된 단계별 가이드를 따르세요.
type: docs
weight: 16
url: /ko/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## Java 슬라이드에서 Notes 슬라이드 보기를 PDF로 변환하는 방법 소개

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 노트 슬라이드 보기가 포함된 PowerPoint 프레젠테이션을 PDF로 변환하는 과정을 안내합니다. 이 라이브러리는 Java에서 PowerPoint 프레젠테이션 작업을 위한 강력한 기능을 제공합니다.

## 전제조건
1. JDK(Java 개발 키트)가 설치되었습니다.
2. 프로젝트에 Java 라이브러리용 Aspose.Slides가 추가되었습니다.

## 1단계: 필요한 클래스 가져오기
시작하려면 Aspose.Slides 라이브러리에서 필요한 클래스를 가져와야 합니다. 이를 수행하는 코드는 다음과 같습니다.

```java
import com.aspose.slides.*;
```

## 2단계: PowerPoint 프레젠테이션 로드
 PowerPoint 프레젠테이션 파일이 준비되어 있어야 합니다. 바꾸다`"Your Document Directory"` 프레젠테이션 파일이 있는 디렉터리의 경로를 사용하세요. 프레젠테이션을 로드하는 코드는 다음과 같습니다.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## 3단계: PDF 옵션 구성
이제 PDF 내보내기 옵션을 구성해 보겠습니다. 특히 PDF의 슬라이드 아래에 메모를 포함하도록 메모 위치를 "BottomFull"로 설정하겠습니다. 코드는 다음과 같습니다.

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

요구 사항에 따라 다른 PDF 옵션을 사용자 정의할 수 있습니다.

## 4단계: 프리젠테이션을 메모와 함께 PDF로 저장
마지막으로 프레젠테이션을 메모를 포함하여 PDF 파일로 저장해 보겠습니다. 출력 파일 이름을 지정할 수 있습니다(예:`"Pdf_Notes_out.pdf"`)을 선택하고 형식(`SaveFormat.Pdf`). 이를 수행하는 코드는 다음과 같습니다.

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 5단계: 리소스 정리
프레젠테이션이 끝나면 리소스를 공개하는 것을 잊지 마세요.

```java
if (presentation != null) presentation.dispose();
```

## Notes 슬라이드 보기를 Java 슬라이드의 PDF로 변환하기 위한 완전한 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프리젠테이션 파일을 나타내는 Presentation 객체를 인스턴스화합니다.
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// 프레젠테이션을 PDF 노트에 저장
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## 결론

이 튜토리얼에서는 Aspose.Slides for Java 라이브러리를 사용하여 노트 슬라이드 보기가 포함된 PowerPoint 프레젠테이션을 PDF로 변환하는 방법을 살펴보았습니다. 우리는 이 변환을 달성하기 위해 소스 코드가 포함된 단계별 가이드를 따랐습니다. 주요 내용은 다음과 같습니다.

## FAQ

### PDF에서 메모 위치를 어떻게 변경합니까?

 PDF에서 메모 위치를 수정하여 변경할 수 있습니다.`setNotesPosition` 메소드 인수. 예를 들어 다음과 같이 설정할 수 있습니다.`NotesPositions.RightFull` 슬라이드 오른쪽에 메모를 배치합니다.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### PDF 내보내기를 추가로 사용자 정의할 수 있나요?

예, 다음의 다양한 옵션을 조정하여 PDF 내보내기를 사용자 정의할 수 있습니다.`PdfOptions` 물체. 예를 들어 필요에 따라 품질, 압축 및 기타 매개변수를 설정할 수 있습니다.

### Java용 Aspose.Slides를 어떻게 구할 수 있나요?

 다음 웹사이트에서 Java용 Aspose.Slides를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/java/).

### Aspose.Slides를 사용하기 위한 라이선스 요구 사항이 있나요?

예, Aspose.Slides를 상업적으로 사용하려면 유효한 라이선스가 필요합니다. Aspose 웹사이트에서 라이선스를 얻을 수 있습니다.

### 추가 문서와 예제는 어디에서 찾을 수 있나요?

 Aspose.Slides for Java에 대한 포괄적인 문서와 예제는 다음에서 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/java/).
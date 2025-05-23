---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 사용자 지정 크기의 TIFF 이미지로 변환하는 방법을 알아보세요. 개발자를 위한 코드 예제가 포함된 단계별 가이드입니다."
"linktitle": "Java Slides에서 사용자 정의 크기로 변환"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "Java Slides에서 사용자 정의 크기로 변환"
"url": "/ko/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slides에서 사용자 정의 크기로 변환


## Java Slides에서 사용자 정의 크기로 변환하는 방법 소개

이 글에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션을 사용자 지정 크기의 TIFF 이미지로 변환하는 방법을 살펴보겠습니다. Aspose.Slides for Java는 개발자가 PowerPoint 파일을 프로그래밍 방식으로 작업할 수 있도록 지원하는 강력한 라이브러리입니다. 이 작업을 수행하는 데 필요한 Java 코드를 단계별로 안내해 드리겠습니다.

## 필수 조건

시작하기에 앞서 다음과 같은 전제 조건이 충족되었는지 확인하세요.

- Java Development Kit(JDK) 설치됨
- Java용 Aspose.Slides 라이브러리

다음 웹사이트에서 Aspose.Slides for Java 라이브러리를 다운로드할 수 있습니다. [Java용 Aspose.Slides 다운로드](https://releases.aspose.com/slides/java/)

## 1단계: Aspose.Slides 라이브러리 가져오기

시작하려면 Aspose.Slides 라이브러리를 Java 프로젝트에 가져와야 합니다. 방법은 다음과 같습니다.

```java
// 필요한 import 문을 추가합니다.
import com.aspose.slides.*;
```

## 2단계: PowerPoint 프레젠테이션 로드

다음으로, TIFF 이미지로 변환하려는 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸기 `"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 포함합니다.

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";

// 프레젠테이션 파일을 나타내는 프레젠테이션 객체를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## 3단계: TIFF 변환 옵션 설정

이제 TIFF 변환 옵션을 설정해 보겠습니다. 압축 유형, DPI(인치당 도트 수), 이미지 크기, 메모 위치 등을 지정합니다. 필요에 따라 이러한 옵션을 사용자 지정할 수 있습니다.

```java
// TiffOptions 클래스를 인스턴스화합니다.
TiffOptions opts = new TiffOptions();

// 압축 유형 설정
opts.setCompressionType(TiffCompressionTypes.Default);

// 이미지 DPI 설정
opts.setDpiX(200);
opts.setDpiY(100);

// 이미지 크기 설정
opts.setImageSize(new Dimension(1728, 1078));

// 음표 위치 설정
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## 4단계: TIFF로 저장

모든 옵션을 구성했으므로 이제 지정된 설정을 사용하여 프레젠테이션을 TIFF 이미지로 저장할 수 있습니다.

```java
// 지정된 이미지 크기로 프레젠테이션을 TIFF로 저장합니다.
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java 슬라이드에서 사용자 정의 크기로 변환하기 위한 전체 소스 코드

```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일을 나타내는 프레젠테이션 객체를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptions 클래스를 인스턴스화합니다.
	TiffOptions opts = new TiffOptions();
	// 압축 유형 설정
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// 압축 유형
	// 기본값 - 기본 압축 방식(LZW)을 지정합니다.
	// 없음 - 압축을 지정하지 않습니다.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// 깊이는 압축 유형에 따라 달라지며 수동으로 설정할 수 없습니다.
	// 해상도 단위는 항상 "2"(인치당 도트 수)와 같습니다.
	// 이미지 DPI 설정
	opts.setDpiX(200);
	opts.setDpiY(100);
	// 이미지 크기 설정
	opts.setImageSize(new Dimension(1728, 1078));
	// 지정된 이미지 크기로 프레젠테이션을 TIFF로 저장합니다.
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

축하합니다! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 사용자 지정 크기의 TIFF 이미지로 성공적으로 변환했습니다. 이 기능은 다양한 용도로 프레젠테이션에서 고품질 이미지를 생성해야 할 때 매우 유용합니다.

## 자주 묻는 질문

### TIFF 이미지의 압축 유형을 어떻게 변경할 수 있나요?

압축 유형을 수정하여 변경할 수 있습니다. `setCompressionType` 방법 `TiffOptions` 클래스. Default, None, CCITT3, CCITT4, LZW, RLE 등 다양한 압축 유형을 사용할 수 있습니다.

### TIFF 이미지의 DPI(인치당 도트 수)를 조정할 수 있나요?

네, 다음을 사용하여 DPI를 조정할 수 있습니다. `setDpiX` 그리고 `setDpiY` 방법 `TiffOptions` 클래스입니다. 원하는 값을 설정하여 이미지 해상도를 제어하세요.

### TIFF 이미지에서 노트 위치를 지정하는 데 사용할 수 있는 옵션은 무엇입니까?

TIFF 이미지의 노트 위치는 다음을 사용하여 구성할 수 있습니다. `setNotesPosition` BottomFull, BottomTruncated, SlideOnly 등의 옵션을 제공하는 방식입니다. 필요에 가장 적합한 방식을 선택하세요.

### TIFF 변환 시 사용자 정의 이미지 크기를 지정할 수 있나요?

물론입니다! 다음을 사용하여 사용자 지정 이미지 크기를 설정할 수 있습니다. `setImageSize` 방법 `TiffOptions` 클래스. 출력 이미지에 사용할 크기(너비와 높이)를 입력하세요.

### Java용 Aspose.Slides에 대한 자세한 정보는 어디에서 찾을 수 있나요?

Aspose.Slides for Java에 대한 자세한 설명서와 추가 정보는 다음 설명서를 참조하세요. [Java용 Aspose.Slides API 참조](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
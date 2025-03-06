---
title: Java 슬라이드에서 사용자 정의 크기로 변환
linktitle: Java 슬라이드에서 사용자 정의 크기로 변환
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 사용자 정의 크기의 TIFF 이미지로 변환하는 방법을 알아보세요. 개발자를 위한 코드 예제가 포함된 단계별 가이드입니다.
weight: 31
url: /ko/java/presentation-conversion/convert-custom-size-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Java 슬라이드에서 사용자 정의 크기로 변환 소개

이 기사에서는 Aspose.Slides for Java API를 사용하여 PowerPoint 프레젠테이션을 사용자 정의 크기의 TIFF 이미지로 변환하는 방법을 살펴보겠습니다. Aspose.Slides for Java는 개발자가 프로그래밍 방식으로 PowerPoint 파일을 작업할 수 있게 해주는 강력한 라이브러리입니다. 우리는 단계별로 진행하여 이 작업을 수행하는 데 필요한 Java 코드를 제공할 것입니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- JDK(Java 개발 키트)가 설치되었습니다.
- Aspose.Slides for Java 라이브러리

 다음 웹사이트에서 Aspose.Slides for Java 라이브러리를 다운로드할 수 있습니다.[Java용 Aspose.Slides 다운로드](https://releases.aspose.com/slides/java/)

## 1단계: Aspose.Slides 라이브러리 가져오기

시작하려면 Aspose.Slides 라이브러리를 Java 프로젝트로 가져와야 합니다. 방법은 다음과 같습니다.

```java
// 필요한 import 문을 추가하세요.
import com.aspose.slides.*;
```

## 2단계: PowerPoint 프레젠테이션 로드

 다음으로 TIFF 이미지로 변환하려는 PowerPoint 프레젠테이션을 로드해야 합니다. 바꾸다`"Your Document Directory"` 프레젠테이션 파일의 실제 경로를 사용하세요.

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";

// 프레젠테이션 파일을 나타내는 프레젠테이션 개체를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## 3단계: TIFF 변환 옵션 설정

이제 TIFF 변환 옵션을 설정해 보겠습니다. 압축 유형, DPI(인치당 도트 수), 이미지 크기 및 메모 위치를 지정합니다. 요구 사항에 따라 이러한 옵션을 사용자 정의할 수 있습니다.

```java
// TiffOptions 클래스 인스턴스화
TiffOptions opts = new TiffOptions();

// 압축 유형 설정
opts.setCompressionType(TiffCompressionTypes.Default);

// 이미지 DPI 설정
opts.setDpiX(200);
opts.setDpiY(100);

// 이미지 크기 설정
opts.setImageSize(new Dimension(1728, 1078));

// 메모 위치 설정
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## 4단계: TIFF로 저장

모든 옵션이 구성되었으므로 이제 지정된 설정을 사용하여 프레젠테이션을 TIFF 이미지로 저장할 수 있습니다.

```java
// 지정된 이미지 크기로 프레젠테이션을 TIFF로 저장
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java 슬라이드에서 사용자 정의 크기로 변환하기 위한 전체 소스 코드

```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 프레젠테이션 파일을 나타내는 프레젠테이션 개체를 인스턴스화합니다.
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptions 클래스 인스턴스화
	TiffOptions opts = new TiffOptions();
	// 압축 유형 설정
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// 압축 유형
	// 기본값 - 기본 압축 방식(LZW)을 지정합니다.
	// 없음 - 압축하지 않음을 지정합니다.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// 깊이는 압축 유형에 따라 다르며 수동으로 설정할 수 없습니다.
	// 해상도 단위는 항상 "2"(인치당 도트 수)와 같습니다.
	// 이미지 DPI 설정
	opts.setDpiX(200);
	opts.setDpiY(100);
	// 이미지 크기 설정
	opts.setImageSize(new Dimension(1728, 1078));
	// 지정된 이미지 크기로 프레젠테이션을 TIFF로 저장
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 결론

축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션을 사용자 정의 크기의 TIFF 이미지로 성공적으로 변환했습니다. 이는 다양한 목적을 위해 프레젠테이션에서 고품질 이미지를 생성해야 할 때 유용한 기능이 될 수 있습니다.

## FAQ

### TIFF 이미지의 압축 유형을 어떻게 변경합니까?

 다음을 수정하여 압축 유형을 변경할 수 있습니다.`setCompressionType` 의 방법`TiffOptions` 수업. 기본, 없음, CCITT3, CCITT4, LZW 및 RLE와 같은 다양한 압축 유형을 사용할 수 있습니다.

### TIFF 이미지의 DPI(인치당 도트 수)를 조정할 수 있습니까?

예, 다음을 사용하여 DPI를 조정할 수 있습니다.`setDpiX` 그리고`setDpiY` 의 방법`TiffOptions` 수업. 이미지 해상도를 제어하려면 원하는 값을 설정하기만 하면 됩니다.

### TIFF 이미지의 메모 위치에 사용할 수 있는 옵션은 무엇입니까?

 TIFF 이미지의 메모 위치는 다음을 사용하여 구성할 수 있습니다.`setNotesPosition` BottomFull, BottomTruncated 및 SlideOnly와 같은 옵션이 있는 메서드입니다. 귀하의 필요에 가장 적합한 것을 선택하십시오.

### TIFF 변환을 위해 사용자 정의 이미지 크기를 지정할 수 있습니까?

 전적으로! 다음을 사용하여 사용자 정의 이미지 크기를 설정할 수 있습니다.`setImageSize` 의 방법`TiffOptions` 수업. 출력 이미지에 원하는 크기(너비 및 높이)를 제공합니다.

### Aspose.Slides for Java에 대한 자세한 정보는 어디서 찾을 수 있나요?

 Java용 Aspose.Slides에 대한 자세한 문서 및 추가 정보를 보려면 다음 문서를 방문하세요.[Java API 참조용 Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

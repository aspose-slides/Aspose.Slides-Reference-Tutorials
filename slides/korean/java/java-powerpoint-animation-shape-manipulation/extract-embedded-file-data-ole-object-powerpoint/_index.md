---
title: PowerPoint의 OLE 개체에서 포함된 파일 데이터 추출
linktitle: PowerPoint의 OLE 개체에서 포함된 파일 데이터 추출
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 포함된 파일 데이터를 추출하고 문서 관리 기능을 향상시키는 방법을 알아보세요.
weight: 22
url: /ko/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## 소개
Java 프로그래밍 영역에서 PowerPoint 프레젠테이션 내의 OLE(Object Linking and Embedding) 개체에서 포함된 파일 데이터를 추출하는 작업은 특히 문서 관리 또는 데이터 추출 응용 프로그램에서 자주 발생하는 작업입니다. Aspose.Slides for Java는 프로그래밍 방식으로 PowerPoint 프레젠테이션을 처리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 OLE 개체에서 포함된 파일 데이터를 추출하는 방법을 살펴보겠습니다.
## 전제 조건
튜토리얼을 자세히 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
- 프로젝트에서 다운로드하고 참조하는 Java 라이브러리용 Aspose.Slides.

## 패키지 가져오기
먼저, Aspose.Slides for Java에서 제공하는 기능을 활용하려면 Java 프로젝트에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

이제 프로세스를 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉터리 경로 제공
```java
String dataDir = "Your Document Directory";
```
 바꾸다`"Your Document Directory"` PowerPoint 프레젠테이션이 포함된 디렉터리의 경로를 사용하세요.
## 2단계: PowerPoint 파일 이름 지정
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
 반드시 교체하세요`"TestOlePresentation.pptx"` PowerPoint 프레젠테이션 파일의 이름으로.
## 3단계: 프레젠테이션 로드
```java
Presentation pres = new Presentation(pptxFileName);
```
 이 줄은`Presentation` 클래스, 지정된 PowerPoint 프리젠테이션 파일을 로드합니다.
## 4단계: 슬라이드와 도형 반복
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
여기서는 프레젠테이션 내의 각 슬라이드와 모양을 반복합니다.
## 5단계: OLE 개체 확인
```java
if (shape instanceof OleObjectFrame) {
```
이 조건은 모양이 OLE 개체인지 확인합니다.
## 6단계: 포함된 파일 데이터 추출
```java
OleObjectFrame oleFrame = (OleObjectFrame) shape;
byte[] data = oleFrame.getEmbeddedData().getEmbeddedFileData();
```
모양이 OLE 개체인 경우 포함된 파일 데이터를 추출합니다.
## 7단계: 파일 확장자 결정
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
이 줄은 추출된 포함 파일의 파일 확장자를 검색합니다.
## 8단계: 추출된 파일 저장
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
마지막으로 추출된 파일 데이터를 지정된 디렉터리에 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 활용하여 PowerPoint 프레젠테이션 내의 OLE 개체에서 포함된 파일 데이터를 추출하는 방법을 배웠습니다. 제공된 단계를 따르면 이 기능을 Java 애플리케이션에 원활하게 통합하여 문서 관리 기능을 향상시킬 수 있습니다.
## FAQ
### Aspose.Slides는 모든 유형의 내장 개체에서 데이터를 추출할 수 있나요?
Aspose.Slides는 OLE 개체, 차트 등을 포함한 다양한 내장 개체에서 데이터를 추출하기 위한 광범위한 지원을 제공합니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
예, Aspose.Slides는 다양한 버전의 PowerPoint 프레젠테이션과의 호환성을 보장하여 내장된 데이터의 원활한 추출을 보장합니다.
### Aspose.Slides를 상업적으로 사용하려면 라이센스가 필요합니까?
 네, Aspose.Slides를 상업적으로 사용하려면 유효한 라이선스가 필요합니다. Aspose에서 라이센스를 얻을 수 있습니다.[웹사이트](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides를 사용하여 추출 프로세스를 자동화할 수 있습니까?
물론, Aspose.Slides는 내장된 파일 데이터 추출과 같은 작업을 자동화하기 위한 포괄적인 API를 제공하여 효율적이고 간소화된 문서 처리를 가능하게 합니다.
### Aspose.Slides에 대한 추가 지원이나 지원은 어디서 찾을 수 있나요?
 문의 사항, 기술 지원 또는 커뮤니티 지원이 필요한 경우 Aspose.슬라이드 포럼을 방문하거나 설명서를 참조하세요.[Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

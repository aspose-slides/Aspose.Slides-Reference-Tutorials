---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에서 내장된 파일 데이터를 추출하는 방법을 알아보고 문서 관리 기능을 향상시켜 보세요."
"linktitle": "PowerPoint에서 OLE 개체에서 내장 파일 데이터 추출"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 OLE 개체에서 내장 파일 데이터 추출"
"url": "/ko/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 OLE 개체에서 내장 파일 데이터 추출


## 소개
Java 프로그래밍 분야에서 PowerPoint 프레젠테이션의 OLE(Object Linking and Embedding) 객체에서 내장 파일 데이터를 추출하는 작업은 특히 문서 관리 또는 데이터 추출 애플리케이션에서 자주 발생하는 작업입니다. Aspose.Slides for Java는 PowerPoint 프레젠테이션을 프로그래밍 방식으로 처리할 수 있는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Slides for Java를 사용하여 OLE 객체에서 내장 파일 데이터를 추출하는 방법을 살펴보겠습니다.
## 필수 조건
튜토리얼을 시작하기에 앞서 다음 필수 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
- 시스템에 JDK(Java Development Kit)가 설치되어 있어야 합니다.
- 프로젝트에 다운로드하여 참조하는 Java 라이브러리인 Aspose.Slides를 참조하세요.

## 패키지 가져오기
첫째, Aspose.Slides for Java가 제공하는 기능을 활용하려면 Java 프로젝트에 필요한 패키지를 가져와야 합니다.
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

이제 이 과정을 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉토리 경로 제공
```java
String dataDir = "Your Document Directory";
```
바꾸다 `"Your Document Directory"` PowerPoint 프레젠테이션이 들어 있는 디렉토리 경로를 포함합니다.
## 2단계: PowerPoint 파일 이름 지정
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
교체를 확인하세요 `"TestOlePresentation.pptx"` PowerPoint 프레젠테이션 파일의 이름을 입력합니다.
## 3단계: 프레젠테이션 로드
```java
Presentation pres = new Presentation(pptxFileName);
```
이 줄은 새 인스턴스를 초기화합니다. `Presentation` 클래스, 지정된 PowerPoint 프레젠테이션 파일을 로드합니다.
## 4단계: 슬라이드 및 도형 반복
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
여기에서는 프레젠테이션 내의 각 슬라이드와 모양을 반복합니다.
## 5단계: OLE 개체 확인
```java
if (shape instanceof OleObjectFrame) {
```
이 조건은 모양이 OLE 개체인지 확인합니다.
## 6단계: 내장된 파일 데이터 추출
```java
OleObjectFrame oleFrame = (OleObjectFrame) shape;
byte[] data = oleFrame.getEmbeddedData().getEmbeddedFileData();
```
모양이 OLE 개체인 경우, 해당 모양에 포함된 파일 데이터를 추출합니다.
## 7단계: 파일 확장자 확인
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
이 줄은 추출된 내장 파일의 파일 확장자를 검색합니다.
## 8단계: 추출된 파일 저장
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
마지막으로 추출된 파일 데이터를 지정된 디렉토리에 저장합니다.

## 결론
이 튜토리얼에서는 Aspose.Slides for Java를 활용하여 PowerPoint 프레젠테이션의 OLE 객체에서 내장 파일 데이터를 추출하는 방법을 알아보았습니다. 제공된 단계를 따라 하면 이 기능을 Java 애플리케이션에 원활하게 통합하여 문서 관리 기능을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Aspose.Slides는 모든 유형의 내장 객체에서 데이터를 추출할 수 있나요?
Aspose.Slides는 OLE 개체, 차트 등 다양한 내장 개체에서 데이터를 추출하는 데 대한 광범위한 지원을 제공합니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
네, Aspose.Slides는 다양한 버전의 PowerPoint 프레젠테이션과의 호환성을 보장하여 내장된 데이터를 원활하게 추출할 수 있습니다.
### Aspose.Slides를 상업적으로 사용하려면 라이선스가 필요합니까?
네, Aspose.Slides를 상업적으로 사용하려면 유효한 라이선스가 필요합니다. Aspose.Slides 웹사이트에서 라이선스를 받으실 수 있습니다. [웹사이트](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides를 사용하여 추출 프로세스를 자동화할 수 있나요?
물론입니다. Aspose.Slides는 내장된 파일 데이터를 추출하는 등의 작업을 자동화하는 포괄적인 API를 제공하여 효율적이고 간소화된 문서 처리가 가능합니다.
### Aspose.Slides에 대한 추가 도움이나 지원은 어디에서 받을 수 있나요?
질문, 기술 지원 또는 커뮤니티 지원이 필요한 경우 Aspose.Slides 포럼을 방문하거나 설명서를 참조하세요. [Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
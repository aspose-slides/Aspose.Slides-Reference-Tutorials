---
"description": "Aspose.Slides for Java를 사용하여 PowerPoint에서 OLE 개체 데이터를 변경하는 방법을 알아보세요. 효율적이고 간편한 업데이트를 위한 단계별 가이드입니다."
"linktitle": "PowerPoint에서 OLE 개체 데이터 변경"
"second_title": "Aspose.Slides Java PowerPoint 처리 API"
"title": "PowerPoint에서 OLE 개체 데이터 변경"
"url": "/ko/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 OLE 개체 데이터 변경

## 소개
PowerPoint 프레젠테이션에서 OLE 개체 데이터를 변경하는 것은 각 슬라이드를 직접 편집하지 않고 내장된 콘텐츠를 업데이트해야 할 때 매우 중요한 작업이 될 수 있습니다. 이 포괄적인 가이드는 PowerPoint 프레젠테이션 처리를 위해 설계된 강력한 라이브러리인 Aspose.Slides for Java를 사용하여 이 과정을 안내합니다. 숙련된 개발자든 초보자든 이 튜토리얼은 유용하고 따라 하기 쉽습니다.
## 필수 조건
코드를 살펴보기 전에 시작하는 데 필요한 모든 것이 있는지 확인해 보겠습니다.
1. Java Development Kit(JDK): 시스템에 JDK가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [오라클 사이트](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Java용 Aspose.Slides: 다음에서 최신 버전을 다운로드하세요. [Aspose.Slides 다운로드 페이지](https://releases.aspose.com/slides/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA, Eclipse, NetBeans 등 Java IDE를 사용할 수 있습니다.
4. Aspose.Cells for Java: OLE 개체 내의 내장 데이터를 수정하는 데 필요합니다. 에서 다운로드하세요. [Aspose.Cells 다운로드 페이지](https://releases.aspose.com/cells/java/).
5. 프레젠테이션 파일: OLE 개체가 포함된 PowerPoint 파일을 준비하세요. 이 튜토리얼에서는 파일 이름을 다음과 같이 지정하겠습니다. `ChangeOLEObjectData.pptx`.
## 패키지 가져오기
먼저, Java 프로젝트에 필요한 패키지를 가져오겠습니다.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

이제 이 과정을 간단하고 관리하기 쉬운 단계로 나누어 보겠습니다.
## 1단계: PowerPoint 프레젠테이션 로드
시작하려면 OLE 개체가 포함된 PowerPoint 프레젠테이션을 로드해야 합니다.
```java
// 문서 디렉토리의 경로입니다.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## 2단계: OLE 개체가 포함된 슬라이드에 액세스
다음으로, OLE 개체가 포함된 슬라이드를 가져옵니다.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3단계: 슬라이드에서 OLE 개체 찾기
슬라이드의 모양을 반복하여 OLE 개체를 찾습니다.
```java
OleObjectFrame ole = null;
// Ole 프레임의 모든 모양 탐색
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## 4단계: OLE 개체에서 내장 데이터 추출
OLE 개체가 발견되면 포함된 데이터를 추출합니다.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## 5단계: Aspose.Cells를 사용하여 내장 데이터 수정
이제 Aspose.Cells를 사용하여 내장된 데이터를 읽고 수정합니다. 이 경우에는 Excel 통합 문서일 가능성이 높습니다.
```java
    Workbook wb = new Workbook(msln);
    // 통합 문서 데이터 수정
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## 6단계: 수정된 데이터를 OLE 개체로 다시 저장
필요한 변경을 한 후 수정된 통합 문서를 OLE 개체로 다시 저장합니다.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## 7단계: 업데이트된 프레젠테이션 저장
마지막으로 업데이트된 PowerPoint 프레젠테이션을 저장합니다.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 결론
Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션의 OLE 개체 데이터를 업데이트하는 것은 간단한 단계로 나누어 보면 매우 간단합니다. 이 가이드에서는 프레젠테이션을 로드하고, 내장된 OLE 데이터에 접근하고 수정하며, 업데이트된 프레젠테이션을 저장하는 방법을 안내했습니다. 이러한 단계를 통해 PowerPoint 슬라이드에 내장된 콘텐츠를 프로그래밍 방식으로 효율적으로 관리하고 업데이트할 수 있습니다.
## 자주 묻는 질문
### PowerPoint의 OLE 개체란 무엇인가요?
OLE(개체 연결 및 포함) 개체를 사용하면 Excel 스프레드시트와 같은 다른 응용 프로그램의 콘텐츠를 PowerPoint 슬라이드에 포함할 수 있습니다.
### Aspose.Slides를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
네, Aspose.Slides는 .NET, Python, C++ 등 여러 언어를 지원합니다.
### PowerPoint에서 OLE 개체를 수정하려면 Aspose.Cells가 필요합니까?
네, OLE 개체가 Excel 스프레드시트인 경우 이를 수정하려면 Aspose.Cells가 필요합니다.
### Aspose.Slides의 평가판이 있나요?
네, 당신은 얻을 수 있습니다 [무료 체험](https://releases.aspose.com/) Aspose.Slides의 기능을 테스트합니다.
### Aspose.Slides에 대한 설명서는 어디에서 찾을 수 있나요?
자세한 문서는 다음에서 찾을 수 있습니다. [Aspose.Slides 문서 페이지](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
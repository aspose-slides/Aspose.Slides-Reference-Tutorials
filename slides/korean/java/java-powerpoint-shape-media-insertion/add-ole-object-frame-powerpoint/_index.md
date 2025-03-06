---
title: PowerPoint에서 OLE 개체 프레임 추가
linktitle: PowerPoint에서 OLE 개체 프레임 추가
second_title: Aspose.Slides Java 파워포인트 프로세싱 API
description: Aspose.Slides for Java를 사용하여 OLE 개체 프레임을 PowerPoint 프레젠테이션에 원활하게 통합하는 방법을 알아보세요.
weight: 13
url: /ko/java/java-powerpoint-shape-media-insertion/add-ole-object-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint에서 OLE 개체 프레임 추가

## 소개
PowerPoint 프레젠테이션에 OLE(개체 연결 및 포함) 개체 프레임을 추가하면 슬라이드의 시각적 매력과 기능을 크게 향상시킬 수 있습니다. Aspose.Slides for Java를 사용하면 이 프로세스가 간소화되고 효율적이 됩니다. 이 튜토리얼에서는 OLE 개체 프레임을 PowerPoint 프레젠테이션에 원활하게 통합하는 데 필요한 단계를 안내합니다.
### 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 개발 환경: 시스템에 JDK(Java Development Kit)가 설치되어 있는지 확인하십시오.
2.  Aspose.Slides for Java: 웹사이트에서 Aspose.Slides for Java를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/slides/java/).
3. Java 프로그래밍의 기본 이해: Java 프로그래밍 개념과 구문을 숙지합니다.
## 패키지 가져오기
먼저 Aspose.Slides for Java의 기능을 활용하려면 필요한 패키지를 가져와야 합니다. 방법은 다음과 같습니다.
```java
import com.aspose.slides.*;

import java.io.ByteArrayOutputStream;
import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
```
## 1단계: 환경 설정
프로젝트가 올바르게 구성되어 있고 Aspose.Slides 라이브러리가 클래스 경로에 포함되어 있는지 확인하세요.
## 2단계: 프레젠테이션 개체 초기화
작업 중인 PowerPoint 파일을 나타내는 프레젠테이션 개체를 만듭니다.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// PPTX를 나타내는 프레젠테이션 클래스 인스턴스화
Presentation pres = new Presentation();
```
## 3단계: 슬라이드에 액세스하고 개체 로드
OLE 개체 프레임을 추가하려는 슬라이드에 액세스하고 개체 파일을 로드합니다.
```java
ISlide sld = pres.getSlides().get_Item(0);
// 스트리밍할 파일 로드
FileInputStream fs = new FileInputStream(dataDir + "book1.xlsx");
ByteArrayOutputStream mstream = new ByteArrayOutputStream();
byte[] buf = new byte[4096];
while (true) {
    int bytesRead = fs.read(buf, 0, buf.length);
    if (bytesRead <= 0)
        break;
    mstream.write(buf, 0, bytesRead);
}
```
## 4단계: 포함된 데이터 개체 만들기
파일을 포함하기 위한 데이터 개체를 만듭니다.
```java
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(mstream.toByteArray(), "xlsx");
```
## 5단계: OLE 개체 프레임 추가
슬라이드에 OLE 개체 프레임 모양을 추가합니다.
```java
IOleObjectFrame oleObjectFrame = sld.getShapes().addOleObjectFrame(0, 0, (float)pres.getSlideSize().getSize().getWidth(),
        (float)pres.getSlideSize().getSize().getHeight(), dataInfo);
```
## 6단계: 프레젠테이션 저장
수정된 프레젠테이션을 디스크에 저장합니다.
```java
pres.save(outPath + "OleEmbed_out.pptx", SaveFormat.Pptx);
```

## 결론
축하해요! Aspose.Slides for Java를 사용하여 PowerPoint 프레젠테이션에 OLE 개체 프레임을 추가하는 방법을 성공적으로 배웠습니다. 이 강력한 기능을 사용하면 다양한 유형의 개체를 삽입하여 슬라이드의 상호 작용성과 시각적 매력을 향상시킬 수 있습니다.

## FAQ
### Aspose.Slides for Java를 사용하여 Excel 파일 이외의 개체를 포함할 수 있나요?
예, Word 문서, PDF 파일 등 다양한 유형의 개체를 포함할 수 있습니다.
### Aspose.Slides는 다른 버전의 PowerPoint와 호환됩니까?
Aspose.Slides는 다양한 PowerPoint 버전과의 호환성을 제공하여 원활한 통합을 보장합니다.
### OLE 개체 프레임의 모양을 사용자 지정할 수 있나요?
전적으로! Aspose.Slides는 OLE 개체 프레임의 모양과 동작을 사용자 정의하기 위한 광범위한 옵션을 제공합니다.
### Aspose.Slides for Java에 사용할 수 있는 평가판이 있습니까?
 예, 다음에서 무료 평가판을 다운로드할 수 있습니다.[여기](https://releases.aspose.com/).
### Java용 Aspose.Slides에 대한 지원은 어디서 찾을 수 있나요?
 Aspose.Slides 포럼에서 지원과 도움을 구할 수 있습니다.[여기](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

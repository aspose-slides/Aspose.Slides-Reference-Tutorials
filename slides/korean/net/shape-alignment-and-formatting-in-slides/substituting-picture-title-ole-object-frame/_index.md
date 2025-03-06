---
title: .NET용 Aspose.Slides를 사용한 OLE 개체 가이드 포함
linktitle: 프레젠테이션 슬라이드에서 OLE 개체 프레임의 그림 제목 대체
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: Aspose.Slides for .NET을 사용하여 동적 OLE 개체로 프레젠테이션 슬라이드를 향상시키는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 15
url: /ko/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 소개
역동적이고 매력적인 프레젠테이션 슬라이드를 만들려면 다양한 멀티미디어 요소를 통합해야 하는 경우가 많습니다. 이 튜토리얼에서는 강력한 Aspose.Slides for .NET 라이브러리를 사용하여 프레젠테이션 슬라이드에서 OLE(Object Linking and Embedding) 개체 프레임의 그림 제목을 대체하는 방법을 살펴보겠습니다. Aspose.Slides는 OLE 개체 처리 프로세스를 단순화하여 개발자에게 프레젠테이션을 쉽게 향상시킬 수 있는 도구를 제공합니다.
## 전제 조건
단계별 가이드를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
-  .NET 라이브러리용 Aspose.Slides: .NET 라이브러리용 Aspose.Slides가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Slides .NET 문서](https://reference.aspose.com/slides/net/).
- 샘플 데이터: 프레젠테이션에 OLE 개체로 포함할 샘플 Excel 파일(예: "ExcelObject.xlsx")을 준비합니다. 또한 OLE 개체의 아이콘 역할을 할 이미지 파일(예: "Image.png")이 있어야 합니다.
- 개발 환경: Visual Studio 또는 .NET 개발을 위해 선호하는 기타 IDE와 같은 필수 도구를 사용하여 개발 환경을 설정합니다.
## 네임스페이스 가져오기
.NET 프로젝트에서 Aspose.Slides 작업에 필요한 네임스페이스를 가져와야 합니다.
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## 1단계: 문서 디렉터리 설정
```csharp
string dataDir = "Your Document Directory";
```
"Your Document Directory"를 문서 디렉터리의 실제 경로로 바꾸십시오.
## 2단계: OLE 소스 파일 및 아이콘 파일 경로 정의
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
샘플 Excel 파일 및 이미지 파일의 실제 경로로 이러한 경로를 업데이트하세요.
## 3단계: 프레젠테이션 인스턴스 만들기
```csharp
using (Presentation pres = new Presentation())
{
    // 후속 단계에 대한 코드가 여기에 표시됩니다.
}
```
 새 인스턴스를 초기화합니다.`Presentation` 수업.
## 4단계: OLE 개체 프레임 추가
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
위치와 크기를 지정하여 OLE 개체 프레임을 슬라이드에 추가합니다.
## 5단계: 이미지 개체 추가
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
이미지 파일을 읽고 프레젠테이션에 이미지 개체로 추가합니다.
## 6단계: 캡션을 OLE 아이콘으로 설정
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
OLE 아이콘에 원하는 캡션을 설정합니다.
## 결론
Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드에 OLE 개체를 통합하는 과정은 간단합니다. 이 튜토리얼에서는 문서 디렉터리 설정부터 OLE 개체 추가 및 사용자 정의까지 필수 단계를 안내했습니다. 프레젠테이션의 시각적 매력을 향상시키기 위해 다양한 파일 형식과 캡션을 실험해보세요.
## 자주 묻는 질문
### Aspose.Slides를 사용하여 다른 유형의 파일을 OLE 개체로 포함할 수 있나요?
예, Aspose.Slides는 Excel 스프레드시트, Word 문서 등과 같은 다양한 유형의 파일 삽입을 지원합니다.
### OLE 개체 아이콘을 사용자 정의할 수 있나요?
전적으로. 프레젠테이션 테마에 더 잘 어울리도록 기본 아이콘을 원하는 이미지로 바꿀 수 있습니다.
### Aspose.Slides는 OLE 개체가 포함된 애니메이션을 지원합니까?
최신 버전부터 Aspose.Slides는 OLE 개체 삽입 및 표시에 중점을 두고 있으며 OLE 개체 내의 애니메이션을 직접 처리하지 않습니다.
### OLE 개체를 슬라이드에 추가한 후 프로그래밍 방식으로 조작할 수 있습니까?
틀림없이. OLE 개체를 프로그래밍 방식으로 완전히 제어할 수 있으므로 필요에 따라 개체의 속성과 모양을 수정할 수 있습니다.
### 포함된 OLE 개체의 크기에 제한이 있습니까?
크기 제한이 있지만 일반적으로 관대합니다. 최적의 성능을 보장하려면 특정 사용 사례로 테스트하는 것이 좋습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

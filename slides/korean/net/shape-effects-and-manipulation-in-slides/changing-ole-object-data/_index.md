---
"description": "OLE 개체 데이터를 손쉽게 변경하는 Aspose.Slides for .NET의 강력한 기능을 살펴보세요. 동적 콘텐츠로 프레젠테이션을 더욱 풍성하게 만들어 보세요."
"linktitle": "Aspose.Slides를 사용하여 프레젠테이션에서 OLE 개체 데이터 변경"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "Aspose.Slides를 사용하여 프레젠테이션에서 OLE 개체 데이터 변경"
"url": "/ko/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides를 사용하여 프레젠테이션에서 OLE 개체 데이터 변경

## 소개
오늘날 디지털 세상에서는 역동적이고 인터랙티브한 파워포인트 프레젠테이션을 만드는 것이 필수적입니다. 이러한 요구 사항을 충족하는 강력한 도구 중 하나는 개발자가 파워포인트 프레젠테이션을 프로그래밍 방식으로 조작하고 향상시킬 수 있는 강력한 라이브러리인 Aspose.Slides for .NET입니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 프레젠테이션 슬라이드 내의 OLE(개체 연결 및 포함) 개체 데이터를 변경하는 과정을 자세히 살펴보겠습니다.
## 필수 조건
Aspose.Slides for .NET을 사용하기 전에 다음 필수 구성 요소가 있는지 확인하세요.
1. 개발 환경: .NET이 설치된 개발 환경을 설정합니다.
2. Aspose.Slides 라이브러리: Aspose.Slides for .NET 라이브러리를 다운로드하여 설치하세요. 라이브러리는 다음 위치에서 찾을 수 있습니다. [여기](https://releases.aspose.com/slides/net/).
3. 기본 이해: C# 프로그래밍과 PowerPoint 프레젠테이션의 기본 개념에 익숙해지세요.
## 네임스페이스 가져오기
C# 프로젝트에서 Aspose.Slides 기능을 사용하는 데 필요한 네임스페이스를 가져옵니다.
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## 1단계: 프로젝트 설정
새 C# 프로젝트를 만들고 Aspose.Slides 라이브러리를 가져오는 것으로 시작하세요. 프로젝트가 올바르게 구성되었고 필요한 종속성이 있는지 확인하세요.
## 2단계: 프레젠테이션 및 슬라이드 액세스
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## 3단계: OLE 개체 찾기
슬라이드의 모든 모양을 탐색하여 OLE 개체 프레임을 찾으세요.
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## 4단계: 통합 문서 데이터 읽기 및 수정
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Workbook에서 개체 데이터 읽기
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // 통합 문서 데이터 수정
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Ole 프레임 객체 데이터 변경
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## 5단계: 프레젠테이션 저장
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## 결론
다음 단계를 따르면 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드 내의 OLE 개체 데이터를 원활하게 변경할 수 있습니다. 이를 통해 특정 요구 사항에 맞춰 동적이고 사용자 정의된 프레젠테이션을 제작할 수 있는 무한한 가능성이 열립니다.
## 자주 묻는 질문
### Aspose.Slides for .NET이란 무엇인가요?
.NET용 Aspose.Slides는 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업하고 쉽게 조작하고 향상시킬 수 있는 강력한 라이브러리입니다.
### Aspose.Slides 문서는 어디에서 찾을 수 있나요?
.NET용 Aspose.Slides에 대한 설명서를 찾을 수 있습니다. [여기](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET을 어떻게 다운로드하나요?
라이브러리는 릴리스 페이지에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).
### Aspose.Slides에 대한 무료 평가판이 있나요?
네, 무료 체험판을 이용하실 수 있습니다. [여기](https://releases.aspose.com/).
### .NET용 Aspose.Slides에 대한 지원은 어디에서 받을 수 있나요?
지원 및 토론을 위해 다음을 방문하세요. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
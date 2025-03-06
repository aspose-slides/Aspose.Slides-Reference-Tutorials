---
title: Aspose.Slides를 사용하여 프레젠테이션에서 OLE 개체 데이터 변경
linktitle: Aspose.Slides를 사용하여 프레젠테이션에서 OLE 개체 데이터 변경
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: OLE 개체 데이터를 손쉽게 변경하는 데 있어 Aspose.Slides for .NET의 강력한 기능을 살펴보세요. 동적 콘텐츠로 프레젠테이션을 향상시키세요.
weight: 25
url: /ko/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 소개
역동적이고 대화형인 PowerPoint 프레젠테이션을 만드는 것은 오늘날 디지털 세계의 일반적인 요구 사항입니다. 이를 달성하기 위한 강력한 도구 중 하나는 개발자가 프로그래밍 방식으로 PowerPoint 프레젠테이션을 조작하고 향상시킬 수 있는 강력한 라이브러리인 Aspose.Slides for .NET입니다. 이 튜토리얼에서는 Aspose.Slides를 사용하여 프레젠테이션 슬라이드 내의 OLE(Object Linking and Embedding) 개체 데이터를 변경하는 프로세스를 살펴보겠습니다.
## 전제 조건
.NET용 Aspose.Slides 작업을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. 개발 환경: .NET이 설치된 개발 환경을 설정합니다.
2.  Aspose.Slides 라이브러리: Aspose.Slides for .NET 라이브러리를 다운로드하고 설치합니다. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/slides/net/).
3. 기본 이해: C# 프로그래밍 및 PowerPoint 프레젠테이션의 기본 개념을 숙지합니다.
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
새 C# 프로젝트를 만들고 Aspose.Slides 라이브러리를 가져오는 것으로 시작하세요. 프로젝트가 올바르게 구성되었는지, 필요한 종속성이 있는지 확인하세요.
## 2단계: 프레젠테이션 및 슬라이드에 액세스
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
슬라이드의 모든 셰이프를 탐색하여 OLE 개체 프레임을 찾습니다.
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
        // 통합 문서에서 개체 데이터 읽기
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
다음 단계를 수행하면 Aspose.Slides for .NET을 사용하여 프레젠테이션 슬라이드 내에서 OLE 개체 데이터를 원활하게 변경할 수 있습니다. 이는 귀하의 특정 요구에 맞는 역동적이고 사용자 정의된 프레젠테이션을 만들 수 있는 가능성의 세계를 열어줍니다.
## 자주 묻는 질문
### .NET용 Aspose.Slides란 무엇입니까?
Aspose.Slides for .NET은 개발자가 PowerPoint 프레젠테이션을 프로그래밍 방식으로 작업하여 쉽게 조작하고 개선할 수 있도록 하는 강력한 라이브러리입니다.
### Aspose.Slides 문서는 어디서 찾을 수 있나요?
 .NET용 Aspose.Slides에 대한 설명서를 찾을 수 있습니다.[여기](https://reference.aspose.com/slides/net/).
### .NET용 Aspose.Slides를 어떻게 다운로드하나요?
 릴리스 페이지에서 라이브러리를 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).
### Aspose.Slides에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### .NET용 Aspose.Slides에 대한 지원은 어디서 받을 수 있나요?
 지원 및 토론을 원하시면 다음 사이트를 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

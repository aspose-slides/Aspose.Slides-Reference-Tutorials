---
"date": "2025-04-15"
"description": "Aspose.Slides .NET을 사용하여 PowerPoint 프레젠테이션에서 OLE 개체를 편집하는 방법을 알아보세요. 이 가이드에서는 슬라이드 내에 포함된 Excel 스프레드시트를 추출, 수정 및 업데이트하는 방법을 다룹니다."
"title": "Aspose.Slides .NET을 사용하여 PowerPoint에서 OLE 개체 편집하기 - 단계별 가이드"
"url": "/ko/net/ole-objects-embedding/edit-ole-objects-powerpoint-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET을 사용하여 PowerPoint에서 OLE 개체 편집: 단계별 가이드

## 소개

Excel 스프레드시트와 같은 개체를 PowerPoint 프레젠테이션에 포함하면 상호 작용성과 기능성이 향상됩니다. 하지만 프레젠테이션 내에서 이러한 포함된 OLE(개체 연결 및 포함) 개체를 직접 편집하려면 적절한 도구가 필요합니다. 이 가이드에서는 Aspose.Slides .NET을 사용하여 PowerPoint에서 OLE 개체를 편집하는 방법을 보여줍니다.

이 튜토리얼에서는 다음 내용을 학습합니다.
- 프레젠테이션에서 OLE 개체 프레임을 추출하는 방법
- 내장된 Excel 통합 문서 내에서 데이터를 수정하는 방법
- 프레젠테이션에 변경 사항을 업데이트하고 다시 저장하는 방법

각 단계로 들어가기 전에 전제 조건을 충족하고 환경을 설정했는지 확인하세요.

## 필수 조건

### 필수 라이브러리 및 종속성
이 튜토리얼을 따르려면 다음 사항이 필요합니다.
- .NET용 Aspose.Slides(버전 22.x 이상)
- .NET용 Aspose.Cells(Excel 작업용)

### 환경 설정 요구 사항
이 가이드에서는 C# 프로그래밍과 Visual Studio 같은 .NET 개발 환경에 대한 기본적인 지식이 있다고 가정합니다.

### 지식 전제 조건
C#의 객체 지향 프로그래밍 개념을 이해하는 것이 좋습니다. PowerPoint 프레젠테이션과 OLE 개체에 대한 지식이 있으면 좋습니다.

## .NET용 Aspose.Slides 설정

시작하려면 Aspose.Slides 패키지를 설치하세요.

**.NET CLI 사용:**
```bash
dotnet add package Aspose.Slides
```

**패키지 관리자 사용:**
```powershell
Install-Package Aspose.Slides
```

또는 Visual Studio의 NuGet 패키지 관리자 UI를 사용하여 "Aspose.Slides"를 검색하여 설치합니다.

### 라이센스 취득 단계
- **무료 체험:** 무료 평가판을 다운로드하세요 [릴리스 페이지](https://releases.aspose.com/slides/net/).
- **임시 면허:** 더 광범위한 테스트를 위해서는 다음을 통해 임시 라이센스를 얻으십시오. [임시 면허 페이지](https://purchase.aspose.com/temporary-license/).
- **구입:** 귀하의 요구 사항에 맞는다고 생각되면 구매를 고려해 보세요. [구매 페이지](https://purchase.aspose.com/buy) 자세한 내용은.

### 기본 초기화 및 설정
설치가 완료되면 프로젝트에서 Aspose.Slides를 초기화하여 프레젠테이션 작업을 시작하세요.

```csharp
using Aspose.Slides;
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation presentation = new Presentation(dataDir + "/YourPresentation.pptx");
```

## 구현 가이드
명확성을 위해 프로세스를 여러 가지 특징으로 나누어 설명하겠습니다.

### 기능 1: 프레젠테이션에서 OLE 개체 추출

**개요:** 이 기능은 PowerPoint 슬라이드에서 내장된 OLE 개체 프레임을 찾아 추출하는 방법을 보여줍니다.

#### 단계별 지침
**프레젠테이션 초기화**
```csharp
using Aspose.Slides;
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation pres = new Presentation(dataDir + "/ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```

**OLE 프레임 찾기**
```csharp
    OleObjectFrame ole = null;

    foreach (IShape shape in slide.Shapes)
    {
        if (shape is OleObjectFrame)
        {
            ole = (OleObjectFrame)shape;
        }
    }
}
```
- **설명:** 첫 번째 슬라이드의 모양을 반복하면서 각 모양의 유형 검사를 통해 OLE 프레임을 식별하고 추출합니다.

### 기능 2: 추출된 OLE 개체에서 통합 문서 데이터 수정

**개요:** 추출 후 OLE 개체로 내장된 Excel 통합 문서 내의 데이터를 수정합니다.

#### 단계별 지침
**내장된 통합 문서 로드**
```csharp
using Aspose.Cells;
OleObjectFrame ole = null; // 'ole'가 이미 할당되었다고 가정합니다.

if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        Workbook Wb = new Workbook(msln);
```

**워크시트 데이터 수정**
```csharp
        using (MemoryStream msout = new MemoryStream())
        {
            // 첫 번째 워크시트 수정
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);

            OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.Xlsx);
            Wb.Save(msout, so1);
        }
    }
}
```
- **설명:** 내장된 데이터 스트림에서 통합 문서를 로드하고, 특정 셀 값을 수정하고, 메모리 스트림에 변경 사항을 저장합니다.

### 기능 3: 수정된 통합 문서 데이터로 OLE 개체 업데이트

**개요:** 이 기능은 수정된 통합 문서 내용에서 파생된 새 데이터로 기존 OLE 개체 프레임을 업데이트합니다.

#### 단계별 지침
```csharp
using Aspose.Slides.DOM.Ole;
OleObjectFrame ole = null; // 'ole'가 이미 할당되었다고 가정합니다.

MemoryStream msout = new MemoryStream(); // 수정된 통합 문서 데이터

if (ole != null)
{
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
    ole.SetEmbeddedData(newData);
}
```
- **설명:** 업데이트된 스트림으로 새 내장 데이터 개체를 만들고 다음을 사용하여 이전 OLE 데이터를 교체합니다. `SetEmbeddedData`.

### 기능 4: 업데이트된 프레젠테이션 저장

**개요:** 프레젠테이션을 디스크에 다시 저장하여 변경 사항을 마무리합니다.

#### 단계별 지침
```csharp
using Aspose.Slides;
string outputDir = "YOUR_OUTPUT_DIRECTORY";
Presentation pres = new Presentation(); // 'pres'가 업데이트된 데이터로 로드되었다고 가정합니다.

// 수정된 프레젠테이션을 저장합니다
pres.Save(outputDir + "/OleEdit_out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
- **설명:** 사용하세요 `Save` 모든 변경 사항을 파일에 다시 기록하여 수정 사항이 지속되도록 하는 방법입니다.

## 실제 응용 프로그램
1. **자동 보고서 업데이트:** 회사 프레젠테이션에 내장된 재무 스프레드시트를 자동으로 업데이트합니다.
2. **동적 데이터 통합:** 수동 개입 없이 업데이트된 데이터 세트를 마케팅 자료에 원활하게 통합합니다.
3. **템플릿 사용자 정의:** 개인화된 고객 제안을 위해 동적 콘텐츠로 템플릿을 사용자 정의하세요.
4. **교육 자료 강화:** 대화형 차트나 표를 삽입하고 업데이트하여 교육용 프레젠테이션을 더욱 풍부하게 만드세요.

## 성능 고려 사항
- **메모리 사용 최적화:** 사용 `MemoryStream` 대용량 파일을 처리할 때 과도한 메모리 소모를 효율적으로 방지합니다.
- **스트림 관리:** 스트림이 적절하게 처리되었는지 확인하십시오. `using` 리소스 누출을 방지하기 위한 진술.
- **일괄 처리:** 여러 개의 프레젠테이션을 처리하는 경우 성능을 향상시키려면 작업을 일괄 처리하는 것을 고려하세요.

## 결론
이 가이드를 따라 하면 Aspose.Slides .NET을 사용하여 PowerPoint에서 OLE 개체를 추출, 수정 및 업데이트하는 방법을 배울 수 있습니다. 이 기능을 사용하면 프레젠테이션에서 동적 콘텐츠 업데이트가 필요한 작업을 크게 간소화할 수 있습니다.

다음 단계로는 Aspose.Slides의 더욱 고급 기능을 탐색하거나 이러한 기능을 대규모 자동화 워크플로에 통합하는 것이 포함될 수 있습니다.

## FAQ 섹션
1. **OLE 개체란 무엇인가요?**
   - OLE 개체를 사용하면 PowerPoint 슬라이드에 Excel 스프레드시트와 같은 개체를 포함하여 대화형 및 동적인 프레젠테이션을 용이하게 할 수 있습니다.
2. **하나의 프레젠테이션에서 여러 OLE 개체를 편집할 수 있나요?**
   - 네, 모든 슬라이드와 도형을 반복하여 필요에 따라 내장된 각 OLE 개체를 찾아 수정합니다.
3. **내장된 데이터가 Excel 파일이 아닌 경우는 어떻게 되나요?**
   - Aspose.Slides는 다양한 파일 형식을 지원합니다. 적절한 라이브러리를 사용해야 합니다(예: Word 문서의 경우 Aspose.Words).
4. **많은 OLE 개체가 포함된 대규모 프레젠테이션을 어떻게 처리합니까?**
   - 애플리케이션 성능을 유지하기 위해 메모리 사용량을 최적화하고 일괄 처리를 고려하세요.
5. **다른 PowerPoint 형식도 지원되나요?**
   - 네, Aspose.Slides는 PPTX, PPTM 등 다양한 형식을 지원합니다. 자세한 내용은 설명서를 참조하세요.

## 자원
- [Aspose 문서](https://reference.aspose.com/slides/net/)
- [Aspose.Slides .NET 다운로드](https://downloads.aspose.com/slides/net)
- [커뮤니티 포럼](https://forum.aspose.com/c/slides)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
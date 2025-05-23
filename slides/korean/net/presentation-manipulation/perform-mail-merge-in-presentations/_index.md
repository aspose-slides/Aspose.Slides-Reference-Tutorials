---
"description": "이 단계별 가이드를 통해 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 메일 병합 기능을 활용하는 방법을 알아보세요. 역동적이고 개인화된 프레젠테이션을 손쉽게 제작할 수 있습니다."
"linktitle": "프레젠테이션에서 메일 병합 수행"
"second_title": "Aspose.Slides .NET PowerPoint 처리 API"
"title": "프레젠테이션에서 메일 병합 수행"
"url": "/ko/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 프레젠테이션에서 메일 병합 수행

## 소개
.NET 개발 분야에서는 동적이고 개인화된 프레젠테이션을 만드는 것이 일반적인 요구 사항입니다. 이러한 과정을 간소화하는 강력한 도구 중 하나가 Aspose.Slides for .NET입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 편지 병합을 수행하는 흥미로운 영역을 살펴보겠습니다.
## 필수 조건
이 여정을 시작하기 전에 다음과 같은 전제 조건이 충족되었는지 확인하세요.
- Aspose.Slides for .NET 라이브러리: Aspose.Slides for .NET 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다. [여기](https://releases.aspose.com/slides/net/).
- 문서 템플릿: 메일 병합의 기반이 될 프레젠테이션 템플릿(예: PresentationTemplate.pptx)을 준비합니다.
- 데이터 소스: 메일 병합을 위한 데이터 소스가 필요합니다. 이 예시에서는 XML 데이터(TestData.xml)를 사용하지만, Aspose.Slides는 RDBMS 등 다양한 데이터 소스를 지원합니다.
이제 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 메일 병합을 수행하는 단계를 살펴보겠습니다.
## 네임스페이스 가져오기
첫째, Aspose.Slides에서 제공하는 기능을 활용하기 위해 필요한 네임스페이스를 가져와야 합니다.
```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Export;
using DataTable = System.Data.DataTable;
```
## 1단계: 문서 디렉터리 설정
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// 결과 경로가 존재하는지 확인하세요
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## 2단계: XML 데이터를 사용하여 데이터 세트 만들기
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 3단계: 레코드를 반복하고 개별 프레젠테이션을 만듭니다.
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // 결과 생성(개별) 프레젠테이션 이름
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // 프레젠테이션 템플릿 로드
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // 메인 테이블의 데이터로 텍스트 상자 채우기
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // 데이터베이스에서 이미지 가져오기
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // 프레젠테이션의 사진 프레임에 이미지 삽입
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // 데이터로 채우기 위해 텍스트 프레임을 가져와 준비합니다.
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // 직원 데이터 채우기
        FillStaffList(textFrame, userRow, staffListTable);
        // 계획 사실 데이터 채우기
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## 4단계: 텍스트 프레임을 목록으로 데이터 채우기
```csharp
static void FillStaffList(ITextFrame textFrame, DataRow userRow, DataTable staffListTable)
{
    foreach (DataRow listRow in staffListTable.Rows)
    {
        if (listRow["UserId"].ToString() == userRow["Id"].ToString())
        {
            Paragraph para = new Paragraph();
            para.ParagraphFormat.Bullet.Type = BulletType.Symbol;
            para.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
            para.Text = listRow["Name"].ToString();
            para.ParagraphFormat.Bullet.Color.ColorType = ColorType.RGB;
            para.ParagraphFormat.Bullet.Color.Color = Color.Black;
            para.ParagraphFormat.Bullet.IsBulletHardColor = NullableBool.True;
            para.ParagraphFormat.Bullet.Height = 100;
            textFrame.Paragraphs.Add(para);
        }
    }
}
```
## 5단계: 보조 PlanFact 테이블에서 데이터 차트 채우기
```csharp
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";
    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();
    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;
    // 선 시리즈에 대한 데이터 포인트 추가
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries
(cellsFactory.GetCell(worksheetIndex, 1, 1, double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2, double.Parse(selRows[0]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1, double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2, double.Parse(selRows[1]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[2]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[3]["FactData"].ToString())));
    chart.ChartData.SetRange(range);
}
```
이 단계에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 편지 병합을 수행하는 방법에 대한 포괄적인 가이드를 보여줍니다. 이제 자주 묻는 몇 가지 질문에 답해 보겠습니다.
## 자주 묻는 질문
### 1. Aspose.Slides for .NET은 다양한 데이터 소스와 호환됩니까?
네, Aspose.Slides for .NET은 XML, RDBMS 등 다양한 데이터 소스를 지원합니다.
### 2. 생성된 프레젠테이션에서 글머리 기호의 모양을 사용자 지정할 수 있나요?
물론입니다! 글머리 기호의 모양을 완벽하게 제어할 수 있습니다. `FillStaffList` 방법.
### 3. Aspose.Slides for .NET을 사용하여 어떤 유형의 차트를 만들 수 있나요?
.NET용 Aspose.Slides는 예시에서 보여준 선형 차트를 비롯해 막대 차트, 원형 차트 등 다양한 차트를 지원합니다.
### 4. Aspose.Slides for .NET에 대한 지원이나 도움을 받으려면 어떻게 해야 하나요?
지원 및 도움을 받으려면 다음을 방문하세요. [Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### 5. 구매하기 전에 Aspose.Slides for .NET을 사용해 볼 수 있나요?
물론입니다! Aspose.Slides for .NET 무료 체험판을 다음에서 이용하실 수 있습니다. [여기](https://releases.aspose.com/).
## 결론
이 튜토리얼에서는 프레젠테이션에서 메일 병합을 수행하는 Aspose.Slides for .NET의 흥미로운 기능을 살펴보았습니다. 단계별 가이드를 따라 하면 역동적이고 개인화된 프레젠테이션을 손쉽게 만들 수 있습니다. Aspose.Slides를 사용하여 원활한 프레젠테이션 생성을 통해 .NET 개발 경험을 향상시키세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
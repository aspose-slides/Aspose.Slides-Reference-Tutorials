---
title: 프레젠테이션에서 메일 병합 수행
linktitle: 프레젠테이션에서 메일 병합 수행
second_title: Aspose.Slides .NET 파워포인트 처리 API
description: 이 단계별 가이드에서 .NET용 Aspose.Slides를 사용하여 프레젠테이션에서 메일 병합을 알아보세요. 역동적이고 개인화된 프레젠테이션을 손쉽게 만들어 보세요.
type: docs
weight: 21
url: /ko/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## 소개
.NET 개발 세계에서는 동적이고 개인화된 프레젠테이션을 만드는 것이 일반적인 요구 사항입니다. 이 프로세스를 단순화하는 강력한 도구 중 하나는 .NET용 Aspose.Slides입니다. 이 튜토리얼에서는 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 메일 병합을 수행하는 흥미로운 영역을 살펴보겠습니다.
## 전제 조건
이 여정을 시작하기 전에 다음과 같은 전제 조건이 갖추어져 있는지 확인하세요.
- .NET 라이브러리용 Aspose.Slides: .NET 라이브러리용 Aspose.Slides가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/slides/net/).
- 문서 템플릿: 메일 병합의 기반이 될 프레젠테이션 템플릿(예: PresentationTemplate.pptx)을 준비합니다.
- 데이터 소스: 메일 병합을 위한 데이터 소스가 필요합니다. 이 예에서는 XML 데이터(TestData.xml)를 사용하지만 Aspose.Slides는 RDBMS와 같은 다양한 데이터 소스를 지원합니다.
이제 Aspose.Slides for .NET을 사용하여 프레젠테이션에서 메일 병합을 수행하는 단계를 살펴보겠습니다.
## 네임스페이스 가져오기
먼저 Aspose.Slides에서 제공하는 기능을 활용하려면 필요한 네임스페이스를 가져와야 합니다.
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
## 1단계: 문서 디렉토리 설정
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// 결과 경로가 존재하는지 확인
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## 2단계: XML 데이터를 사용하여 DataSet 만들기
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 3단계: 기록 반복 및 개별 프레젠테이션 만들기
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // 결과 생성(개별) 프레젠테이션 이름
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // 프리젠테이션 템플릿 로드
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // 기본 테이블의 데이터로 텍스트 상자 채우기
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // 데이터베이스에서 이미지 가져오기
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //프레젠테이션의 액자에 이미지 삽입
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // 데이터로 채울 텍스트 프레임을 가져와 준비합니다.
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
## 4단계: 데이터를 목록으로 텍스트 프레임 채우기
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
    // 선 계열에 대한 데이터 포인트 추가
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
이 단계에서는 .NET용 Aspose.Slides를 사용하여 프레젠테이션에서 메일 병합을 수행하는 방법에 대한 포괄적인 가이드를 보여줍니다. 이제 자주 묻는 몇 가지 질문을 살펴보겠습니다.
## 자주 묻는 질문
### 1. Aspose.Slides for .NET은 다른 데이터 소스와 호환됩니까?
예, Aspose.Slides for .NET은 XML, RDBMS 등을 포함한 다양한 데이터 소스를 지원합니다.
### 2. 생성된 프리젠테이션에서 글머리 기호 모양을 사용자 정의할 수 있습니까?
 틀림없이! 다음에서 설명한 대로 글머리 기호 모양을 완전히 제어할 수 있습니다.`FillStaffList` 방법.
### 3. Aspose.Slides for .NET을 사용하여 어떤 유형의 차트를 만들 수 있나요?
.NET용 Aspose.Slides는 예제에 표시된 선 차트, 막대 차트, 원형 차트 등을 포함하여 광범위한 차트를 지원합니다.
### 4. Aspose.Slides for .NET에 대한 지원을 받거나 도움을 받으려면 어떻게 해야 합니까?
 지원 및 지원을 받으려면 다음을 방문하세요.[Aspose.Slides 포럼](https://forum.aspose.com/c/slides/11).
### 5. 구매하기 전에 Aspose.Slides for .NET을 사용해 볼 수 있나요?
 틀림없이! .NET용 Aspose.Slides의 무료 평가판을 다음에서 이용할 수 있습니다.[여기](https://releases.aspose.com/).
## 결론
이 튜토리얼에서는 프레젠테이션에서 메일 병합을 수행할 때 Aspose.Slides for .NET의 흥미로운 기능을 살펴보았습니다. 단계별 가이드를 따르면 역동적이고 개인화된 프레젠테이션을 쉽게 만들 수 있습니다. 원활한 프레젠테이션 생성을 위해 Aspose.Slides를 사용하여 .NET 개발 경험을 향상하세요.
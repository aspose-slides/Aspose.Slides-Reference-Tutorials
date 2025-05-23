---
"description": "เรียนรู้การผสานจดหมายในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ในคู่มือทีละขั้นตอนนี้ สร้างงานนำเสนอที่เป็นแบบไดนามิกและปรับแต่งได้เองได้อย่างง่ายดาย"
"linktitle": "ดำเนินการผสานจดหมายในงานนำเสนอ"
"second_title": "API การประมวลผล PowerPoint ของ Aspose.Slides .NET"
"title": "ดำเนินการผสานจดหมายในงานนำเสนอ"
"url": "/th/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ดำเนินการผสานจดหมายในงานนำเสนอ

## การแนะนำ
ในโลกของการพัฒนา .NET การสร้างงานนำเสนอแบบไดนามิกและปรับแต่งตามความต้องการทั่วไปถือเป็นข้อกำหนดทั่วไป เครื่องมืออันทรงพลังที่ช่วยลดความซับซ้อนของกระบวนการนี้คือ Aspose.Slides สำหรับ .NET ในบทช่วยสอนนี้ เราจะเจาะลึกถึงขอบเขตที่น่าสนใจของการทำจดหมายเวียนในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้นการเดินทางครั้งนี้ โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
- ไลบรารี Aspose.Slides สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ .NET แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/net/).
- เทมเพลตเอกสาร: เตรียมเทมเพลตการนำเสนอ (เช่น PresentationTemplate.pptx) ที่จะทำหน้าที่เป็นฐานสำหรับการผสานจดหมาย
- แหล่งข้อมูล: คุณต้องมีแหล่งข้อมูลสำหรับการผสานจดหมาย ในตัวอย่างของเรา เราจะใช้ข้อมูล XML (TestData.xml) แต่ Aspose.Slides รองรับแหล่งข้อมูลต่างๆ เช่น RDBMS
ตอนนี้เรามาดูขั้นตอนการดำเนินการผสานจดหมายในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET กัน
## นำเข้าเนมสเปซ
ประการแรก ให้แน่ใจว่าคุณนำเข้าเนมสเปซที่จำเป็นเพื่อใช้ประโยชน์จากฟังก์ชันการทำงานที่ Aspose.Slides จัดให้:
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
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีเอกสารของคุณ
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// ตรวจสอบว่าเส้นทางผลลัพธ์มีอยู่หรือไม่
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## ขั้นตอนที่ 2: สร้างชุดข้อมูลโดยใช้ข้อมูล XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## ขั้นตอนที่ 3: วนซ้ำผ่านบันทึกและสร้างการนำเสนอส่วนบุคคล
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // สร้างผลงาน (รายบุคคล) ชื่อการนำเสนอ
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // โหลดเทมเพลตการนำเสนอ
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // กรอกกล่องข้อความด้วยข้อมูลจากตารางหลัก
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // รับภาพจากฐานข้อมูล
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // แทรกภาพเข้าในกรอบรูปของงานนำเสนอ
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // รับและเตรียมกรอบข้อความเพื่อกรอกข้อมูล
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // กรอกข้อมูลพนักงาน
        FillStaffList(textFrame, userRow, staffListTable);
        // กรอกข้อมูลข้อเท็จจริงของแผน
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## ขั้นตอนที่ 4: เติมกรอบข้อความด้วยข้อมูลเป็นรายการ
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
## ขั้นตอนที่ 5: กรอกแผนภูมิข้อมูลจากตาราง Secondary PlanFact
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
    // เพิ่มจุดข้อมูลสำหรับชุดเส้น
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
ขั้นตอนเหล่านี้จะแสดงคำแนะนำที่ครอบคลุมเกี่ยวกับการดำเนินการผสานจดหมายในงานนำเสนอโดยใช้ Aspose.Slides สำหรับ .NET ตอนนี้เรามาตอบคำถามที่พบบ่อยกัน
## คำถามที่พบบ่อย
### 1. Aspose.Slides สำหรับ .NET เข้ากันได้กับแหล่งข้อมูลอื่นหรือไม่
ใช่ Aspose.Slides สำหรับ .NET รองรับแหล่งข้อมูลต่างๆ รวมถึง XML, RDBMS และอื่นๆ อีกมากมาย
### 2. ฉันสามารถปรับแต่งลักษณะที่ปรากฏของจุดหัวข้อในงานนำเสนอที่สร้างขึ้นได้หรือไม่
แน่นอน! คุณสามารถควบคุมการปรากฏของจุดหัวข้อได้เต็มที่ ดังที่แสดงใน `FillStaffList` วิธี.
### 3. ฉันสามารถสร้างแผนภูมิประเภทใดได้บ้างโดยใช้ Aspose.Slides สำหรับ .NET
Aspose.Slides สำหรับ .NET รองรับแผนภูมิต่างๆ มากมาย รวมถึงแผนภูมิเส้นดังที่แสดงในตัวอย่างของเรา แผนภูมิแท่ง แผนภูมิวงกลม และอื่นๆ อีกมากมาย
### 4. ฉันจะได้รับการสนับสนุนหรือขอความช่วยเหลือเกี่ยวกับ Aspose.Slides สำหรับ .NET ได้อย่างไร
หากต้องการการสนับสนุนและความช่วยเหลือ คุณสามารถไปที่ [ฟอรั่ม Aspose.Slides](https://forum-aspose.com/c/slides/11).
### 5. ฉันสามารถทดลองใช้ Aspose.Slides สำหรับ .NET ก่อนซื้อได้หรือไม่
แน่นอน! คุณสามารถใช้ประโยชน์จากการทดลองใช้ Aspose.Slides สำหรับ .NET ฟรีได้จาก [ที่นี่](https://releases-aspose.com/).
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจความสามารถที่น่าสนใจของ Aspose.Slides สำหรับ .NET ในการทำจดหมายเวียนในงานนำเสนอ โดยปฏิบัติตามคำแนะนำทีละขั้นตอน คุณสามารถสร้างงานนำเสนอแบบไดนามิกและปรับแต่งได้เองอย่างง่ายดาย ยกระดับประสบการณ์การพัฒนา .NET ของคุณด้วย Aspose.Slides เพื่อการสร้างงานนำเสนอที่ราบรื่น

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: تنفيذ دمج البريد في العروض التقديمية
linktitle: تنفيذ دمج البريد في العروض التقديمية
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET في هذا الدليل التفصيلي خطوة بخطوة. قم بإنشاء عروض تقديمية ديناميكية وشخصية دون عناء.
type: docs
weight: 21
url: /ar/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## مقدمة
في عالم تطوير .NET، يعد إنشاء عروض تقديمية ديناميكية وشخصية مطلبًا شائعًا. إحدى الأدوات القوية التي تعمل على تبسيط هذه العملية هي Aspose.Slides for .NET. في هذا البرنامج التعليمي، سنتعمق في المجال الرائع لإجراء دمج البريد في العروض التقديمية باستخدام Aspose.Slides for .NET.
## المتطلبات الأساسية
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Slides لمكتبة .NET: تأكد من تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).
- قالب المستند: قم بإعداد قالب العرض التقديمي (على سبيل المثال، PresentationTemplate.pptx) الذي سيكون بمثابة الأساس لدمج البريد.
- مصدر البيانات: أنت بحاجة إلى مصدر بيانات لدمج البريد. في مثالنا، سنستخدم بيانات XML (TestData.xml)، لكن Aspose.Slides يدعم مصادر بيانات متنوعة مثل RDBMS.
الآن، دعنا نتعمق في خطوات تنفيذ دمج البريد في العروض التقديمية باستخدام Aspose.Slides for .NET.
## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء اللازمة للاستفادة من الوظائف التي يوفرها Aspose.Slides:
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
## الخطوة 1: قم بإعداد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// تحقق من وجود مسار النتيجة
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## الخطوة 2: إنشاء مجموعة بيانات باستخدام بيانات XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## الخطوة 3: قم بالتمرير عبر السجلات وإنشاء عروض تقديمية فردية
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // إنشاء اسم العرض التقديمي الناتج (فردي).
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // تحميل قالب العرض التقديمي
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // املأ مربعات النص بالبيانات من الجدول الرئيسي
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // الحصول على الصورة من قاعدة البيانات
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //أدخل الصورة في إطار الصورة للعرض التقديمي
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // احصل على إطار النص وقم بإعداده لملئه بالبيانات
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // تعبئة بيانات الموظفين
        FillStaffList(textFrame, userRow, staffListTable);
        // ملء بيانات حقيقة الخطة
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## الخطوة 4: املأ إطار النص بالبيانات كقائمة
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
## الخطوة 5: املأ مخطط البيانات من جدول PlanFact الثانوي
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
    // إضافة نقاط البيانات لسلسلة الخطوط
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
توضح هذه الخطوات دليلاً شاملاً حول إجراء دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET. الآن، دعونا نتناول بعض الأسئلة المتداولة.
## أسئلة مكررة
### 1. هل يتوافق Aspose.Slides for .NET مع مصادر البيانات المختلفة؟
نعم، يدعم Aspose.Slides for .NET مصادر البيانات المتنوعة، بما في ذلك XML وRDBMS والمزيد.
### 2. هل يمكنني تخصيص مظهر النقاط في العرض التقديمي الذي تم إنشاؤه؟
 بالتأكيد! لديك السيطرة الكاملة على مظهر النقاط، كما هو موضح في`FillStaffList` طريقة.
### 3. ما أنواع المخططات التي يمكنني إنشاؤها باستخدام Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET نطاقًا واسعًا من المخططات، بما في ذلك المخططات الخطية كما هو موضح في مثالنا، والمخططات الشريطية، والمخططات الدائرية، والمزيد.
### 4. كيف يمكنني الحصول على الدعم أو طلب المساعدة فيما يتعلق بـ Aspose.Slides لـ .NET؟
 للحصول على الدعم والمساعدة، يمكنك زيارة[منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. هل يمكنني تجربة Aspose.Slides لـ .NET قبل الشراء؟
 بالتأكيد! يمكنك الاستفادة من النسخة التجريبية المجانية من Aspose.Slides لـ .NET من[هنا](https://releases.aspose.com/).
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا الإمكانات المثيرة لـ Aspose.Slides لـ .NET في إجراء دمج البريد في العروض التقديمية. باتباع الدليل الموضح خطوة بخطوة، يمكنك إنشاء عروض تقديمية ديناميكية وشخصية دون عناء. ارفع مستوى تجربة تطوير .NET الخاصة بك باستخدام Aspose.Slides لإنشاء عروض تقديمية سلسة.
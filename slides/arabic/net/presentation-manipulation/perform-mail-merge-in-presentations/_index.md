---
"description": "تعلّم دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET في هذا الدليل المفصل. أنشئ عروضًا تقديمية ديناميكية ومخصصة بكل سهولة."
"linktitle": "تنفيذ دمج البريد في العروض التقديمية"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تنفيذ دمج البريد في العروض التقديمية"
"url": "/ar/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تنفيذ دمج البريد في العروض التقديمية

## مقدمة
في عالم تطوير .NET، يُعد إنشاء عروض تقديمية ديناميكية ومخصصة مطلبًا شائعًا. ومن الأدوات الفعّالة التي تُبسّط هذه العملية أداة Aspose.Slides لـ .NET. في هذا البرنامج التعليمي، سنتعمق في مجال دمج المراسلات في العروض التقديمية باستخدام Aspose.Slides لـ .NET.
## المتطلبات الأساسية
قبل أن نبدأ هذه الرحلة، تأكد من توفر المتطلبات الأساسية التالية:
- مكتبة Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).
- قالب المستند: قم بإعداد قالب عرض تقديمي (على سبيل المثال، PresentationTemplate.pptx) والذي سيكون بمثابة الأساس لدمج البريد.
- مصدر البيانات: ستحتاج إلى مصدر بيانات لدمج البريد. في مثالنا، سنستخدم بيانات XML (TestData.xml)، لكن Aspose.Slides يدعم مصادر بيانات متنوعة مثل أنظمة إدارة قواعد البيانات العلائقية (RDBMS).
الآن، دعنا نتعمق في خطوات تنفيذ دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET.
## استيراد مساحات الأسماء
أولاً، تأكد من استيراد مساحات الأسماء الضرورية للاستفادة من الوظائف التي يوفرها Aspose.Slides:
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
## الخطوة 1: إعداد دليل المستندات الخاص بك
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// التحقق من وجود مسار النتيجة
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
## الخطوة 3: تكرار السجلات وإنشاء عروض تقديمية فردية
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // إنشاء اسم العرض التقديمي للنتيجة (الفردية)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // تحميل قالب العرض التقديمي
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // املأ مربعات النص بالبيانات من الجدول الرئيسي
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // الحصول على الصورة من قاعدة البيانات
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // إدراج الصورة في إطار الصورة للعرض التقديمي
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
        // إملأ بيانات الموظفين
        FillStaffList(textFrame, userRow, staffListTable);
        // بيانات خطة التعبئة
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## الخطوة 4: ملء إطار النص بالبيانات كقائمة
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
توضّح هذه الخطوات دليلاً شاملاً حول دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET. والآن، لنتناول بعض الأسئلة الشائعة.
## الأسئلة الشائعة
### 1. هل Aspose.Slides for .NET متوافق مع مصادر البيانات المختلفة؟
نعم، يدعم Aspose.Slides for .NET مصادر بيانات مختلفة، بما في ذلك XML، وRDBMS، والمزيد.
### 2. هل يمكنني تخصيص مظهر النقاط في العرض التقديمي الذي تم إنشاؤه؟
بالتأكيد! لديك تحكم كامل في مظهر النقاط، كما هو موضح في `FillStaffList` طريقة.
### 3. ما أنواع المخططات البيانية التي يمكنني إنشاؤها باستخدام Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET مجموعة واسعة من المخططات، بما في ذلك المخططات الخطية كما هو موضح في مثالنا، والمخططات الشريطية، والمخططات الدائرية، والمزيد.
### 4. كيف يمكنني الحصول على الدعم أو طلب المساعدة مع Aspose.Slides لـ .NET؟
للحصول على الدعم والمساعدة يمكنك زيارة [منتدى Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. هل يمكنني تجربة Aspose.Slides لـ .NET قبل الشراء؟
بالتأكيد! يمكنك الاستفادة من تجربة مجانية لبرنامج Aspose.Slides لـ .NET من [هنا](https://releases.aspose.com/).
## خاتمة
في هذا البرنامج التعليمي، استكشفنا الإمكانات الرائعة لأداة Aspose.Slides لـ .NET في دمج البريد في العروض التقديمية. باتباع هذا الدليل المفصل، يمكنك إنشاء عروض تقديمية ديناميكية ومخصصة بسهولة. ارتقِ بتجربة تطوير .NET لديك مع Aspose.Slides لإنشاء عروض تقديمية سلسة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
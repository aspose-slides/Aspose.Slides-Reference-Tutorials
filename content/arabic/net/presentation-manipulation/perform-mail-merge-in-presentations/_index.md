---
title: تنفيذ دمج البريد في العروض التقديمية
linktitle: تنفيذ دمج البريد في العروض التقديمية
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إجراء دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET في هذا الدليل الشامل خطوة بخطوة. قم بإنشاء عروض تقديمية مخصصة وديناميكية بسهولة.
type: docs
weight: 21
url: /ar/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

في مجال تطوير البرمجيات، يعد إنشاء عروض تقديمية ديناميكية وشخصية مطلبًا شائعًا. غالبًا ما تحتاج الشركات إلى إنشاء عروض تقديمية مخصصة لبيانات محددة، وهنا يأتي دور وظيفة دمج البريد. في هذا البرنامج التعليمي، سنرشدك خلال عملية تنفيذ دمج البريد في العروض التقديمية باستخدام Aspose.Slides for .NET.

## مقدمة

يعد دمج البريد تقنية فعالة تسمح لك بملء قوالب العرض التقديمي ببيانات من مصادر مختلفة، مثل قواعد البيانات أو ملفات XML. في هذا البرنامج التعليمي، سنركز على استخدام Aspose.Slides for .NET لإجراء دمج البريد في العروض التقديمية خطوة بخطوة.

## إعداد بيئتك

قبل أن نتعمق في عملية دمج البريد، تحتاج إلى إعداد بيئة التطوير الخاصة بك. تأكد من توفر المتطلبات الأساسية التالية:

- Visual Studio أو أي بيئة تطوير أخرى لـ C#.
-  تم تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله[هنا](https://releases.aspose.com/slides/net/).

## فهم مصدر البيانات

لدمج البريد، ستحتاج إلى مصدر بيانات. في هذا البرنامج التعليمي، سنستخدم ملف XML كمصدر بياناتنا. فيما يلي مثال لكيفية ظهور مصدر بياناتك:

```xml
<!-- TestData.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<MailMerge>
    <TestTable>
        <Id>1</Id>
        <Code>105</Code>
        <Name>Samuel Ellington</Name>
        <Department>Legal Department</Department> <Img></Img>
    </TestTable>
    <StaffList>
        <Id>18</Id>
        <UserId>1</UserId>
        <Name>Amelia Walker</Name>
    </StaffList>
    <Plan_Fact>
        <Id>1</Id>
        <UserId>1</UserId>
        <OnDate>2020/01</OnDate>
        <PlanData>2,0</PlanData>
        <FactData>2,8</FactData>
    </Plan_Fact>
</MailMerge>
```

## إنشاء قالب العرض التقديمي

لإجراء دمج البريد، ستحتاج إلى قالب العرض التقديمي (ملف PPTX) الذي يحدد تخطيط العروض التقديمية النهائية. يمكنك إنشاء هذا القالب باستخدام Microsoft PowerPoint أو أي أداة أخرى من اختيارك.

## عملية دمج البريد

الآن، دعنا نتعمق في عملية دمج البريد الفعلية باستخدام Aspose.Slides لـ .NET. سنقوم بتقسيمها إلى خطوات:

1. قم بتحميل قالب العرض التقديمي.
2. تعبئة مربعات النص بالبيانات من مصدر البيانات.
3. إدراج الصور في العرض التقديمي.
4. إعداد وملء إطارات النص.
5. حفظ العروض التقديمية الفردية.

فيما يلي مقتطف من كود C# الذي ينجز هذه الخطوات:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // المسار إلى البيانات.
    // تعد بيانات XML أحد الأمثلة على مصادر بيانات MailMerge المحتملة (بين RDBMS والأنواع الأخرى من مصادر البيانات).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // تحقق من وجود مسار النتيجة
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // إنشاء DataSet باستخدام بيانات XML
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // لجميع السجلات في الجدول الرئيسي سنقوم بإنشاء عرض تقديمي منفصل
        foreach (DataRow userRow in usersTable.Rows)
        {
            // إنشاء اسم العرض التقديمي الناتج (فردي).
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //تحميل قالب العرض التقديمي
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // املأ مربعات النص بالبيانات من الجدول الرئيسي لقاعدة البيانات
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // الحصول على الصورة من قاعدة البيانات
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // إدراج الصورة في إطار الصورة للعرض التقديمي
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // احصل على إطار نص abd لملئه بالبيانات
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // ملء بيانات الموظفين
                FillStaffList(textFrame, userRow, staffListTable);

                // ملء بيانات حقيقة الخطة
                FillPlanFact(pres, userRow, planFactTable);

                pres.Save(presPath, SaveFormat.Pptx);
            }
        }
    }

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

// يملأ مخطط البيانات من جدول PlanFact الثانوي
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";

    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();

    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 1,
            double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2,
            double.Parse(selRows[0]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1,
            double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2,
            double.Parse(selRows[1]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[2]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[3]["FactData"].ToString())));

    chart.ChartData.SetRange(range);
}		
```

## حفظ النتيجة

بمجرد الانتهاء من عملية دمج البريد لكافة السجلات في مصدر البيانات، سيكون لديك عروض تقديمية فردية جاهزة. يمكنك حفظها في الموقع الذي تريده.

## خاتمة

يؤدي إجراء دمج البريد في العروض التقديمية باستخدام Aspose.Slides for .NET إلى فتح عالم من الإمكانيات لإنشاء عروض تقديمية مخصصة ومعتمدة على البيانات. لقد أرشدك هذا البرنامج التعليمي خلال الخطوات الأساسية لتحقيق ذلك بسلاسة.

## الأسئلة الشائعة

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
ج1: على الرغم من أن Aspose.Slides for .NET يعد خيارًا قويًا، إلا أن المكتبات والأدوات الأخرى توفر أيضًا وظائف مماثلة. يعتمد الأمر في النهاية على متطلباتك وتفضيلاتك المحددة.

**Q2: Can I use different data sources apart from XML files?**
ج2: نعم، يدعم Aspose.Slides for .NET مصادر البيانات المتنوعة، بما في ذلك قواعد البيانات وهياكل البيانات المخصصة.

**Q3: How can I format the merged presentations further?**
ج3: يمكنك تطبيق تنسيقات وأنماط ورسوم متحركة إضافية على العروض التقديمية المدمجة باستخدام مجموعة الميزات الغنية لـ Aspose.Slides.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 ج4: نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET[هنا](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 ج5: للحصول على الدعم الفني والمناقشات، يمكنك زيارة[منتدى Aspose.Slides](https://forum.aspose.com/).

الآن بعد أن تعلمت كيفية إجراء دمج البريد في العروض التقديمية باستخدام Aspose.Slides لـ .NET، يمكنك البدء في إنشاء عروض تقديمية ديناميكية وغنية بالبيانات لمشروعاتك. ترميز سعيد!

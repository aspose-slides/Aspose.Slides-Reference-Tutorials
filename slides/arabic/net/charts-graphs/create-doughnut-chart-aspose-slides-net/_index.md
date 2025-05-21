---
"date": "2025-04-15"
"description": "تعرّف على كيفية إنشاء مخططات دائرية ديناميكية باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل للحصول على تعليمات خطوة بخطوة، بما في ذلك الإعداد والميزات المتقدمة."
"title": "دليل خطوة بخطوة لإنشاء مخطط دائري باستخدام Aspose.Slides .NET | المخططات والرسوم البيانية"
"url": "/ar/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# دليل خطوة بخطوة: إنشاء مخطط دائري باستخدام Aspose.Slides .NET

## مقدمة

تخيل أنك مُكلف بعرض نتائج تحليل البيانات على فريقك أو عملائك، وتحتاج إلى طريقة جذابة لعرض المعلومات. إليك أداة الرسم البياني الدائري، وهي أداة متعددة الاستخدامات تُحوّل الأرقام الخام إلى رؤى واضحة وسهلة الفهم. مع Aspose.Slides لـ .NET، أصبح إنشاء رسم بياني دائري مُخصص في شرائح العرض التقديمي أمرًا سهلًا وفعالًا. سيُرشدك هذا الدليل إلى كيفية استخدام Aspose.Slides لإنشاء رسم بياني دائري جذاب بصريًا، مع تكوينات سلسلة مُخصصة.

**ما سوف تتعلمه:**
- إعداد بيئة التطوير الخاصة بك باستخدام Aspose.Slides لـ .NET
- إنشاء مخططات دائرية وتخصيصها في العروض التقديمية
- تنفيذ ميزات متقدمة مثل أسماء الفئات وخطوط القادة
- تحسين الأداء لمجموعات البيانات الكبيرة

دعونا نلقي نظرة على المتطلبات الأساسية التي تحتاجها للبدء.

## المتطلبات الأساسية

قبل تطبيق هذه الميزة، تأكد من إعداد بيئة التطوير لديك بشكل صحيح. يتطلب هذا البرنامج التعليمي معرفة أساسية ببرمجة .NET وخبرة في استخدام Visual Studio أو بيئة تطوير متكاملة مشابهة.

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides لـ .NET**:تأكد من التوافق مع الإصدار الأحدث من خلال التحقق منه [الوثائق الرسمية](https://reference.aspose.com/slides/net/).

### متطلبات إعداد البيئة
- بيئة عمل .NET.
- الوصول إلى محرر الكود، مثل Visual Studio.

### متطلبات المعرفة
- فهم أساسي لـ C# وإطار عمل .NET.
- المعرفة بمفاهيم برامج العرض التقديمي (اختياري ولكن مفيد).

## إعداد Aspose.Slides لـ .NET

لبدء استخدام Aspose.Slides في مشروعك، عليك تثبيته عبر NuGet. إليك الطرق المتاحة:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**استخدام مدير الحزم:**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:**
ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص

1. **نسخة تجريبية مجانية**:ابدأ بـ [نسخة تجريبية مجانية](https://releases.aspose.com/slides/net/) لاستكشاف الوظائف الأساسية.
2. **رخصة مؤقتة**:احصل على ترخيص مؤقت إذا كنت بحاجة إلى الوصول إلى الميزات الكاملة لأغراض التقييم من خلال زيارة [هنا](https://purchase.aspose.com/temporary-license/).
3. **شراء**:للاستخدام التجاري، قم بشراء ترخيص من [موقع Aspose](https://purchase.aspose.com/buy).

بمجرد التثبيت والترخيص، قم بتشغيل Aspose.Slides في مشروعك:
```csharp
using Aspose.Slides;

// تهيئة Aspose.Slides لـ .NET
var presentation = new Presentation();
```

## دليل التنفيذ

### إنشاء عرض تقديمي جديد وإضافة مخطط دائري

#### ملخص
سنبدأ بإنشاء عرض تقديمي جديد وإضافة مخطط دائري إلى الشريحة الأولى. يتناول هذا القسم تحميل عرض تقديمي موجود، والوصول إلى الشرائح، وإدراج المخططات.

**الخطوة 1: تحميل أو إنشاء عرض تقديمي**
أولاً، حدد دليل المستند الخاص بك وقم بتحميل عرض تقديمي موجود:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
إذا لم يكن لديك ملف موجود، قم بإنشاء ملف جديد باستخدام `new Presentation()`.

**الخطوة 2: الوصول إلى الشريحة الأولى**
احصل على إمكانية الوصول إلى الشريحة الأولى حيث سنضيف مخططنا:
```csharp
ISlide slide = pres.Slides[0];
```

**الخطوة 3: إضافة مخطط دائري**
أضف مخططًا دائريًا عند الإحداثيات والأبعاد المحددة:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### تكوين مصنف البيانات

#### ملخص
يوضح هذا القسم كيفية تكوين مصنف البيانات المرتبط بمخطط الدونات الخاص بك.

**الخطوة 4: الوصول إلى البيانات الموجودة ومسحها**
ادخل إلى مصنف بيانات الرسم البياني. ثم امسح أي سلاسل أو فئات موجودة:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**الخطوة 5: تعطيل الأسطورة وإضافة السلسلة**
قم بتعطيل الأسطورة للحفاظ على نظافة الرسم البياني، ثم أضف ما يصل إلى 15 سلسلة باستخدام تكوينات مخصصة:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### إضافة الفئات ونقاط البيانات

#### ملخص
الآن، دعنا نملأ الرسم البياني بالفئات ونقاط البيانات لكل سلسلة.

**الخطوة 6: إضافة الفئات**
قم بالتكرار لإضافة 15 فئة:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**الخطوة 7: ملء نقاط البيانات**
أضف نقاط البيانات لكل سلسلة ضمن الفئة الحالية:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // تخصيص المظهر
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // تكوين تنسيق الملصق للسلسلة الأخيرة
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // تكوين عرض الملصق
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### حفظ العرض التقديمي

**الخطوة 8: حفظ الملف**
وأخيرًا، احفظ العرض التقديمي الخاص بك في الدليل المحدد:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
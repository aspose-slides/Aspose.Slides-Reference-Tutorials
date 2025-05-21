---
"description": "تعلّم كيفية إنشاء مخططات بيانية مذهلة باستخدام Aspose.Slides لـ .NET. ارتقِ بمهاراتك في عرض البيانات مع دليلنا المفصل."
"linktitle": "كيانات الرسم البياني والتنسيق"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "إنشاء مخططات بيانية جميلة باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# إنشاء مخططات بيانية جميلة باستخدام Aspose.Slides لـ .NET


في عالمنا اليوم الذي يعتمد على البيانات، يُعدّ التصور الفعّال للبيانات أمرًا أساسيًا لإيصال المعلومات إلى جمهورك. تُعدّ Aspose.Slides for .NET مكتبة فعّالة تُمكّنك من إنشاء عروض تقديمية وشرائح رائعة، بما في ذلك مخططات بيانية جذابة. في هذا البرنامج التعليمي، سنشرح لك عملية إنشاء مخططات بيانية رائعة باستخدام Aspose.Slides for .NET. سنُقسّم كل مثال إلى عدة خطوات لمساعدتك على فهم كيانات المخططات وتنسيقها وتطبيقها. هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء مخططات بيانية جميلة باستخدام Aspose.Slides لـ .NET، ستحتاج إلى التأكد من توفر المتطلبات الأساسية التالية لديك:

1. Aspose.Slides لـ .NET: تأكد من تثبيت مكتبة Aspose.Slides لـ .NET. يمكنك تنزيلها من [موقع إلكتروني](https://releases.aspose.com/slides/net/).

2. بيئة التطوير: يجب أن يكون لديك بيئة تطوير عمل مع Visual Studio أو أي IDE آخر يدعم تطوير .NET.

3. المعرفة الأساسية بلغة C#: المعرفة ببرمجة C# ضرورية لهذا البرنامج التعليمي.

الآن بعد أن قمنا بترتيب المتطلبات الأساسية لدينا، فلننتقل إلى إنشاء مخططات بيانية جميلة باستخدام Aspose.Slides لـ .NET.

## استيراد مساحات الأسماء

أولاً، يتعين عليك استيراد المساحات الأساسية اللازمة للعمل مع Aspose.Slides لـ .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## الخطوة 1: إنشاء عرض تقديمي

نبدأ بإنشاء عرض تقديمي جديد للعمل عليه. سيكون هذا العرض بمثابة لوحة رسم بياني.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";

// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// إنشاء عرض تقديمي
Presentation pres = new Presentation();
```

## الخطوة 2: الوصول إلى الشريحة الأولى

لننتقل إلى الشريحة الأولى في العرض التقديمي حيث سنضع مخططنا.

```csharp
// الوصول إلى الشريحة الأولى
ISlide slide = pres.Slides[0];
```

## الخطوة 3: إضافة مخطط عينة

الآن، سنضيف مخططًا نموذجيًا إلى شريحتنا. في هذا المثال، سننشئ مخططًا خطيًا بعلامات.

```csharp
// إضافة مخطط العينة
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## الخطوة 4: تعيين عنوان الرسم البياني

سنعطي لمخططنا عنوانًا، مما يجعله أكثر إفادة وجاذبية بصريًا.

```csharp
// إعداد عنوان الرسم البياني
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## الخطوة 5: تخصيص خطوط شبكة المحور الرأسي

في هذه الخطوة، سنقوم بتخصيص خطوط شبكة المحور الرأسي لجعل الرسم البياني الخاص بنا أكثر جاذبية من الناحية البصرية.

```csharp
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور القيمة
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// ضبط تنسيق خطوط الشبكة الثانوية لمحور القيمة
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// ضبط تنسيق رقم محور القيمة
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## الخطوة 6: تحديد نطاق المحور الرأسي

في هذه الخطوة، سنقوم بتعيين القيم القصوى والدنيا والوحدة للمحور الرأسي.

```csharp
// تعيين الحد الأقصى والحد الأدنى للقيم في المخطط
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## الخطوة 7: تخصيص نص المحور الرأسي

سنقوم الآن بتخصيص مظهر النص على المحور الرأسي.

```csharp
// تعيين خصائص نص محور القيمة
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// تعيين عنوان محور القيمة
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## الخطوة 8: تخصيص خطوط شبكة المحور الأفقي

الآن، دعونا نقوم بتخصيص خطوط الشبكة للمحور الأفقي.

```csharp
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور الفئة
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// تعيين خصائص نص محور الفئة
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## الخطوة 9: تخصيص تسميات المحور الأفقي

في هذه الخطوة، سنقوم بتعديل موضع ودوران تسميات المحور الأفقي.

```csharp
// تعيين موضع تسمية محور الفئة
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// ضبط زاوية دوران تسمية محور الفئة
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## الخطوة 10: تخصيص الأساطير

دعونا نعمل على تعزيز الأساطير في مخططنا لتحسين قابلية القراءة.

```csharp
// ضبط خصائص نص الأساطير
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// تعيين أساطير عرض الرسم البياني دون تداخل الرسم البياني
chart.Legend.Overlay = true;
```

## الخطوة 11: تخصيص خلفية الرسم البياني

سنقوم بتخصيص ألوان الخلفية للرسم البياني والجدار الخلفي والأرضية.

```csharp
// مخطط ضبط لون الجدار الخلفي
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// ضبط لون منطقة الرسم البياني
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## الخطوة 12: حفظ العرض التقديمي

وأخيرًا، دعنا نحفظ عرضنا التقديمي بالمخطط المنسق.

```csharp
// حفظ العرض التقديمي
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## خاتمة

أصبح إنشاء مخططات بيانية جميلة وغنية بالمعلومات في عروضك التقديمية أسهل من أي وقت مضى مع Aspose.Slides لـ .NET. في هذا البرنامج التعليمي، تناولنا الخطوات الأساسية لتخصيص جوانب مختلفة من المخطط، لجعله جذابًا بصريًا وغنيًا بالمعلومات. باستخدام هذه التقنيات، يمكنك إنشاء مخططات بيانية رائعة تعرض بياناتك بفعالية لجمهورك.

ابدأ بالتجربة مع Aspose.Slides لـ .NET وخذ تصور البيانات الخاص بك إلى المستوى التالي!

## الأسئلة الشائعة

### 1. ما هو Aspose.Slides لـ .NET؟

Aspose.Slides for .NET هي مكتبة فعّالة تُمكّن مطوري .NET من إنشاء عروض Microsoft PowerPoint التقديمية وتعديلها وتحويلها. تُوفّر مجموعة واسعة من الميزات للعمل مع الشرائح والأشكال والمخططات وغيرها.

### 2. أين يمكنني تنزيل Aspose.Slides لـ .NET؟

يمكنك تنزيل Aspose.Slides لـ .NET من موقع الويب [هنا](https://releases.aspose.com/slides/net/).

### 3. هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟

نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET من [هنا](https://releases.aspose.com/).

### 4. كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟

إذا كنت بحاجة إلى ترخيص مؤقت، يمكنك الحصول عليه من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

### 5. هل يوجد مجتمع أو منتدى دعم لـ Aspose.Slides لـ .NET؟

نعم، يمكنك العثور على مجتمع Aspose.Slides ومنتدى الدعم [هنا](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
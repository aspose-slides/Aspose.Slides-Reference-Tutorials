---
title: إنشاء مخططات جميلة باستخدام Aspose.Slides لـ .NET
linktitle: كيانات المخطط وتنسيقه
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء مخططات مذهلة باستخدام Aspose.Slides لـ .NET. ارفع مستوى لعبة تصور البيانات الخاصة بك من خلال دليلنا خطوة بخطوة.
type: docs
weight: 13
url: /ar/net/advanced-chart-customization/chart-entities/
---

في عالم اليوم القائم على البيانات، يعد التصور الفعال للبيانات أمرًا أساسيًا لنقل المعلومات إلى جمهورك. Aspose.Slides for .NET هي مكتبة قوية تمكنك من إنشاء عروض تقديمية وشرائح مذهلة، بما في ذلك المخططات الجذابة. في هذا البرنامج التعليمي، سنرشدك خلال عملية إنشاء مخططات جميلة باستخدام Aspose.Slides for .NET. سنقوم بتقسيم كل مثال إلى خطوات متعددة لمساعدتك على فهم وتنفيذ كيانات المخطط وتنسيقه. اذا هيا بنا نبدأ!

## المتطلبات الأساسية

قبل أن نتعمق في إنشاء مخططات جميلة باستخدام Aspose.Slides لـ .NET، ستحتاج إلى التأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Slides for .NET: تأكد من تثبيت مكتبة Aspose.Slides for .NET. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/net/).

2. بيئة التطوير: يجب أن يكون لديك بيئة تطوير عمل مع Visual Studio أو أي بيئة تطوير متكاملة أخرى تدعم تطوير .NET.

3. المعرفة الأساسية بـ C#: الإلمام ببرمجة C# ضروري لهذا البرنامج التعليمي.

الآن بعد أن قمنا بفرز متطلباتنا الأساسية، فلنتابع إنشاء مخططات جميلة باستخدام Aspose.Slides for .NET.

## استيراد مساحات الأسماء

أولاً، تحتاج إلى استيراد مساحات الأسماء الضرورية للعمل مع Aspose.Slides لـ .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## الخطوة 1: إنشاء عرض تقديمي

نبدأ بإنشاء عرض تقديمي جديد للعمل معه. سيكون هذا العرض التقديمي بمثابة لوحة الرسم البياني لدينا.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";

// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// تجسيد العرض التقديمي
Presentation pres = new Presentation();
```

## الخطوة 2: الوصول إلى الشريحة الأولى

دعنا نصل إلى الشريحة الأولى في العرض التقديمي حيث سنضع مخططنا.

```csharp
// الوصول إلى الشريحة الأولى
ISlide slide = pres.Slides[0];
```

## الخطوة 3: إضافة نموذج للمخطط

الآن، سوف نقوم بإضافة نموذج للمخطط إلى الشريحة الخاصة بنا. في هذا المثال، سنقوم بإنشاء مخطط خطي باستخدام العلامات.

```csharp
// إضافة نموذج الرسم البياني
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## الخطوة 4: تعيين عنوان المخطط

سنعطي مخططنا عنوانًا، مما يجعله أكثر إفادة وجاذبية من الناحية المرئية.

```csharp
// تحديد عنوان الرسم البياني
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

في هذه الخطوة، سنقوم بتخصيص خطوط شبكة المحور الرأسي لجعل مخططنا أكثر جاذبية من الناحية المرئية.

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

// تحديد تنسيق رقم محور القيمة
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## الخطوة 6: تحديد نطاق المحور الرأسي

في هذه الخطوة، سنقوم بتعيين الحد الأقصى والحد الأدنى وقيم الوحدة للمحور الرأسي.

```csharp
// تحديد الحد الأقصى للرسم البياني والحد الأدنى للقيم
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## الخطوة 7: تخصيص نص المحور العمودي

سنقوم الآن بتخصيص مظهر النص على المحور الرأسي.

```csharp
// ضبط خصائص نص محور القيمة
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// تحديد عنوان محور القيمة
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

الآن، دعونا نخصص خطوط الشبكة للمحور الأفقي.

```csharp
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور الفئة
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

//ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// ضبط خصائص نص محور الفئة
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

في هذه الخطوة، سنقوم بضبط موضع وتدوير تسميات المحاور الأفقية.

```csharp
// تحديد موضع تسمية محور الفئة
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// تحديد زاوية دوران تسمية محور الفئة
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## الخطوة 10: تخصيص الأساطير

دعونا نعزز وسائل الإيضاح في مخططنا لتحسين إمكانية القراءة.

```csharp
// ضبط خصائص نص وسائل الإيضاح
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// قم بتعيين إظهار وسائل إيضاح المخطط دون تداخل المخطط
chart.Legend.Overlay = true;
```

## الخطوة 11: تخصيص خلفية الرسم البياني

سنقوم بتخصيص ألوان خلفية المخطط والجدار الخلفي والأرضية.

```csharp
// تحديد لون الجدار الخلفي للمخطط
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// تحديد لون منطقة الأرض
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## الخطوة 12: احفظ العرض التقديمي

أخيرًا، دعونا نحفظ عرضنا التقديمي بالمخطط المنسق.

```csharp
// حفظ العرض التقديمي
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## خاتمة

أصبح الآن إنشاء مخططات جميلة وغنية بالمعلومات في عروضك التقديمية أسهل من أي وقت مضى باستخدام Aspose.Slides for .NET. في هذا البرنامج التعليمي، قمنا بتغطية الخطوات الأساسية لتخصيص الجوانب المختلفة للمخطط، مما يجعله جذابًا وغنيًا بالمعلومات. باستخدام هذه التقنيات، يمكنك إنشاء مخططات مذهلة تنقل بياناتك إلى جمهورك بشكل فعال.

ابدأ بتجربة Aspose.Slides لـ .NET وانتقل بتصور بياناتك إلى المستوى التالي!

## أسئلة مكررة

### 1. ما هو Aspose.Slides لـ .NET؟

Aspose.Slides for .NET هي مكتبة قوية تسمح لمطوري .NET بإنشاء عروض Microsoft PowerPoint التقديمية ومعالجتها وتحويلها. فهو يوفر مجموعة واسعة من الميزات للعمل مع الشرائح والأشكال والمخططات والمزيد.

### 2. أين يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides for .NET من موقع الويب[هنا](https://releases.aspose.com/slides/net/).

### 3. هل تتوفر نسخة تجريبية مجانية من Aspose.Slides لـ .NET؟

نعم، يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لـ .NET من[هنا](https://releases.aspose.com/).

### 4. كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET؟

 إذا كنت بحاجة إلى ترخيص مؤقت، يمكنك الحصول عليه من[هذا الرابط](https://purchase.aspose.com/temporary-license/).

### 5. هل يوجد مجتمع أو منتدى دعم لـ Aspose.Slides for .NET؟

 نعم، يمكنك العثور على مجتمع Aspose.Slides ومنتدى الدعم[هنا](https://forum.aspose.com/).

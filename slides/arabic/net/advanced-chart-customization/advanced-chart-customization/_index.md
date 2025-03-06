---
title: تخصيص الرسم البياني المتقدم في Aspose.Slides
linktitle: تخصيص الرسم البياني المتقدم في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على التخصيص المتقدم للمخططات في Aspose.Slides لـ .NET. قم بإنشاء مخططات جذابة بصريًا مع إرشادات خطوة بخطوة.
weight: 10
url: /ar/net/advanced-chart-customization/advanced-chart-customization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


يعد إنشاء مخططات جذابة وغنية بالمعلومات جزءًا أساسيًا من عرض البيانات في العديد من التطبيقات. يوفر Aspose.Slides for .NET أدوات قوية لتخصيص المخططات، مما يسمح لك بضبط كل جانب من جوانب المخططات الخاصة بك. في هذا البرنامج التعليمي، سنستكشف تقنيات تخصيص المخططات المتقدمة باستخدام Aspose.Slides لـ .NET.

## المتطلبات الأساسية

قبل الغوص في التخصيص المتقدم للمخططات باستخدام Aspose.Slides for .NET، تأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides لمكتبة .NET: تحتاج إلى تثبيت مكتبة Aspose.Slides وتكوينها بشكل صحيح في مشروع .NET الخاص بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net/).

2. بيئة تطوير .NET: يجب أن يكون لديك بيئة تطوير .NET، بما في ذلك Visual Studio أو أي بيئة تطوير متكاملة (IDE) أخرى من اختيارك.

3. المعرفة الأساسية بـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا، حيث سنقوم بكتابة كود C# للعمل مع Aspose.Slides.

الآن، دعنا نقسم التخصيص المتقدم للمخطط إلى خطوات متعددة لإرشادك خلال العملية.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، قم بإنشاء عرض تقديمي جديد باستخدام Aspose.Slides.

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

في هذه الخطوة، نبدأ عرضًا تقديميًا جديدًا سيحمل مخططنا.

## الخطوة 2: الوصول إلى الشريحة الأولى

بعد ذلك، قم بالوصول إلى الشريحة الأولى في العرض التقديمي حيث تريد إضافة المخطط.

```csharp
// الوصول إلى الشريحة الأولى
ISlide slide = pres.Slides[0];
```

يتيح لك مقتطف الكود هذا العمل مع الشريحة الأولى في العرض التقديمي.

## الخطوة 3: إضافة نموذج للمخطط

الآن، دعونا نضيف نموذجًا للمخطط إلى الشريحة. في هذا المثال، سنقوم بإنشاء مخطط خطي باستخدام العلامات.

```csharp
// إضافة نموذج الرسم البياني
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

هنا نحدد نوع المخطط (LineWithMarkers) وموضعه وأبعاده على الشريحة.

## الخطوة 4: تحديد عنوان المخطط

لنقم بتعيين عنوان للمخطط لتوفير السياق.

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

يقوم هذا الرمز بتعيين عنوان للمخطط، مع تحديد النص والمظهر ونمط الخط.

## الخطوة 5: تخصيص خطوط الشبكة الرئيسية

الآن، دعونا نخصص خطوط الشبكة الرئيسية لمحور القيمة.

```csharp
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور القيمة
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

تقوم هذه الخطوة بتكوين مظهر خطوط الشبكة الرئيسية على محور القيمة.

## الخطوة 6: تخصيص خطوط الشبكة الصغيرة

وبالمثل، يمكننا تخصيص خطوط الشبكة الثانوية لمحور القيمة.

```csharp
// ضبط تنسيق خطوط الشبكة الثانوية لمحور القيمة
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

يضبط هذا الرمز مظهر خطوط الشبكة الثانوية على محور القيمة.

## الخطوة 7: تحديد تنسيق رقم محور القيمة

تخصيص تنسيق الأرقام لمحور القيمة.

```csharp
// تحديد تنسيق رقم محور القيمة
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

تتيح لك هذه الخطوة تنسيق الأرقام المعروضة على محور القيمة.

## الخطوة 8: تعيين القيم القصوى والدنيا للمخطط

تحديد الحد الأقصى والحد الأدنى للقيم للمخطط.

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

هنا، يمكنك تحديد نطاق القيم التي يجب أن يعرضها محور المخطط.

## الخطوة 9: تخصيص خصائص نص محور القيمة

يمكنك أيضًا تخصيص خصائص النص لمحور القيمة.

```csharp
// ضبط خصائص نص محور القيمة
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

يسمح لك هذا الرمز بضبط نمط الخط ومظهر تسميات محور القيمة.

## الخطوة 10: إضافة عنوان محور القيمة

إذا كان المخطط الخاص بك يتطلب عنوانًا لمحور القيمة، فيمكنك إضافته بهذه الخطوة.

```csharp
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

في هذه الخطوة، يمكنك تعيين عنوان لمحور القيمة.

## الخطوة 11: تخصيص خطوط الشبكة الرئيسية لمحور الفئة

الآن، دعونا نركز على خطوط الشبكة الرئيسية لمحور الفئة.

```csharp
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور الفئة
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

يقوم هذا الرمز بتكوين مظهر خطوط الشبكة الرئيسية على محور الفئة.

## الخطوة 12: تخصيص خطوط الشبكة الصغيرة لمحور الفئة

كما هو الحال مع محور القيمة، يمكنك تخصيص خطوط الشبكة الثانوية لمحور الفئة.

```csharp
// ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

هنا، يمكنك ضبط مظهر خطوط الشبكة الثانوية على محور الفئة.

## الخطوة 13: تخصيص خصائص نص محور الفئة

قم بتخصيص خصائص النص لتسميات محاور الفئة.

```csharp
// ضبط خصائص نص محور الفئة
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

يتيح لك هذا الرمز ضبط نمط الخط ومظهر تسميات محور الفئة.

## الخطوة 14: إضافة عنوان محور الفئة

يمكنك أيضًا إضافة عنوان إلى محور الفئة إذا لزم الأمر.

```csharp
// تحديد عنوان الفئة
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

في هذه الخطوة، يمكنك تعيين عنوان لمحور الفئة.

## الخطوة 15: تخصيصات إضافية

يمكنك استكشاف المزيد من التخصيصات، مثل وسائل الإيضاح وألوان الجدار الخلفي للمخطط والأرضية ومنطقة قطعة الأرض. تسمح لك هذه التخصيصات بتحسين المظهر المرئي للمخطط الخاص بك.

```csharp
// تخصيصات إضافية (اختياري)

// ضبط خصائص نص وسائل الإيضاح
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// قم بتعيين إظهار وسائل إيضاح المخطط دون تداخل المخطط
chart.Legend.Overlay = true;

// رسم السلسلة الأولى على محور القيمة الثانوية (إذا لزم الأمر)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// تحديد لون الجدار الخلفي للمخطط
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// تحديد لون أرضية الرسم البياني
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//تحديد لون منطقة الأرض
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// احفظ العرض التقديمي
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

تعتبر هذه التخصيصات الإضافية اختيارية ويمكن تطبيقها بناءً على متطلبات تصميم المخطط المحددة الخاصة بك.

## خاتمة

في هذا الدليل التفصيلي خطوة بخطوة، اكتشفنا التخصيص المتقدم للمخطط باستخدام Aspose.Slides for .NET. لقد تعلمت كيفية إنشاء عرض تقديمي وإضافة مخطط وضبط مظهره، بما في ذلك خطوط الشبكة وتسميات المحاور والعناصر المرئية الأخرى. باستخدام خيارات التخصيص القوية التي توفرها Aspose.Slides، يمكنك إنشاء مخططات تنقل بياناتك بشكل فعال وتجذب جمهورك.

 إذا كانت لديك أية أسئلة أو واجهت أي تحديات أثناء العمل مع Aspose.Slides for .NET، فلا تتردد في استكشاف الوثائق[هنا](https://reference.aspose.com/slides/net/) أو طلب المساعدة في Aspose.Slides[المنتدى](https://forum.aspose.com/).

## الأسئلة الشائعة

### ما هي إصدارات .NET التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET إصدارات .NET المختلفة، بما في ذلك .NET Framework و.NET Core. يمكنك الرجوع إلى الوثائق للحصول على القائمة الكاملة للإصدارات المدعومة.

### هل يمكنني إنشاء مخططات من مصادر البيانات مثل ملفات Excel باستخدام Aspose.Slides لـ .NET؟
نعم، يسمح لك Aspose.Slides for .NET بإنشاء مخططات من مصادر بيانات خارجية مثل جداول بيانات Excel. يمكنك استكشاف الوثائق للحصول على أمثلة مفصلة.

### كيف يمكنني إضافة تسميات بيانات مخصصة إلى سلسلة المخططات الخاصة بي؟
 لإضافة تسميات بيانات مخصصة إلى سلسلة المخططات الخاصة بك، يمكنك الوصول إلى`DataLabels` ملكية السلسلة وتخصيص التسميات حسب الحاجة. راجع الوثائق للحصول على نماذج التعليمات البرمجية والأمثلة.

### هل من الممكن تصدير المخطط إلى تنسيقات ملفات مختلفة، مثل تنسيقات PDF أو الصور؟
نعم، يوفر Aspose.Slides for .NET خيارات لتصدير العرض التقديمي الخاص بك مع المخططات إلى تنسيقات مختلفة، بما في ذلك تنسيقات PDF والصور. يمكنك استخدام المكتبة لحفظ عملك بتنسيق الإخراج المطلوب.

### أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة حول Aspose.Slides لـ .NET؟
 يمكنك العثور على مجموعة كبيرة من البرامج التعليمية وأمثلة التعليمات البرمجية والوثائق على Aspose.Slides[موقع إلكتروني](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

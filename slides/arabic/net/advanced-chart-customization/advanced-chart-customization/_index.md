---
"description": "تعلّم تخصيص المخططات البيانية بشكل متقدم في Aspose.Slides لـ .NET. أنشئ مخططات بيانية جذابة بصريًا مع إرشادات خطوة بخطوة."
"linktitle": "تخصيص المخططات المتقدمة في Aspose.Slides"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تخصيص المخططات المتقدمة في Aspose.Slides"
"url": "/ar/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تخصيص المخططات المتقدمة في Aspose.Slides


يُعد إنشاء مخططات بيانية جذابة بصريًا وغنية بالمعلومات جزءًا أساسيًا من عرض البيانات في العديد من التطبيقات. يوفر Aspose.Slides for .NET أدوات فعّالة لتخصيص المخططات، مما يتيح لك ضبط جميع جوانبها بدقة. في هذا البرنامج التعليمي، سنستكشف تقنيات متقدمة لتخصيص المخططات باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل الغوص في تخصيص المخططات المتقدمة باستخدام Aspose.Slides لـ .NET، تأكد من توفر المتطلبات الأساسية التالية:

1. مكتبة Aspose.Slides لـ .NET: يجب تثبيت مكتبة Aspose.Slides وتهيئتها بشكل صحيح في مشروع .NET الخاص بك. يمكنك تنزيلها من [هنا](https://releases.aspose.com/slides/net/).

2. بيئة تطوير .NET: يجب أن يكون لديك بيئة تطوير .NET مهيأة، بما في ذلك Visual Studio أو أي بيئة تطوير متكاملة أخرى من اختيارك.

3. المعرفة الأساسية بلغة C#: ستكون المعرفة بلغة البرمجة C# مفيدة، حيث سنقوم بكتابة كود C# للعمل مع Aspose.Slides.

الآن، دعنا نقسم تخصيص الرسم البياني المتقدم إلى خطوات متعددة لإرشادك خلال العملية.

## الخطوة 1: إنشاء عرض تقديمي

أولاً، قم بإنشاء عرض تقديمي جديد باستخدام Aspose.Slides.

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

في هذه الخطوة، نبدأ عرضًا تقديميًا جديدًا يحمل مخططنا.

## الخطوة 2: الوصول إلى الشريحة الأولى

بعد ذلك، قم بالوصول إلى الشريحة الأولى في العرض التقديمي حيث تريد إضافة الرسم البياني.

```csharp
// الوصول إلى الشريحة الأولى
ISlide slide = pres.Slides[0];
```

يتيح لك مقتطف التعليمات البرمجية هذا العمل مع الشريحة الأولى في العرض التقديمي.

## الخطوة 3: إضافة مخطط عينة

الآن، لنُضِف مخططًا نموذجيًا إلى الشريحة. في هذا المثال، سنُنشئ مخططًا خطيًا بعلامات.

```csharp
// إضافة مخطط العينة
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

هنا نقوم بتحديد نوع المخطط (LineWithMarkers) وموقعه وأبعاده على الشريحة.

## الخطوة 4: تعيين عنوان الرسم البياني

دعونا نضع عنوانًا للرسم البياني لتوفير السياق.

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

يقوم هذا الكود بتعيين عنوان للرسم البياني، وتحديد النص والمظهر ونمط الخط.

## الخطوة 5: تخصيص خطوط الشبكة الرئيسية

الآن، دعنا نقوم بتخصيص خطوط الشبكة الرئيسية لمحور القيمة.

```csharp
// ضبط تنسيق خطوط الشبكة الرئيسية لمحور القيمة
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

تعمل هذه الخطوة على تكوين مظهر خطوط الشبكة الرئيسية على محور القيمة.

## الخطوة 6: تخصيص خطوط الشبكة الثانوية

وبنفس الطريقة، يمكننا تخصيص خطوط الشبكة الثانوية لمحور القيمة.

```csharp
// ضبط تنسيق خطوط الشبكة الثانوية لمحور القيمة
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

يقوم هذا الكود بتعديل مظهر خطوط الشبكة الثانوية على محور القيمة.

## الخطوة 7: تحديد تنسيق رقم محور القيمة

تخصيص تنسيق الأرقام لمحور القيمة.

```csharp
// ضبط تنسيق رقم محور القيمة
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

تتيح لك هذه الخطوة تنسيق الأرقام المعروضة على محور القيمة.

## الخطوة 8: تعيين الحد الأقصى والحد الأدنى لقيم الرسم البياني

قم بتحديد الحد الأقصى والحد الأدنى للقيم في الرسم البياني.

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

هنا، يمكنك تحديد نطاق القيم التي يجب أن يعرضها محور الرسم البياني.

## الخطوة 9: تخصيص خصائص نص محور القيمة

يمكنك أيضًا تخصيص خصائص النص لمحور القيمة.

```csharp
// تعيين خصائص نص محور القيمة
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

يتيح لك هذا الكود ضبط نمط الخط ومظهر تسميات محور القيمة.

## الخطوة 10: إضافة عنوان محور القيمة

إذا كان الرسم البياني الخاص بك يتطلب عنوانًا لمحور القيمة، فيمكنك إضافته بهذه الخطوة.

```csharp
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

يقوم هذا الكود بتكوين مظهر خطوط الشبكة الرئيسية على محور الفئة.

## الخطوة 12: تخصيص خطوط الشبكة الثانوية لمحور الفئة

على غرار محور القيمة، يمكنك تخصيص خطوط الشبكة الثانوية لمحور الفئة.

```csharp
// ضبط تنسيق خطوط الشبكة الثانوية لمحور الفئة
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

هنا، يمكنك ضبط مظهر خطوط الشبكة الثانوية على محور الفئة.

## الخطوة 13: تخصيص خصائص نص محور الفئة

تخصيص خصائص النص لعناوين محور الفئة.

```csharp
// تعيين خصائص نص محور الفئة
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

يتيح لك هذا الكود ضبط نمط الخط ومظهر علامات محور الفئة.

## الخطوة 14: إضافة عنوان محور الفئة

يمكنك أيضًا إضافة عنوان إلى محور الفئة إذا لزم الأمر.

```csharp
// إعداد الفئة العنوان
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

## الخطوة 15: التخصيصات الإضافية

يمكنك استكشاف المزيد من التخصيصات، مثل الأساطير، وجدار الرسم البياني الخلفي، والأرضية، وألوان منطقة الرسم البياني. تتيح لك هذه التخصيصات تحسين المظهر البصري لرسمك البياني.

```csharp
// تخصيصات إضافية (اختياري)

// ضبط خصائص نص الأساطير
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// تعيين أساطير عرض الرسم البياني دون تداخل الرسم البياني
chart.Legend.Overlay = true;

// رسم السلسلة الأولى على محور القيمة الثانوي (إذا لزم الأمر)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true؛

// مخطط ضبط لون الجدار الخلفي
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// مخطط ضبط لون الأرضية
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// ضبط لون منطقة الرسم البياني
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// حفظ العرض التقديمي
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

تعد هذه التخصيصات الإضافية اختيارية ويمكن تطبيقها استنادًا إلى متطلبات تصميم الرسم البياني المحددة لديك.

## خاتمة

في هذا الدليل التفصيلي، استكشفنا التخصيص المتقدم للمخططات البيانية باستخدام Aspose.Slides لـ .NET. تعلمت كيفية إنشاء عرض تقديمي، وإضافة مخطط بياني، وضبط مظهره، بما في ذلك خطوط الشبكة، وتسميات المحاور، وعناصر مرئية أخرى. بفضل خيارات التخصيص الفعّالة التي يوفرها Aspose.Slides، يمكنك إنشاء مخططات بيانية تعرض بياناتك بفعالية وتجذب جمهورك.

إذا كانت لديك أي أسئلة أو واجهت أي تحديات أثناء العمل مع Aspose.Slides لـ .NET، فلا تتردد في استكشاف الوثائق [هنا](https://reference.aspose.com/slides/net/) أو اطلب المساعدة في Aspose.Slides [المنتدى](https://forum.aspose.com/).

## الأسئلة الشائعة

### ما هي إصدارات .NET التي يدعمها Aspose.Slides لـ .NET؟
يدعم Aspose.Slides for .NET إصدارات .NET مختلفة، بما في ذلك .NET Framework و.NET Core. يمكنك مراجعة الوثائق للاطلاع على القائمة الكاملة للإصدارات المدعومة.

### هل يمكنني إنشاء مخططات بيانية من مصادر بيانات مثل ملفات Excel باستخدام Aspose.Slides لـ .NET؟
نعم، يتيح لك Aspose.Slides for .NET إنشاء مخططات بيانية من مصادر بيانات خارجية، مثل جداول بيانات Excel. يمكنك الاطلاع على الوثائق للاطلاع على أمثلة مفصلة.

### كيف يمكنني إضافة تسميات بيانات مخصصة إلى سلسلة المخططات الخاصة بي؟
لإضافة تسميات بيانات مخصصة إلى سلسلة المخططات الخاصة بك، يمكنك الوصول إلى `DataLabels` خصائص السلسلة، وخصّص التسميات حسب الحاجة. راجع الوثائق للاطلاع على نماذج وأمثلة التعليمات البرمجية.

### هل من الممكن تصدير الرسم البياني إلى تنسيقات ملفات مختلفة، مثل تنسيقات PDF أو الصور؟
نعم، يوفر Aspose.Slides لـ .NET خيارات لتصدير عرضك التقديمي مع المخططات إلى تنسيقات مختلفة، بما في ذلك تنسيقات PDF والصور. يمكنك استخدام المكتبة لحفظ عملك بالتنسيق المطلوب.

### أين يمكنني العثور على المزيد من البرامج التعليمية والأمثلة لـ Aspose.Slides لـ .NET؟
يمكنك العثور على مجموعة كبيرة من البرامج التعليمية وأمثلة التعليمات البرمجية والوثائق على Aspose.Slides [موقع إلكتروني](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
title: خيارات علامة الرسم البياني على نقطة البيانات
linktitle: خيارات علامة الرسم البياني على نقطة البيانات
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين تصورات البيانات الخاصة بك باستخدام Aspose.Slides لـ .NET. استكشف خيارات علامات الرسم البياني خطوة بخطوة.
type: docs
weight: 11
url: /ar/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

## مقدمة إلى خيارات علامة الرسم البياني

خيارات علامة المخطط هي تحسينات مرئية يمكن تطبيقها على نقاط البيانات الفردية في المخطط. تساعد هذه العلامات في تسليط الضوء على قيم بيانات محددة، مما يسهل على الجمهور تفسير المعلومات المقدمة. باستخدام خيارات علامة المخطط، يمكنك جذب الانتباه إلى نقاط البيانات الهامة والتأكيد على الاتجاهات أو القيم المتطرفة.

## تهيئة بيئة التطوير

قبل أن نتعمق في العمل مع خيارات علامات المخطط باستخدام Aspose.Slides for .NET، دعونا نتأكد من أن لدينا الأدوات اللازمة في مكانها الصحيح.

## تثبيت Aspose.Slides لـ .NET

 للبدء، تحتاج إلى تثبيت Aspose.Slides for .NET في بيئة التطوير لديك. يمكنكم تحميل المكتبة من الموقع:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net).

## إنشاء مشروع جديد

بمجرد تثبيت Aspose.Slides for .NET، قم بإنشاء مشروع جديد في بيئة تطوير .NET المفضلة لديك. يمكنك استخدام Visual Studio أو أي بيئة تطوير متكاملة (IDE) أخرى من اختيارك.

## تحميل وتعديل عرض تقديمي موجود

للعمل مع خيارات علامات المخطط، نحتاج إلى عرض تقديمي موجود يحتوي على مخطط. لنبدأ بتحميل عرض تقديمي موجود والوصول إلى الشريحة التي تحتوي على المخطط.

## تحميل ملف العرض التقديمي

```csharp
// قم بتحميل العرض التقديمي
using (Presentation presentation = new Presentation("sample.pptx"))
{
    // الكود الخاص بك للعمل مع العرض التقديمي موجود هنا
}
```

## الوصول إلى الشريحة مع الرسم البياني

بعد ذلك، دعونا نحدد الشريحة التي تحتوي على المخطط الذي نريد تعديله.

```csharp
//الوصول إلى شريحة باستخدام مخطط
ISlide slide = presentation.Slides[0]; // استبدل 0 بفهرس الشريحة
```

## الوصول إلى سلسلة بيانات الرسم البياني

من أجل تطبيق خيارات العلامة على نقاط البيانات، نحتاج أولاً إلى الوصول إلى سلسلة البيانات ذات الصلة داخل المخطط.

## تحديد سلسلة البيانات

```csharp
// الوصول إلى الرسم البياني على الشريحة
IChart chart = slide.Shapes[0] as IChart;

// الوصول إلى سلسلة البيانات الأولى
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries dataSeries = chart.ChartData.Series[0];
```

## الوصول إلى نقاط البيانات

الآن بعد أن أصبح لدينا إمكانية الوصول إلى سلسلة البيانات، يمكننا العمل مع نقاط البيانات الفردية.

```csharp
// الوصول إلى نقاط البيانات الفردية
foreach (IChartDataPoint dataPoint in dataSeries.DataPoints)
{
    // الكود الخاص بك للعمل مع نقاط البيانات موجود هنا
}
```

## تطبيق خيارات العلامة

دعونا الآن نطبق خيارات العلامة على نقاط البيانات داخل المخطط.

## تمكين العلامات لنقاط البيانات

```csharp
// تمكين العلامات لنقاط البيانات
foreach (IChartDataPoint dataPoint in dataSeries.DataPoints)
{
    dataPoint.Marker.Symbol.MarkerType = MarkerStyleType.Circle; // يمكنك اختيار نوع علامة مختلف
    dataPoint.Marker.Symbol.Size = 10; // اضبط حجم العلامة حسب الحاجة
    dataPoint.Marker.Visible = true; // إظهار العلامات
}
```

## تخصيص مظهر العلامة

يمكنك أيضًا تخصيص مظهر العلامات لجعلها أكثر جاذبية من الناحية المرئية.

```csharp
// تخصيص مظهر العلامة
foreach (IChartDataPoint dataPoint in dataSeries.DataPoints)
{
    dataPoint.Marker.Symbol.MarkerType = MarkerStyleType.Diamond;
    dataPoint.Marker.Symbol.Size = 12;
    dataPoint.Marker.Symbol.Fill.SolidFillColor.Color = Color.Red;
    dataPoint.Marker.Symbol.LineFormat.FillFormat.FillType = FillType.Solid;
    dataPoint.Marker.Symbol.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## إضافة تسميات إلى العلامات

يمكن أن تؤدي إضافة تسميات البيانات إلى العلامات إلى توفير السياق والوضوح للمخطط.

## عرض تسميات البيانات

```csharp
// عرض تسميات البيانات
foreach (IChartDataPoint dataPoint in dataSeries.DataPoints)
{
    IDataLabel dataLabel = dataPoint.Label;
    dataLabel.ShowCategoryName = true;
    dataLabel.ShowValue = true;
}
```

## تنسيق تسميات البيانات

يمكنك تنسيق تسميات البيانات لتناسب تفضيلاتك.

```csharp
// تنسيق تسميات البيانات
foreach (IChartDataPoint dataPoint in dataSeries.DataPoints)
{
    IDataLabel dataLabel = dataPoint.Label;
    dataLabel.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
    dataLabel.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 14;
}
```

## التعامل مع علامة التداخل

في الحالات التي تتداخل فيها العلامات وتسبب فوضى بصرية، فمن المهم التعامل مع مواضع العلامات.

## ضبط تداخل العلامة

```csharp
// ضبط تداخل العلامة
chart.Placement = PlacementType.FreeFloating;
chart.MarkerOverlap = -30; // اضبط قيمة التداخل حسب الحاجة
```

## اختيار مواضع العلامات المثالية

```csharp
// اختيار مواضع العلامات الأمثل
chart.MarkerClustered = false;
chart.MarkerSymbolSpacing = 2; // ضبط التباعد حسب الحاجة
```

## حفظ وتصدير العرض التقديمي المعدل

بمجرد إجراء التعديلات اللازمة على المخطط، يمكنك حفظ العرض التقديمي المعدل وتصديره.

## الحفظ بتنسيقات مختلفة

```csharp
// الحفظ في صيغ مختلفة
presentation.Save("modified.pptx", SaveFormat.Pptx);
presentation.Save("modified.pdf", SaveFormat.Pdf);
```

## التصدير إلى PDF أو صورة

```csharp
// التصدير إلى PDF أو الصورة
using (FileStream stream = new FileStream("output.pdf", FileMode.Create))
{
    PdfOptions options = new PdfOptions();
    presentation.Save(stream

, SaveFormat.Pdf);
}
```

## حالات الاستخدام في العالم الحقيقي

تعتبر خيارات علامة الرسم البياني لا تقدر بثمن عند تحليل سيناريوهات البيانات الواقعية.

## تحليل أداء المبيعات

باستخدام خيارات التحديد، يمكن لمحللي المبيعات تحديد أشهر المبيعات الاستثنائية وتصور الاتجاهات بمرور الوقت.

## اتجاهات سوق الأوراق المالية

يمكن للمستثمرين الاستفادة من خيارات العلامات لتحديد التقلبات الكبيرة في أسعار الأسهم واتخاذ قرارات مستنيرة.

## أفضل الممارسات لتصور البيانات الفعالة

عند إنشاء المخططات، ضع أفضل الممارسات هذه في الاعتبار.

## الحفاظ على الرسوم البيانية بسيطة وواضحة

البساطة تعزز الفهم. تجنب اكتظاظ المخططات بعلامات زائدة.

## استخدام أنواع المخططات المناسبة

اختر أنواع المخططات التي تنقل بياناتك بشكل فعال. لا تتطلب كافة مجموعات البيانات علامات.

## خاتمة

في هذه المقالة، بحثنا في عالم خيارات علامات المخطط باستخدام Aspose.Slides لـ .NET. لقد استكشفنا العملية خطوة بخطوة لتمكين العلامات وتخصيصها وإدارتها على نقاط البيانات داخل المخططات. باتباع التقنيات الموضحة في هذا الدليل، يمكنك رفع مهاراتك في تصور البيانات وإنشاء عروض تقديمية مقنعة تلقى صدى لدى جمهورك.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides for .NET من صفحة الإصدارات:[تنزيل Aspose.Slides لـ .NET](https://releases.aspose.com/slides/net).

### هل يمكنني تخصيص مظهر العلامات؟

قطعاً! يمكنك الاختيار من بين أنواع العلامات المختلفة وتخصيص حجمها ولونها وشكلها.

### هل هناك طريقة للتعامل مع تداخل العلامات؟

نعم، يمكنك ضبط إعدادات تداخل العلامات لمنع الفوضى المرئية في مخططاتك.

### ما هي التنسيقات التي يمكنني حفظ العرض التقديمي المعدل بها؟

يدعم Aspose.Slides for .NET حفظ العروض التقديمية بتنسيقات مختلفة، بما في ذلك PPTX وPDF.

### كيف يمكنني إضافة تسميات البيانات إلى العلامات؟

يمكنك بسهولة إضافة تسميات البيانات إلى العلامات وتنسيقها وفقًا لتفضيلاتك.
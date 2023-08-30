---
title: إنشاء المخطط وتخصيصه في Aspose.Slides
linktitle: إنشاء المخطط وتخصيصه في Aspose.Slides
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء مخططات مذهلة وتخصيصها باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 10
url: /ar/net/chart-creation-and-customization/chart-creation-and-customization/
---

## مقدمة إلى Aspose.Slides

Aspose.Slides هي مكتبة قوية توفر واجهات برمجة التطبيقات للعمل مع عروض PowerPoint التقديمية بلغات برمجة مختلفة، بما في ذلك .NET. فهو يمكّن المطورين من إنشاء عناصر مختلفة من العروض التقديمية ومعالجتها وإدارتها، مثل الشرائح والأشكال والنصوص والمخططات.

## إعداد مشروعك

قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides في مشروع .NET الخاص بك. يمكنك تنزيله من موقع Aspose أو تثبيته عبر مدير الحزم NuGet.

```csharp
// قم بتثبيت Aspose.Slides عبر NuGet
Install-Package Aspose.Slides
```

## إنشاء مخطط

لإنشاء مخطط باستخدام Aspose.Slides، اتبع الخطوات التالية:

1. قم باستيراد مساحات الأسماء الضرورية:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

2. تهيئة العرض التقديمي:
```csharp
Presentation presentation = new Presentation();
ISlide slide = presentation.Slides.AddEmptySlide();
```

3. إضافة مخطط إلى الشريحة:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Column, 100, 100, 500, 300);
```

## إضافة البيانات إلى الرسم البياني

بعد ذلك، دعونا نضيف البيانات إلى المخطط لدينا:

1. الوصول إلى مصنف المخطط:
```csharp
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
```

2. إضافة فئات وسلسلة:
```csharp
workbook.AddCell(0, 1, "Category 1");
workbook.AddCell(0, 2, "Category 2");

IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, 1), chart.Type);
```

3. تعيين قيم للسلسلة:
```csharp
series.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 2));
```

## تخصيص عناصر الرسم البياني

يمكنك تخصيص عناصر المخطط المختلفة:

1. تخصيص عنوان المخطط:
```csharp
chart.HasTitle = true;
chart.ChartTitle.Text.Text = "Sales Data";
```

2. تعديل خصائص المحور:
```csharp
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.Text.Text = "Months";
```

3. ضبط خطوط الشبكة وعلامات التجزئة:
```csharp
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Gray;
```

## تطبيق الأنماط والألوان

تحسين مظهر الرسم البياني الخاص بك:

1. تطبيق نمط الرسم البياني:
```csharp
chart.ChartStyle = 5; // اختر النمط المطلوب
```

2. تعيين ألوان السلسلة:
```csharp
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = Color.Blue;
```

## تنسيق المحاور والتسميات

تنسيق محور التحكم والتسميات:

1. تنسيق قيم المحور:
```csharp
chart.Axes.HorizontalAxis.NumberFormat.FormatCode = "mm/dd";
```

2. تدوير تسميات المحور:
```csharp
chart.Axes.HorizontalAxis.TextFormat.RotationAngle = 45;
```

## إضافة العناوين والأساطير

أضف العناوين والأساطير لتعزيز الوضوح:

1. تخصيص خصائص وسيلة الإيضاح:
```csharp
chart.Legend.Position = LegendPosition.Bottom;
chart.Legend.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

2. تعيين عناوين المحاور:
```csharp
chart.Axes.VerticalAxis.Title.Text.Text = "Sales";
```

## العمل مع سلسلة متعددة

دمج سلاسل متعددة لتمثيل البيانات الشاملة:

1. إضافة سلسلة إضافية:
```csharp
IChartSeries series2 = chart.ChartData.Series.Add(workbook.GetCell(0, 2), chart.Type);
```

2. تعيين قيم للسلسلة الجديدة:
```csharp
series2.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 3));
```

## حفظ وتصدير العرض التقديمي

وأخيرًا، قم بحفظ العرض التقديمي وتصديره:

```csharp
presentation.Save("ChartPresentation.pptx", SaveFormat.Pptx);
```
## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إنشاء المخططات وتخصيصها ومعالجتها باستخدام مكتبة Aspose.Slides لـ .NET. يوفر Aspose.Slides مجموعة شاملة من الميزات التي تمكّن المطورين من العمل برمجيًا مع عروض PowerPoint التقديمية والتعامل بكفاءة مع المهام المتعلقة بالمخططات.

## الأسئلة الشائعة

### كيف يمكنني تغيير نوع المخطط بعد إنشائه؟

 يمكنك تعديل نوع المخطط باستخدام`ChangeType` الطريقة على كائن المخطط وتوفير المطلوب`ChartType` قيمة التعداد.

### هل يمكنني تطبيق تأثيرات ثلاثية الأبعاد على المخطط الخاص بي؟

 نعم، يمكنك إضافة تأثيرات ثلاثية الأبعاد إلى المخطط الخاص بك عن طريق تكوين`Format.ThreeDFormat` خصائص سلسلة الرسم البياني.

### هل من الممكن تضمين الرسوم البيانية في تطبيقات الويب؟

قطعاً! يمكنك إنشاء مخططات باستخدام Aspose.Slides ثم عرضها في تطبيقات الويب عن طريق تصدير الشرائح كصور أو HTML تفاعلي.

### هل يمكنني تخصيص مظهر نقاط البيانات الفردية؟

 بالتأكيد! يمكنك الوصول إلى نقاط البيانات الفردية باستخدام`DataPoints`جمع وتطبيق التنسيق لهم.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ .NET؟

 للحصول على وثائق وأمثلة مفصلة، قم بزيارة[Aspose.Slides لوثائق .NET](https://reference.aspose.com/slides/net).
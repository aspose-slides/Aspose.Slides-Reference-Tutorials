---
title: كيانات المخطط وتنسيقه
linktitle: كيانات المخطط وتنسيقه
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعلم كيفية إنشاء وتنسيق المخططات الديناميكية في PowerPoint باستخدام Aspose.Slides لـ .NET. دليل خطوة بخطوة مع كود المصدر.
type: docs
weight: 13
url: /ar/net/advanced-chart-customization/chart-entities/
---

## مقدمة إلى Aspose.Slides والتلاعب بالرسوم البيانية

Aspose.Slides for .NET هي مكتبة شاملة تمكّن المطورين من إنشاء عروض PowerPoint التقديمية وتحريرها ومعالجتها برمجياً. عندما يتعلق الأمر بالمخططات، يوفر Aspose.Slides مجموعة واسعة من الوظائف لإضافة المخططات وتعديلها وتنسيقها داخل شرائح العرض التقديمي.

## إعداد بيئة التطوير الخاصة بك

 للبدء، تأكد من أن لديك بيئة تطوير عمل مع تثبيت Aspose.Slides for .NET. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/slides/net/).

## إضافة مخطط إلى شريحة

لنبدأ بإضافة مخطط إلى الشريحة. يوضح التعليمة البرمجية التالية كيفية إنشاء عرض تقديمي جديد وإضافة شريحة وإدراج مخطط فيها:

```csharp
// إنشاء كائن العرض التقديمي
Presentation presentation = new Presentation();

// أضف شريحة
ISlide slide = presentation.Slides.AddEmptySlide();

// أضف مخططًا إلى الشريحة
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 100, 100, 500, 300);
```

## تعديل بيانات الرسم البياني

الرسوم البيانية لا شيء بدون بيانات. يمكّنك Aspose.Slides من ملء المخططات بالبيانات بسهولة. إليك كيفية تعديل بيانات المخطط:

```csharp
// مصنف الوصول إلى المخطط
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// الوصول إلى ورقة عمل الرسم البياني
IChartDataWorksheet worksheet = workbook.Worksheets[0];

// تعبئة بيانات المخطط
worksheet.Cells["A1"].Value = "Category";
worksheet.Cells["A2"].Value = "Apple";
worksheet.Cells["A3"].Value = "Banana";
// ...

worksheet.Cells["B1"].Value = "Value";
worksheet.Cells["B2"].Value = 25;
worksheet.Cells["B3"].Value = 40;
// ...
```

## تخصيص مظهر الرسم البياني

يؤدي تنسيق المخطط إلى تحسين جاذبيته البصرية. دعنا نستكشف كيفية تنسيق الجوانب المختلفة للمخطط:

## تنسيق عنوان المخطط ومحاوره

يمكنك تنسيق عنوان المخطط ومحاوره باستخدام الكود التالي:

```csharp
chart.HasTitle = true;
chart.ChartTitle.TextFrame.Text = "Sales Report";

chart.Axes.HorizontalAxis.Title.TextFrame.Text = "Fruits";
chart.Axes.VerticalAxis.Title.TextFrame.Text = "Quantity";
```

## تطبيق أنماط الرسم البياني

قم بتطبيق أنماط المخططات المحددة مسبقًا لجعل المخطط الخاص بك أكثر جاذبية:

```csharp
chart.ChartStyle = ChartStylePreset.Style2;
```

## ضبط تسميات البيانات

توفر تسميات البيانات سياقًا للمخطط. تعديلهم مثل هذا:

```csharp
IDataLabel label = chart.Series[0].DataPoints[0].Label;
label.ShowValue = true;
label.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

## العمل مع عناصر الرسم البياني

تعمل إدارة عناصر المخطط على تحسين قدرتك على التحكم في التمثيل المرئي للمخطط. دعنا نستكشف بعض التقنيات:

## إدارة سلسلة البيانات

يمكنك إضافة سلسلة بيانات وإزالتها ومعالجتها كما يلي:

```csharp
IChartSeries series = chart.ChartData.Series.Add(worksheet.Cells, "A2:A3", "B2:B3");
```

## التعامل مع أساطير الرسم البياني

توفر وسائل الإيضاح معلومات أساسية حول مكونات المخطط:

```csharp
chart.Legend.Position = LegendPosition.Bottom;
```

## التعامل مع نقاط البيانات

اضبط نقاط البيانات بشكل فردي للتأكيد:

```csharp
chart.Series[0].DataPoints[0].Format.Fill.FillType = FillType.Solid;
chart.Series[0].DataPoints[0].Format.Fill.SolidFillColor.Color = Color.Red;
```

## تصدير وحفظ العرض التقديمي المعدل

بمجرد إجراء التعديلات المطلوبة على الرسم البياني، يمكنك حفظ العرض التقديمي:

```csharp
presentation.Save("ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## خاتمة

في هذا الدليل، اكتشفنا العالم الرائع لكيانات المخطط وتنسيقه باستخدام Aspose.Slides for .NET. لقد بدأنا بأساسيات إضافة المخططات وتعديلها، وتعمقنا في تخصيص مظهرها، وحتى إدارة عناصر المخطط المختلفة. يوفر Aspose.Slides للمطورين مجموعة أدوات قوية لإنشاء مخططات جذابة وغنية بالمعلومات برمجيًا.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides لـ .NET من[هنا](https://releases.aspose.com/slides/net/).

### هل يمكنني تطبيق أنماط مخصصة على الرسوم البيانية؟

نعم، يمكنك تطبيق أنماط مخصصة على المخططات من خلال معالجة خصائص المخطط المختلفة.

### كيف أقوم بإضافة تسميات البيانات إلى نقاط بيانات المخطط؟

 يمكنك إضافة تسميات البيانات إلى نقاط بيانات المخطط باستخدام`DataLabel` خاصية نقطة البيانات.

### هل Aspose.Slides مناسب للمطورين المتقدمين فقط؟

لا، Aspose.Slides مصمم لتلبية احتياجات المطورين على جميع المستويات، من المبتدئين إلى الخبراء.

### هل يمكنني تصدير المخططات إلى تنسيقات مختلفة باستخدام Aspose.Slides؟

قطعاً! يدعم Aspose.Slides تصدير العروض التقديمية إلى تنسيقات مختلفة، بما في ذلك PowerPoint وPDF.
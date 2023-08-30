---
title: استرداد المصنف من الرسم البياني
linktitle: استرداد المصنف من الرسم البياني
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية استرداد مصنف من مخطط باستخدام Aspose.Slides لـ .NET. استخراج بيانات المخطط وإنشاء مصنفات Excel برمجياً.
type: docs
weight: 12
url: /ar/net/additional-chart-features/chart-recover-workbook/
---

## مقدمة

من الممكن أن تقع حوادث، وقد تجد نفسك بحاجة إلى استرداد مصنف من مخطط. يأتي Aspose.Slides for .NET للإنقاذ في مثل هذه المواقف. تتيح لك هذه المكتبة القوية استخراج البيانات من المخططات في العروض التقديمية وتحويلها إلى مصنف جديد. في هذا الدليل المفصّل خطوة بخطوة، سنرشدك خلال عملية استرداد مصنف من مخطط باستخدام Aspose.Slides for .NET.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر ما يلي:

- Visual Studio: قم بتنزيل وتثبيت Visual Studio، وهو أمر ضروري لتطوير .NET.
-  Aspose.Slides for .NET: يمكنك تنزيل المكتبة من[هنا](https://downloads.aspose.com/slides/net).

## الخطوة 1: تثبيت Aspose.Slides لـ .NET

إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل Aspose.Slides وتثبيته لـ .NET. توفر هذه المكتبة ميزات شاملة للعمل مع عروض PowerPoint التقديمية برمجياً.

## الخطوة 2: قم بتحميل العرض التقديمي

للبدء، قم بإنشاء مشروع C# جديد في Visual Studio. قم بإضافة مراجع إلى تجميعات Aspose.Slides الضرورية. قم بتحميل عرض PowerPoint التقديمي الذي يحتوي على المخطط الذي تريد استرداد البيانات منه.

```csharp
// قم بتحميل العرض التقديمي
Presentation presentation = new Presentation("your-presentation.pptx");
```

## الخطوة 3: تحديد المخطط

 حدد الشريحة والمخطط الذي تريد استرداد البيانات منه. يمكنك الوصول إلى الشرائح باستخدام`presentation.Slides` جمع والرسوم البيانية باستخدام`slide.Shapes` مجموعة.

```csharp
// احصل على الشريحة التي تحتوي على المخطط
ISlide slide = presentation.Slides[0];

// احصل على الرسم البياني
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## الخطوة 4: استخراج البيانات من الرسم البياني

استخرج البيانات من المخطط باستخدام واجهة برمجة تطبيقات Aspose.Slides. يمكنك استرداد القيم من سلسلة وفئات المخطط.

```csharp
// استخراج بيانات الرسم البياني
IChartData chartData = chart.ChartData;
```

## الخطوة 5: إنشاء مصنف جديد

قم بإنشاء مصنف Excel جديد باستخدام مكتبة مثل EPPlus أو ClosedXML.

```csharp
// إنشاء مصنف Excel جديد
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // أضف التعليمات البرمجية هنا لملء رؤوس ورقة العمل
}
```

## الخطوة 6: تعبئة المصنف ببيانات المخطط

قم بملء ورقة عمل Excel بالبيانات المستخرجة من المخطط.

```csharp
//تعبئة ورقة عمل Excel ببيانات الرسم البياني
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // أضف التعليمات البرمجية هنا لملء ورقة العمل ببيانات السلسلة
    rowIndex++;
}
```

## الخطوة 7: احفظ المصنف

احفظ مصنف Excel مع بيانات المخطط المستردة.

```csharp
// احفظ مصنف Excel
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## خاتمة

أصبح استرداد مصنف من مخطط أمرًا سهلاً باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك استخراج البيانات برمجيًا من مخطط في عرض تقديمي لـ PowerPoint وإنشاء مصنف Excel جديد باستخدام البيانات المستردة. يمكن أن تكون هذه العملية منقذة للحياة عند وقوع حوادث، ويجب إنقاذ البيانات.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

 يمكنك تنزيل Aspose.Slides لـ .NET من[هنا](https://downloads.aspose.com/slides/net).

### هل يمكنني استعادة البيانات من أنواع مختلفة من الرسوم البيانية؟

نعم، يدعم Aspose.Slides for .NET أنواعًا مختلفة من المخططات، بما في ذلك المخططات الشريطية، والمخططات الخطية، والمخططات الدائرية، والمزيد.

### هل Aspose.Slides for .NET مناسب للاستخدام المهني؟

قطعاً! Aspose.Slides for .NET هي مكتبة قوية يستخدمها المطورون للعمل مع عروض PowerPoint التقديمية بكفاءة.

### هل هناك أي متطلبات ترخيص لاستخدام Aspose.Slides لـ .NET؟

 نعم، يتطلب Aspose.Slides for .NET ترخيصًا صالحًا للاستخدام التجاري. يمكنك العثور على تفاصيل الترخيص على[موقع أسبوز](https://purchase.aspose.com).

### هل يمكنني تخصيص مظهر مصنف Excel المسترد؟

نعم، يمكنك تخصيص مظهر مصنف Excel وتنسيقه باستخدام مكتبات مثل EPPlus أو ClosedXML.
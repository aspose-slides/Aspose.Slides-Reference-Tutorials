---
title: تلوين الرسم البياني باستخدام Aspose.Slides لـ .NET
linktitle: أضف اللون إلى نقاط البيانات في المخطط
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة لون إلى نقاط البيانات في مخطط باستخدام Aspose.Slides لـ .NET. قم بتحسين عروضك التقديمية بصريًا وإشراك جمهورك بشكل فعال.
weight: 12
url: /ar/net/licensing-and-formatting/add-color-to-data-points/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


في هذا الدليل خطوة بخطوة، سنرشدك خلال عملية إضافة اللون إلى نقاط البيانات في المخطط باستخدام Aspose.Slides for .NET. Aspose.Slides هي مكتبة قوية للعمل مع عروض PowerPoint التقديمية في تطبيقات .NET. يمكن أن تؤدي إضافة لون إلى نقاط البيانات في المخطط إلى جعل عروضك التقديمية أكثر جاذبية من الناحية المرئية وأسهل للفهم.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: أنت بحاجة إلى تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك.

2.  Aspose.Slides لـ .NET: قم بتنزيل Aspose.Slides لـ .NET وتثبيته من[رابط التحميل](https://releases.aspose.com/slides/net/).

3. الفهم الأساسي لـ C#: يجب أن تكون لديك معرفة أساسية ببرمجة C#.

4. دليل المستندات الخاص بك: استبدل "دليل المستندات الخاص بك" في الكود بالمسار الفعلي لدليل المستندات الخاص بك.

## استيراد مساحات الأسماء

قبل أن تتمكن من العمل مع Aspose.Slides لـ .NET، تحتاج إلى استيراد مساحات الأسماء الضرورية. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


في هذا المثال، سنقوم بإضافة لون إلى نقاط البيانات في المخطط باستخدام نوع المخطط Sunburst.

```csharp
using (Presentation pres = new Presentation())
{
    // المسار إلى دليل المستندات.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // سيتم إضافة بقية الكود في الخطوات التالية.
}
```

## الخطوة 1: الوصول إلى نقاط البيانات

لإضافة لون إلى نقاط بيانات محددة في مخطط، يتعين عليك الوصول إلى نقاط البيانات تلك. في هذا المثال، سنستهدف نقطة البيانات 3.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## الخطوة 2: تخصيص تسميات البيانات

الآن، دعونا نخصص تسميات البيانات لنقطة البيانات 0. سنقوم بإخفاء اسم الفئة وإظهار اسم السلسلة.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## الخطوة 3: تحديد تنسيق النص ولون التعبئة

يمكننا تحسين مظهر تسميات البيانات عن طريق تحديد تنسيق النص ولون التعبئة. في هذه الخطوة، سنقوم بتعيين لون النص إلى اللون الأصفر لنقطة البيانات 0.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## الخطوة 4: تخصيص لون تعبئة نقطة البيانات

الآن، دعونا نغير لون تعبئة نقطة البيانات 9. سنقوم بتعيينه على لون معين.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## الخطوة 5: حفظ العرض التقديمي

بعد تخصيص المخطط، يمكنك حفظ العرض التقديمي مع التغييرات.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في إضافة اللون إلى نقاط البيانات في مخطط باستخدام Aspose.Slides لـ .NET. يمكن أن يؤدي ذلك إلى تحسين المظهر البصري ووضوح عروضك التقديمية بشكل كبير.

## خاتمة

تعد إضافة لون إلى نقاط البيانات في المخطط طريقة فعالة لجعل عروضك التقديمية أكثر جاذبية وغنية بالمعلومات. باستخدام Aspose.Slides for .NET، لديك الأدوات اللازمة لإنشاء مخططات جذابة بصريًا تنقل بياناتك بفعالية.

## الأسئلة المتداولة (الأسئلة الشائعة)

### ما هو Aspose.Slides لـ .NET؟
   Aspose.Slides for .NET هي مكتبة تتيح لمطوري .NET العمل مع عروض PowerPoint التقديمية برمجيًا.

### هل يمكنني تخصيص خصائص المخطط الأخرى باستخدام Aspose.Slides؟
   نعم، يمكنك تخصيص جوانب مختلفة من المخططات، مثل تسميات البيانات والخطوط والألوان والمزيد، باستخدام Aspose.Slides for .NET.

### أين يمكنني العثور على وثائق Aspose.Slides لـ .NET؟
    يمكنك العثور على وثائق مفصلة على[رابط التوثيق](https://reference.aspose.com/slides/net/).

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
    نعم، يمكنك تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).

### كيف يمكنني الحصول على دعم Aspose.Slides لـ .NET؟
    للحصول على الدعم والمناقشات، قم بزيارة[منتدى Aspose.Slides](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}

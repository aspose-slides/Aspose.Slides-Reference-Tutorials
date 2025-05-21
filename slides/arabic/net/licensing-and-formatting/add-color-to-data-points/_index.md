---
"description": "تعرّف على كيفية إضافة ألوان إلى نقاط البيانات في مخطط بياني باستخدام Aspose.Slides لـ .NET. حسّن عروضك التقديمية بصريًا وتفاعل مع جمهورك بفعالية."
"linktitle": "إضافة اللون إلى نقاط البيانات في الرسم البياني"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "تلوين المخططات باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/licensing-and-formatting/add-color-to-data-points/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# تلوين المخططات باستخدام Aspose.Slides لـ .NET


في هذا الدليل التفصيلي، سنشرح لك عملية إضافة ألوان إلى نقاط البيانات في مخطط بياني باستخدام Aspose.Slides لـ .NET. Aspose.Slides مكتبة فعّالة للعمل مع عروض PowerPoint التقديمية في تطبيقات .NET. إضافة الألوان إلى نقاط البيانات في مخطط بياني تجعل عروضك التقديمية أكثر جاذبية بصريًا وأسهل فهمًا.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من توفر المتطلبات الأساسية التالية:

1. Visual Studio: تحتاج إلى تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك.

2. Aspose.Slides لـ .NET: قم بتنزيل Aspose.Slides لـ .NET وتثبيته من [رابط التحميل](https://releases.aspose.com/slides/net/).

3. فهم أساسي لـ C#: يجب أن يكون لديك معرفة أساسية ببرمجة C#.

4. دليل المستندات الخاص بك: استبدل "دليل المستندات الخاص بك" في الكود بالمسار الفعلي إلى دليل المستندات الخاص بك.

## استيراد مساحات الأسماء

قبل أن تتمكن من العمل مع Aspose.Slides لـ .NET، تحتاج إلى استيراد المساحات الأساسية الضرورية. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


في هذا المثال، سنضيف اللون إلى نقاط البيانات في مخطط باستخدام نوع مخطط Sunburst.

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

لإضافة لون إلى نقاط بيانات محددة في مخطط بياني، يجب الوصول إلى هذه النقاط. في هذا المثال، سنستهدف نقطة البيانات 3.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## الخطوة 2: تخصيص تسميات البيانات

الآن، دعنا نقوم بتخصيص تسميات البيانات لنقطة البيانات 0. سنقوم بإخفاء اسم الفئة وإظهار اسم السلسلة.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## الخطوة 3: ضبط تنسيق النص ولون التعبئة

يمكننا تحسين مظهر تسميات البيانات بشكل أكبر من خلال ضبط تنسيق النص ولون التعبئة. في هذه الخطوة، سنضبط لون النص إلى الأصفر لنقطة البيانات 0.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## الخطوة 4: تخصيص لون تعبئة نقطة البيانات

الآن، دعنا نغير لون التعبئة لنقطة البيانات 9. سنقوم بتعيينه إلى لون محدد.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## الخطوة 5: حفظ العرض التقديمي

بعد تخصيص الرسم البياني، يمكنك حفظ العرض التقديمي بالتغييرات.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

تهانينا! لقد نجحت في إضافة ألوان إلى نقاط البيانات في مخطط باستخدام Aspose.Slides لـ .NET. هذا يُحسّن بشكل كبير من جاذبية عروضك التقديمية ووضوحها.

## خاتمة

إضافة الألوان إلى نقاط البيانات في المخطط البياني طريقة فعّالة لجعل عروضك التقديمية أكثر جاذبيةً وإثراءً بالمعلومات. مع Aspose.Slides لـ .NET، تتوفر لديك الأدوات اللازمة لإنشاء مخططات بيانية جذابة بصريًا تعرض بياناتك بفعالية.

## الأسئلة الشائعة

### ما هو Aspose.Slides لـ .NET؟
   Aspose.Slides for .NET هي مكتبة تسمح لمطوري .NET بالعمل مع عروض PowerPoint برمجيًا.

### هل يمكنني تخصيص خصائص الرسم البياني الأخرى باستخدام Aspose.Slides؟
   نعم، يمكنك تخصيص جوانب مختلفة من المخططات، مثل تسميات البيانات، والخطوط، والألوان، والمزيد، باستخدام Aspose.Slides لـ .NET.

### أين يمكنني العثور على وثائق Aspose.Slides لـ .NET؟
   يمكنك العثور على وثائق مفصلة في [رابط التوثيق](https://reference.aspose.com/slides/net/).

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
   نعم، يمكنك تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

### كيف أحصل على الدعم لـ Aspose.Slides لـ .NET؟
   للحصول على الدعم والمناقشات، قم بزيارة [منتدى Aspose.Slides](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
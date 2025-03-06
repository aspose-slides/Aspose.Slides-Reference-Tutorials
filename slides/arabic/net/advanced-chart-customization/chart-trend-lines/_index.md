---
title: استكشاف خطوط اتجاه المخطط في Aspose.Slides لـ .NET
linktitle: خطوط الاتجاه الرسم البياني
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة خطوط اتجاه متنوعة إلى المخططات باستخدام Aspose.Slides لـ .NET في هذا الدليل التفصيلي خطوة بخطوة. تعزيز مهارات تصور البيانات الخاصة بك بكل سهولة!
weight: 12
url: /ar/net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# استكشاف خطوط اتجاه المخطط في Aspose.Slides لـ .NET


في عالم تصور البيانات وعرضها، يمكن أن يكون دمج المخططات وسيلة قوية لنقل المعلومات بشكل فعال. يوفر Aspose.Slides for .NET مجموعة غنية بالميزات من الأدوات للعمل مع المخططات، بما في ذلك القدرة على إضافة خطوط الاتجاه إلى المخططات الخاصة بك. في هذا البرنامج التعليمي، سوف نتعمق في عملية إضافة خطوط الاتجاه إلى الرسم البياني بطريقة خطوة بخطوة باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نبدأ العمل مع Aspose.Slides for .NET، ستحتاج إلى التأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides for .NET: للوصول إلى المكتبة واستخدامها، يجب أن يكون Aspose.Slides for .NET مثبتًا لديك. يمكنك الحصول على المكتبة من[صفحة التحميل](https://releases.aspose.com/slides/net/).

2. بيئة التطوير: يجب أن يكون لديك بيئة تطوير معدة، ويفضل استخدام بيئة تطوير متكاملة .NET مثل Visual Studio.

3. المعرفة الأساسية بـ C#: يعد الفهم الأساسي لبرمجة C# مفيدًا، حيث سنستخدم C# للعمل مع Aspose.Slides لـ .NET.

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، دعونا نقسم عملية إضافة خطوط الاتجاه إلى الرسم البياني خطوة بخطوة.

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء الضرورية إلى مشروع C# الخاص بك. تعد مساحات الأسماء هذه ضرورية للعمل مع Aspose.Slides لـ .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## الخطوة 1: إنشاء عرض تقديمي

في هذه الخطوة، نقوم بإنشاء عرض تقديمي فارغ للعمل عليه.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";

// قم بإنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// إنشاء عرض تقديمي فارغ
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

بعد ذلك، نضيف مخططًا عموديًا متفاوت المسافات إلى الشريحة.

```csharp
// إنشاء مخطط عمود متفاوت المسافات
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## الخطوة 3: إضافة خطوط الاتجاه إلى المخطط

الآن، نضيف أنواعًا مختلفة من خطوط الاتجاه إلى سلسلة المخططات.

### إضافة خط الاتجاه الأسي

```csharp
// إضافة خط الاتجاه الأسي لسلسلة الرسم البياني 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### إضافة خط الاتجاه الخطي

```csharp
// إضافة خط اتجاه خطي لسلسلة الرسم البياني 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### إضافة خط الاتجاه اللوغاريتمي

```csharp
// إضافة خط الاتجاه اللوغاريتمي لسلسلة المخططات 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### إضافة خط اتجاه المتوسط المتحرك

```csharp
// إضافة خط اتجاه المتوسط المتحرك لسلسلة الرسم البياني 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### إضافة خط اتجاه متعدد الحدود

```csharp
// إضافة خط اتجاه متعدد الحدود لسلسلة المخططات 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### إضافة خط اتجاه الطاقة

```csharp
// إضافة خط اتجاه الطاقة لسلسلة الرسم البياني 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## الخطوة 4: احفظ العرض التقديمي

بعد إضافة خطوط الاتجاه إلى المخطط، احفظ العرض التقديمي.

```csharp
// حفظ العرض التقديمي
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إضافة خطوط اتجاه متنوعة إلى المخطط الخاص بك باستخدام Aspose.Slides لـ .NET.

## خاتمة

Aspose.Slides for .NET هي مكتبة متعددة الاستخدامات تتيح لك إنشاء الرسوم البيانية ومعالجتها بسهولة. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك إضافة أنواع مختلفة من خطوط الاتجاه إلى مخططاتك، مما يعزز التمثيل المرئي لبياناتك.

### الأسئلة الشائعة

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
 يمكنك الوصول إلى الوثائق[هنا](https://reference.aspose.com/slides/net/).

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟
 يمكنك تنزيل Aspose.Slides for .NET من صفحة التنزيل[هنا](https://releases.aspose.com/slides/net/).

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
 نعم، يمكنك تجربة Aspose.Slides لـ .NET مجانًا من خلال زيارة الموقع[هذا الرابط](https://releases.aspose.com/).

### أين يمكنني شراء Aspose.Slides لـ .NET؟
 لشراء Aspose.Slides لـ .NET، قم بزيارة صفحة الشراء[هنا](https://purchase.aspose.com/buy).

### هل أحتاج إلى ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET من[هذا الرابط](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---
"description": "تعلّم كيفية إضافة خطوط اتجاهات متنوعة إلى الرسوم البيانية باستخدام Aspose.Slides لـ .NET في هذا الدليل المفصل. طوّر مهاراتك في تصور البيانات بسهولة!"
"linktitle": "خطوط اتجاه الرسم البياني"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "استكشاف خطوط اتجاه الرسم البياني في Aspose.Slides لـ .NET"
"url": "/ar/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# استكشاف خطوط اتجاه الرسم البياني في Aspose.Slides لـ .NET


في عالم عرض البيانات وتصورها، يُعدّ دمج المخططات البيانية وسيلة فعّالة لعرض المعلومات بفعالية. يوفر Aspose.Slides for .NET مجموعة أدوات غنية بالميزات للتعامل مع المخططات البيانية، بما في ذلك إمكانية إضافة خطوط اتجاه إليها. في هذا البرنامج التعليمي، سنتناول بالتفصيل عملية إضافة خطوط الاتجاه إلى مخطط بياني باستخدام Aspose.Slides for .NET. 

## المتطلبات الأساسية

قبل أن نبدأ العمل مع Aspose.Slides لـ .NET، ستحتاج إلى التأكد من توفر المتطلبات الأساسية التالية:

1. Aspose.Slides لـ .NET: للوصول إلى المكتبة واستخدامها، يجب تثبيت Aspose.Slides لـ .NET. يمكنك الحصول على المكتبة من [صفحة التحميل](https://releases.aspose.com/slides/net/).

2. بيئة التطوير: يجب أن يكون لديك بيئة تطوير مهيأة، ويفضل استخدام بيئة تطوير متكاملة .NET مثل Visual Studio.

3. المعرفة الأساسية بلغة C#: إن الفهم الأساسي لبرمجة C# مفيد، حيث سنستخدم C# للعمل مع Aspose.Slides لـ .NET.

الآن بعد أن قمنا بتغطية المتطلبات الأساسية، دعنا نستعرض عملية إضافة خطوط الاتجاه إلى الرسم البياني خطوة بخطوة.

## استيراد مساحات الأسماء

أولاً، تأكد من استيراد مساحات الأسماء اللازمة إلى مشروع C# الخاص بك. هذه المساحات ضرورية للعمل مع Aspose.Slides لـ .NET.

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

// إنشاء الدليل إذا لم يكن موجودًا بالفعل.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// إنشاء عرض تقديمي فارغ
Presentation pres = new Presentation();
```

## الخطوة 2: إضافة مخطط إلى الشريحة

بعد ذلك، نضيف مخططًا عموديًا مجمعًا إلى الشريحة.

```csharp
// إنشاء مخطط عمودي مجمع
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## الخطوة 3: إضافة خطوط الاتجاه إلى الرسم البياني

الآن، نضيف أنواعًا مختلفة من خطوط الاتجاه إلى سلسلة الرسم البياني.

### إضافة خط اتجاه أسي

```csharp
// إضافة خط الاتجاه الأسّي لسلسلة الرسم البياني 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### إضافة خط اتجاه خطي

```csharp
// إضافة خط اتجاه خطي لسلسلة الرسم البياني 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### إضافة خط اتجاه لوغاريتمي

```csharp
// إضافة خط الاتجاه اللوغاريتمي لسلسلة الرسم البياني 2
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
// إضافة خط اتجاه متعدد الحدود لسلسلة الرسم البياني 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### إضافة خط اتجاه القوة

```csharp
// إضافة خط اتجاه القوة لسلسلة الرسم البياني 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## الخطوة 4: حفظ العرض التقديمي

بعد إضافة خطوط الاتجاه إلى الرسم البياني، احفظ العرض التقديمي.

```csharp
// حفظ العرض التقديمي
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

هذا كل شيء! لقد نجحت في إضافة خطوط اتجاهات مختلفة إلى مخططك باستخدام Aspose.Slides لـ .NET.

## خاتمة

Aspose.Slides for .NET هي مكتبة متعددة الاستخدامات تُمكّنك من إنشاء الرسوم البيانية ومعالجتها بسهولة. باتباع هذا الدليل المُفصّل، يُمكنك إضافة أنواع مُختلفة من خطوط الاتجاه إلى رسومك البيانية، مما يُحسّن العرض المرئي لبياناتك.

### الأسئلة الشائعة

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Slides لـ .NET؟
يمكنك الوصول إلى الوثائق [هنا](https://reference.aspose.com/slides/net/).

### كيف يمكنني تنزيل Aspose.Slides لـ .NET؟
يمكنك تنزيل Aspose.Slides لـ .NET من صفحة التنزيل [هنا](https://releases.aspose.com/slides/net/).

### هل هناك نسخة تجريبية مجانية متاحة لـ Aspose.Slides لـ .NET؟
نعم، يمكنك تجربة Aspose.Slides for .NET مجانًا من خلال زيارة [هذا الرابط](https://releases.aspose.com/).

### أين يمكنني شراء Aspose.Slides لـ .NET؟
لشراء Aspose.Slides لـ .NET، تفضل بزيارة صفحة الشراء [هنا](https://purchase.aspose.com/buy).

### هل أحتاج إلى ترخيص مؤقت لـ Aspose.Slides لـ .NET؟
يمكنك الحصول على ترخيص مؤقت لـ Aspose.Slides لـ .NET من [هذا الرابط](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
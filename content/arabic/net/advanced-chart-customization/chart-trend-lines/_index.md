---
title: خطوط الاتجاه الرسم البياني
linktitle: خطوط الاتجاه الرسم البياني
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إنشاء خطوط اتجاه الرسم البياني باستخدام Aspose.Slides لـ .NET. قم بتحسين تصورات البيانات من خلال إرشادات خطوة بخطوة وأمثلة التعليمات البرمجية.
type: docs
weight: 12
url: /ar/net/advanced-chart-customization/chart-trend-lines/
---

## مقدمة لخطوط الاتجاه الرسم البياني

في تصور البيانات، تلعب خطوط الاتجاه دورًا حاسمًا في الكشف عن الأنماط والاتجاهات الأساسية داخل مجموعات البيانات. خط الاتجاه هو خط مستقيم أو منحني يمثل الاتجاه العام لنقاط البيانات. من خلال إضافة خطوط الاتجاه إلى المخططات الخاصة بك، يمكنك بسهولة تحديد الاتجاهات والارتباطات والانحرافات.

## إعداد بيئة التطوير الخاصة بك

قبل أن نتعمق في إنشاء خطوط اتجاه الرسم البياني، فلنقم بإعداد بيئة التطوير الخاصة بنا.

## تثبيت Aspose.Slides لـ .NET

للبدء، تحتاج إلى تثبيت Aspose.Slides لمكتبة .NET. يمكنك تنزيله من موقع الويب أو استخدام مدير الحزم مثل NuGet.

```csharp
// قم بتثبيت Aspose.Slides لـ .NET عبر NuGet
Install-Package Aspose.Slides
```

## إنشاء مشروع .NET جديد

بمجرد تثبيت المكتبة، قم بإنشاء مشروع .NET جديد في بيئة التطوير المفضلة لديك، مثل Visual Studio.

## إضافة البيانات إلى الرسم البياني

لتوضيح خطوط الاتجاه، سنقوم بإنشاء بعض نماذج البيانات وإنشاء مخطط أساسي باستخدام Aspose.Slides.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// إنشاء عرض تقديمي جديد
Presentation presentation = new Presentation();

// أضف شريحة
ISlide slide = presentation.Slides.AddSlide(0, SlideLayoutType.TitleAndContent);

// أضف مخططًا إلى الشريحة
IChart chart = slide.Shapes.AddChart(ChartType.Line, 100, 100, 500, 300);

// إضافة البيانات إلى المخطط
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), fact.GetCell(0, 0, 2, 20));
chart.ChartData.Series.Add(fact.GetCell(0, 1, 1, "Series 2"), fact.GetCell(0, 1, 2, 35));
// أضف المزيد من نقاط البيانات حسب الحاجة

// تعيين عنوان الرسم البياني
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart with Trend Lines";

// احفظ العرض التقديمي
presentation.Save("ChartWithTrendLines.pptx", SaveFormat.Pptx);
```

## إضافة خطوط الاتجاه

تأتي خطوط الاتجاه في أنواع مختلفة، بما في ذلك الخطوط الخطية والأسية ومتعددة الحدود. دعنا نستكشف كيفية إضافة خطوط الاتجاه هذه إلى مخططنا.

## إضافة خطوط الاتجاه الخطية

تكون خطوط الاتجاه الخطية مفيدة عندما تتبع نقاط البيانات نمط خط مستقيم تقريبًا. إن إضافة خط اتجاه خطي إلى الرسم البياني الخاص بنا هو أمر واضح ومباشر.

```csharp
// أضف خط اتجاه خطي إلى السلسلة الأولى
ITrendline linearTrendline = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
linearTrendline.DisplayEquation = true;
linearTrendline.DisplayRSquaredValue = true;
```

## إضافة خطوط الاتجاه الأسي

تعتبر خطوط الاتجاه الأسية مناسبة للبيانات التي تتغير بمعدل متسارع. إضافة خط الاتجاه الأسي يتبع عملية مماثلة.

```csharp
// أضف خط الاتجاه الأسي إلى السلسلة الثانية
ITrendline exponentialTrendline = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Exponential);
exponentialTrendline.DisplayEquation = true;
exponentialTrendline.DisplayRSquaredValue = true;
```

## إضافة خطوط الاتجاه كثيرة الحدود

تكون خطوط الاتجاه متعددة الحدود مفيدة عندما تكون تقلبات البيانات أكثر تعقيدًا. يمكنك إضافة خط اتجاه متعدد الحدود بالكود التالي.

```csharp
// أضف خط اتجاه متعدد الحدود إلى السلسلة الثانية
ITrendline polynomialTrendline = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Polynomial, 2);
polynomialTrendline.DisplayEquation = true;
polynomialTrendline.DisplayRSquaredValue = true;
```

## تخصيص خطوط الاتجاه

لتحسين التمثيل المرئي لخطوط الاتجاه الخاصة بك، يمكنك تخصيص مظهرها.

## تنسيق خطوط الاتجاه

يمكنك تنسيق خطوط الاتجاه عن طريق ضبط نمط الخط ولونه وسمكه.

```csharp
// تخصيص مظهر خط الاتجاه
linearTrendline.Format.Line.Style = LineStyle.ThickBetweenThin;
linearTrendline.Format.Line.DashStyle = LineDashStyle.DashDot;
linearTrendline.Format.Line.Width = 2;
linearTrendline.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

## التعامل مع التسميات والشروح

يمكن أن تؤدي إضافة تسميات البيانات والتعليقات التوضيحية إلى توفير سياق للمخطط الخاص بك.

## إضافة تسميات البيانات

تعرض تسميات البيانات قيم نقاط البيانات الفردية في المخطط.

```csharp
// إظهار تسميات البيانات للسلسلة الأولى
chart.ChartData.Series[0].Labels.ShowValue = true;
```

## شرح نقاط البيانات

تساعد التعليقات التوضيحية في تسليط الضوء على نقاط بيانات محددة أو أحداث مهمة.

```csharp
// إضافة تعليق توضيحي إلى نقطة البيانات
IChartDataPoint dataPoint = chart.ChartData.Series[0].DataPoints[0];
dataPoint.Marker.Format.Fill.FillType = FillType.Solid;
dataPoint.Marker.Format.Fill.SolidFillColor.Color = Color.Green;
```

## حفظ ومشاركة الرسم البياني الخاص بك

بمجرد إنشاء المخطط الخاص بك وتخصيصه باستخدام خطوط الاتجاه، فقد حان الوقت لحفظ عملك ومشاركته.

## الحفظ بتنسيقات مختلفة

يمكنك حفظ المخطط الخاص بك بتنسيقات مختلفة، مثل PPTX أو PDF أو تنسيقات الصور.

```csharp
// احفظ العرض التقديمي بتنسيقات مختلفة
presentation.Save("ChartWithTrendLines.pdf", SaveFormat.Pdf);
presentation.Save("ChartWithTrendLines.png", SaveFormat.Png);
```

## التضمين في العروض التقديمية

يمكنك أيضًا تضمين المخطط الخاص بك في عرض تقديمي أكبر لتوفير السياق والرؤى.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إنشاء خطوط اتجاه الرسم البياني باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك تحسين تمثيلات بياناتك باستخدام خطوط الاتجاه التي تكشف عن رؤى قيمة. قم بتجربة أنواع مختلفة من خطوط الاتجاه وخيارات التخصيص لجعل مخططاتك أكثر إفادة وجاذبية.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Slides لـ .NET؟

 يمكنك تثبيت Aspose.Slides لـ .NET عبر NuGet. للحصول على تعليمات مفصلة، راجع[توثيق](https://docs.aspose.com/slides/net/installation/).

### هل يمكنني تخصيص مظهر خطوط الاتجاه؟

نعم، يمكنك تخصيص خطوط الاتجاه عن طريق ضبط السمات مثل نمط الخط واللون والسمك. 

### هل من الممكن إضافة التعليقات التوضيحية إلى نقاط البيانات؟

 قطعاً! يمكنك إضافة تعليقات توضيحية إلى نقاط البيانات عن طريق تعديل سمات العلامة وإضافة معلومات سياقية. تعرف على المزيد في[توثيق](https://reference.aspose.com/slides/net/).

### كيف يمكنني حفظ الرسم البياني الخاص بي بتنسيقات مختلفة؟

 يمكنك حفظ المخطط الخاص بك بتنسيقات مختلفة، مثل PDF أو تنسيقات الصور، باستخدام`Save` طريقة. العثور على أمثلة في[توثيق](https://reference.aspose.com/slides/net/).

### أين يمكنني الوصول إلى مكتبة Aspose.Slides for .NET؟

 يمكنك الوصول إلى مكتبة Aspose.Slides for .NET من خلال زيارة الموقع[صفحة التحميل](https://releases.aspose.com/slides/net/). تأكد من تحديد الإصدار المناسب لمشروعك.
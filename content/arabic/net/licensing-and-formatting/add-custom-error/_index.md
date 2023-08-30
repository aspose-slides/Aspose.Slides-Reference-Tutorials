---
title: إضافة أشرطة خطأ مخصصة إلى المخطط
linktitle: إضافة أشرطة خطأ مخصصة إلى المخطط
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية إضافة أشرطة خطأ مخصصة إلى المخططات باستخدام Aspose.Slides لـ .NET. قم بإنشاء أشرطة الأخطاء وتصميمها وتخصيصها للحصول على تصور دقيق للبيانات.
type: docs
weight: 13
url: /ar/net/licensing-and-formatting/add-custom-error/
---

## مقدمة إلى أشرطة الخطأ المخصصة

أشرطة الخطأ عبارة عن تمثيلات رسومية تستخدم للإشارة إلى التباين أو عدم اليقين في نقاط البيانات في المخطط. ويمكن أن تساعد في تصوير النطاق الذي من المحتمل أن تقع ضمنه القيمة الحقيقية لنقطة البيانات. تسمح لك أشرطة الخطأ المخصصة بتحديد قيم خطأ محددة لكل نقطة بيانات، مما يوفر المزيد من التحكم في كيفية عرض عدم اليقين في المخطط الخاص بك.

## تهيئة بيئة التطوير

 قبل أن نبدأ، تأكد من تثبيت مكتبة Aspose.Slides for .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/slides/net). اتبع تعليمات التثبيت المتوفرة في الوثائق.

## إنشاء نموذج للمخطط

لنبدأ بإنشاء نموذج مخطط باستخدام Aspose.Slides لـ .NET. سنقوم بإنشاء مخطط شريطي أساسي لأغراض العرض التوضيحي. تأكد من أنك قمت بالرجوع إلى المكتبة في مشروعك.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// إنشاء كائن العرض التقديمي
using Presentation presentation = new Presentation();

// أضف شريحة
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// أضف مخططًا
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// أضف بيانات العينة
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// تعيين تسميات الفئات
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// تعيين عنوان الرسم البياني
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// احفظ العرض التقديمي
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

يقوم هذا الرمز بإنشاء عرض تقديمي لـ PowerPoint مع نموذج مخطط شريطي.

## إضافة أشرطة الخطأ إلى المخطط

الآن دعونا نضيف أشرطة الخطأ إلى المخطط. تتم إضافة أشرطة الخطأ إلى نقاط بيانات محددة في سلسلة. سنضيف أشرطة الخطأ إلى نقطة البيانات الأولى في نموذج الرسم البياني الخاص بنا.

```csharp
// الوصول إلى السلسلة الأولى
IChartSeries firstSeries = chart.ChartData.Series[0];

// إضافة أشرطة الخطأ
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// تعيين قيمة شريط الخطأ
errorBarsFormat.Value = 5; // يمكنك ضبط القيمة وفقًا لبياناتك

// احفظ العرض التقديمي المحدث
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

يضيف هذا الرمز أشرطة خطأ ذات قيمة ثابتة إلى نقطة البيانات الأولى في المخطط.

## تخصيص قيم شريط الخطأ

يمكنك تخصيص قيم شريط الخطأ لكل نقطة بيانات على حدة. دعونا نعدل الكود لتعيين قيم خطأ مختلفة لكل نقطة بيانات.

```csharp
// قم بتعيين قيم الخطأ المخصصة لكل نقطة
double[] errorValues = { 3, 6 }; // قيم الخطأ لنقطتي البيانات

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// احفظ العرض التقديمي المحدث
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

يقوم هذا الرمز بتعيين قيم خطأ مخصصة لكل نقطة بيانات في السلسلة.

## أشرطة خطأ التصميم

يمكنك تصميم أشرطة الأخطاء لتحسين رؤيتها ومطابقة جماليات المخطط الخاص بك. دعونا نخصص مظهر أشرطة الخطأ.

```csharp
// تخصيص مظهر شريط الخطأ
errorBarsFormat.LineFormat.Width = 2; // ضبط عرض الخط
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; //ضبط لون الخط

// احفظ العرض التقديمي المحدث
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

يضبط هذا الرمز عرض الخط ولون أشرطة الخطأ.

## تحديث بيانات الرسم البياني

إذا كنت بحاجة إلى تحديث بيانات المخطط، فيمكنك القيام بذلك بسهولة باستخدام Aspose.Slides for .NET. دعونا نستبدل البيانات بقيم جديدة.

```csharp
// تحديث بيانات الرسم البياني
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// احفظ العرض التقديمي المحدث
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

يقوم هذا الرمز بتحديث قيم بيانات المخطط.

## أشرطة الخطأ لسلسلة متعددة

يمكنك إضافة أشرطة خطأ إلى سلاسل متعددة في المخطط. دعونا نضيف أشرطة الخطأ إلى السلسلة الثانية في نموذج الرسم البياني الخاص بنا.

```csharp
// الوصول إلى السلسلة الثانية
IChartSeries secondSeries = chart.ChartData.Series[1];

// إضافة أشرطة الخطأ إلى السلسلة الثانية
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// قم بتعيين قيمة شريط الخطأ للسلسلة الثانية
secondSeriesErrorBars.Value = 10; // يمكنك ضبط القيمة

// احفظ العرض التقديمي المحدث
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

يضيف هذا الرمز أشرطة الخطأ إلى السلسلة الثانية في المخطط.

## التعامل مع الأخطاء السلبية والإيجابية

يمكن أن تمثل أشرطة الخطأ الأخطاء الإيجابية والسلبية. دعونا نعدل الكود لإضافة كلا النوعين من أشرطة الخطأ.

```csharp
// إضافة أشرطة الخطأ الإيجابية والسلبية
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // قيمة الخطأ الإيجابية
errorBarsFormat.MinusValue = 2; // قيمة الخطأ السلبية

// احفظ العرض التقديمي المحدث
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

يضيف هذا الرمز أشرطة خطأ إيجابية وسلبية مخصصة إلى المخطط.

## حفظ وتصدير الرسم البياني

بمجرد إضافة أشرطة الأخطاء وتخصيص المخطط الخاص بك، يمكنك حفظه وتصديره لمزيد من الاستخدام.

```csharp
// احفظ الرسم البياني النهائي
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

يحفظ هذا الرمز المخطط النهائي مع أشرطة الخطأ.

## خاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية إضافة أشرطة خطأ مخصصة إلى مخطط باستخدام Aspose.Slides لـ .NET. لقد قمنا بتغطية إنشاء نموذج مخطط، وإضافة أشرطة الخطأ، وتخصيص قيم الخطأ، وتصميم أشرطة الخطأ، وتحديث بيانات المخطط، وإضافة أشرطة الخطأ إلى سلاسل متعددة، ومعالجة الأخطاء الإيجابية والسلبية. مع Aspose.Slides for .NET، لديك المرونة اللازمة لإنشاء مخططات إعلامية وجذابة بصريًا مع أشرطة خطأ مخصصة تنقل تنوع بياناتك بشكل فعال.

## الأسئلة الشائعة

### كيف يمكنني ضبط سمك أشرطة الخطأ؟

 يمكنك ضبط سمك أشرطة الخطأ عن طريق تعديل`LineFormat.Width` ملكية`ErrorBarsFormat`.

### هل يمكنني استخدام قيم خطأ مختلفة لكل نقطة بيانات؟

نعم، يمكنك تعيين قيم خطأ مخصصة لكل نقطة بيانات على حدة باستخدام حلقة و`Value` ممتلكات`ErrorBarsFormat`.

### هل من الممكن إضافة أشرطة خطأ إلى سلاسل متعددة في مخطط واحد؟

بالتأكيد، يمكنك إضافة أشرطة خطأ إلى سلاسل متعددة في نفس المخطط. ما عليك سوى الوصول إلى السلسلة المطلوبة وتطبيق أشرطة الخطأ كما هو موضح في المقالة.

### هل يمكنني إزالة أشرطة الخطأ بعد إضافتها؟

 نعم، يمكنك إزالة أشرطة الخطأ عن طريق الاتصال بـ`Clear` الطريقة على`ErrorBarsFormat` هدف.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Slides لـ .NET؟

 يمكنك العثور على وثائق وأمثلة تفصيلية لـ Aspose.Slides for .NET على الموقع[موقع التوثيق Aspose](https://reference.aspose.com/slides/net/).
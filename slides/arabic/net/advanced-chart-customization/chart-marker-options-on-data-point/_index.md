---
title: استخدام خيارات علامة المخطط على نقطة البيانات في Aspose.Slides .NET
linktitle: خيارات علامة الرسم البياني على نقطة البيانات
second_title: Aspose.Slides .NET واجهة برمجة تطبيقات معالجة PowerPoint
description: تعرف على كيفية تحسين مخططات PowerPoint الخاصة بك باستخدام Aspose.Slides لـ .NET. تخصيص علامات نقطة البيانات مع الصور. إنشاء عروض تقديمية جذابة.
weight: 11
url: /ar/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


عند العمل مع العروض التقديمية وتصور البيانات، يقدم Aspose.Slides for .NET مجموعة واسعة من الميزات القوية لإنشاء المخططات وتخصيصها ومعالجتها. في هذا البرنامج التعليمي، سوف نستكشف كيفية استخدام خيارات علامة المخطط على نقاط البيانات لتحسين عروض الرسم البياني الخاصة بك. سيرشدك هذا الدليل خطوة بخطوة خلال العملية، بدءًا من المتطلبات الأساسية واستيراد مساحات الأسماء، وحتى تقسيم كل مثال إلى خطوات متعددة.

## المتطلبات الأساسية

قبل أن نتعمق في استخدام خيارات علامات المخطط على نقاط البيانات، تأكد من توفر المتطلبات الأساسية التالية:

-  Aspose.Slides for .NET: تأكد من تثبيت Aspose.Slides for .NET. يمكنك تنزيله من[موقع إلكتروني](https://releases.aspose.com/slides/net/).

- نموذج عرض تقديمي: في هذا البرنامج التعليمي، سنستخدم نموذج عرض تقديمي يسمى "Test.pptx." يجب أن يكون لديك هذا العرض التقديمي في دليل المستندات الخاص بك.

الآن، لنبدأ باستيراد مساحات الأسماء الضرورية.

## استيراد مساحات الأسماء

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

لقد قمنا باستيراد مساحات الأسماء المطلوبة وقمنا بتهيئة العرض التقديمي الخاص بنا. الآن، دعنا ننتقل إلى استخدام خيارات علامة الرسم البياني على نقاط البيانات.

## الخطوة 1: إنشاء المخطط الافتراضي

```csharp

// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//إنشاء المخطط الافتراضي
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

نقوم بإنشاء مخطط افتراضي من النوع "LineWithMarkers" على الشريحة في موقع وحجم محددين.

## الخطوة 2: الحصول على فهرس ورقة عمل بيانات المخطط الافتراضي

```csharp
// الحصول على فهرس ورقة عمل بيانات المخطط الافتراضي
int defaultWorksheetIndex = 0;
```

هنا، نحصل على فهرس ورقة عمل بيانات المخطط الافتراضي.

## الخطوة 3: الحصول على ورقة عمل بيانات المخطط

```csharp
// الحصول على ورقة عمل بيانات المخطط
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

نقوم بإحضار مصنف بيانات المخطط للعمل مع بيانات المخطط.

## الخطوة 4: تعديل سلسلة المخططات

```csharp
// حذف السلسلة التجريبية
chart.ChartData.Series.Clear();

// إضافة سلسلة جديدة
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

في هذه الخطوة، نقوم بإزالة أي سلسلة تجريبية موجودة ونضيف سلسلة جديدة تسمى "السلسلة 1" إلى المخطط.

## الخطوة 5: إعداد تعبئة الصورة لنقاط البيانات

```csharp
// تعيين الصورة للعلامات
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.ChartData.Series[0];

// إضافة نقاط بيانات جديدة مع تعبئة الصورة
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

نقوم بتعيين علامات الصورة لنقاط البيانات، مما يسمح لك بتخصيص كيفية ظهور كل نقطة بيانات على المخطط.

## الخطوة 6: تغيير حجم علامة سلسلة المخطط

```csharp
// تغيير حجم علامة سلسلة الرسم البياني
series.Marker.Size = 15;
```

هنا، نقوم بضبط حجم علامة سلسلة المخططات لجعلها جذابة بصريًا.

## الخطوة 7: حفظ العرض التقديمي

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

وأخيرًا، نقوم بحفظ العرض التقديمي بإعدادات الرسم البياني الجديدة.

## خاتمة

يمكّنك Aspose.Slides for .NET من إنشاء عروض تقديمية مذهلة للمخططات مع خيارات التخصيص المتنوعة. في هذا البرنامج التعليمي، ركزنا على استخدام خيارات علامات المخطط على نقاط البيانات لتحسين التمثيل المرئي لبياناتك. باستخدام Aspose.Slides for .NET، يمكنك الارتقاء بعروضك التقديمية إلى المستوى التالي، مما يجعلها أكثر جاذبية وغنية بالمعلومات.

إذا كانت لديك أية أسئلة أو كنت بحاجة إلى مساعدة فيما يتعلق بـ Aspose.Slides for .NET، فلا تتردد في زيارة[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/) أو الوصول إلى[مجتمع أسوس](https://forum.aspose.com/) للدعم.

## الأسئلة المتداولة (الأسئلة الشائعة)

### هل يمكنني استخدام صور مخصصة كعلامات لنقاط البيانات في Aspose.Slides لـ .NET؟
نعم، يمكنك استخدام صور مخصصة كعلامات لنقاط البيانات في Aspose.Slides لـ .NET، كما هو موضح في هذا البرنامج التعليمي.

### كيف يمكنني تغيير نوع المخطط في Aspose.Slides لـ .NET؟
 يمكنك تغيير نوع المخطط عن طريق تحديد نوع مختلف`ChartType` عند إنشاء المخطط، مثل "شريط" أو "دائري" أو "منطقة".

### هل يتوافق Aspose.Slides for .NET مع أحدث إصدارات PowerPoint؟
تم تصميم Aspose.Slides for .NET للعمل مع تنسيقات PowerPoint المختلفة ويتم تحديثه بانتظام للحفاظ على التوافق مع أحدث إصدارات PowerPoint.

### أين يمكنني العثور على المزيد من البرامج التعليمية والموارد الخاصة بـ Aspose.Slides لـ .NET؟
 يمكنك استكشاف البرامج التعليمية والموارد الإضافية في[Aspose.Slides الوثائق](https://reference.aspose.com/slides/net/).

### هل تتوفر نسخة تجريبية من Aspose.Slides لـ .NET؟
 نعم، يمكنك تجربة Aspose.Slides for .NET عن طريق تنزيل نسخة تجريبية مجانية من[هنا](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

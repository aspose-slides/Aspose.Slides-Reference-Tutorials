---
"description": "تعرّف على كيفية تحسين مخططات PowerPoint باستخدام Aspose.Slides لـ .NET. خصّص علامات نقاط البيانات بالصور، وأنشئ عروضًا تقديمية جذابة."
"linktitle": "خيارات علامة الرسم البياني على نقطة البيانات"
"second_title": "واجهة برمجة تطبيقات معالجة PowerPoint لـ Aspose.Slides .NET"
"title": "استخدام خيارات علامة الرسم البياني على نقطة البيانات في Aspose.Slides .NET"
"url": "/ar/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# استخدام خيارات علامة الرسم البياني على نقطة البيانات في Aspose.Slides .NET


عند العمل مع العروض التقديمية وتصور البيانات، يوفر Aspose.Slides for .NET مجموعة واسعة من الميزات الفعّالة لإنشاء المخططات وتخصيصها ومعالجتها. في هذا البرنامج التعليمي، سنستكشف كيفية استخدام خيارات تحديد المخططات على نقاط البيانات لتحسين عروضك التقديمية. سيرشدك هذا الدليل خطوة بخطوة خلال العملية، بدءًا من المتطلبات الأساسية واستيراد مساحات الأسماء، وصولًا إلى تقسيم كل مثال إلى خطوات متعددة.

## المتطلبات الأساسية

قبل أن نتعمق في استخدام خيارات علامة الرسم البياني على نقاط البيانات، تأكد من توفر المتطلبات الأساسية التالية:

- Aspose.Slides لـ .NET: تأكد من تثبيت Aspose.Slides لـ .NET. يمكنك تنزيله من [موقع إلكتروني](https://releases.aspose.com/slides/net/).

- نموذج عرض تقديمي: في هذا البرنامج التعليمي، سنستخدم نموذج عرض تقديمي باسم "Test.pptx". يجب أن يكون هذا العرض التقديمي موجودًا في مجلد المستندات لديك.

الآن، دعونا نبدأ باستيراد مساحات الأسماء الضرورية.

## استيراد مساحات الأسماء

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

لقد استوردنا مساحات الأسماء المطلوبة وقمنا بتهيئة عرضنا التقديمي. الآن، لننتقل إلى استخدام خيارات علامات الرسم البياني على نقاط البيانات.

## الخطوة 1: إنشاء الرسم البياني الافتراضي

```csharp

// المسار إلى دليل المستندات.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// إنشاء الرسم البياني الافتراضي
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

نقوم بإنشاء مخطط افتراضي من نوع "LineWithMarkers" على الشريحة في موقع وحجم محددين.

## الخطوة 2: الحصول على فهرس ورقة عمل بيانات الرسم البياني الافتراضية

```csharp
// الحصول على فهرس ورقة عمل بيانات الرسم البياني الافتراضية
int defaultWorksheetIndex = 0;
```

هنا، نحصل على فهرس ورقة عمل بيانات الرسم البياني الافتراضية.

## الخطوة 3: الحصول على ورقة عمل بيانات الرسم البياني

```csharp
// الحصول على ورقة عمل بيانات الرسم البياني
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

نقوم بإحضار مصنف بيانات الرسم البياني للعمل مع بيانات الرسم البياني.

## الخطوة 4: تعديل سلسلة الرسم البياني

```csharp
// حذف سلسلة العروض التوضيحية
chart.ChartData.Series.Clear();

// إضافة سلسلة جديدة
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

في هذه الخطوة، نقوم بإزالة أي سلسلة تجريبية موجودة ونضيف سلسلة جديدة تسمى "السلسلة 1" إلى الرسم البياني.

## الخطوة 5: إعداد تعبئة الصورة لنقاط البيانات

```csharp
// تعيين الصورة للعلامات
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// خذ سلسلة الرسم البياني الأولى
IChartSeries series = chart.ChartData.Series[0];

// إضافة نقاط بيانات جديدة باستخدام تعبئة الصورة
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

لقد قمنا بتعيين علامات الصور لنقاط البيانات، مما يسمح لك بتخصيص كيفية ظهور كل نقطة بيانات على الرسم البياني.

## الخطوة 6: تغيير حجم علامة سلسلة الرسم البياني

```csharp
// تغيير حجم علامة سلسلة الرسم البياني
series.Marker.Size = 15;
```

هنا، نقوم بتعديل حجم علامة سلسلة الرسم البياني لجعلها جذابة بصريًا.

## الخطوة 7: حفظ العرض التقديمي

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

وأخيرًا، نحفظ العرض التقديمي بإعدادات الرسم البياني الجديدة.

## خاتمة

يُمكّنك Aspose.Slides for .NET من إنشاء عروض تقديمية بيانية مذهلة مع خيارات تخصيص متنوعة. في هذا البرنامج التعليمي، ركزنا على استخدام خيارات علامات البيانات على نقاط البيانات لتحسين العرض المرئي لبياناتك. مع Aspose.Slides for .NET، يمكنك الارتقاء بعروضك التقديمية إلى مستوى أعلى، مما يجعلها أكثر جاذبية وإثراءً بالمعلومات.

إذا كانت لديك أي أسئلة أو تحتاج إلى مساعدة بشأن Aspose.Slides لـ .NET، فلا تتردد في زيارة [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/) أو تواصل مع [مجتمع Aspose](https://forum.aspose.com/) للحصول على الدعم.

## الأسئلة الشائعة

### هل يمكنني استخدام صور مخصصة كعلامات لنقاط البيانات في Aspose.Slides لـ .NET؟
نعم، يمكنك استخدام الصور المخصصة كعلامات لنقاط البيانات في Aspose.Slides لـ .NET، كما هو موضح في هذا البرنامج التعليمي.

### كيف يمكنني تغيير نوع الرسم البياني في Aspose.Slides لـ .NET؟
يمكنك تغيير نوع الرسم البياني عن طريق تحديد نوع مختلف `ChartType` عند إنشاء الرسم البياني، مثل "الشريط" أو "الدائري" أو "المساحة".

### هل Aspose.Slides for .NET متوافق مع أحدث إصدارات PowerPoint؟
تم تصميم Aspose.Slides for .NET للعمل مع تنسيقات PowerPoint المختلفة ويتم تحديثه بانتظام للحفاظ على التوافق مع أحدث إصدارات PowerPoint.

### أين يمكنني العثور على المزيد من البرامج التعليمية والموارد الخاصة بـ Aspose.Slides لـ .NET؟
يمكنك استكشاف الدروس والموارد الإضافية في [توثيق Aspose.Slides](https://reference.aspose.com/slides/net/).

### هل هناك نسخة تجريبية من Aspose.Slides لـ .NET متاحة؟
نعم، يمكنك تجربة Aspose.Slides لـ .NET عن طريق تنزيل نسخة تجريبية مجانية من [هنا](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
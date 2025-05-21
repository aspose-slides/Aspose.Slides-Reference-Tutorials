---
"date": "2025-04-15"
"description": "تعلّم كيفية تحسين عروضك التقديمية باستخدام مخططات التشتت باستخدام Aspose.Slides لـ .NET. اتبع هذا الدليل الشامل لإنشاء مخططات وتخصيصها بفعالية."
"title": "إضافة مخططات التشتت إلى العروض التقديمية باستخدام Aspose.Slides .NET - دليل خطوة بخطوة"
"url": "/ar/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إضافة مخططات التشتت إلى العروض التقديمية باستخدام Aspose.Slides .NET: دليل خطوة بخطوة

## مقدمة
هل ترغب في تحسين عروضك التقديمية من خلال دمج مخططات التشتت بسهولة؟ بفضل قوة Aspose.Slides لـ .NET، أصبح إنشاء المخططات وتخصيصها غاية في السهولة. سيرشدك هذا البرنامج التعليمي إلى كيفية إضافة مخططات التشتت إلى شرائحك باستخدام Aspose.Slides لـ .NET. بإتقان هذه التقنيات، ستتمكن من عرض البيانات بفعالية أكبر وإنشاء عروض تقديمية جذابة بصريًا.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides لـ .NET في مشروعك
- إنشاء عرض تقديمي جديد والوصول إلى الشريحة الأولى منه
- إضافة مخططات التشتت ذات الخطوط الناعمة إلى الشرائح
- مسح السلاسل الموجودة وإضافة سلاسل جديدة إلى المخططات البيانية
- تعديل نقاط البيانات وأنماط العلامات لتحسين التصور
- حفظ العرض التقديمي في دليل محدد

دعونا نبدأ بمراجعة المتطلبات الأساسية.

## المتطلبات الأساسية
قبل تنفيذ Aspose.Slides لـ .NET، تأكد من توفر ما يلي:
- **مكتبة Aspose.Slides لـ .NET**:الإصدار 23.7 أو أحدث.
- **بيئة التطوير**:Visual Studio 2019 أو أحدث مع .NET Framework 4.6.1+ أو .NET Core/5+.
- **المعرفة الأساسية بلغة C#**:الإلمام بالبرمجة الكائنية التوجه في C#.

## إعداد Aspose.Slides لـ .NET
لبدء استخدام Aspose.Slides، عليك تثبيت المكتبة في مشروعك. إليك الطريقة:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**استخدام وحدة تحكم إدارة الحزم:**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:**
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
يمكنك البدء بفترة تجريبية مجانية أو التقدم بطلب للحصول على ترخيص مؤقت لاستكشاف جميع الميزات. للشراء، اتبع الخطوات التالية:
1. يزور [شراء Aspose.Slides](https://purchase.aspose.com/buy) لشراء ترخيص كامل.
2. للحصول على ترخيص مؤقت، قم بزيارة [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).

بمجرد حصولك على ملف الترخيص، قم بإضافته إلى مشروعك باستخدام:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## دليل التنفيذ
سنقوم بتقسيم التنفيذ إلى أقسام منطقية استنادًا إلى الميزات.

### إنشاء عرض تقديمي وإضافة شريحة
يوضح هذا القسم كيفية إنشاء عرض تقديمي والوصول إلى الشريحة الأولى منه.

#### ملخص
ابدأ بإنشاء مثيل لـ `Presentation` الفئة التي تُمثل ملف PowerPoint الخاص بك. الوصول إلى الشرائح سهل باستخدام نموذج الكائن هذا.

#### خطوات التنفيذ
**الخطوة 1: تهيئة العرض التقديمي**
```csharp
using Aspose.Slides;

// إنشاء عرض تقديمي جديد
t Presentation pres = new Presentation();
```
يقوم هذا الكود بتهيئة مستند عرض تقديمي جديد.

**الخطوة 2: الوصول إلى الشريحة الأولى**
```csharp
// الوصول إلى الشريحة الأولى في العرض التقديمي
ISlide slide = pres.Slides[0];
```
هنا، `pres.Slides[0]` الوصول إلى الشريحة الأولى. 

### إضافة مخطط التشتت إلى الشريحة
الآن دعنا نضيف مخططًا تشتتًا إلى العرض التقديمي الخاص بك.

#### ملخص
تُساعدك إضافة المخططات البيانية على تمثيل البيانات بصريًا في العروض التقديمية. يُسهّل Aspose.Slides دمج أنواع مختلفة من المخططات البيانية، بما في ذلك مخططات التشتت.

#### خطوات التنفيذ
**الخطوة 1: إنشاء وإضافة مخطط التشتت**
```csharp
using Aspose.Slides.Charts;

// إنشاء وإضافة مخطط تشتت افتراضي بخطوط ناعمة
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
تضيف هذه القطعة الصغيرة مخططًا تشتتًا في الموضع والحجم المحددين.

### مسح وإضافة سلسلة إلى بيانات الرسم البياني
#### ملخص
قد تحتاج إلى تخصيص مخططك البياني بمسح السلاسل الحالية وإضافة سلاسل جديدة. يغطي هذا القسم هذه الوظيفة.

#### خطوات التنفيذ
**الخطوة 1: الوصول إلى مصنف بيانات الرسم البياني**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// مسح أي سلسلة موجودة مسبقًا
chart.ChartData.Series.Clear();
```
يقوم هذا الكود بمسح البيانات الموجودة للبدء من جديد بسلسلة جديدة.

**الخطوة 2: إضافة سلسلة جديدة**
```csharp
// أضف سلسلة جديدة باسم "السلسلة 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// أضف سلسلة أخرى باسم "السلسلة 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
تضيف هذه الخطوات سلسلتين جديدتين إلى الرسم البياني.

### تعديل نقاط بيانات السلسلة الأولى ونمط العلامة
#### ملخص
قم بتخصيص نقاط البيانات وأنماط العلامات لتحسين تصور مخططات التشتت الخاصة بك.

#### خطوات التنفيذ
**الخطوة 1: الوصول إلى نقاط البيانات وإضافتها**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// أضف نقاط البيانات (1، 3) و(2، 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**الخطوة 2: تعديل نمط العلامة**
```csharp
// تغيير نوع السلسلة وتعديل نمط العلامة
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### تعديل نقاط بيانات السلسلة الثانية ونمط العلامة
#### ملخص
وبنفس الطريقة، قم بتخصيص السلسلة الثانية لتناسب احتياجات العرض التقديمي الخاص بك.

#### خطوات التنفيذ
**الخطوة 1: الوصول إلى نقاط بيانات متعددة وإضافتها**
```csharp
// الوصول إلى سلسلة المخططات الثانية
series = chart.ChartData.Series[1];

// إضافة نقاط بيانات متعددة
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**الخطوة 2: تعديل نمط العلامة**
```csharp
// تغيير حجم العلامة والرمز للسلسلة الثانية
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك في الدليل المحدد.

#### خطوات التنفيذ
**الخطوة 1: تعريف الدليل**
تأكد من وجود دليل الإخراج. إذا لم يكن موجودًا، فأنشئه:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// حفظ العرض التقديمي
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
يحفظ هذا الكود ملف العرض التقديمي الخاص بك في موقع محدد.

## خاتمة
لقد نجحت الآن في إضافة مخططات التشتت إلى عروضك التقديمية باستخدام Aspose.Slides لـ .NET. واصل استكشاف الميزات والتخصيصات الإضافية المتاحة في المكتبة لتحسين مهاراتك في تصور البيانات.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
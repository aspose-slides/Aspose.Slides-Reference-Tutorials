---
"date": "2025-04-15"
"description": "تعرّف على كيفية إنشاء مخططات خطية مع علامات باستخدام Aspose.Slides لـ .NET. يغطي هذا الدليل خطوة بخطوة إعداد المخططات وإنشائها وتخصيصها."
"title": "كيفية إنشاء مخطط خطي مع علامات في C# باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء مخطط خطي مع علامات في C# باستخدام Aspose.Slides لـ .NET

## مقدمة
يعد إنشاء مخططات خطية جذابة بصريًا وغنية بالمعلومات أمرًا ضروريًا لتقديم البيانات بشكل فعال في C#. **Aspose.Slides لـ .NET** يُبسّط عملية إضافة مخططات بيانية احترافية، بما في ذلك المخططات ذات العلامات. سيرشدك هذا البرنامج التعليمي إلى كيفية إنشاء مخطط خطي بعلامات افتراضية باستخدام Aspose.Slides لـ .NET.

في هذا البرنامج التعليمي، سوف تتعلم:
- إعداد البيئة الخاصة بك لاستخدام Aspose.Slides لـ .NET.
- إنشاء عرض تقديمي وتخصيصه باستخدام مخطط خطي يتضمن علامات.
- تكوين خصائص الرسم البياني مثل الفئات والسلاسل ونقاط البيانات.
- حفظ ملف العرض التقديمي النهائي.

دعونا نبدأ بمراجعة المتطلبات الأساسية اللازمة قبل تنفيذ حلنا.

## المتطلبات الأساسية
قبل أن تبدأ، تأكد من أن لديك ما يلي:
- **المكتبات المطلوبة:** تم تثبيت Aspose.Slides لـ .NET في بيئة التطوير الخاصة بك عبر NuGet.
- **متطلبات إعداد البيئة:** بيئة تطوير C# عاملة مثل Visual Studio وإطار عمل .NET مثبتة على جهازك.
- **المتطلبات المعرفية:** فهم أساسي لبرمجة C# والتعرف على كيفية إنشاء العروض التقديمية برمجيًا.

## إعداد Aspose.Slides لـ .NET
### معلومات التثبيت
لبدء استخدام Aspose.Slides لـ .NET، أضفه إلى مشروعك عبر إحدى الطرق التالية:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**عبر وحدة تحكم إدارة الحزم في Visual Studio:**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:**
- افتح الحل الخاص بك في Visual Studio.
- انتقل إلى "إدارة حزم NuGet للحل..."
- ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
قبل استخدام Aspose.Slides، احصل على نسخة تجريبية أو قم بشراء الترخيص:
1. **نسخة تجريبية مجانية:** يزور [صفحة التجربة المجانية لـ Aspose](https://releases.aspose.com/slides/net/) للبدء بسرعة.
2. **رخصة مؤقتة:** للحصول على وصول موسع، قم بزيارة [صفحة الترخيص المؤقت](https://purchase.aspose.com/temporary-license/).
3. **شراء:** لاستخدام Aspose.Slides في الإنتاج، قم بشراء ترخيص من [شراء Aspose](https://purchase.aspose.com/buy).

### التهيئة الأساسية
بعد إعداد مشروعك والحصول على التراخيص اللازمة، قم بتشغيل Aspose.Slides على النحو التالي:
```csharp
using Aspose.Slides;
// إنشاء مثيل لفئة العرض التقديمي
Presentation pres = new Presentation();
```
الآن بعد أن قمنا بإعداد بيئتنا، فلننتقل إلى إنشاء مخطط خطي باستخدام العلامات.

## دليل التنفيذ
### إنشاء مخطط خطي باستخدام العلامات
في هذا القسم، ستتعلم كل خطوة مطلوبة لإنشاء مخطط خطي وتكوينه باستخدام العلامات الافتراضية في العرض التقديمي الخاص بك باستخدام Aspose.Slides لـ .NET.

#### الخطوة 1: إنشاء كائن عرض تقديمي
ابدأ بإنشاء مثيل لـ `Presentation` فصل:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
هنا، نصل إلى الشريحة الأولى في العرض التقديمي الذي تم إنشاؤه حديثًا.

#### الخطوة 2: إضافة مخطط خطي مع علامات
بعد ذلك، أضف مخططًا خطيًا به علامات إلى الشريحة الخاصة بك:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
يضيف هذا الكود مخططًا جديدًا من النوع `LineWithMarkers` عند الإحداثيات `(10, 10)` مع الأبعاد `400x400`.

#### الخطوة 3: مسح السلاسل والفئات الموجودة
قبل إضافة البيانات، قم بمسح أي سلسلة أو فئات موجودة:
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
وهذا يضمن أن الرسم البياني لدينا يبدأ بصفحة نظيفة.

#### الخطوة 4: تكوين مصنف بيانات الرسم البياني
الوصول إلى `ChartDataWorkbook` لإدارة بيانات الرسم البياني الخاص بك:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
يعد هذا الكائن ضروريًا لإدارة الخلايا التي تحتوي على بيانات السلسلة والفئة.

#### الخطوة 5: إضافة السلسلة والفئات
أضف سلسلة جديدة إلى الرسم البياني وقم بملئها بنقاط البيانات:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// تحديد الفئات ونقاط البيانات المقابلة
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// أضف نقطة بيانات فارغة لإظهار كيفية التعامل مع القيم المفقودة
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
هنا، نملأ المخطط بالفئات وبيانات السلسلة المقابلة. لاحظ كيف `null` يتم التعامل مع القيمة كعرض توضيحي.

#### الخطوة 6: إضافة سلسلة أخرى
كرر العملية لإضافة سلسلة أخرى:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### الخطوة 7: تمكين وتكوين الأسطورة
تمكين أسطورة الرسم البياني لتحسين إمكانية القراءة:
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
ويضمن هذا أن تكون الأسطورة مرئية وليست متراكبة على الرسم البياني.

#### الخطوة 8: حفظ العرض التقديمي
وأخيرًا، احفظ عرضك التقديمي باستخدام الرسم البياني المضاف حديثًا:
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### نصائح استكشاف الأخطاء وإصلاحها
- **أخطاء ربط البيانات:** تأكد من أن نقاط البيانات تتوافق مع الفئات بشكل صحيح.
- **الرسم البياني لا يعرض:** تأكد من ذلك `chart.HasLegend` ويتم تعيين الخصائص الأخرى بشكل مناسب.

## التطبيقات العملية
1. **التقارير التجارية:** استخدم المخططات الخطية ذات العلامات لتتبع أداء المبيعات بمرور الوقت، وإظهار الاتجاهات في الإيرادات الشهرية.
2. **التحليل المالي:** تصور تحركات أسعار الأسهم باستخدام علامات افتراضية لتسليط الضوء على القمم والقيعان.
3. **البحث العلمي:** عرض النتائج التجريبية حيث تحتاج نقاط البيانات إلى تحديد واضح للتحليل.

## اعتبارات الأداء
- قم بالتحسين عن طريق الحد من عدد سلاسل البيانات والفئات عند التعامل مع مجموعات البيانات الكبيرة.
- استخدم تقنيات إدارة الذاكرة مثل التخلص من الكائنات بسرعة في .NET لتقليل استخدام الموارد.

## خاتمة
في هذا البرنامج التعليمي، تعلمت كيفية إنشاء مخطط خطي مع علامات باستخدام Aspose.Slides لـ .NET. باتباع هذه الخطوات، يمكنك تحسين عروضك التقديمية بمخططات تفصيلية واحترافية. فكّر في استكشاف ميزات أخرى في Aspose.Slides لإثراء عروض الشرائح الخاصة بك بشكل أكبر.

### الخطوات التالية
- قم بتجربة أنواع المخططات المختلفة المتوفرة في Aspose.Slides.
- قم بتخصيص مظهر المخططات للحصول على تأثير بصري أفضل.
- استكشف الوثائق الإضافية حول Aspose.Slides للحصول على وظائف أكثر تقدمًا.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
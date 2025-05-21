---
"date": "2025-04-15"
"description": "تعرّف على كيفية إنشاء وتخصيص المخططات البيانية باستخدام Aspose.Slides لـ .NET، بما في ذلك عرض النسب المئوية كعناوين بيانات. اتبع هذا الدليل خطوة بخطوة."
"title": "كيفية إنشاء وتخصيص المخططات البيانية باستخدام Aspose.Slides .NET وعرض النسب المئوية كعناوين"
"url": "/ar/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء المخططات البيانية وتخصيصها باستخدام Aspose.Slides .NET: عرض النسب المئوية كعناوين

## مقدمة

يُعد عرض البيانات بفعالية أمرًا بالغ الأهمية في العديد من المجالات، وتلعب المخططات البيانية دورًا حيويًا في تحويل المعلومات المعقدة إلى صور واضحة. يتطلب إنشاء مخطط بياني مثالي مهام تخصيص، مثل عرض النسب المئوية على الملصقات، وهي مهمة أصبحت أسهل مع Aspose.Slides لـ .NET. تُبسط هذه المكتبة عملية إنشاء المخططات البيانية وتعديلها في عروض PowerPoint التقديمية.

في هذا البرنامج التعليمي، ستتعلم كيفية استخدام Aspose.Slides لـ .NET لإنشاء مخطط عمودي مكدس من الصفر وتخصيصه بعرض النسب المئوية كعناوين بيانات. باتباع هذه الخطوات، ستتمكن من تحسين شرائحك بتمثيلات بيانات دقيقة وجذابة بصريًا.

**ما سوف تتعلمه:**
- تهيئة Aspose.Slides لـ .NET
- إنشاء مخطط عمودي مكدس
- حساب النسب المئوية وعرضها على تسميات البيانات
- أفضل ممارسات تحسين أداء الرسم البياني

قبل أن نتعمق في التنفيذ، دعونا نتأكد من أن كل شيء جاهز للبدء.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي بشكل فعال، تأكد من أن لديك:
- **مجموعة أدوات تطوير البرامج .NET Core** تم تثبيته على جهازك.
- فهم أساسي لتطوير تطبيقات C# و.NET.
- Visual Studio أو IDE مماثل لكتابة وتشغيل كود C#.

ستحتاج إلى Aspose.Slides لـ .NET لإنشاء المخططات البيانية، لذا تأكد من إعداده كما هو موضح أدناه.

## إعداد Aspose.Slides لـ .NET

Aspose.Slides for .NET هي مكتبة فعّالة تُمكّنك من العمل مع عروض PowerPoint التقديمية برمجيًا. إليك كيفية إضافتها إلى مشروعك:

### تثبيت

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزمة:**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:** 
- افتح مدير حزم NuGet وابحث عن "Aspose.Slides". ثبّت أحدث إصدار.

### الحصول على الترخيص

للاستفادة الكاملة من Aspose.Slides، ابدأ بفترة تجريبية مجانية. للاستخدام الممتد، فكّر في الحصول على ترخيص مؤقت أو شراء ترخيص من [أسبوزي](https://purchase.aspose.com/buy). اتبع إرشاداتهم لإعداد الترخيص الخاص بك في بيئة مشروعك.

### التهيئة الأساسية

بمجرد التثبيت، قم بتشغيل `Presentation` الصف لبدء إنشاء الشرائح:
```csharp
using Aspose.Slides;

// تهيئة مثيل فئة العرض التقديمي
tPresentation presentation = new Presentation();
```

الآن، دعنا ننتقل إلى تنفيذ ميزة إنشاء المخطط وتخصيصه باستخدام Aspose.Slides لـ .NET.

## دليل التنفيذ

### إنشاء مخطط عمودي مكدس

هدفنا هو إنشاء مخطط بياني عمودي مُكدّس وتخصيصه بعرض النسب المئوية كعناوين بيانات. إليك الطريقة:

#### تهيئة العرض التقديمي

ابدأ بإنشاء مثيل لـ `Presentation`:
```csharp
using Aspose.Slides;

// تهيئة مثيل فئة العرض التقديمي
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### إضافة مخطط إلى الشريحة

أضف مخططًا عموديًا مكدسًا إلى الشريحة الأولى عند الإحداثيات والأبعاد المحددة:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
هذا الخط ينشئ `StackedColumn` الرسم البياني في الموضع (20، 20) بعرض وارتفاع 400.

#### حساب القيم الإجمالية لحساب النسبة المئوية

لعرض النسب المئوية، احسب القيمة الإجمالية لكل فئة عبر جميع السلاسل:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // جمع قيم جميع السلاسل لكل فئة
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### تخصيص تسميات البيانات لإظهار قيم النسب المئوية

بعد ذلك، قم بالتكرار خلال كل سلسلة وقم بتخصيص تسميات البيانات:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // حساب النسبة المئوية
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // نص واضح لتجنب التداخل
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // تكوين تنسيق التسمية لإخفاء تسميات البيانات الافتراضية
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

يقوم هذا القسم بحساب النسبة المئوية لكل نقطة بيانات وتعيينها كعلامة مخصصة، مما يضمن عدم وجود تداخل مع العلامات الافتراضية.

#### حفظ العرض التقديمي

وأخيرًا، احفظ عرضك التقديمي لعرض النتيجة:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## التطبيقات العملية

قد يكون عرض النسب المئوية في المخططات مفيدًا بشكل خاص في السيناريوهات مثل:
1. **التقارير المالية:** إظهار توزيعات المحفظة أو عوائد الاستثمار كنسب مئوية.
2. **تحليل المبيعات:** تمثيل بيانات حصة السوق كنسبة مئوية لتسليط الضوء على الأداء عبر المناطق.
3. **نتائج الاستطلاع:** عرض استجابات الاستطلاع كنسب مئوية لمقارنة بصرية أفضل.
4. **إدارة المشاريع:** استخدم المخططات الدائرية مع النسب المئوية لتوضيح تخصيص الموارد.
5. **تعليم:** اشرح المفاهيم الإحصائية باستخدام صور واضحة تعتمد على النسبة المئوية.

إن دمج هذه المخططات المخصصة في أنظمة مثل CRM أو ERP يمكن أن يعزز لوحات المعلومات والتقارير، مما يساعد في عمليات اتخاذ القرار.

## اعتبارات الأداء

عند العمل مع Aspose.Slides لـ .NET، وخاصةً مع مجموعات البيانات الكبيرة:
- **إدارة الذاكرة:** تخلص من عناصر العرض التقديمي بشكل صحيح لتحرير الذاكرة. استخدم `using` البيانات حيثما ينطبق ذلك.
- **التعامل الفعال مع البيانات:** قم بإجراء العمليات الحسابية خارج الحلقات عندما يكون ذلك ممكنًا لتقليل التكلفة الحسابية.
- **موازنة التحميل:** بالنسبة لتطبيقات الويب، تأكد من توفير موارد الخادم بشكل مناسب لطلبات إنشاء المخططات المتزامنة.

## خاتمة

تناول هذا البرنامج التعليمي إنشاء وتخصيص المخططات البيانية باستخدام Aspose.Slides لـ .NET، وذلك بعرض النسب المئوية كعناوين. يتيح لك إتقان هذه التقنيات تحسين عروضك التقديمية بتمثيلات بيانات مفصلة وجذابة بصريًا.

كخطوة تالية، استكشف أنواعًا أخرى من المخططات وخيارات التخصيص المتاحة في Aspose.Slides. جرّب مجموعات بيانات مختلفة لتحويلها إلى عناصر مرئية فعّالة تُعبّر عن الأفكار بوضوح.

## قسم الأسئلة الشائعة

**س1: كيف أتعامل مع مجموعات البيانات الكبيرة عند إنشاء المخططات البيانية باستخدام Aspose.Slides لـ .NET؟**
ج١: بالنسبة لمجموعات البيانات الكبيرة، يُنصح بتحسين العمليات الحسابية واستخدام تقنيات فعّالة لإدارة الذاكرة. قسّم مهام المعالجة لتجنب زيادة تحميل الذاكرة.

**س2: هل يمكنني استخدام Aspose.Slides لـ .NET في تطبيق ويب؟**
ج٢: نعم، يُمكن دمجه في تطبيقات ASP.NET. تأكد من تخصيص موارد الخادم بشكل صحيح لتحقيق الأداء الأمثل.

**س3: هل من الممكن تصدير المخططات التي تم إنشاؤها باستخدام Aspose.Slides إلى تنسيقات أخرى؟**
ج٣: بالتأكيد! يمكنك تصدير العروض التقديمية التي تحتوي على مخططاتك المُخصصة إلى صيغ مُختلفة، مثل ملفات PDF والصور، باستخدام إمكانيات المكتبة.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
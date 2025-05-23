---
"date": "2025-04-15"
"description": "تعرف على كيفية تعيين تنسيقات التاريخ المخصصة على محاور الفئات في المخططات باستخدام Aspose.Slides لـ .NET، مما يعزز الجاذبية البصرية والدقة في عروضك التقديمية."
"title": "كيفية تخصيص تنسيقات التاريخ على محاور الفئات في المخططات البيانية باستخدام Aspose.Slides لـ .NET"
"url": "/ar/net/charts-graphs/custom-date-formats-charts-asposeslides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تخصيص تنسيقات التاريخ على محاور الفئات في المخططات البيانية باستخدام Aspose.Slides لـ .NET

## مقدمة

غالبًا ما يتطلب إنشاء عروض تقديمية جذابة بصريًا استخدام المخططات البيانية لعرض اتجاهات البيانات بفعالية. ومن التحديات الشائعة التي يواجهها المطورون تخصيص تنسيقات التاريخ على محاور المخططات البيانية لتناسب احتياجات العروض التقديمية المحددة أو المعايير الإقليمية. سيرشدك هذا البرنامج التعليمي إلى كيفية تعيين تنسيق تاريخ مخصص لمحور الفئة في المخطط البياني باستخدام Aspose.Slides لـ .NET.

### ما سوف تتعلمه:
- إعداد وتكوين البيئة الخاصة بك باستخدام Aspose.Slides لـ .NET.
- تعليمات خطوة بخطوة حول تنفيذ تنسيقات التاريخ المخصصة لفئات الرسم البياني.
- تطبيقات عملية ونصائح لتحسين الأداء.
- استكشاف الأخطاء الشائعة التي قد تواجهها وإصلاحها.

دعونا نتعمق في المتطلبات الأساسية قبل أن نبدأ!

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من تكوين بيئة التطوير الخاصة بك بشكل صحيح:

### المكتبات والإصدارات والتبعيات المطلوبة
- **Aspose.Slides لـ .NET**تأكد من تثبيت هذه المكتبة. فهي توفر ميزات شاملة لإدارة عروض PowerPoint برمجيًا.

### متطلبات إعداد البيئة
- إصدار متوافق مع .NET Framework أو .NET Core/5+/6+.
- محرر أكواد مثل Visual Studio أو VS Code.

### متطلبات المعرفة
- فهم أساسي لمفاهيم تطوير C# و.NET.
- التعرف على كيفية العمل مع المخططات البيانية في العروض التقديمية، على الرغم من أن هذا البرنامج التعليمي سوف يرشدك خلال كل خطوة.

## إعداد Aspose.Slides لـ .NET

للبدء في استخدام Aspose.Slides لـ .NET، اتبع تعليمات التثبيت التالية:

### معلومات التثبيت

**.NET CLI**

```bash
dotnet add package Aspose.Slides
```

**مدير الحزم**

```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**

ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### خطوات الحصول على الترخيص

يمكنك الحصول على نسخة تجريبية مجانية من Aspose.Slides لتقييم ميزاته. للاستخدام الممتد، يمكنك شراء ترخيص أو طلب ترخيص مؤقت عبر موقعهم الإلكتروني:

- **نسخة تجريبية مجانية**:متاح للتحميل الفوري.
- **رخصة مؤقتة**:تم الطلب عبر الموقع الرسمي لشركة Aspose لأغراض التقييم غير التجاري.
- **شراء**:تتوفر تراخيص كاملة للمشاريع التجارية.

### التهيئة والإعداد الأساسي

بعد التثبيت، ابدأ مشروعك بإضافة مساحات الأسماء اللازمة في تطبيق C#. إليك طريقة الإعداد السريعة:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## دليل التنفيذ

دعنا نتعرف على كيفية إعداد تنسيق تاريخ مخصص لمحاور الفئة.

### 1. إنشاء وتكوين الرسم البياني

#### ملخص

سنبدأ بإضافة مخطط إلى شريحة العرض التقديمي الخاصة بك وتكوينه لعرض التواريخ بالتنسيق المطلوب.

#### إضافة الرسم البياني وتكوينه

```csharp
// تحديد الدليل لتخزين المستندات
class Program
{
    static void Main()
    {
        // تحديد الدليل لتخزين المستندات
        string dataDir = @"YOUR_DOCUMENT_DIRECTORY";

        using (Presentation pres = new Presentation())
        {
            // أضف مخططًا إلى الشريحة الأولى بأبعاد محددة
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Area, 50, 50, 450, 300);
        }
    }
}
```

### 2. الوصول إلى بيانات الرسم البياني وتعديلها

#### ملخص

سنقوم بتعديل مصنف بيانات الرسم البياني لإدراج قيم التاريخ كفئات.

#### مسح الفئات والسلاسل الموجودة

```csharp
// الوصول إلى مصنف بيانات الرسم البياني للتلاعب به
class Program
{
    static void Main()
    {
        using (Presentation pres = new Presentation())
        {
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Area, 50, 50, 450, 300);
            IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

            // مسح الفئات والسلاسل الموجودة في بيانات الرسم البياني
            chart.ChartData.Categories.Clear();
            chart.ChartData.Series.Clear();
        }
    }
}
```

#### إضافة قيم التاريخ كفئات جديدة

استخدم هذا المقطع لإدراج التواريخ:

```csharp
// الوصول إلى مصنف بيانات الرسم البياني للتلاعب به
class Program
{
    static void Main()
    {
        using (Presentation pres = new Presentation())
        {
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Area, 50, 50, 450, 300);
            IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

            // إضافة قيم التاريخ كفئات جديدة إلى الرسم البياني
            chart.ChartData.Categories.Add(wb.GetCell(0, "A2", DateTime.Now.AddDays(-30)));
            chart.ChartData.Categories.Add(wb.GetCell(0, "A3", DateTime.Now));
            chart.ChartData.Categories.Add(wb.GetCell(0, "A4", DateTime.Now.AddDays(30)));

            // أضف سلسلة واملأها بالبيانات
            IChartSeries series = chart.ChartData.Series.Add(wb.GetCell(0, "B1", "Sample Series"), chart.Type);
        }
    }
}
```

### 3. تعيين تنسيق التاريخ المخصص

#### ملخص

الآن، قم بتكوين محور الفئة لعرض التواريخ بالتنسيق المفضل لديك.

#### تكوين محور الفئة

```csharp
// الوصول إلى محور الفئة وتعيين تنسيق التاريخ المخصص
class Program
{
    static void Main()
    {
        using (Presentation pres = new Presentation())
        {
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Area, 50, 50, 450, 300);
            IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

            // إضافة قيم التاريخ كفئات جديدة إلى الرسم البياني
            chart.ChartData.Categories.Add(wb.GetCell(0, "A2", DateTime.Now.AddDays(-30)));
            chart.ChartData.Categories.Add(wb.GetCell(0, "A3", DateTime.Now));
            chart.ChartData.Categories.Add(wb.GetCell(0, "A4", DateTime.Now.AddDays(30)));

            // أضف سلسلة واملأها بالبيانات
            IChartSeries series = chart.ChartData.Series.Add(wb.GetCell(0, "B1", "Sample Series"), chart.Type);

            // الوصول إلى محور الفئة وتعيين تنسيق التاريخ المخصص
            IAxis categoryAxis = chart.Axes.HorizontalAxis;
            categoryAxis.MajorUnit = 1; // تعيين الوحدة الرئيسية كأيام
            categoryAxis.NumberFormat.FormatCode = "dd-MMM"; // تنسيق مخصص: اختصار اليوم والشهر

            // حفظ العرض التقديمي مع التغييرات
            pres.Save(@"YOUR_DOCUMENT_DIRECTORY\FormattedChart.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
        }
    }
}
```

#### شرح المعلمات والطرق
- **الوحدة الرئيسية**:يحدد الفاصل الزمني للعلامات الرئيسية على المحور.
- **تنسيق الرقم.رمز التنسيق**: يُحدد كيفية عرض التواريخ. التنسيق `"dd-MMM"` يعرض اختصار اليوم والشهر.

### نصائح استكشاف الأخطاء وإصلاحها

1. تأكد من إعداد ترخيص Aspose.Slides الخاص بك بشكل صحيح لتجنب القيود في الوظائف.
2. التحقق من قيم التاريخ والتنسيقات، وخاصة عند التعامل مع إعدادات محلية أو إقليمية مختلفة.

## التطبيقات العملية

إن فهم كيفية التعامل مع بيانات الرسم البياني يمكن أن يكون مفيدًا:
- **التقارير المالية**:قم بتخصيص المخططات البيانية للتقارير الفصلية من خلال عرض فترات مالية محددة.
- **تخطيط المشروع**:استخدم مخططات جانت عندما تكون التواريخ مهمة للمعالم.
- **تحليلات التسويق**:تصور مدة الحملة والأحداث الرئيسية على جدول زمني.

استكشف التكامل مع الأنظمة الأخرى، مثل قواعد البيانات أو ملفات Excel، لأتمتة إدخال البيانات في العروض التقديمية الخاصة بك.

## اعتبارات الأداء

لتحسين الأداء عند العمل مع Aspose.Slides:
- إدارة الموارد عن طريق التخلص من الكائنات بشكل صحيح باستخدام `using` تصريحات.
- تجنب العمليات غير الضرورية داخل الحلقات لتقليل وقت المعالجة.
- استخدم هياكل بيانات فعالة للتعامل مع مجموعات البيانات الكبيرة في المخططات البيانية.

التزم بأفضل الممارسات لإدارة ذاكرة .NET، مما يضمن تشغيل تطبيقك بسلاسة دون استهلاك مفرط للموارد.

## خاتمة

لقد تعلمتَ كيفية تعيين تنسيقات تاريخ مخصصة على محاور الفئات باستخدام Aspose.Slides لـ .NET. تُحسّن هذه المهارة وضوح العرض التقديمي واحترافيته، مما يجعل البيانات أكثر سهولة في الوصول إليها وجاذبية بصريًا.

### الخطوات التالية
- تجربة أنواع مختلفة من المخططات والتكوينات.
- استكشف المزيد من خيارات التخصيص المتوفرة في Aspose.Slides.

هل أنت مستعد لتحسين عروضك التقديمية؟ ابدأ بتطبيق هذه التقنيات اليوم!

## قسم الأسئلة الشائعة

**س1: كيف يمكنني تغيير تنسيق التاريخ إذا كان العرض التقديمي الخاص بي يحتاج إلى موقع مختلف؟**
أ1: تعديل `NumberFormat.FormatCode` مع سلسلة تنسيق التاريخ المطلوبة، مثل `"MM/dd/yyyy"` للغة الإنجليزية الأمريكية.

**س2: ماذا يجب أن أفعل إذا واجهت مشكلات في الأداء أثناء العمل مع مجموعات بيانات كبيرة في المخططات البيانية؟**
ج٢: التحسين من خلال إدارة الموارد بشكل صحيح واستخدام هياكل بيانات فعّالة. تجنّب العمليات غير الضرورية داخل الحلقات.

**س3: هل يمكنني دمج Aspose.Slides for .NET مع تطبيقات أو قواعد بيانات أخرى لأتمتة إنشاء المخططات؟**
ج3: نعم، يمكنك دمجه مع أنظمة مثل قواعد بيانات Excel أو SQL لأتمتة عملية إدخال البيانات في المخططات البيانية الخاصة بك.

## توصيات الكلمات الرئيسية
- "تخصيص تنسيقات التاريخ في الرسوم البيانية"
- "Aspose.Slides لـ .NET"
- "دليل تخصيص الرسم البياني"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
---
"date": "2025-04-15"
"description": "تعرف على كيفية تعديل محاور فئات المخطط في PowerPoint باستخدام Aspose.Slides لـ .NET، مما يعزز قابلية قراءة البيانات في العرض التقديمي الخاص بك وجاذبيته البصرية."
"title": "كيفية تعديل محور فئة الرسم البياني في PowerPoint باستخدام Aspose.Slides .NET"
"url": "/ar/net/charts-graphs/modify-chart-category-axis-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية تعديل محور فئة الرسم البياني في PowerPoint باستخدام Aspose.Slides .NET

## مقدمة

عزّز التأثير البصري للمخططات في عروض PowerPoint التقديمية من خلال تعديل محاور فئات المخططات. يتناول هذا الدليل كيفية تعديل نوع محور فئة المخطط باستخدام Aspose.Slides لـ .NET، مما يُحسّن قابلية قراءة البيانات وجودة العرض، خاصةً مع بيانات السلاسل الزمنية.

في عالمنا اليوم الذي يعتمد على البيانات، يُعدّ تحويل الأشكال الخام إلى رسومات بديهية أمرًا بالغ الأهمية. باستخدام Aspose.Slides لـ .NET، يُمكن للمطورين معالجة مخططات PowerPoint بفعالية لضمان تواصل واضح في عروضهم التقديمية.

**ما سوف تتعلمه:**
- تعديل نوع محور فئة الرسم البياني باستخدام Aspose.Slides لـ .NET.
- قم بتكوين إعدادات الوحدة الرئيسية على المحور الأفقي للحصول على تمثيل أفضل للبيانات.
- احفظ تغييراتك بسهولة في ملف PowerPoint جديد.

## المتطلبات الأساسية

### المكتبات والإصدارات والتبعيات المطلوبة
لتنفيذ هذه الميزة، تأكد من أن لديك:
- **Aspose.Slides لـ .NET**:المكتبة الأساسية للتعامل مع عروض PowerPoint التقديمية.
- **.NET Framework أو .NET Core/5+/6+** تم تثبيته على جهازك (تحقق من التوافق مع وثائق Aspose).

### متطلبات إعداد البيئة
تأكد من أن بيئة التطوير الخاصة بك تدعم تطبيقات .NET، باستخدام Visual Studio أو بيئة التطوير المتكاملة المكافئة.

### متطلبات المعرفة
يُفضّل فهم أساسيات لغة C# والإلمام بعروض PowerPoint. تُعدّ الخبرة السابقة في استخدام Aspose.Slides لـ .NET مفيدة، ولكنها ليست ضرورية.

## إعداد Aspose.Slides لـ .NET

قم بتثبيت Aspose.Slides في بيئة مشروعك للبدء.

**خيارات التثبيت:**

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
ابحث عن "Aspose.Slides" وانقر على "تثبيت" للحصول على الإصدار الأحدث.

### الحصول على الترخيص
- **نسخة تجريبية مجانية**:قم بتنزيل نسخة تجريبية مجانية من [صفحة إصدارات Aspose](https://releases.aspose.com/slides/net/).
- **رخصة مؤقتة**:الحصول على ترخيص مؤقت للوصول الموسع دون قيود في [صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).
- **شراء**:فكر في شراء ترخيص مباشرة من [صفحة شراء Aspose](https://purchase.aspose.com/buy) للاستخدام طويل الأمد.

**التهيئة الأساسية:**
```csharp
// إنشاء مثيل لفئة العرض التقديمي باستخدام (العرض التقديمي = العرض التقديمي الجديد())
{
    // العمليات باستخدام Aspose.Slides
}
```

## دليل التنفيذ

### تغيير محور فئة الرسم البياني إلى التاريخ
تتيح لك هذه الميزة تعديل نوع محور الفئة في الرسم البياني الخاص بك، وهي مثالية لبيانات السلاسل الزمنية.

#### ملخص
سنُغيّر محور الفئة في مخطط موجود في عرض تقديمي على PowerPoint إلى تنسيق التاريخ، ونُهيئ إعدادات وحدته الرئيسية. سيُضفي هذا التعديل وضوحًا وسلاسةً على المخططات الزمنية.

#### خطوات:

**الخطوة 1: تحميل العرض التقديمي الخاص بك**
قم بتحميل عرض تقديمي موجود يحتوي على الرسم البياني الذي ترغب في تعديله.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation presentation = new Presentation(dataDir + "/ExistingChart.pptx"))
{
    // الوصول إلى الشكل الأول في الشريحة الأولى وإرساله إلى IChart
    IChart chart = presentation.Slides[0].Shapes[0] as IChart;
```

**الخطوة 2: تعديل نوع محور الفئة**
تغيير نوع محور الفئة إلى `Date`، مثالي لمجموعات البيانات ذات البيانات الزمنية.
```csharp
    // تغيير نوع محور الفئة إلى التاريخ
    chart.Axes.HorizontalAxis.CategoryAxisType = CategoryAxisType.Date;
```

**الخطوة 3: تكوين إعدادات الوحدة الرئيسية**
قم بتعيين عناصر التحكم اليدوية على فترات خطوط الشبكة الرئيسية، مما يعزز الوضوح والدقة في العرض التقديمي الخاص بك.
```csharp
    // تكوين إعدادات الوحدة الرئيسية على المحور الأفقي
    chart.Axes.HorizontalAxis.IsAutomaticMajorUnit = false; 
    chart.Axes.HorizontalAxis.MajorUnit = 1;
    chart.Axes.HorizontalAxis.MajorUnitScale = TimeUnitType.Months;
```

**الخطوة 4: حفظ التغييرات**
وأخيرًا، احفظ العرض التقديمي الخاص بك مع الرسم البياني المعدل في ملف جديد.
```csharp
    // حفظ العرض التقديمي المحدث
    presentation.Save(dataDir + "/ChangeChartCategoryAxis_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
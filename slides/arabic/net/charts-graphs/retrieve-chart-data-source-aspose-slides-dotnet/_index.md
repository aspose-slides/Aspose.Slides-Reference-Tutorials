---
"date": "2025-04-15"
"description": "تعرّف على كيفية استرجاع أنواع مصادر بيانات المخططات بكفاءة في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. أتمتة العروض التقديمية ودمجها بسهولة."
"title": "كيفية استرداد نوع مصدر بيانات الرسم البياني باستخدام Aspose.Slides لـ .NET - المخططات والرسوم البيانية"
"url": "/ar/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية استرداد نوع مصدر بيانات الرسم البياني باستخدام Aspose.Slides لـ .NET

## مقدمة

هل تواجه صعوبة في إدارة مصادر البيانات داخل مخططات عروض PowerPoint التقديمية برمجيًا؟ يواجه العديد من المطورين تحديات عند محاولة استخراج بيانات المخططات ومعالجتها في ملفات Microsoft Office باستخدام C#. في هذا البرنامج التعليمي، سنرشدك خلال عملية استرداد نوع مصدر بيانات مخطط في عرض تقديمي على PowerPoint باستخدام Aspose.Slides لـ .NET. يُعد هذا الحل مثاليًا إذا كنت بحاجة إلى أتمتة العروض التقديمية أو دمجها في تطبيقاتك.

**ما سوف تتعلمه:**
- إعداد Aspose.Slides واستخدامه لـ .NET
- استرجاع نوع مصدر البيانات للمخططات في شرائح PowerPoint
- التعامل مع مسارات المصنفات الخارجية عند الاقتضاء
- حفظ التغييرات مرة أخرى في العرض التقديمي

قبل أن نبدأ، دعونا نغطي بعض المتطلبات الأساسية.

## المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي بشكل فعال، ستحتاج إلى:
1. **مكتبة Aspose.Slides لـ .NET:** تأكد من تثبيت الإصدار الأحدث.
2. **بيئة التطوير:** إعداد عمل لبرنامج Visual Studio أو أي بيئة تطوير متكاملة مفضلة تدعم تطوير C#.
3. **المعرفة الأساسية:** المعرفة بلغة C# ومفاهيم البرمجة الموجهة للكائنات ومعالجة مسارات الملفات في .NET.

## إعداد Aspose.Slides لـ .NET

أولاً، عليك تثبيت مكتبة Aspose.Slides. إليك الطريقة:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**استخدام مدير الحزم:**
```powershell
Install-Package Aspose.Slides
```

**عبر واجهة مستخدم NuGet Package Manager:**
ابحث عن "Aspose.Slides" في مدير الحزم NuGet وقم بتثبيته.

### الحصول على الترخيص
- **نسخة تجريبية مجانية:** ابدأ بإصدار تجريبي مجاني لاستكشاف الوظائف.
- **رخصة مؤقتة:** احصل على ترخيص مؤقت للوصول الموسع دون قيود.
- **شراء:** فكر في الشراء إذا وجدت أن Aspose.Slides يلبي احتياجاتك.

بمجرد التثبيت، قم بتهيئة مشروعك عن طريق تضمين المساحات الأساسية الضرورية:
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## دليل التنفيذ

سنُقسّم هذه الميزة إلى خطوات للتوضيح. لنستكشف كيفية استرجاع نوع مصدر بيانات الرسم البياني.

### الخطوة 1: تحميل العرض التقديمي الخاص بك

أولاً، قم بتحميل عرض PowerPoint الذي يحتوي على المخططات البيانية الخاصة بك:
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // تعيين إلى مسار الدليل الخاص بك

using (Presentation pres = new Presentation(dataDir + "/pres.pptx"))
{
    // متابعة بالخطوات التالية...
}
```

### الخطوة 2: الوصول إلى الشريحة والمخطط الخاص بها

قم بالوصول إلى الشريحة الأولى والمخطط الموجود بداخلها:
```csharp
// احصل على الشريحة الأولى من العرض التقديمي
ISlide slide = pres.Slides[0];

// تأكد من أن الشكل هو في الواقع مخطط
IChart chart = (IChart)slide.Shapes[0];
```

### الخطوة 3: استرداد نوع مصدر البيانات

الآن، دعنا نسترد نوع مصدر البيانات:
```csharp
// احصل على نوع مصدر البيانات للرسم البياني
ChartDataSourceType sourceType = chart.ChartData.DataSourceType;
```

### الخطوة 4: التعامل مع مسارات المصنف الخارجية

إذا كان الرسم البياني الخاص بك يستخدم مصنفًا خارجيًا، فيمكنك جلب مساره على النحو التالي:
```csharp
if (sourceType == ChartDataSourceType.ExternalWorkbook)
{
    string path = chart.ChartData.ExternalWorkbookPath;
}
```

### الخطوة 5: احفظ العرض التقديمي الخاص بك

وأخيرًا، احفظ العرض التقديمي بعد إجراء أي تعديلات:
```csharp
pres.Save(dataDir + "/Result.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
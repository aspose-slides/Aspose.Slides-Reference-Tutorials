---
"date": "2025-04-16"
"description": "تعرف على كيفية إضافة المحتوى والنص العمودي والمخططات وعناصر الجدول بكفاءة إلى شرائح PowerPoint الخاصة بك باستخدام Aspose.Slides لـ .NET."
"title": "كيفية إضافة عناصر نائبة في .NET Slides باستخدام Aspose.Slides"
"url": "/ar/net/shapes-text-frames/add-placeholders-in-dotnet-slides-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إضافة عناصر نائبة في .NET Slides باستخدام Aspose.Slides

## مقدمة

هل تبحث عن طريقة فعّالة لأتمتة إضافة عناصر نائبة، مثل المحتوى والنصوص العمودية والرسوم البيانية والجداول، إلى عروضك التقديمية؟ مع Aspose.Slides لـ .NET، تصبح هذه العملية سلسة للغاية. يرشدك هذا البرنامج التعليمي إلى كيفية استخدام Aspose.Slides لتبسيط إضافة العناصر النائبة في شرائح PowerPoint ضمن بيئة .NET.

في هذا الدليل الشامل، سنستكشف:
- إعداد Aspose.Slides لـ .NET
- تعليمات خطوة بخطوة لإضافة عناصر نائبة مختلفة
- التطبيقات الواقعية لهذه الميزات
- اعتبارات الأداء للاستخدام الأمثل

## المتطلبات الأساسية

### المكتبات والإصدارات المطلوبة
لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- Aspose.Slides لمكتبة .NET الإصدار 22.x أو الأحدث.
- بيئة .NET متوافقة (على سبيل المثال، .NET Core 3.1 أو أحدث).

### متطلبات إعداد البيئة
تأكد من إعداد بيئة التطوير لديك باستخدام Visual Studio أو أي بيئة تطوير متكاملة أخرى تدعم مشاريع .NET.

### متطلبات المعرفة
ستكون المعرفة الأساسية بلغة C# والتعرف على مفاهيم برمجة .NET مفيدة ولكنها ليست ضرورية، حيث سنغطي جميع الأساسيات على طول الطريق.

## إعداد Aspose.Slides لـ .NET
لبدء استخدام Aspose.Slides في مشروعك، عليك تثبيته. إليك الطريقة:

**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**استخدام وحدة تحكم إدارة الحزم:**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:**
ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
لتجربة Aspose.Slides، يمكنك اختيار تجربة مجانية أو الحصول على ترخيص مؤقت. للاستخدام الإنتاجي، فكّر في شراء ترخيص كامل. تفضل بزيارة [صفحة شراء Aspose](https://purchase.aspose.com/buy) لمعرفة المزيد عن خيارات الترخيص.

#### التهيئة الأساسية
قم بتهيئة مشروعك عن طريق إنشاء مثيل لـ `Presentation` فصل:
```csharp
using Aspose.Slides;
// ...
var presentation = new Presentation();
```

## دليل التنفيذ

### إضافة عنصر نائب للمحتوى
إضافة عنصر نائب للمحتوى يتيح لك إدراج نصوص وصور ووسائط أخرى في الشرائح. إليك كيفية القيام بذلك باستخدام Aspose.Slides لـ .NET.

#### ملخص
سوف يرشدك هذا القسم خلال عملية إضافة عنصر نائب للمحتوى إلى تخطيط شريحة فارغة باستخدام Aspose.Slides لـ .NET.

#### خطوات التنفيذ
**1. قم بإعداد مشروعك**
ابدأ بإنشاء مشروع C# جديد وتثبيت مكتبة Aspose.Slides كما ذكرنا سابقًا.

**2. تهيئة العرض التقديمي**
إنشاء مثيل لـ `Presentation` للعمل مع الشرائح:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "content_placeholder.pptx");

using (var pres = new Presentation())
{
    // سيتم إضافة الكود هنا.
}
```
**3. شريحة تخطيط الوصول**
استرجع شريحة التخطيط الفارغة حيث ستضيف العنصر النائب الخاص بك:
```csharp
// الحصول على شريحة تخطيط فارغة.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
تتيح لك هذه الخطوة الوصول إلى تخطيط فارغ محدد مسبقًا، وهو مثالي للتصميمات المخصصة.

**4. إضافة عنصر نائب للمحتوى**
استخدم `PlaceholderManager` لإدراج عنصر نائب للمحتوى في إحداثيات وحجم محددين:
```csharp
// الحصول على مدير العنصر النائب لشريحة التخطيط.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// إضافة عنصر نائب للمحتوى في الموضع (10، 10) بحجم (300 × 200).
placeholderManager.AddContentPlaceholder(10, 10, 300, 200);
```
المعلمات تحدد الموضع `(x, y)` والأبعاد `(width x height)` من العنصر النائب.

**5. حفظ العرض التقديمي**
وأخيرًا، احفظ ملف العرض التقديمي الخاص بك:
```csharp
// حفظ العرض التقديمي مع إضافة عنصر نائب للمحتوى.
pres.Save(outFilePath, SaveFormat.Pptx);
```
يؤدي هذا إلى حفظ التخطيط المعدل في دليل محدد.

### إضافة عنصر نائب للنص العمودي
تعتبر عناصر النص الرأسية مثالية للأشرطة الجانبية أو عناصر التصميم الفريدة التي تتطلب تغييرات في اتجاه النص.

#### ملخص
في هذا القسم، ستتعلم كيفية إضافة عنصر نائب للنص الرأسي لتعزيز المظهر الجمالي لشريحتك.

#### خطوات التنفيذ
**1. تهيئة العرض التقديمي**
إنشاء مثيل جديد من `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "vertical_text_placeholder.pptx");

using (var pres = new Presentation())
{
    // سيتم إضافة الكود هنا.
}
```
**2. شريحة تخطيط الوصول**
استرجاع شريحة التخطيط الفارغة:
```csharp
// الحصول على شريحة تخطيط فارغة.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. إضافة عنصر نائب للنص العمودي**
أضف عنصر نائب للنص العمودي باستخدام `PlaceholderManager`:
```csharp
// الحصول على مدير العنصر النائب لشريحة التخطيط.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// إضافة نص عمودي في الموضع (350، 10) بحجم (200 × 300).
placeholderManager.AddVerticalTextPlaceholder(350, 10, 200, 300);
```
**4. حفظ العرض التقديمي**
احفظ العرض التقديمي الخاص بك:
```csharp
// حفظ العرض التقديمي مع إضافة نص عمودي.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### إضافة عنصر نائب للرسم البياني
تُعدّ المخططات البيانية أساسيةً لعرض البيانات في العروض التقديمية. إليك كيفية إضافة عنصر نائب للمخطط البياني باستخدام Aspose.Slides.

#### ملخص
سيساعدك هذا القسم على دمج عنصر نائب للرسم البياني في شرائح PowerPoint الخاصة بك باستخدام Aspose.Slides.

#### خطوات التنفيذ
**1. تهيئة العرض التقديمي**
إنشاء مثيل لـ `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "chart_placeholder.pptx");

using (var pres = new Presentation())
{
    // سيتم إضافة الكود هنا.
}
```
**2. شريحة تخطيط الوصول**
استرجاع شريحة التخطيط الفارغة:
```csharp
// الحصول على شريحة تخطيط فارغة.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. إضافة عنصر نائب للرسم البياني**
يستخدم `PlaceholderManager` لإضافة عنصر نائب للرسم البياني:
```csharp
// الحصول على مدير العنصر النائب لشريحة التخطيط.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// إضافة عنصر نائب للرسم البياني في الموضع (10، 350) بحجم (300 × 300).
placeholderManager.AddChartPlaceholder(10, 350, 300, 300);
```
**4. حفظ العرض التقديمي**
احفظ العرض التقديمي الخاص بك:
```csharp
// حفظ العرض التقديمي مع إضافة عنصر نائب للرسم البياني.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### إضافة عنصر نائب للجدول
تنظم الجداول البيانات بشكل فعال ويتم استخدامها غالبًا في العروض التقديمية من أجل الوضوح.

#### ملخص
تعلم كيفية إضافة عنصر نائب للجدول لتنظيم المعلومات بشكل أنيق على الشرائح الخاصة بك باستخدام Aspose.Slides.

#### خطوات التنفيذ
**1. تهيئة العرض التقديمي**
إنشاء مثيل لـ `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "table_placeholder.pptx");

using (var pres = new Presentation())
{
    // سيتم إضافة الكود هنا.
}
```
**2. شريحة تخطيط الوصول**
استرجاع شريحة التخطيط الفارغة:
```csharp
// الحصول على شريحة تخطيط فارغة.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. إضافة عنصر نائب للجدول**
يستخدم `PlaceholderManager` لإضافة عنصر نائب للجدول:
```csharp
// الحصول على مدير العنصر النائب لشريحة التخطيط.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// إضافة عنصر نائب للجدول في الموضع (350، 350) بحجم (300 × 200).
placeholderManager.AddTablePlaceholder(350, 350, 300, 200);
```
**4. حفظ العرض التقديمي**
احفظ العرض التقديمي الخاص بك:
```csharp
// حفظ العرض التقديمي مع إضافة عنصر نائب للجدول.
pres.Save(outFilePath, SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
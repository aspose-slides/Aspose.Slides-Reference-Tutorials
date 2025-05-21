---
"date": "2025-04-16"
"description": "تعرّف على كيفية إنشاء جداول وأشكال ديناميكية في عروض PowerPoint التقديمية باستخدام Aspose.Slides لـ .NET. اتبع دليلنا خطوة بخطوة لتحسين المظهر."
"title": "إنشاء الجداول والأشكال في PowerPoint باستخدام Aspose.Slides لـ .NET - دليل خطوة بخطوة"
"url": "/ar/net/shapes-text-frames/aspose-slides-dotnet-table-shape-creation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء الجداول والأشكال في PowerPoint باستخدام Aspose.Slides لـ .NET: دليل خطوة بخطوة

## مقدمة

حسّن عروض PowerPoint التقديمية بإنشاء جداول ديناميكية أو رسم أشكال حول النص باستخدام C# مع Aspose.Slides لـ .NET. سيرشدك هذا الدليل خلال عملية إنشاء الجداول ورسم الأشكال، مما يجعل شرائحك أكثر إفادة وجاذبية بصريًا.

في هذا البرنامج التعليمي، سنغطي:
- إنشاء الجداول في عروض PowerPoint
- إضافة فقرات تحتوي على أجزاء نصية إلى خلايا الجدول
- تضمين إطارات النص داخل الأشكال
- رسم مستطيلات حول عناصر نصية محددة

بنهاية هذا الدليل، ستكون جاهزًا تمامًا لتحسين شرائح عرضك التقديمي باستخدام Aspose.Slides لـ .NET. لنبدأ بالمتطلبات الأساسية أولًا.

### المتطلبات الأساسية

لمتابعة هذا البرنامج التعليمي، تأكد من أن لديك:
- **بيئة التطوير**:تم تثبيت Visual Studio على جهازك.
- **مكتبة Aspose.Slides لـ .NET**:سنستخدم الإصدار 22.x أو إصدارًا أحدث.
- **المعرفة الأساسية بلغة C#**:مطلوب معرفة بقواعد اللغة والمفاهيم C#.

## إعداد Aspose.Slides لـ .NET

قبل البدء بالبرمجة، لنبدأ بتثبيت مكتبة Aspose.Slides في مشروعك. هناك عدة طرق لتثبيتها:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزم**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**:ابحث عن "Aspose.Slides" وانقر على زر التثبيت.

### الحصول على الترخيص

يمكنك البدء بفترة تجريبية مجانية لاستكشاف جميع الميزات. للاستخدام الممتد، يمكنك اختيار ترخيص مؤقت أو شراء ترخيص من [موقع Aspose](https://purchase.aspose.com/buy).

بمجرد التثبيت، قم بتهيئة Aspose.Slides في مشروعك عن طريق إضافة:

```csharp
using Aspose.Slides;
```

## دليل التنفيذ

### إنشاء جدول على شريحة

**ملخص:**
إنشاء الجداول أمرٌ أساسي لعرض البيانات بوضوح. مع Aspose.Slides، يمكنك تحديد أبعاد الجداول ومواضعها بسهولة.

#### الخطوة 1: تهيئة العرض التقديمي
ابدأ بإنشاء مثيل لـ `Presentation` فصل:

```csharp
Presentation pres = new Presentation();
```

#### الخطوة 2: إضافة جدول
استخدم `AddTable` طريقة لإضافة جدول إلى الشريحة. حدد موضع وحجم الصفوف والأعمدة:

```csharp
ITable tbl = pres.Slides[0].Shapes.AddTable(50, 50, new double[] { 50, 70 }, new double[] { 50, 50, 50 });
```

**المعلمات موضحة:**
- `50, 50`:إحداثيات X وY للزاوية العلوية اليسرى.
- تحدد المصفوفات عرض الأعمدة وارتفاع الصفوف.

#### الخطوة 3: حفظ العرض التقديمي
وأخيرًا، احفظ العرض التقديمي الخاص بك:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY/CreateTable_Out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
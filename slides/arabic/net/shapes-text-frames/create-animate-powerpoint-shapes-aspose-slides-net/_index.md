---
"date": "2025-04-16"
"description": "تعرّف على كيفية إنشاء الأشكال وتحريكها برمجيًا في PowerPoint باستخدام Aspose.Slides لـ .NET. يتناول هذا الدليل إنشاء الأشكال التلقائية، وتطبيق انتقالات التحويل، وحفظ العروض التقديمية."
"title": "إنشاء وتحريك أشكال PowerPoint باستخدام Aspose.Slides لـ .NET - دليل شامل"
"url": "/ar/net/shapes-text-frames/create-animate-powerpoint-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# إنشاء وتحريك أشكال PowerPoint باستخدام Aspose.Slides لـ .NET: دليل شامل

## مقدمة

حسّن عروض PowerPoint التقديمية برمجيًا باستخدام قوة Aspose.Slides لـ .NET. سيرشدك هذا البرنامج التعليمي خلال إنشاء عروض مرئية ديناميكية باستخدام لغة C#، وأتمتة إنشاء الشرائح، وتخصيص الانتقالات لتبسيط سير عملك.

### ما سوف تتعلمه:
- كيفية إنشاء الأشكال التلقائية وتعديلها في PowerPoint.
- تطبيق تأثيرات انتقال Morph بين الشرائح.
- حفظ العروض التقديمية برمجيًا باستخدام Aspose.Slides لـ .NET.

دعونا نبدأ بالتأكد من أن لديك المتطلبات الأساسية اللازمة!

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك المتطلبات التالية:

### المكتبات والإصدارات المطلوبة
- **Aspose.Slides لـ .NET**تُسهّل هذه المكتبة أتمتة PowerPoint ضمن تطبيقات .NET. تأكد من استخدام إصدار متوافق.

### متطلبات إعداد البيئة
- بيئة تطوير مع تثبيت .NET (على سبيل المثال، Visual Studio).
  

### متطلبات المعرفة
- فهم أساسي للغة C# والتعرف على البرمجة الكائنية التوجه.
- سيكون من المفيد الحصول على بعض المعرفة حول العمل مع العروض التقديمية في PowerPoint.

## إعداد Aspose.Slides لـ .NET

بدء استخدام Aspose.Slides سهل للغاية. اتبع الخطوات التالية لتثبيت المكتبة في مشروعك:

### خيارات التثبيت:
**استخدام .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم مدير الحزمة:**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير حزمة NuGet:**
- ابحث عن "Aspose.Slides" في مدير الحزم NuGet وقم بتثبيته.

### خطوات الحصول على الترخيص:
- **نسخة تجريبية مجانية**:ابدأ بإصدار تجريبي مجاني لاستكشاف الوظائف الأساسية.
- **رخصة مؤقتة**:احصل على ترخيص مؤقت لفتح الميزات الكاملة أثناء التقييم.
- **شراء**:قم بشراء ترخيص من موقع Aspose الإلكتروني للاستخدام المستمر.

#### التهيئة والإعداد الأساسي:
بعد التثبيت، قم بتهيئة مشروعك باستخدام مقتطف التعليمات البرمجية التالي:

```csharp
using Aspose.Slides;

// تهيئة مثيل عرض تقديمي جديد
Presentation presentation = new Presentation();
```

## دليل التنفيذ

في هذا القسم، سنقوم بتقسيم التنفيذ إلى ثلاث ميزات رئيسية: إنشاء الأشكال، وتطبيق الانتقالات، وحفظ العروض التقديمية.

### إنشاء الأشكال وتعديلها

تتيح لك هذه الميزة إضافة تأثيرات بصرية ديناميكية إلى شرائحك. لنرَ كيف يمكنك إنشاء شكل مستطيل وتعديل خصائصه:

#### الخطوة 1: إضافة شكل تلقائي
```csharp
using Aspose.Slides;
using System;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation presentation = new Presentation())
{
    // أضف شكل مستطيل إلى الشريحة الأولى بأبعاد محددة
    AutoShape autoshape = (AutoShape)presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 400, 100);
    
    // تعيين النص داخل الشكل التلقائي
    autoshape.TextFrame.Text = "Test text";
}
```
**توضيح**: هنا، `AddAutoShape` يُستخدم لإنشاء مستطيل بإحداثيات وأبعاد محددة. `TextFrame` تتيح لك الخاصية إضافة محتوى نصي داخل الشكل.

#### الخطوة 2: استنساخ الشريحة
```csharp
// استنساخ الشريحة الأولى وإضافتها كشريحة جديدة
presentation.Slides.AddClone(presentation.Slides[0]);
```
**توضيح**:يعد الاستنساخ مفيدًا لتكرار الشرائح باستخدام التكوينات الموجودة، مما يوفر الوقت في الإعدادات المتكررة.

### تطبيق انتقال مورف

تُوفّر انتقالات التحويل رسومًا متحركة سلسة بين الشرائح. لنطبّق تأثير الانتقال هذا:

```csharp
using Aspose.Slides;
using System;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation presentation = new Presentation())
{
    // تعديل خصائص الشكل في الشريحة 1
    presentation.Slides[1].Shapes[0].X += 100; // التحرك إلى اليمين بمقدار 100 وحدة
    presentation.Slides[1].Shapes[0].Y += 50;  // التحرك للأسفل بمقدار 50 وحدة
    presentation.Slides[1].Shapes[0].Width -= 200; // تقليل العرض بمقدار 200 وحدة
    presentation.Slides[1].Shapes[0].Height -= 10; // تقليل الارتفاع بمقدار 10 وحدات
    
    // تعيين نوع انتقال الشريحة 1 إلى Morph
    presentation.Slides[1].SlideShowTransition.Type = Aspose.Slides.SlideShow.TransitionType.Morph;
}
```
**توضيح**:من خلال تعديل خصائص الشكل وتعيين `TransitionType` ل `Morph`، يمكنك إنشاء انتقال شريحة جذاب بصريًا.

### حفظ العرض التقديمي

بمجرد الانتهاء من إنشاء العرض التقديمي الخاص بك، قم بحفظه باستخدام الكود التالي:

```csharp
using Aspose.Slides;
using System;

string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation presentation = new Presentation())
{
    // حفظ العرض التقديمي في المسار المحدد بتنسيق PPTX
    presentation.Save(dataDir + "presentation-out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
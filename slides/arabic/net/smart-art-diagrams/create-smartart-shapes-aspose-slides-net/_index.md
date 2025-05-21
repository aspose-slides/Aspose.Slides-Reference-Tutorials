---
"date": "2025-04-16"
"description": "تعرّف على كيفية إنشاء رسومات SmartArt ديناميكية في PowerPoint باستخدام Aspose.Slides لـ .NET. حسّن عروضك التقديمية مع هذا الدليل الشامل."
"title": "إنشاء أشكال SmartArt في PowerPoint باستخدام Aspose.Slides لـ .NET - دليل خطوة بخطوة"
"url": "/ar/net/smart-art-diagrams/create-smartart-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# كيفية إنشاء أشكال SmartArt في PowerPoint باستخدام Aspose.Slides لـ .NET: دليل خطوة بخطوة

## مقدمة

حسّن عروض PowerPoint التقديمية بدمج رسومات SmartArt الديناميكية باستخدام C#. مع Aspose.Slides لـ .NET، يمكنك إنشاء أشكال SmartArt وإدارتها بسلاسة داخل شرائحك. سيرشدك هذا الدليل خلال عملية إعداد SmartArt وتطبيقه مع Aspose.Slides لـ .NET.

**ما سوف تتعلمه:**
- إعداد بيئتك باستخدام Aspose.Slides لـ .NET
- إنشاء شكل SmartArt داخل شريحة PowerPoint
- إدارة الدلائل بشكل فعال في الكود الخاص بك

## المتطلبات الأساسية (H2)

لتنفيذ هذا الحل بنجاح، تأكد من أن لديك:
- **المكتبات المطلوبة**: Aspose.Slides لـ .NET (يوصى بالإصدار 21.11 أو إصدار أحدث)
- **بيئة التطوير**: .NET Core أو .NET Framework
- **المعرفة الأساسية**:الإلمام بلغة C# وعمليات نظام الملفات

## إعداد Aspose.Slides لـ .NET (H2)

### تثبيت

ابدأ بتثبيت Aspose.Slides باستخدام إحدى الطرق التالية:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**وحدة تحكم إدارة الحزم في Visual Studio**
```powershell
Install-Package Aspose.Slides
```

**واجهة مستخدم مدير الحزم NuGet**
1. افتح مدير الحزم NuGet.
2. ابحث عن "Aspose.Slides" وقم بتثبيت الإصدار الأحدث.

### الحصول على الترخيص
- **نسخة تجريبية مجانية**:تنزيل ترخيص مؤقت من [هنا](https://purchase.aspose.com/temporary-license/) لتقييم قدرات Aspose.Slides الكاملة.
- **شراء**:للاستخدام المستمر، قم بشراء ترخيص من خلال [هذا الرابط](https://purchase.aspose.com/buy).

بمجرد حصولك على ملف الترخيص الخاص بك، قم بتهيئته في تطبيقك على النحو التالي:
```csharp
License license = new License();
license.SetLicense("Aspose.Slides.lic");
```

## دليل التنفيذ (H2)

### الميزة: إنشاء شكل SmartArt (H2)

تتيح لك هذه الميزة إضافة رسومات SmartArt جذابة بصريًا إلى شرائح PowerPoint الخاصة بك برمجيًا.

#### نظرة عامة على العملية (H3)
سنبدأ بإعداد دليل وإنشاء كائن عرض تقديمي ثم إضافة شكل SmartArt.

#### شرح الكود (H3)
1. **إدارة الدليل**
   تأكد من وجود دليل المستندات الخاص بك أو قم بإنشائه إذا لزم الأمر:
   ```csharp
   string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // تحديد مسار دليل المستند المستهدف
   bool isExists = Directory.Exists(dataDir); // التحقق من وجود الدليل
   if (!isExists) 
       Directory.CreateDirectory(dataDir); // إنشاء الدليل إذا لم يكن موجودًا
   ```

2. **إنشاء عرض تقديمي جديد**
   قم بإنشاء عرض تقديمي جديد والوصول إلى الشريحة الأولى منه:
   ```csharp
   using (Presentation pres = new Presentation())
   {
       ISlide slide = pres.Slides[0]; // الوصول إلى الشريحة الأولى
   ```
   
3. **إضافة SmartArt إلى الشريحة**
   أضف شكل SmartArt عند الإحداثيات المحددة مع الأبعاد ونوع التخطيط المطلوبين:
   ```csharp
   // إضافة شكل SmartArt باستخدام تخطيط BasicBlockList
   ISmartArt smart = slide.Shapes.AddSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);
   ```

4. **حفظ العرض التقديمي**
   وأخيرًا، احفظ العرض التقديمي في الدليل المطلوب:
   ```csharp
   pres.Save(dataDir + "SimpleSmartArt_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}